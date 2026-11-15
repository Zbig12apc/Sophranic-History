# Sophranic — Design System v1.0
## 1. Purpose and Design Direction
- Establish a consistent visual identity across the Sophranic website.
- Reflect the brand statement: Technology with Purpose. Responsibility and Simplicity by Design.
- Present Sophranic Advisory as professional, sophisticated, calm and expert-led.
- Allow greater creativity, spontaneity and visual flexibility within Sophranic Products.
- Maintain a shared visual foundation across both business pillars.
- Treat the Claude HTML prototype as a visual reference. Accepted human decisions take precedence over the prototype.
- Preserve approved content. Substantive content changes require human approval.
## 2. Colour System
### 2.1 Primary Background Variants
Three primary background variants:
- **Dark Navy:** `linear-gradient(100deg, #071B34 0%, #0C2C4E 55%, #123C68 100%)`
- **Dark Green:** `linear-gradient(100deg, #0B2A1D 0%, #143C2A 55%, #1E4D36 100%)`
- **Light Peach:** `linear-gradient(100deg, #FBEBE2 0%, #F6DCCC 55%, #F1CDB7 100%)`
### 2.2 Supporting Colours
| Token | Value |
|---|---|
| Orange accent | #F59A73 |
| Green accent | #A9E58B |
| Footer background | #04122A |
| Dark primary text | #FFFFFF |
| Dark secondary text | #B9C7D9 |
| Light primary text | #14110F |
| Light secondary text | #4D443E |
### 2.3 Colour Application
- Dark Navy is the primary dark variant for Sophranic corporate pages and Advisory.
- Dark Green is the primary dark variant for Products.
- Light Peach is shared across both business pillars.
- Alternate dark and light sections to establish visual rhythm.
- Use subtle horizontal gradients.
- Use orange and green accents sparingly and purposefully.
- Establish accessible darker accent variants for use on light backgrounds.
- Preserve visual balance between Advisory and Products.
- Maintain sufficient text, link and interactive element contrast.
## 3. Typography
### 3.1 Font Families
- Display and headings: Newsreader.
- Body, navigation and UI: Inter.
- Editorial introductions and selected statements: Newsreader Italic.
- Newsreader weights: 400, 500, italic 400.
- Inter weights: 400, 500, 600.
### 3.2 Initial Typography Scale
| Element | Desktop | Mobile |
|---|---:|---:|
| H1 / Hero | 64–96 px | 40–48 px |
| H2 / Section | 44 px | 32 px |
| H3 / Subsection | 30 px | 26 px |
| Editorial introduction | 24 px | 21 px |
| Body | 17 px | 16 px |
| Labels and navigation | 14 px | 14 px |
| Buttons | 15 px | 15 px |
| Supporting text | 14 px | 14 px |
### 3.3 Typography Rules
- Body line-height: 1.65.
- Use elegant, predominantly regular-weight headings.
- Use italic serif typography for short editorial introductions and guiding statements.
- Use bold text selectively.
- Maintain readable paragraph widths.
- Allow individual Hero heading sizes within the defined range.
- Treat font sizes as initial values subject to visual validation.
## 4. Layout and Geometry
### 4.1 Shared Geometry
| Parameter | Desktop | Tablet | Mobile |
|---|---:|---:|---:|
| Maximum content container | 1200 px | 1200 px | 1200 px |
| Horizontal padding | 48 px | 32 px | 24 px |
| Section vertical padding | 104 px | 80 px | 56 px |
| Standard column gap | 48 px | 32 px | 24 px |
| Separator thickness | 1 px | 1 px | 1 px |
### 4.2 Standard Layouts
**Asymmetric — 40/60**
- Primary narrative layout.
- Left column: number, heading, short introduction or principle identifier.
- Right column: explanatory content.
- Maintain consistent column alignment across consecutive sections.
- Use subtle horizontal separators between sequential items.
**Symmetric — 50/50**
- Use for equivalent content areas, business pillars, engagement models and contact cards.
- Maintain equal visual weight between columns.
**Single Column**
- Use for Hero sections, introductions, legal content and mobile presentation.
- Maintain readable text widths.
### 4.3 Composition Rules
- Use full-width section backgrounds and a shared content container.
- Maintain consistent horizontal alignment across pages.
- Prevent horizontal shifts in column alignment between adjacent sections.
- Prefer editorial composition over excessive card-based layouts.
- Preserve sufficient whitespace while avoiding unnecessarily large empty areas.
- Allow Products to intentionally extend beyond the standard layouts where justified.
## 5. Buttons, CTA and Links
### 5.1 Standard Buttons
- Transparent background matching the underlying section.
- Thin 1 px outline.
- Rounded pill-shaped ends.
- Primary CTA: outline and text in the appropriate accent colour.
- Secondary CTA: neutral outline and text.
- Subtle hover and visible keyboard focus states.
- Minimum interactive target: 44 px.
### 5.2 Filled Buttons
- Reserved for exceptional, explicitly justified applications.
- Outlined buttons remain the default.
### 5.3 Text Links
- Clearly distinguish links from surrounding text.
- Use accessible accent colours and visible underlining.
- Provide hover and keyboard focus states.
- Ensure all email addresses are functional `mailto:` links, including legal documents.
- Preserve existing email-copy functionality.
## 6. Navigation
### 6.1 Navbar
- Shared Dark Navy background across all pages.
- Original Sophranic logo linking to Home.
- Sticky positioning on desktop and mobile.
- Compact height and consistent horizontal alignment.
- Subtle active navigation indicators.
- Outlined Get in touch CTA linking to Contact.
### 6.2 Navigation Structure
- Advisory
  - How We Help → `/advisory`
  - SAFE VIBE → `/safe-vibe`
