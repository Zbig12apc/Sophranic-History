# Product Roadmap: Data Platform v2

This document provides the implementation roadmap for Data Platform v2, based on the accepted Product Direction. Its purpose is to guide the subsequent technical design and implementation phases.

## 1. Overview and Goals

The primary goal is to re-platform the MVP's data architecture to align with the accepted Product Direction. This involves moving from a tightly coupled model to a decoupled one based on clear domain concepts: `AuthoritativeProduct`, `UserContribution`, and a formal `Verification` process.

This roadmap prioritizes establishing a solid foundation for the new data platform, followed by a phased migration of existing data and features. The roadmap itself does not triggerdesign or implementation which can start once an explicit acceptance is obtained.

## 2. Scope

### In Scope
- **Conceptual Data Model:** Defining the target domain model at a conceptual level.
- **Migration Strategy:** A high-level plan for migrating MVP data to the v2 model.
- **Backend Capabilities:** Defining the required backend services and logic to support the new model.
- **Client Impact Assessment:** Identifying necessary changes in client applications (SeeLabel, Sophranic Site).
- **Verification Plan:** Outlining the cross-platform validation strategy for the completed implementation.

### Out of Scope
- **Database/SQL Schema Design:** Detailed table structures, fields, and relationships.
- **API Specification:** Detailed design of API endpoints, request/response payloads.
- **Infrastructure Changes:** Changes to the underlying cloud infrastructure unless strictly required by the data model.
- **Application Code Implementation:** Writing any application, migration, or testing code.
- **Redesign of Unrelated Features:** Any feature not directly impacted by the domain model redesign is out of scope.

## 3. Roadmap Phases

The implementation will proceed in logical phases to manage dependencies and risk.

### Phase 1: Foundational Platform Implementation
*Goal: Build the core components of the new data platform. All new components will be designed to run in parallel with the existing system without impacting it.*

**1.1. Data Platform (Supabase):**
- **Core Models:** Design and implement the initial database structures for `AuthoritativeProduct` and `UserContribution`.
- **Data Provenance:** Design and implement a mechanism to preserve the history and provenance of all data, linking authoritative information back to its original `UserContribution` and source (Hunt). This is a **required design decision** for the Database Architect.
- **Taxonomy:** Design and implement a flexible structure for product categorization. The specific implementation (e.g., simple tags, hierarchies) is a **required design decision** for the Database Architect, based on product requirements.
- **Verification:** Design and implement a mechanism for tracking verification status at the attribute level for `AuthoritativeProduct` data. This is a **required design decision** for the Database Architect.

**1.2. Backend:**
- **Contribution Handling:** Design and implement a backend capability to handle the intake, processing, and storage of all `UserContributions`. The specific architecture (e.g., a new service, refactoring existing services) is a **required design decision** for the Architecture Planner.
- **Transitional Data Strategy:** Design a strategy to ensure service continuity while both v1 and v2 data models are active. This strategy (e.g., dual-write, event-sourcing, data synchronization) is a **required design decision** for the Architecture Planner and must be evaluated for technical feasibility and risk.
- **Verification and Moderation Logic:** Develop the initial business logic for the verification and moderation workflows based on the defined product requirements.

### Phase 2: Data Migration
*Goal: Migrate all existing MVP data into the new v2 structure without disrupting live services.*

**2.1. Migration Preparation:**
- **Data Analysis and Classification:** Analyze the existing mixed dataset to define clear rules for classifying records into what will become `AuthoritativeProduct` and `UserContribution`. This is a **required decision** that needs human or appropriate agetn input.
- **Script Development:** Develop and test migration scripts in a staging environment.
- **Validation Tooling:** Create tools to validate the integrity and completeness of the migrated data against the source.

