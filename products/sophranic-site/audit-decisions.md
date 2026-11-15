# Sophranic Site — Pre-Redesign Audit Decisions
## 1. Purpose
- Consolidate accepted non-visual decisions from the Sophranic Site end-to-end review.
- Use this document together with the Sophranic Design System v1.0 as the foundation for the implementation handoff.
- Preserve accepted human decisions throughout implementation.
## 2. Brand and Content
- Maintain two business pillars: Sophranic Advisory and Sophranic Products.
- SAFE VIBE is a proprietary methodology within Advisory, not a separate business pillar.
- Preserve the dedicated SAFE VIBE page.
- Preserve approved Advisory, SAFE VIBE, About and Founder content.
- Obtain human approval for substantive content changes and new substantive copy.
- Update legacy brand descriptions still presenting Sophranic exclusively as an app development company.
- Align Footer content and default metadata with the current two-pillar brand.
- Preserve the approved Founder biography.
- Use the original source document as the authoritative reference for Greek terminology and etymology on the About page.
- The initial interpretation of Sophranic used "Spirit".
- Following a renewed analysis, a new interpretation was adopted: "Balance".
- The change was accepted and implemented ono Sophranic Site.
- "Balance" is currenty associated with the colour green.
## 3. Products
- Preserve Sophranic Products as an equally important business pillar.
- Maintain the Products page with an introduction and product development philosophy.
- Remove Atlas, Pulse and Prism from public presentation.
- Introduce individual product entries only when actual product development begins.
- Withdraw the entire SeeLabel public area until the project resumes.
- Remove SeeLabel from the Products page, Footer, public navigation and sitemap.
- Withdraw SeeLabel Product, Privacy, Terms, Support and Reset Password pages from public access.
- Remove Request Early Access and other SeeLabel-related public CTAs.
- Preserve SeeLabel application code, backend, database and project documentation.
- Preserve withdrawn website functionality and content for potential future reactivation.
- Defer verification of SeeLabel application dependencies and app store requirements until the project resumes, before its future launch.
- No SeeLabel dependency analysis is required during the current redesign.
## 4. Contact and Legal
- Preserve the approved two-channel Contact structure.
- Advisory enquiries: advisory@sophranic.com.
- Products and general enquiries: support@sophranic.com.
- Official privacy contact: privacy@sophranic.com.
- Update applicable privacy documentation accordingly.
- Update Contact page metadata to reflect both business areas.
- Preserve Sophranic corporate Privacy Policy and Terms of Use.
- Ensure all email addresses are functional `mailto:` links, including those in legal documents.
- Clearly distinguish links from ordinary text.
- Preserve existing email-copy functionality.
- Do not introduce an additional contact form.
- Defer automatic SeeLabel privacy email subject tagging.
## 5. Navigation
- Preserve homepage access through the Sophranic logo.
- Maintain the following primary navigation structure:
  - Advisory
    - How We Help → `/advisory`
    - SAFE VIBE → `/safe-vibe`
  - Products → `/apps`
  - About
    - About Sophranic
    - Our Philosophy
    - Meet the Founder
  - Contact → `/contact`
- Maintain About as one page, with anchors linking to its three sections.
- Improve SAFE VIBE discoverability through navigation and relevant page content.
- Preserve the Get in touch CTA leading to Contact.
- Implement sticky Navbar on desktop and mobile.
- Keep dropdowns collapsed by default.
- Follow the navigation and interaction requirements defined in the Design System.
- Maintain simplified top-level navigation in the Footer.
- Keep individual product links and detailed subsection links outside the Footer.
## 6. SEO and Metadata
- Index public Sophranic pages.
- Exclude authentication and moderation routes from search engine indexing.
- Apply appropriate noindex metadata to retained non-public routes.
- Remove withdrawn SeeLabel pages from the sitemap.
- Align page descriptions and default metadata with current brand positioning.
- Replace artificial sitemap lastModified dates with accurate dates or omit the property.
- Review canonical URLs and internal links after implementation.
- Ensure metadata reflects the actual publicly available content.
## 7. Authentication and Moderation
- Preserve the accepted removal of public authentication UI and public-layout session checks.
- Preserve authentication and authorization mechanisms required by moderation.
- Preserve moderator route protection and server-action authorization.
- Keep moderation functionality outside the current redesign scope.
- Preserve existing authentication functionality required for moderator access.
- Defer moderator sign-out UI until moderation work resumes.
- Defer detailed moderation review.
## 8. Content Quality and External Links
- Correct encoding errors and corrupted characters in active content and components.
- Verify Greek terminology against the original source document.
- Preserve approved content unless explicitly instructed otherwise.
- Check for broken internal links, outdated CTAs and misleading metadata.
- Remove inactive or placeholder social media links, including Facebook, X/Twitter and GitHub, where present.
- Introduce future product-specific social media links only when relevant.
- Include the personal LinkedIn profile exclusively within Meet the Founder.
- LinkedIn URL: https://www.linkedin.com/in/zbigniewdawydzik/
- LinkedIn profile updates are independent of the website redesign.
- Use the supplied authentic Founder photograph: `public/images/founder.png`.
- Allow future photograph replacement independently of the page layout.
## 9. Out of Scope
- Cleanup of inactive and legacy components.
- Consolidation of legacy product data sources.
- Unrelated architectural refactoring.
- Middleware migration unrelated to current requirements.
- SeeLabel application or backend development.
- SeeLabel application dependency and app store requirements analysis.
- Supabase database changes.
- Moderation functional improvements.
- LinkedIn profile updates.
- Founder photograph background replacement.
## 10. Validation and Acceptance
- Verify production build and lint results.
- Distinguish existing warnings from newly introduced issues.
- Verify all retained public routes, navigation, CTAs and legal links.
- Verify dropdown behaviour and About anchor navigation.
- Verify email links, email-copy functionality and the Founder LinkedIn link.
- Verify desktop, tablet and mobile presentation.
- Confirm withdrawn content is no longer publicly accessible.
- Confirm withdrawn content is excluded from navigation, Footer and sitemap.
- Confirm retained authentication and moderation mechanisms remain protected.
- Verify SEO and indexing requirements.
- Validate visual implementation against the accepted Design System.
- Obtain explicit human acceptance before final production deployment.

## 12. Change Control
### 12.1 Pre-Redesign Checkpoint
- Checkpoint commit: `9d92365`.
- Commit description: Prepare Sophranic 2.0 content and structure before visual redesign.
- Develop and main synchronized at the checkpoint.
- Production build completed successfully.
- Lint completed with zero errors and six existing warnings.
- Preview deployment verified and accepted by the human.
- Transitional production deployment completed.
- Temporary public presentation of SeeLabel and Request Early Access explicitly accepted as a low business risk until redesign implementation.
- Redesign work continues on develop.
### 12.2 Implementation Governance
- Treat the Claude HTML prototype as a visual reference.
- Explicitly accepted human decisions take precedence over prototype content and structure.
- Maintain visual specifications in the separate Sophranic Design System v1.0 document.
- Incorporate both documents into the implementation roadmap and one consolidated implementation handoff.
- Follow existing Sophranic engineering and technology standards.
- Obtain human approval of the implementation handoff before commencing implementation.
- Obtain human acceptance of the implemented website before final production deployment.
- AI assists. Humans decide.