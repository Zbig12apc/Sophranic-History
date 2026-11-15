# Product Direction: Data Platform v2

This document outlines the product direction for the redesign of the data platform, referred to as Data Platform v2.

## 1. Problem Statement

The current MVP has evolved organically, leading to a domain model where several distinct concepts are coupled. This tight coupling creates significant challenges for scalability, maintainability, and future feature development.

The key issues are:
- **Data Ambiguity:** Product definitions, user contributions, and product discovery events (hunts) are not stored as separate domain concepts, making the data difficult to interpret and manage.
- **Lack of Authoritative Source:** Verified, authoritative product data is mixed with user-submitted data, making it difficult to establish a reliable source of truth.
- **Brittle Features:** Core features like moderation and preference matching are tightly coupled to the current storage model. This makes them difficult to improve without causing unintended side effects.
- **Inflexible Categorization:** The product categorization system is not designed to support a growing and evolving taxonomy, limiting our ability to organize and surface relevant products to users.

## 2. Proposed Solution

The proposed solution is to redesign the domain around clear, decoupled concepts. Before proposing a concrete data model, we must first establish the boundaries and definitions of the core domain concepts. This conceptual clarity will form the foundation for a more robust and scalable platform.

### 2.1. Core Domain Concepts

#### 2.1.1. Product Definition
A **Product** is the central entity in the domain. Conceptually, it represents a unique, purchasable item. The definition of a Product is composed of various attributes. While the final data structure is a design concern for a later stage, the conceptual definition includes attributes such as:
- **Core Identity:** Brand, name, variant (e.g., size, flavor).
- **Categorization:** A flexible category or set of tags.
- **Detailed Attributes:** Ingredients, origin (made-in), barcode (GTIN), etc.
- Product information may change over time. The platform must preserve the identity of the physical Product while allowing its authoritative attributes and state to evolve as the real-world product changes.
A Product is identified by its barcode (GTIN). A record containing only a barcode may exist as an incomplete Product, but it cannot be considered verified until sufficient product information has been established and verified.
A key principle is that the **Product** represents the abstract, authoritative definition of the item, separate from user-generated content about it.

#### 2.1.2. User Contribution
A **User Contribution** is any piece of information submitted by a user. It is a distinct, atomic unit of input that can be tracked, moderated, and processed. Types of contributions include:
- **New Product Submission:** A complete set of information proposing a new product that doesn't exist in our database.
- **Correction:** A partial input that suggests a change to a single attribute of an *existing* authoritative Product (e.g., correcting a typo in the name, updating the ingredient list).
- **Augmentation:** A partial input that adds new information to an existing Product (e.g., adding a barcode that was previously missing).
- **New Entity Suggestion:** A submission proposing a new entity that is not a product itself but is related, for example, a new `Ingredient`, `Brand`, or `Category`.
Different contribution types may differ in scope, completeness and value to the platform. These differences may later be used for moderation, contribution evaluation or user rewards, but those mechanisms are outside the scope of this Product Direction.
Every contribution is treated as a *proposal* that exists independently from the authoritative data until it is reviewed and integrated.

#### 2.1.3. Verification & Authoritative Data
**Authoritative Data** is the curated, trusted "golden record" of information for a Product. **Verification** is the process by which information becomes authoritative.
- **What "verified" means:** Information that has been reviewed and confirmed for accuracy by a trusted source (e.g., internal moderation team, data partner).
- **Verification Scope:** Verification is not necessarily a property of the entire Product record. Instead, individual attributes of a product can have their own verification state and source. For example, the brand name might be verified by the moderation team, while an ingredient list might be verified against a partner's data feed.
- **Becoming Authoritative:** A `User Contribution` becomes part of the authoritative data only after it passes the verification process. An accepted correction updates a specific attribute of the authoritative Product, and the contribution is logged for historical purposes.

#### 2.1.4. Hunting
A **Hunt** is a user-facing workflow or discovery event, not a core domain entity itself. It is the *process* by which a user finds and submits information. A single "Hunt" can *result* in one or more `User Contributions`. For example, a user "hunting" a product they found in a store might submit a `New Product Submission` along with photos. Another user might "hunt" for a correction by spotting a typo on the website and submitting a `Correction`.

A Hunt is also retained as historical context and provenance for the resulting contributions and product information. This is particularly important while the platform is building a sufficiently reliable body of verified product data and may need to return to the original source. The Hunt itself does not define the Product; it provides context for how product information was discovered and contributed.

## 3. Expected User Value

While this is primarily an architectural change, it will deliver significant indirect value to users:

- **Improved Data Quality:** By establishing a clear process for verification and separating authoritative data from user submissions, we can ensure users see more accurate and reliable product information.
- **Faster Feature Development:** A well-defined and decoupled domain model will allow us to build and ship new features and improvements more quickly.
- **Enhanced Discovery:** A more flexible product definition and categorization system will enable better discovery and recommendation features.
- **More Transparent Moderation:** Tracking every contribution as a distinct unit will allow for a more transparent moderation process, giving users clearer feedback on their submissions.

## 4. Business Rationale

The current data model is a significant source of technical debt, hindering our ability to scale and respond to new business opportunities. This redesign is essential for long-term growth.

The key business benefits are:
- **Increased Development Velocity:** A cleaner, more maintainable codebase will allow the engineering team to work more efficiently.
- **Improved Scalability:** The new domain model is designed to scale with a growing user base and increasing data volume.
- **Future-Proofing:** A flexible, decoupled architecture will make it easier to add new features, product lines, and data sources in the future.
- **Reduced Risk:** Improving data quality and system stability reduces the risk of data-related bugs and service disruptions.

## 5. Assumptions

- The core concepts of Product, User Contribution, and Verification are sufficient to model the domain for current and foreseeable future needs.
- We can establish a clear and effective workflow for moderating and verifying user contributions to maintain data quality.
- Separating the "Hunt" as a workflow from the core data model is a viable approach that will not result in the loss of critical information.

## 6. Open Questions

- **Product Definition:** What is the complete, exhaustive list of attributes that constitute a "Product"? Which are required, and which are optional?
- **User Contributions:** What are all the types of entities users can contribute (e.g., Ingredients, Brands)? What is the priority for supporting each type? What specific fields are required for a "complete" new product submission versus a "partial" correction?
- **Verification:** What are the specific business rules for the verification process? Who are the trusted sources, and what is the workflow for a contribution to become authoritative? Can verification status expire or be revoked?
- **Data Provenance:** How do we need to track the history and origin of each piece of authoritative data (e.g., which user submission or internal process led to the current value of an attribute)?
- **Impact Analysis:** What other systems, services, or user-facing features depend on the current data model, and what is the full impact of this redesign on them?
