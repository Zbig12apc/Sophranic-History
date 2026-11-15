# Handoff 05 — Functional Closure
## 1. Task Definition
- Recipient: Code-Writer.
- Status: pending.
- Dependencies: Accepted Handoffs 01–04.
- Objective: Complete the remaining functional, legal and SEO requirements of the Sophranic website.
- Scope is strictly limited to the items below.
## 2. Working Instructions
- Follow the Sophranic Knowledge Base startup procedure and applicable Code-Writer instructions.
- Read this handoff first.
- Inspect the current repository state before making changes.
- Read only the specific source files and documentation required for each task.
- Do not reread completed handoffs or unrelated Knowledge Base documents.
- Do not duplicate information already available in the relevant source files.
- Treat existing accepted implementation and current project decisions as authoritative.
- Diagnose before changing. Preserve working functionality.
- Read only documentation directly relevant to the assigned task.
- Do not reread documents already available in the current working context.
- Do not follow references to additional documents unless their contents are necessary to complete or verify a specific task requirement.
- If a requirement can be verified directly from the relevant source code or configuration, do not load unrelated project documentation.
## 3. Implementation Scope
### 3.1 SeeLabel Public Area
- Withdraw the entire public SeeLabel website area.
- Remove obsolete SeeLabel product links, navigation entries and CTAs throughout the public Sophranic website.
- Identify all affected routes and references before removal.
- Preserve authentication, password recovery and other functionality still required by the retained application or protected administrative areas.
- Do not modify the SeeLabel mobile application, backend or database.
### 3.2 SEO and Indexing
- Align page metadata with the current Sophranic brand, content and active routes.
- Update sitemap and indexing requirements.
- Ensure withdrawn public routes are no longer advertised or indexed.
- Preserve appropriate indexing rules for retained public pages.
### 3.3 Corporate Legal Pages
- Ensure `/privacy` and `/terms` contain the current corporate Privacy Policy and Terms of Use.
- Use existing approved legal content and project sources.
- Do not invent legal provisions or silently rewrite approved legal terms.
- Identify missing or unresolved legal content for human review.
### 3.4 Functional Email Links
- Verify email links across the website.
- Preserve the approved contact addresses and existing copy-to-clipboard / mailto behaviour.
- Correct broken or obsolete email destinations.
### 3.5 Content Encoding
- Find and correct remaining active-content encoding problems, including incorrectly displayed special characters.
- Limit changes to actual content defects.
### 3.6 Authentication and Moderation Protection
- Verify that retained authentication and moderation routes remain protected.
- Verify relevant access-control and redirect behaviour.
- Do not redesign or refactor authentication, authorization or moderation.
- Do not weaken existing security controls.
### 3.7 Cross-Page Functional Consistency
- Verify internal links, navigation destinations, CTAs and retained routes.
- Remove references to withdrawn content.
- Check that all active public routes work consistently.
## 4. Scope Boundaries
- No visual redesign.
- No global layout or Design System changes.
- No changes to the Products footer/layout issue.
- No SeeLabel mobile app, Supabase schema or backend changes.
- No unrelated refactoring or dependency upgrades.
- No new product content or announcements.
- No Handoff 06 work.
If a requirement cannot be completed safely without expanding scope, stop and report the issue.
## 5. Verification
- Run `npm run build`.
- Run `npm run lint`.
- Verify active public routes and withdrawn SeeLabel routes.
- Verify sitemap and indexing output.
- Verify corporate Privacy Policy and Terms of Use.
- Verify email interactions.
- Verify retained authentication and moderation protection.
- Verify navigation and cross-page links.
- Report automated and manual verification separately.
## 6. Completion Report
Use the established completion-report structure:
1. Implemented changes.
2. Files modified or removed.
3. Technical verification.
4. Manual verification results and remaining checks.
5. Scope deviations and unresolved issues.
6. Git status and repository state.
## 7. Human Acceptance Checkpoint
- Stop after implementation, verification and completion report.
- Await explicit human acceptance.
- No commit, push or deployment.
- Do not update the roadmap status to done.
- Do not start subsequent work.
AI assists. Humans decide.