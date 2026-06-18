# Tech Review Buying Guide Site Redesign

Date: 2026-05-12

## Goal

Redesign the current broad technology news site into a focused English technology review and buying-guide publication that is more credible for Google AdSense review.

The site should no longer look like a generic, inflated tech-news portal. It should look like a focused editorial site with clear authorship, practical product-selection value, transparent policies, and a clean public page set.

## Positioning

New positioning: a practical technology review and buying-advice site for readers comparing devices, software, AI tools, subscriptions, and everyday tech products.

The site should emphasize:

- Practical buying decisions
- Clear trade-offs instead of hype
- Independent editorial judgment
- Modest and believable author/editor identity
- Updated guides and correction paths
- No fabricated large team, awards, or unverifiable credentials

## Scope

Use the medium-consolidation approach:

- Keep the existing static HTML/CSS/JS architecture.
- Keep existing article files in the repository.
- Remove or de-emphasize scattered low-value topics from main navigation and sitemap.
- Rewrite public trust pages and visible site identity.
- Rebuild homepage and categories around review/buying-guide use cases.
- Keep ads.txt publisher ID unchanged.
- Do not introduce CMS, build tooling, frameworks, or complex routing.

## Brand Direction

The current TechPulse brand should be replaced with a new professional review-site brand.

Recommended brand: **Practical Tech Guide**.

Rationale:

- It communicates usefulness and buying guidance clearly.
- It is broader than AI-only, matching the user's choice to preserve a technology-site direction.
- It avoids the generic news-portal feel of TechPulse.
- It is simple to apply consistently across metadata, headers, footers, policies, and schema.

## Navigation

Use a compact, consistent navigation on all public pages:

- Home
- Buying Guides
- Reviews
- AI Tools
- About
- Editorial Policy
- Contact

Implementation can map these to existing static pages without creating unnecessary new files:

- Home -> index.html
- Buying Guides / Reviews -> categories.html
- AI Tools -> categories.html section anchor if practical, otherwise categories.html
- About -> about.html
- Editorial Policy -> editorial-policy.html
- Contact -> contact.html

Avoid href="#" placeholder links in final edited pages.

## Homepage Design

The homepage should answer four questions quickly:

1. What does this site help readers do?
2. What product or tool areas does it cover?
3. Why should readers trust the guidance?
4. Where should readers go next?

Recommended sections:

1. Hero section
   - Clear one-sentence positioning.
   - Emphasize buying guidance, comparisons, and practical trade-offs.
   - Avoid “daily news”, “latest trends”, and inflated authority claims.

2. Featured guides
   - Link to strongest existing articles.
   - Prefer AI, smartphone, cybersecurity, cloud, smart home, and work/productivity content if they are substantial.

3. Buying-guide topic tracks
   - AI tools and productivity software
   - Phones and mobile devices
   - Home and everyday tech
   - Security and privacy tools
   - Work setup and cloud services

4. Editorial trust block
   - Independent selection
   - Clear correction path
   - No paid ranking claim unless true
   - Content updated when products change

5. Policy and trust links
   - Privacy Policy
   - Terms of Service
   - Cookie Policy
   - Editorial Policy
   - Disclaimer
   - Contact

## Categories Page Design

Rebuild categories.html as a buying-guide map instead of a broad technology taxonomy.

Recommended category cards:

1. AI Tools and Productivity Software
   - ChatGPT / Claude / AI agents / future work AI articles

2. Phones and Mobile Devices
   - Smartphone and flagship phone articles
   - Apple Intelligence article if framed as mobile AI buying context

3. Home and Everyday Tech
   - Smart home and practical consumer-tech articles

4. Security and Privacy
   - Cybersecurity and privacy-related articles

5. Cloud and Work Technology
   - Cloud, edge computing, and work technology articles

6. Emerging Tech to Watch
   - Robotics, quantum, blockchain, VR/AR, green tech only if framed as explainers rather than main commercial categories

Remove “View All” links that point to #. If there is no destination page, omit the link.

## Trust Pages

### About Page

Rewrite about.html around:

- Why the site exists
- What the site covers
- How recommendations are selected
- What the site does not do
- Corrections and updates
- Contact path

Avoid fictional staff histories, unverifiable awards, famous previous employers, degrees, or claims of a large newsroom.

### Authors Page

Use either one editor or a very small editorial model. The safer AdSense-oriented choice is one clear editor.

Recommended author framing:

- Name: Alex Morgan
- Role: Editor, Practical Tech Guide
- Bio: modest, focused on practical technology evaluation and plain-language buying advice

Do not claim degrees, employers, awards, or certifications unless they are real.

### Editorial Policy

Must cover:

- How products/tools are selected
- How reviews and buying guides are researched
- Difference between editorial content and ads
- No paid placement in rankings unless explicitly disclosed
- Corrections process
- Update policy
- AI assistance disclosure if AI is used in drafting or editing
- Last updated date: May 12, 2026

### Contact Page

Make contact paths practical:

- General feedback
- Corrections
- Privacy requests
- Copyright concerns
- Editorial suggestions

If the form is static and has no backend, state that email is the reliable contact method or remove misleading form behavior.

## Legal and Policy Pages

Update these pages to use the new site identity and consistent domain/email references:

- privacy-policy.html
- terms-of-service.html
- cookie-policy.html
- disclaimer.html
- faq.html
- 404.html

The disclaimer should explicitly say content is for general informational and educational purposes and is not professional, legal, financial, security, medical, or tax advice.

Add a caveat that technology products, pricing, availability, features, and terms change frequently, so readers should verify current details with official providers before buying or relying on a tool.

## Sitemap and Robots

Rebuild sitemap.xml around:

- Core public pages
- Trust and legal pages
- Strongest review/buying-guide articles
- De-emphasized broad-topic articles can remain as files but should not be highlighted in sitemap if they weaken the focused site signal

robots.txt should stay simple:

```txt
User-agent: *
Allow: /

Sitemap: https://aicoolgames.com/sitemap.xml
```

ads.txt must preserve the existing line:

```txt
google.com, pub-8306112973766890, DIRECT, f08c47fec0942fa0
```

Do not invent or replace the publisher ID.

## Content Quality Rules

For AdSense approval, edited public pages should avoid:

- Placeholder links
- Empty sections
- Fake team or fake credentials
- Inflated article counts
- “Daily latest news” claims if the site is not actually updated daily
- Broad categories with only one thin article
- Misleading contact forms
- Ads placeholders before approval
- Obvious AI boilerplate and repetitive generic claims

Prefer:

- Specific reader value
- Transparent limits
- Practical decision frameworks
- Clear update/correction process
- Consistent navigation and footer
- Realistic author/editor identity

## Testing and Validation

After implementation, validate:

1. Required public pages exist.
2. No old brand references remain in edited public pages.
3. No href="#" placeholders remain in edited public pages.
4. Homepage reads as a focused review/buying-guide site.
5. About/authors/editorial policy are consistent and modest.
6. sitemap.xml contains only intended final URLs.
7. robots.txt points to sitemap.xml.
8. ads.txt publisher line remains unchanged.
9. There are no obvious encoding artifacts in edited pages.
10. Navigation works consistently across public pages.

## Out of Scope

- No git commit unless explicitly requested.
- No new CMS or framework.
- No external API integrations.
- No destructive deletion of existing articles during this phase.
- No fabricated business identity or team history.
