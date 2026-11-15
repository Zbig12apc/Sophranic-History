# Database Architecture: Data Platform v2

## 1. Architectural Objective

This document provides the complete, authoritative database architecture for the Data Platform v2, incorporating all architectural decisions. It translates the accepted Product Direction into a detailed technical design for the Supabase platform and serves as the source of truth for implementation.

The architecture establishes a clear separation between authoritative product data, user contributions, personalization, and scan history, while providing a robust foundation for security, moderation, and future growth.

---

## 2. Core Data Model & Evaluation

### 2.1. `products` Table
-   **Purpose:** Stores the single source of truth for each product.
-   **Identity:** `id` (UUID, PK).
-   **Core Fields:**
    -   `barcode` (TEXT, NOT NULL).
    -   `product_domain` (TEXT, NOT NULL): An architectural extension point for future product types (e.g., `'food'`, `'cosmetic'`). The complete taxonomy is not defined now.
    -   `status` (ENUM: `verified`, `postponed`, `rejected`): The overall moderation status. `postponed` is a valid state for viewing and moderation. `rejected` products are not returned via user-facing RPCs.
    -   `product_name` (TEXT).
    -   `product_image_url` (TEXT).
    -   `ingredients` (TEXT[]): List of literal ingredient strings. Renaming to a generic `components` is deferred.
-   **Attribute-Level Provenance:** Key attributes are linked to `attribute_history` to provide an audit trail.

### 2.2. `attribute_history` Table
-   **Purpose:** Provides a full audit trail for every change to an authoritative attribute.
-   **Fields:** `id`, `product_id`, `attribute_name`, `value`, `contribution_id`, `created_at`.

### 2.3. Evaluation Model
-   **Evaluation Status:** There are four mutually exclusive evaluation states: `OK` (`danger=0, trace=0`), `WARNING` (`danger=0, trace>0`), `DANGER` (`danger>0`), and `NO_INGREDIENTS`. For `NO_INGREDIENTS`, the accompanying `ok`/`trace`/`danger` counts must be `0/0/0`.
-   **Data Source:** Scan results must identify their specific data source (e.g., `'SeeLabel DB'`, `'OFF DB'`) in an extensible string field.

---

## 3. Contribution Model

### 3.1. `contributions` Table
-   **Purpose:** An immutable log of all proposals to change authoritative data.
-   **Fields:**
    -   `id` (UUID, PK).
    -   `user_id` (FK to `auth.users`).
    -   `type` (ENUM: `new_product`, `change`, `promotion`).
    -   `payload` (JSONB): The specific data for the contribution proposal.
    -   `legacy_product_id` (FK to `legacy_products`, NULLABLE): For `promotion` types, providing a provenance link.

### 3.2. Contribution Payloads & Workflow
-   **`new_product`:** Represents raw user-submitted **evidence**. The payload requires `{ "barcode": "string", "country": "string" }`. Must be associated with a `hunt` record containing at least one source photo. Data extraction (OCR/AI) is a subsequent moderation step.
-   **`change`:** Represents one logical operation.
    -   **Payload:** `{ "product_id": "uuid", "op": "string", "field": "string", "value": "any" }`.
    -   It does **not** contain `old_value`. `apply_contribution` is responsible for recording the previous state in `attribute_history`.
    -   Validation is generic based on `op` and `field` semantics.
-   **`promotion`:** The `payload` contains the complete, moderator-approved authoritative data for the new product record.

---

## 4. User Scan History Model

### 4.1. `scan_history` Table
-   **Purpose:** Stores a historical snapshot of the exact evaluation result delivered to the user.
-   **Schema:** `id` (PK), `user_id` (FK), `product_id` (FK), `scanned_at` (TIMESTAMPTZ), `status` (TEXT), `result_snapshot` (JSONB).

### 4.2. `scan_history_matches` Table
-   **Purpose:** Stores relational data on specific ingredient matches for efficient analytics. List-versioning concepts are not stored here.
-   **Schema:** `id` (PK), `scan_history_id` (FK), `ingredient_name` (TEXT, the literal string), `match_status` (TEXT: `TRACE` or `DANGER`).

---

## 5. Personalization Model (V2 Scope)

### 5.1. Conceptual Model
The architecture is `User -> Criterion Library -> Lists -> Active Lists -> Evaluation`. For V2, lists are **negative/avoidance lists**.

### 5.2. `user_criteria` Table
-   **Purpose:** The user's master library of personalization criteria. Represents an abstract rule container.
-   **Schema:** `id`, `user_id`, `rule_type` (e.g., `'ingredient'`), `rule_target` (e.g., a FK to `canonical_ingredients`).

