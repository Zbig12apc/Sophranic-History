# Handoff 01 — Design Foundation
## 1. Task Definition
- Recipient: Code-Writer.
- Project: Sophranic Site Redesign.
- Status: pending.
- Objective: establish the shared design foundation required for subsequent page redesign tasks.
- Working directory: `C:\sophranic\products\sophranic-site`
- Branch: `develop`
- Baseline commit: `9d92365`
## 2. Mandatory Source Materials
Follow the applicable Sophranic Knowledge Base startup procedure, agent framework, engineering standards and Next.js technology requirements.
Read the following project documents from `C:\sophranic\work\sophranic-site-redesign\`:
- `implementation-roadmap.md`
- `audit-decisions.md`
- `design-system.md`
- `Sophranic-redesign_direction.html`
The Design System and Audit Decisions define the accepted requirements. The HTML prototype is a visual reference, not implementation architecture.
Read the prototype selectively to avoid unnecessary context consumption caused by embedded assets.
## 3. Pre-Implementation Verification
- Verify the current branch and baseline commit.
- Inspect the working tree and identify existing uncommitted changes.
- Preserve the supplied `public/images/founder.png` asset.
- Inspect existing global styles, font configuration, layout and shared components.
- Verify existing component usage before modifying shared components.
- Consult the installed Next.js documentation where required.
- Compare the accepted colour values with the HTML reference. Report discrepancies without silently changing accepted values.
- Escalate material conflicts or missing requirements to the human before proceeding.
## 4. Implementation Scope
### 4.1 Design Tokens and Global Styles
Implement the shared foundation defined in Design System sections 2–4:
- Dark Navy, Dark Green and Light Peach background variants.
- Supporting colours and accessible accent variants.
- Newsreader and Inter typography.
- Initial typography scale and font weights.
- Responsive container geometry.
- Standard 40/60, 50/50 and single-column layouts.
- Section spacing and separators.
- Responsive breakpoints.
Use a consistent, reusable implementation compatible with the existing Next.js and Tailwind CSS configuration.
### 4.2 Shared Components
Implement or adapt reusable components required for:
- Section containers and background variants.
- Page and section headings.
- Asymmetric and symmetric layouts.
- Outlined primary and secondary buttons.
- Clearly identifiable text links.
- Accessible hover and focus states.
- Responsive behaviour.
Follow Design System sections 3–5, 15 and 16.
Reuse existing components where appropriate. Avoid unrelated component cleanup.
### 4.3 Navbar
Implement Design System section 6:
- Shared Dark Navy background.
- Original Sophranic logo linking to Home.
- Sticky positioning on desktop and mobile.
- Advisory dropdown: How We Help and SAFE VIBE.
- Products.
- About dropdown: About Sophranic, Our Philosophy and Meet the Founder.
- Contact.
- Outlined Get in touch CTA.
- Dropdowns closed by default.
- Accessible click, tap, keyboard and dismissal behaviour.
- Responsive mobile navigation.
Establish the About anchor identifiers required by Handoff 04. Ensure submenu destinations resolve to meaningful existing content during the transitional implementation.
Preserve existing authentication and moderation functionality.
### 4.4 Footer
Implement Design System section 7:
- Shared footer background.
- Compact Brand, Explore and Contact layout.
- Current brand statements.
- Top-level navigation only.
- Functional advisory and support email links.
- Corporate Privacy Policy and Terms of Use links.
- Dynamically updated copyright year.
- Remove SeeLabel references and inactive social media links from the Footer.
- Responsive composition.
- No personal LinkedIn link in the Footer.
## 5. Scope Boundaries
- Do not redesign individual page compositions during this handoff.
- Shared styling changes affecting existing pages are expected. Preserve their content and functionality.
- Do not rewrite substantive page content.
- Do not withdraw SeeLabel routes at this stage.
- Do not implement the Founder section or photograph presentation.
- Do not perform the comprehensive SEO and metadata update.
- Do not modify authentication, authorization or moderation business logic.
- Do not modify Supabase, database schemas or backend functions.
- Do not perform unrelated refactoring, dependency upgrades or legacy component cleanup.
- Do not deploy to production.
- Do not begin Handoff 02.
## 6. Acceptance Criteria
### 6.1 Design Foundation
- All three primary background variants are available through reusable styling.
- Newsreader and Inter are correctly loaded and applied.
- Shared typography and geometry follow the accepted Design System.
- Standard layouts are available for subsequent handoffs.
- Outlined buttons and identifiable text links are implemented.
- Shared styling is responsive.
- No unintended horizontal overflow.
### 6.2 Navbar
- Desktop and mobile navigation function correctly.
- Sticky positioning works.
- Dropdowns remain closed by default.
- Dropdowns open and close correctly.
- Keyboard navigation and focus states work.
- Navigation labels and destinations match accepted decisions.
- Logo and Get in touch CTA function correctly.
### 6.3 Footer
- Footer reflects the current two-pillar brand.
- Only top-level navigation is presented.
- Contact and legal links work.
- SeeLabel and inactive social media references are removed from the Footer.
- Footer remains readable and functional on smaller screens.
### 6.4 Technical Validation
- `npm run build` completes successfully.
- `npm run lint` reports zero errors.
- No new lint warnings introduced by this handoff.
- Existing public pages remain functional.
- Existing authentication and moderation protection remain intact.
- No unintended changes outside the approved scope.
## 7. Completion Report
Provide a concise report containing:
- Implemented requirements.
- Modified and created files.
- Shared design tokens and reusable components available to subsequent handoffs.
- Navigation anchor identifiers and their current implementation status.
- Build and lint results.
- Functional and responsive verification results.
- Existing warnings and any new issues.
- Differences between the accepted Design System and HTML reference.
- Decisions requiring human review.
- Outstanding requirements and explicitly deferred items.
- Current repository state.
Clearly distinguish verified results from items requiring human browser verification.
## 8. Session Continuity
If context or token limits approach:
- Stop at a safe implementation boundary.
- Report completed and remaining work.
- Record modified files and verification results.
- Preserve sufficient information for another session to resume.
- Obtain human confirmation before resuming interrupted work.
## 9. Human Acceptance Checkpoint
Stop after completing this handoff and presenting the completion report.
Human visual and functional review is required before acceptance.
Do not commit, push, update the roadmap status to done or proceed to Handoff 02 without explicit human approval.
AI assists. Humans decide.