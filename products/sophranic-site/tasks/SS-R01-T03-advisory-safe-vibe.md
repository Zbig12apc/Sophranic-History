# Handoff 03 — Advisory and SAFE VIBE
## 1. Task Definition
- Recipient: Code-Writer.
- Project: Sophranic Site Redesign.
- Status: pending.
- Dependencies: Accepted Handoffs 01 and 02.
- Objective: Implement the complete Advisory and dedicated SAFE VIBE pages using the accepted Sophranic Design System and shared Design Foundation.
- Working directory: `C:\sophranic\products\sophranic-site`
- Branch: `develop`.
- Accepted baseline commit: `1617857` — Implement Sophranic Home page redesign.
## 2. Authoritative Source Materials
Redesign workspace:
`C:\sophranic\work\sophranic-site-redesign`
- `implementation-roadmap.md`
- `audit-decisions.md`
- `design-system.md`
- `Sophranic-redesign_direction.html`
Project content sources:
- `docs/Advisory.md`
- `docs/SAFE-VIBE.md`
- `lib/content/advisory.ts`
- `lib/content/safe-vibe.ts`
- Existing Advisory and SAFE VIBE page implementations.
Knowledge Base:
- Follow the Sophranic Knowledge Base startup procedure.
- Follow the applicable agent framework, engineering standards and Next.js technology requirements.
The accepted content documents are authoritative for substantive messaging. The Design System and Audit Decisions define accepted visual and functional requirements. The HTML prototype is a visual reference. Explicitly accepted human decisions take precedence.
If sources disagree or approved content is missing, report the discrepancy before making a consequential decision. Do not invent or silently rewrite content.
## 3. Pre-Implementation Verification
Before editing:
1. Verify branch `develop` and accepted baseline `1617857`.
2. Inspect the working tree. Preserve unrelated and untracked files.
3. Inspect the current Advisory and SAFE VIBE page implementations.
4. Read the complete approved content documents and corresponding content modules.
5. Inspect the relevant Advisory and SAFE VIBE prototype boards.
6. Inspect the reusable Design Foundation components from Handoff 01.
7. Identify existing interactions, animations, links and content that must be preserved.
8. Compare the current implementations with the accepted content and design requirements.
9. Identify any existing defects or deviations before making changes.
Preserve valid existing work. Do not restart either page from scratch without a specific technical reason.
## 4. Implementation Scope
### 4.1 Advisory Hero
- Implement the approved Advisory Hero composition.
- Preserve the approved positioning, headline, supporting copy and calls to action.
- Establish a clear visual hierarchy and appropriate editorial typography.
- Ensure the primary CTA leads to the intended Contact destination.
- Maintain consistency with the accepted Home design and shared Design Foundation.
### 4.2 Four-Step Proposition
- Implement the approved four-step proposition.
- Preserve the exact approved step names, sequence, descriptions and relationships.
- Make the progression visually understandable.
- Use consistent spacing, typography and alignment.
- Ensure the presentation remains clear on smaller screens.
### 4.3 Four Areas of Advisory
Present the four approved areas:
1. AI Discovery
2. AI Governance & Security
3. IT & AI GRC
4. AI-assisted Development Governance
- Preserve approved descriptions and supporting content.
- Maintain a clear and consistent structure across all four areas.
- Use balanced layouts and appropriate visual differentiation.
- Avoid making one area appear more important solely because of its content length.
### 4.4 Engagement Models
- Implement all eight approved engagement models.
- Preserve their approved names, descriptions and distinctions.
- Present them in a coherent and readable layout.
- Ensure consistent alignment and responsive behaviour.
- Do not merge, rename or invent engagement models.
### 4.5 SAFE VIBE Introduction within Advisory
- Present SAFE VIBE as Sophranic's proprietary methodology.
- Give it an appropriately prominent and distinct presentation.
- Include the approved explanation of its purpose and relationship to Advisory.
- Provide a clear link to the dedicated SAFE VIBE page.
- Do not present SAFE VIBE as a fifth Advisory service.
- Do not present it as a replacement for established governance frameworks.
### 4.6 Dedicated SAFE VIBE Page
Implement the complete approved SAFE VIBE page, preserving its accepted content and narrative.
The methodology must communicate that:
- It extends existing governance and management practices.
- Organisations retain their chosen frameworks, including approaches such as NIST and ISO.
- It helps identify and address AI-specific gaps and risks, including relevant areas such as OWASP.
- Its application is proportional to organisational scope, context and risk.
Preserve the approved eight principles:
- S — Scope
- A — Accountability
- F — Framework
- E — Evaluation
- V — Visibility
- I — Intelligence
- B — Boundaries
- E — Escalation
Implement the complete approved narrative, including the existing sections on governance integration, practical application, frameworks and proportionality.
Do not reduce SAFE VIBE to an acronym list or generic AI governance framework.
### 4.7 Narrative Layouts and Alignment
- Use consistent narrative layouts across both pages.
- Apply the shared container geometry and typography.
- Maintain deliberate column alignment and consistent section spacing.
- Use asymmetric or two-column layouts where supported by the approved composition.
- Align related headings, descriptions, visual elements and CTAs.
- Ensure that longer content does not produce unintended visual imbalance.
- Preserve the accepted Navy, Light Peach and Dark Green visual language according to section purpose.
### 4.8 Responsive Presentation
- Implement the approved desktop, tablet and mobile compositions.
- Preserve intended content order and hierarchy.
- Ensure cards and columns stack appropriately.
- Maintain readable typography and adequate spacing.
- Prevent horizontal overflow.
- Verify navigation, links and interactive elements on smaller screens.
## 5. Shared Design Foundation
Reuse the accepted components and tokens from Handoff 01:
- Section and its surface variants.
- PageHeader.
- SectionHeading.
- Button.
- TextLink.
- AsymmetricLayout.
- TwoColumnLayout.
- Separator.
- EmailLink where applicable.
- Shared typography classes, colour tokens and container geometry.
Do not duplicate shared components or introduce competing design tokens.
Do not modify Navbar, Footer or global Design Foundation unless a concrete integration defect requires attention. Report such a defect before expanding scope.
## 6. Scope Boundaries
- Modify the Advisory and dedicated SAFE VIBE pages and their directly related content modules only.
- Preserve all approved substantive content.
- Do not redesign Home.
- Do not redesign Products, About or Contact.
- Do not modify the shared Navbar or Footer.
- Do not implement Handoff 04 or Handoff 05 requirements.
- Do not withdraw SeeLabel routes.
- Do not perform comprehensive SEO or metadata work.
- Do not modify authentication, authorization or moderation logic.
- Do not modify Supabase, database schemas or backend functions.
- No dependency upgrades.
- No unrelated refactoring or legacy cleanup.
- No production deployment.
## 7. Acceptance Criteria
### 7.1 Content
- Advisory contains the approved Hero, four-step proposition, four areas and eight engagement models.
- SAFE VIBE is presented as a proprietary Advisory methodology.
- The dedicated SAFE VIBE page contains the complete approved narrative and all eight principles.
- No unapproved substantive copy has been introduced.
### 7.2 Visual Quality
- Both pages follow the accepted Design System.
- Narrative layouts are consistent and well aligned.
- Section hierarchy and visual rhythm are clear.
- SAFE VIBE has an appropriately distinctive presentation.
- Desktop, tablet and mobile layouts preserve the intended composition.
### 7.3 Functional Quality
- All internal links lead to the correct destinations.
- Advisory links to the dedicated SAFE VIBE page.
- CTAs lead to their approved destinations.
- No broken links or unintended navigation behaviour.
- Existing Navbar and Footer remain functional.
### 7.4 Technical Validation
- `npm run build` completes successfully.
- `npm run lint` reports zero errors.
- No new lint warnings are introduced.
- No unintended changes outside the approved scope.
## 8. Completion Report
Provide:
- Implemented Advisory sections.
- Implemented SAFE VIBE sections.
- Modified and created files.
- Reused shared components.
- Any new components and their justification.
- Desktop, tablet and mobile verification results.
- Build and lint results.
- Deviations from the accepted prototype or Design System.
- Content or design decisions requiring human review.
- Outstanding issues and deferred requirements.
- Current repository state.
Clearly distinguish automated verification from browser testing and human visual review.
## 9. Session Continuity
- Treat this handoff as an independently executable task.
- If context or token limits approach, stop at a safe implementation boundary.
- Record completed work, remaining work, modified files, verification results and repository state.
- Do not leave implementation in an ambiguous state.
- Preserve enough information for a new session to resume safely.
- Human approval is required before resuming interrupted work.
## 10. Human Acceptance Checkpoint
- Stop after implementation and the completion report.
- Await human visual and functional review.
- Do not commit, push, update the roadmap status to done or begin Handoff 04 without explicit human approval.
- Do not deploy to production.
AI assists. Humans decide.