### 5.3. `user_lists` Table
-   **Purpose:** A named, activatable group of criteria.
-   **Schema:** `id`, `user_id`, `name` (TEXT), `is_active` (BOOLEAN).
-   **Note:** Domain-scoped lists are an intentionally deferred feature.

### 5.4. `user_list_criteria` Table
-   **Purpose:** The many-to-many linking table between `user_lists` and `user_criteria`.
-   **Schema:** `list_id` (FK), `criterion_id` (FK).

---

## 6. Ingredient Identity Model

### 6.1. Conceptual Model
The system distinguishes between `Literal Ingredient String` (on the product) and `Canonical Ingredient` (the abstract concept). The mapping is optional, many-to-one, and based on a hybrid of explicit aliases and technical normalization. `Canonical Ingredients` and their representations are exclusively curated data. Unmapped literal strings are valid product data and serve as signals for the curation process.

### 6.2. `canonical_ingredients` Table
-   **Purpose:** Stores the abstract, language-independent ingredient concepts.
-   **Schema:** `id` (PK).

### 6.3. `ingredient_representations` Table
-   **Purpose:** Stores the various language-specific textual representations for canonical concepts.
-   **Schema:** `id` (PK), `canonical_ingredient_id` (FK), `representation_text` (TEXT), `language_code` (TEXT), `is_preferred_for_language` (BOOLEAN). There can be at most one preferred representation per `(canonical_ingredient_id, language_code)`. The decision on a global uniqueness constraint for `(representation_text, language_code)` is deferred.

---

## 7. Migration & System Boundaries

### 7.1. Migration Architecture
-   **Strategy:** Clean-Slate with On-Demand Promotion. The MVP `products` table is renamed to `legacy_products`.

### 7.2. User Engagement & Rewards
-   **Architectural Boundary:** The Rewards domain is architecturally separate from the Data Platform.
-   **Communication:** Communication is one-way, from Data Platform to Rewards, via **decoupled batch processing**.
-   **Conceptual Model:** The model is based on:
    -   **Reward Trigger:** A factual event that can qualify for rewards (e.g., `'contribution.accepted'`).
    -   **Reward Rule:** The business logic that processes triggers to grant a reward.
-   **Output (`Reward Grant`):** The output of a successful rule is an immutable `Reward Grant` record, capturing the `user_id`, the `rule_id` that triggered it, the specific `reward` granted, and a `timestamp`.
-   **State Ownership:** The Rewards domain **owns its own processing and idempotency state**. Reward-specific processing fields will not be added to Data Platform tables.
-   **Fulfillment:** Fulfillment is asynchronous via a state machine (`pending_fulfillment`, `fulfilled`, `failed`). External API calls (e.g., to RevenueCat) occur outside database transaction boundaries. A failed fulfillment must leave the `Reward Grant` in a recoverable state.

---

## 8. Security and Database API (RPCs)

RLS **must be enabled on all application data tables.**

### 8.1. `evaluate_product_for_guest(p_barcode TEXT)`
-   **Purpose:** Secure entry point for Guest users.
-   **Security:** `SECURITY DEFINER`, `SET search_path = ''`, owned by a low-privilege role.
-   **Limits:** Enforces a security limit (20 req/hr/session, 100 req/hr/IP), separate from the 10-scan client-side product entitlement.
-   **Response:** Returns a minimal evaluation result (`OK`/`WARNING`/`DANGER`/`NO_INGREDIENTS` status, counts, and data source).

### 8.2. `get_product_for_user(p_barcode TEXT)`
-   **Purpose:** Secure read path for authenticated users.
-   **Security:** `SECURITY DEFINER` with the same safety principles.
-   **Scope:** Queries `v2 products` table only (for `verified` or `postponed` products). The client handles fallbacks.
-   **Response:** Returns raw data for client-side evaluation: `{ "product_name", "product_image_url", "product_status", "ingredients": [...] }`.

### 8.3. `apply_contribution(contribution_id)`
-   **Purpose:** Trusted RPC to apply an `accepted` contribution.
-   **Responsibility:** Validates and processes the `payload`. It is responsible for determining the previous state of an attribute and recording it in `attribute_history`.

### 8.4. Permission Matrix

| Role | `products` | `contributions` | `evaluate_product_for_guest()` | `get_product_for_user()` | `apply_contribution()` |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Guest (anon)** | Denied | Denied | `EXECUTE` | Denied | Denied |
| **Auth. User** | Denied | `SELECT` (own), `INSERT` | Denied | `EXECUTE` | Denied |
| **Moderator** | `SELECT` (all) | `SELECT`/`UPDATE` (all) | `EXECUTE` | `EXECUTE` | `EXECUTE` |
| **Service Role** | `ALL` (via functions)| `ALL` | N/A | `EXECUTE` | `EXECUTE` |
