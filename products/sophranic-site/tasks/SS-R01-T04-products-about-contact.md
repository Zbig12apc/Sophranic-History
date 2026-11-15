# Handoff 04 — Products, About and Contact
## 1. Task Definition
- Recipient: Code-Writer.
- Status: pending.
- Dependencies: Accepted Handoffs 01–03.
- Objective: Complete the Products, About and Contact pages using the accepted Sophranic Design System and approved content direction.
- This is an implementation task, not a new product or brand strategy exercise.
## 2. Authoritative Instructions
- Follow the Sophranic Knowledge Base startup procedure.
- Follow applicable Code-Writer instructions.
- Read and follow the accepted Design System, Audit Decisions and Implementation Roadmap.
- Treat this handoff as the authoritative task specification.
- Inspect the current implementation before editing.
- Preserve accepted work from Handoffs 01–03.
- Reuse existing shared components wherever appropriate.
- Do not invent content, products, credentials, founder achievements or business claims.
## 3. Products Page
### 3.1 Products Positioning
Present Sophranic Products as the digital product development pillar of Sophranic.
Approved product philosophy:
"Creating digital products that make information easier to understand, reduce complexity and support thoughtful, personal decisions."
The broader philosophy is to make everyday life simpler and help people make confident choices.
### 3.2 Visual Structure
- Hero: Dark Green, using the established Products visual identity.
- Product development approach: Light Peach.
- Follow the accepted Design System for typography, spacing, section composition and responsive behaviour.
- Maintain a clear visual hierarchy between the introduction and the product development philosophy.
### 3.3 Product Placeholders
- Remove empty product cards, fictional products, portfolio placeholders and unsupported product announcements.
- SeeLabel has not launched and is currently suspended while its future direction is being considered in connection with Data Platform v2.
- Do not present SeeLabel as an available, launched or downloadable product.
- Do not imply that other products currently exist.
- Preserve existing dedicated SeeLabel routes and their functional/legal requirements. Do not delete or redesign those routes as part of this task.
- The Products page should remain meaningful without a list of currently available products.
## 4. About Page
The About page is one continuous page with three sections:
1. About Sophranic.
2. Our Philosophy.
3. Meet the Founder.
Preserve the existing navigation/dropdown structure and section anchors:
- `#about-sophranic`
- `#our-philosophy`
- `#meet-the-founder`
Each anchor must navigate to the actual beginning of its corresponding section, respecting the sticky Navbar.
Repeated activation of the same anchor must work after scrolling away, in both directions.
### 4.1 About Sophranic — Name and Etymology
Explain the name Sophranic using the approved Greek linguistic roots and concepts:
- `sōs (σῶς)` — safe, sound and whole.
- `phrēn (φρήν)` — mind, thought and the seat of reason.
- `sōphrosynē (σωφροσύνη)` — composure, self-restraint and sound judgment.
Present the relationship between these concepts clearly and accurately.
Distinguish the individual roots from the broader Greek concept. Do not invent a literal historical Greek word or claim that "Sophranic" itself is an ancient Greek word.
The explanation should communicate the brand's connection to sound judgment, balance and thoughtful use of technology.
### 4.2 Our Philosophy
Preserve the accepted three-dimensional philosophy and its relationship to the Sophranic logo colours:
- Brain — Blue: logic, clarity, structure and intelligent thinking.
- Emotion — Orange: connection, empathy, energy and intuition.
- Balance — Green: meaning, values, purpose and balance.
Use the approved term Balance. Do not reintroduce Spirit.
Preserve the established editorial presentation and explain how the three dimensions complement one another.
The broader philosophy should communicate that technology should help people understand information, reduce complexity and make thoughtful, confident decisions.
### 4.3 Meet the Founder
- Founder: Zbigniew Dawydzik.
- Use the existing founder photograph: `public/images/founder.png`.
- Preserve the image and do not replace, regenerate or modify it.
- Include the approved LinkedIn destination:
  `https://www.linkedin.com/in/zbigniewdawydzik/`
- The LinkedIn link must be clearly identifiable and functional.
- Use concise, factual founder information consistent with the existing approved Sophranic content.
- Do not invent qualifications, employers, awards, publications or professional achievements.
## 5. Contact Page
### 5.1 Structure
- Present exactly two contact channels.
- Use two equivalent visual cards/columns on desktop and a responsive stacked layout on smaller screens.
- Do not add a contact form.
- Reuse the existing EmailLink component.
### 5.2 Approved Contact Channels
**Channel 1 — Sophranic Advisory**
- Purpose: Business advisory, AI governance and responsible technology implementation.
- Email: `advisory@sophranic.com`
- Supporting description: "For business advisory, AI governance and responsible technology implementation:"
**Channel 2 — Sophranic Products & General Enquiries**
- Purpose: Digital products and general enquiries.
- Email: `support@sophranic.com`
- Supporting description: "For our digital products and all general enquiries:"
### 5.3 Email Interaction
Preserve the approved EmailLink interaction:
- Clicking the email address copies it to the clipboard.
- Display "Copy" and "Copied!" feedback.
- Retain the `mailto:` fallback.
- Ensure keyboard accessibility and responsive presentation.
Do not introduce additional email addresses or contact channels.
## 6. Shared Design Requirements
- Follow the accepted Design System from Handoff 01.
- Reuse Section, PageHeader, SectionHeading, Button, TextLink and existing layout components where appropriate.
- Maintain the established typography hierarchy and colour palette.
- Maintain consistent eyebrow styling.
- Use the approved section colours and appropriate contrast.
- Preserve the established visual rhythm across all pages.
- Ensure responsive presentation on desktop, tablet and mobile.
- Preserve Navbar and Footer behaviour.
## 7. Scope Boundaries
In scope:
- Products page.
- About page and its three sections.
- Contact page.
- Directly related content modules.
- Necessary local anchor and email interaction corrections.
Out of scope:
- Home, Advisory and SAFE VIBE redesign.
- Global Design System redesign.
- Navbar or Footer redesign.
- SeeLabel mobile application.
- SeeLabel backend, database or Supabase changes.
- Authentication and moderation.
- SEO strategy or unrelated metadata changes.
- Product development or Data Platform v2 implementation.
- New product announcements or fictional portfolio content.
- Handoff 05 or any subsequent work.
If a shared component change appears necessary, explain the reason and expected impact before expanding scope.
## 8. Technical Verification
- Run `npm run build`.
- Run `npm run lint`.
- Confirm no new lint errors or warnings.
- Verify all three About anchors, including repeated navigation.
- Verify both Contact email-copy interactions and their mailto fallbacks.
- Verify the founder image and LinkedIn link.
- Verify Products page contains no empty or fictional product placeholders.
- Verify the responsive layouts.
- Distinguish automated verification from actual browser testing in the completion report.
## 9. Completion Report
Produce a completion report using the same structure and level of detail as Handoffs 01–03.
Include:
1. Implemented sections.
2. Files modified and created.
3. Shared components reused.
4. Build and lint results.
5. Manual browser verification requirements and results.
6. Scope deviations or unresolved issues.
7. Git status and repository state.
## 10. Human Acceptance Checkpoint
- Stop after implementation, verification and completion report.
- Await explicit human visual and functional acceptance.
- Do not commit, push or deploy.
- Do not update the roadmap status to done.
- Do not start subsequent handoffs.
AI assists. Humans decide.