- Products → `/apps`
- About
  - About Sophranic
  - Our Philosophy
  - Meet the Founder
- Contact → `/contact`
### 6.3 Dropdown Behaviour
- Dropdowns are closed by default.
- Open on intentional click or tap.
- Close after selection, outside click or Escape.
- Provide accessible keyboard navigation.
- Mobile dropdowns expand inside the vertical mobile menu.
- About submenu items link to corresponding sections within one About page.
- Account for sticky Navbar height when navigating to anchors.
## 7. Footer
- Shared background: #04122A.
- Compact composition with reduced vertical spacing.
- Desktop: three columns — Brand, Explore, Contact.
- Brand: original logo and current brand statements.
- Explore: Advisory, Products, About and Contact.
- Contact: advisory@sophranic.com and support@sophranic.com.
- Bottom row: dynamically updated copyright year, Privacy Policy and Terms of Use.
- Use only top-level navigation links.
- Keep individual products and detailed subsection links outside the Footer.
- Ensure functional email and navigation links.
- Remove SeeLabel and inactive social media links.
- Personal LinkedIn belongs exclusively to Meet the Founder.
- Adapt columns to smaller screens.
## 8. Home
### 8.1 Hero — Dark Navy
- Present the Sophranic brand statement and positioning.
- Use prominent serif typography and restrained orange accents.
- Preserve approved content and CTA destinations.
- Apply outlined button styling.
### 8.2 Two Business Pillars — Light Peach
- Heading: Two paths, one purpose.
- Two equivalent cards in a 50/50 layout.
- Advisory card: Dark Navy with orange accents.
- Products card: Dark Green with green accents.
- Maintain equivalent visual weight, dimensions and CTA placement.
- Use subtle separators within cards.
- Preserve the importance of Products despite the temporary absence of publicly presented products.
### 8.3 SAFE VIBE — Dark Navy
- Preserve SAFE VIBE as a proprietary Advisory methodology.
- Use an asymmetric layout with introductory content on the left.
- Present eight outlined principle tiles on the right.
- Desktop tile arrangement: four columns, two rows.
- Mobile tile arrangement: two columns, four rows.
- Principle sequence: Scope, Accountability, Framework, Evaluation, Visibility, Intelligence, Boundaries, Escalation.
- Use prominent orange letters and readable principle names.
- Provide direct access to the dedicated SAFE VIBE page.
### 8.4 About — Light Peach
- Two-column composition: Philosophy and Meet the Founder.
- Present Brain, Emotion and Balance using subtle colour indicators and horizontal separators.
- Include authentic Founder photography, a concise introduction and a link to the full Founder section.
## 9. Advisory
### 9.1 Hero — Dark Navy
- Preserve approved Advisory positioning and content.
- Prominent serif headline and concise supporting introduction.
- Outlined CTAs to Contact and SAFE VIBE.
### 9.2 Four-Step Proposition — Light Peach
- Present the four stages sequentially:
  1. Discover & Understand.
  2. Assess.
  3. Structure.
  4. Implement & Improve.
