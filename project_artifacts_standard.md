# Project Artifacts Standard

## Purpose
Project Artifacts preserve the execution history of Sophranic projects.
Unlike the Knowledge Base, which stores permanent and reusable knowledge, Project Artifacts document planning, execution, reviews and project decisions.

## Separation of Responsibilities
### Knowledge Base
Contains permanent and reusable knowledge:
- engineering rules
- architecture
- technology
- product documentation
### History
Contains project execution history:
- roadmaps
- tasks
- reviews
- project decisions

## History Areas
History is organized into independent areas:
- Company
- Platform
- Products
Each area maintains its own Roadmaps, Tasks and Reviews.

## Artifact Naming
### Prefixes
- F = Company
- P = Platform
- SL = SeeLabel
- SS = Sophranic Site
Additional prefixes may be introduced for future products.
### Roadmaps
Format:
`<Prefix>-R<NN>-<short-description>.md`
Examples:
- `P-R01-data-platform-v2.md`
- `SL-R02-launch-readiness.md`
- `SS-R03-admin-panel.md`
Rules:
- Roadmap numbers are globally sequential across all areas.
- Parent Roadmaps are referenced inside the document.
- Parent relationships are never encoded in filenames.
### Tasks
Format:
`<Roadmap>-T<NN>-<short-description>.md`
Example:
- `P-R01-T03-update-seelabel.md`
Rules:
- Task numbering is local to its Roadmap.
- Every Task belongs to exactly one Roadmap.
### Reviews
Format:
`<Task>-RV<NN>.md`
Examples:
- `P-R01-T03-RV01.md`
- `P-R01-T03-RV02.md`
Rules:
- Review numbering is local to its Task.
- Every Review belongs to exactly one Task.
### Architecture Decision Records
Format:
`ADR-<NNN>-<short-description>.md`
Examples:
- `ADR-001-migration-first.md`
- `ADR-002-session-repository.md`
Rules:
- ADR numbering is chronological.
- ADRs are independent of Roadmaps.

## Identifier Rules
- Identifiers are permanent.
- Document titles and contents may evolve.
- Filenames and identifiers never change after creation.

## Relationships
Roadmap → Task → Review
A Roadmap may reference one or more parent Roadmaps.
Relationships are documented inside the Roadmap rather than encoded in filenames.

## Guiding Principle
- Knowledge Base is the Source of Truth.
- History is the Source of Project Memory.