**2.2. Migration Execution:**
- **Staging Migration:** Perform a full migration in a staging environment that mirrors production to test scripts and the validation tooling.
- **Production Migration Strategy:** Define and document the final production migration strategy, including timing, rollback plans, and communication. The approach (e.g., requiring a maintenance window vs. a zero-downtime online migration) is a **required decision** based on business needs and technical constraints.
- **Production Execution:** Execute the approved migration plan.

### Phase 3: Client and Feature Re-platforming
*Goal: Update the client applications (SeeLabel, Sophranic Site) to use the new v2 data platform and APIs.*

**3.1. Sophranic Site (Moderation & Ops):**
- **Contribution Management UI:** Build the required interface for moderators to review and manage incoming `UserContributions`.
- **Verification Workflow UI:** Implement the UI to support the new verification workflow, enabling the promotion of user-provided data into `AuthoritativeProduct` records.
- **API Integration:** Plan and execute the cutover for the Sophranic Site backend to read from and write to the new v2 data platform. This requires a **defined API contract**.

**3.2. SeeLabel (Mobile App):**
- **Data Layer Refactoring:** Update the app's data sources and repositories to fetch product data from the new v2 authoritative source. This requires a **defined API contract**.
- **Contribution Flow Refactoring:** Modify the scanning and submission flows to create `UserContribution` records via the new backend capabilities.
- **State Management:** Assess and update client-side state management to accommodate the new data models.

### Phase 4: Deprecation and Cleanup
*Goal: Fully decommission the old MVP data model and associated code.*

**4.1. Deprecate Transitional Strategy:**
- Once legacy MVP paths / data stores and  are fully migrated to the v2 platform, execute the plan to decommission the transitional data strategy (e.g., remove dual-writes, shut down sync jobs).

**4.2. Deprecate Old Data Model:**
- Remove the legacy MVP tables from the database.
- Remove all backend code, data access layers, and services that interacted with the legacy tables.

## 4. Cross-Platform Responsibilities

- **Data Platform (Supabase):** The source of truth for all authoritative data and user contributions. Responsible for data integrity, security (RLS), and performance.
- **Backend:** Owns the business logic for contribution processing, verification flows, and enforcing domain rules. Provides a stable, secure, and well-documented API for clients.
- **SeeLabel:** Responsible for capturing user input accurately and presenting authoritative product data to the user.
- **Sophranic Site:** Responsible for providing the tools for internal operations, including moderation, verification, and data curation.

## 5. Verification and Validation Strategy

The completed implementation will be validated at each level:
- **Data Integrity:** Validation scripts must be executed post-migration to ensure data consistency and correctness.
- **Backend Behavior:** A suite of automated tests (integration, contract) must be developed to verify the API and business logic.
- **SeeLabel & Sophranic Site:** End-to-end testing (manual and automated) must be conducted for all flows that interact with the data platform.
- **Security:** A security review of RLS policies and API endpoints must be performed.

## 6. Open Decisions and Dependencies

The following decisions must be made by the appropriate specialist before the relevant implementation work can begin.

### Architectural & Design Decisions:
- **Data Provenance Model:** The Database Architect must design the specific database model for tracking data history and provenance.
- **Taxonomy Model:** The Database Architect must design the database model for product categorization.
- **Verification Model:** The Database Architect must design the implementation for attribute-level verification tracking.
- **Backend Contribution Architecture:** The Architecture Planner must design the target architecture for backend contribution handling.
- **Transitional Data Strategy:** The Architecture Planner must evaluate options (e.g., dual-write, event sourcing) and select a migration strategy.
- **API Contract:** The backend and client teams must collaboratively design and document the v2 API contract.
- **Production Migration Plan:** The technical team must produce a detailed plan for the production data migration, including the final decision on downtime requirements.

### Product & Business Decisions:
- **Data Classification Rules:** The human or appropriate agetn must provide definitive rules for classifying legacy data.
- **Detailed Taxonomy Requirements:** The human or appropriate agetn must provide the detailed requirements for the taxonomy system (e.g., required categories, need for hierarchies).