- Replace the prototype's 2×2 white-card layout with vertically stacked narrative rows.
- Use the same asymmetric composition as the following Four Areas section.
- Left column: stage number, heading and short italic introduction.
- Right column: approved explanatory content.
- Separate stages using subtle horizontal lines.
### 9.3 Four Areas of Advisory — Dark Navy
- Preserve all four approved areas and their content.
- Use sequential asymmetric rows.
- Maintain consistent typography, separators and column alignment.
- Match the geometry of the preceding Four-Step Proposition.
### 9.4 Engagement Models — Light Peach
- Preserve all eight approved engagement models.
- Present numbered entries in two equivalent columns on desktop.
- Use subtle horizontal separators.
- Adapt to a single column on smaller screens while maintaining sequence.
### 9.5 SAFE VIBE Introduction — Dark Navy
- Present the methodology and its value within Advisory.
- Preserve the approved content.
- Use the same asymmetric column alignment as the other narrative sections.
- Use green accents selectively to highlight key benefits.
- Provide a link to the dedicated SAFE VIBE page.
## 10. SAFE VIBE
### 10.1 Hero — Dark Navy
- Prominent SAFE VIBE heading.
- Subtitle: A Practical Method for Integrated IT & AI Governance.
- Italic statement: Extend What Exists. Add What Is Necessary. Scale with Scope and Risk.
### 10.2 Methodology Introduction — Light Peach
- Preserve the approved introductory content.
- Retain the complementary themes of evolving governance and integrated IT & AI Governance.
- Use a balanced two-column editorial layout.
### 10.3 Eight Principles — Dark Navy
- Preserve the sequential presentation of all eight principles.
- Use the asymmetric narrative layout.
- Left column: prominent orange principle letter, number and principle name.
- Right column: italic guiding statement and explanatory content.
- Preserve the large decorative letters from the visual reference.
- Increase the size and readability of principle names, especially on mobile.
- Avoid unnecessary horizontal space between the principle identifier and its explanation.
- Maintain subtle horizontal separators.
- Preserve all approved methodology content.
## 11. Products
### 11.1 Hero — Dark Green
- Establish Sophranic Products as an independent and equally important business pillar.
- Use the shared typography and outlined CTA conventions.
### 11.2 Our Approach — Light Peach
- Present the philosophy of creating responsible, simple and valuable digital products.
- Keep the initial page concise.
- Obtain human approval for any new substantive copy.
### 11.3 Future Product Presentation
- Add individual product entries when actual development begins.
- Allow greater creativity, spontaneity and product-specific visual identities.
- Maintain the shared Sophranic foundation.
- Exclude SeeLabel, Atlas, Pulse and Prism from the current public presentation.
- Avoid empty product cards, placeholders and unsupported launch announcements.
## 12. About
### 12.1 About Sophranic — Dark Navy
- Present the brand story, motivation and etymology.
- Preserve approved content.
- Verify Greek terminology against the original source document.
### 12.2 Our Philosophy — Light Peach
- Present Brain, Emotion and Balance.
- Use subtle blue, orange and green indicators respectively.
- Preserve approved philosophy and approach content.
- Use editorial composition and horizontal separators where appropriate.
### 12.3 Meet the Founder — Dark Navy
- Preserve the approved Founder biography.
- Use authentic photography from `public/images/founder.png`.
- Separate the biography into readable paragraphs.
- Highlight professional experience and relevant previous organisations.
- Include a subtle LinkedIn icon and clearly identifiable functional link.
- LinkedIn URL: https://www.linkedin.com/in/zbigniewdawydzik/
- Keep LinkedIn exclusively within the Founder section.
- Ensure future photograph replacement can be performed independently of the page layout.
### 12.4 Navigation
- Maintain one About page.
- Provide individual anchors for all three sections.
- Connect the anchors to the About dropdown.
## 13. Contact
### 13.1 Hero — Dark Navy
- Heading: Get in touch.
- Preserve approved introductory content.
### 13.2 Contact Channels — Light Peach
- Two equivalent cards in a 50/50 layout.
- Advisory card: Dark Navy with orange accents.
- Products and general enquiries card: Dark Green with green accents.
- Advisory email: advisory@sophranic.com.
- Products and general enquiries email: support@sophranic.com.
- Provide functional email links and preserve email-copy functionality.
- Stack cards vertically on mobile.
- No additional contact form.
## 14. Legal Pages
- Preserve corporate Privacy Policy and Terms of Use.
- Apply shared typography, geometry and navigation.
- Prioritise readability and clear document hierarchy.
- Official privacy email: privacy@sophranic.com.
- Ensure all links and email addresses are functional and visually identifiable.
## 15. Responsive Design
### 15.1 Breakpoints
- Desktop: ≥1024 px.
- Tablet: 768–1023 px.
- Mobile: below 768 px.
### 15.2 Layout Behaviour
- Desktop: full navigation and standard multi-column layouts.
- Tablet: mobile navigation, single-column narrative layouts and two-column layouts where content permits.
- Mobile: mobile navigation and predominantly single-column layouts.
- Preserve intended reading order when stacking columns.
- Preserve colour hierarchy and visual identity across devices.
- Prevent horizontal overflow.
- Ensure readable email addresses and comfortable interactive targets.
- Account for sticky Navbar positioning and anchor navigation.
## 16. Accessibility and Interaction
- Maintain semantic heading hierarchy.
- Provide appropriate colour contrast.
- Ensure keyboard-accessible navigation and dropdowns.
- Provide visible keyboard focus indicators.
- Use descriptive link labels.
- Provide meaningful alternative text for relevant images.
- Preserve existing functional behaviour unless explicitly changed.
- Avoid excessive decorative animation.
## 17. Implementation Principles
- Establish shared design tokens and reusable styling.
- Maintain consistent components rather than page-specific duplication.
- Follow existing Sophranic engineering and technology standards.
- Consult the installed Next.js documentation where required.
- Preserve approved content and underlying application functionality.
- Keep authentication and moderation functionality outside the visual redesign scope.
- Avoid unrelated refactoring and legacy component cleanup.
- Treat the visual prototype as reference material rather than implementation architecture.
## 18. Validation and Outstanding Items
### 18.1 Visual Validation
- Verify all pages on desktop, tablet and mobile.
- Review gradient balance, typography, spacing and section rhythm.
- Verify consistent column alignment across narrative sections.
- Verify equivalent visual weight between business pillars.
- Check SAFE VIBE principle readability.
- Validate buttons, links, dropdowns and email-copy functionality.
### 18.2 Values Requiring Final Validation
- Individual Hero heading sizes.
- Final typography and spacing adjustments.
- Accessible accent colours on light backgrounds.
- Founder photograph presentation and future background replacement.
- Exact principle identifier dimensions and spacing.
- Breakpoints against actual content.
### 18.3 Outstanding Source Material
- Original document containing Greek terminology and Sophranic etymology.
### 18.4 Acceptance
- Obtain explicit human approval of the Design System before implementation.
- Consolidate this specification with accepted Pre-Redesign Audit Decisions into one implementation handoff.
- Obtain human acceptance of the implemented website before final production deployment.
- AI assists. Humans decide.