# Handoff 02 — Home
## 1. Task Definition
- Recipient: Code-Writer.
- Project: Sophranic Site Redesign.
- Status: pending.
- Objective: implement the complete Home page using the accepted Sophranic Design System and the shared Design Foundation delivered in Handoff 01.
- Working directory: `C:\sophranic\products\sophranic-site`
- Branch: `develop`
- Accepted baseline commit: `f8e6cea` — Implement Sophranic design foundation.
## 2. Authoritative Source Materials
Directory: `C:\sophranic\work\sophranic-site-redesign`
- `implementation-roadmap.md`
- `audit-decisions.md`
- `design-system.md`
- `Sophranic-redesign_direction.html`
Additional authoritative project sources:
- Existing approved Home content and content modules.
- Current Sophranic brand and business positioning documentation.
Follow the applicable Sophranic Knowledge Base startup procedure, agent framework, engineering standards and Next.js technology requirements.
The Design System and Audit Decisions define accepted requirements. The HTML prototype is a visual reference. Accepted human decisions take precedence over the prototype.
Inspect only the Home-related prototype material and relevant existing project files.
## 3. Pre-Implementation Verification
- Verify branch `develop` and accepted baseline `f8e6cea`.
- Check the working tree and preserve unrelated or untracked files.
- Inspect the existing Home implementation and its content sources.
- Inspect reusable components delivered in Handoff 01.
- Identify existing animations and interactions that should be retained or adapted.
- Verify the exact content and section order against the accepted prototype and approved project content.
- Do not invent missing content or silently rewrite approved messaging.
- Raise material conflicts or missing requirements before implementation.
## 4. Implementation Scope
### 4.1 Home Hero
- Implement the approved Home Hero composition.
- Preserve the current two-pillar Sophranic positioning.
- Apply the accepted typography, colour palette, gradients and layout geometry.
- Ensure the primary navigation and calls to action lead to the correct destinations.
- Maintain the intended visual hierarchy on desktop and mobile.
### 4.2 Two Business Pillars
Present the two equally important Sophranic business areas:
- Advisory — Dark Navy as the principal visual identity.
- Products — Dark Green as the principal visual identity.
Preserve the accepted distinction between the two pillars.
Products may use slightly more visual spontaneity while remaining consistent with the shared Design System.
Both areas must have clear navigation to their respective destinations.
### 4.3 SAFE VIBE Introduction
- Implement the approved initial SAFE VIBE presentation with eight tiles.
- Preserve the approved SAFE VIBE terminology and content.
- Use the accepted visual treatment and spacing.
- Provide a clear route to the dedicated SAFE VIBE page.
- Ensure the tiles remain legible and coherent on mobile.
### 4.4 Philosophy
- Implement the approved Home philosophy section.
- Use the accepted four-area visual language and composition where specified by the prototype.
- Preserve the relationship between the philosophy and Sophranic's two business pillars.
- Reuse the shared layout and typography components.
- Avoid introducing new substantive messaging without human approval.
### 4.5 Founder Introduction
- Implement the approved Home-level Founder introduction.
- Provide an appropriate route to Meet the Founder on the About page.
- Do not create or redesign the dedicated Meet the Founder section.
- Do not introduce a new photograph treatment or modify `public/images/founder.png`; the dedicated Founder presentation and photograph belong to Handoff 04.
### 4.6 Section Flow and Backgrounds
- Follow the accepted alternating light and dark section rhythm.
- Use Dark Navy, Light Peach and Dark Green according to the approved Design System and section purpose.
- Preserve the intended visual flow between sections.
- Maintain consistent container widths, column boundaries and spacing while scrolling.
- Avoid unintended horizontal shifts or inconsistent section alignment.
### 4.7 Responsive Behaviour
- Implement the approved composition across desktop, tablet and mobile.
- Preserve intended section order and visual hierarchy.
- Ensure columns transform into readable mobile layouts.
- Check typography, spacing, tile dimensions and CTA accessibility at smaller widths.
- Avoid horizontal overflow.
## 5. Shared Design Foundation
Reuse the components and tokens delivered in Handoff 01:
- Design tokens and surface variants.
- Newsreader and Inter typography.
- Section and SectionHeading.
- PageHeader.
- Button and TextLink.
- AsymmetricLayout and TwoColumnLayout.
- Separator.
- Shared container geometry and section spacing.
Do not duplicate shared components or create competing design tokens.
Do not modify Navbar, Footer or shared navigation behaviour unless a concrete Home integration defect requires a minimal correction. Escalate such defects before expanding scope.
## 6. Scope Boundaries
- Modify the Home page and its directly related components only.
- Preserve approved content unless explicitly authorised to change it.
- Do not redesign Advisory or SAFE VIBE pages.
- Do not redesign Products, About or Contact pages.
- Do not implement the dedicated Founder section or photograph presentation.
- Do not withdraw SeeLabel routes.
- Do not perform the comprehensive SEO or metadata update.
- Do not modify authentication, authorization or moderation logic.
- Do not modify Supabase, database schemas or backend functions.
- Do not perform unrelated refactoring or dependency upgrades.
- Do not deploy to production.
- Do not begin Handoff 03.
## 7. Acceptance Criteria
### 7.1 Content and Composition
- All approved Home sections are implemented.
- Both business pillars are clearly presented and distinguishable.
- SAFE VIBE is introduced using eight tiles.
- Philosophy and Founder introduction are included as approved.
- No unapproved substantive content has been introduced.
### 7.2 Visual Quality
- The page follows the accepted Design System.
- Light and dark sections alternate according to the approved composition.
- Dark Green establishes the Products visual identity.
- Typography and spacing are consistent with Handoff 01.
- Section widths and column boundaries remain consistent while scrolling.
- Desktop and mobile compositions preserve the intended visual flow.
### 7.3 Functional Quality
- All Home navigation links and CTAs lead to the correct destinations.
- No broken internal links.
- Existing Navbar and Footer remain functional.
- Existing interactions and animations work as intended.
### 7.4 Technical Validation
- `npm run build` completes successfully.
- `npm run lint` reports zero errors.
- No new lint warnings introduced by this handoff.
- No unintended changes outside the approved scope.
## 8. Completion Report
Provide:
- Implemented Home sections.
- Modified and created files.
- Reused shared components.
- Any new components and the reason for introducing them.
- Desktop, tablet and mobile verification results.
- Build and lint results.
- Deviations from the accepted prototype or Design System.
- Content or design decisions requiring human review.
- Outstanding issues and deferred requirements.
- Current repository state.
Clearly distinguish automated verification from browser testing and human visual review.
## 9. Session Continuity
- Keep the task independently executable using persisted project documentation.
- If context or token limits approach, stop at a safe implementation boundary.
- Record completed work, remaining work, modified files, verification results and repository state.
- Do not leave the implementation in an ambiguous state.
- Obtain human confirmation before resuming interrupted work.
## 10. Human Acceptance Checkpoint
- Stop after completing the Home implementation and presenting the report.
- Human visual and functional review is required.
- Do not commit, push, update the roadmap status to done or proceed to Handoff 03 without explicit human approval.
- Do not perform production deployment.
AI assists. Humans decide.