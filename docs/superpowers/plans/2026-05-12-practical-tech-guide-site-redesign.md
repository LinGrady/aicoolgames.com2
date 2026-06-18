# Practical Tech Guide Site Redesign Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Rework the current site into a focused technology review and buying-guide publication that looks credible, useful, and consistent enough for AdSense review.

**Architecture:** Keep the site static. Update the public-facing pages, shared navigation, policy pages, sitemap, and robots metadata so they all tell the same story: a practical, editor-led technology guide site with clear pages, modest claims, and no placeholder content. Reuse existing article files where they still fit the new direction, but stop surfacing low-value or off-theme sections in the main experience.

**Tech Stack:** Static HTML5, CSS, plain JavaScript already embedded in pages, sitemap.xml, robots.txt, ads.txt.

---

## File Structure

**Modify:**
- `index.html` — homepage positioning, hero copy, featured guides, trust block, navigation, footer.
- `categories.html` — rebuild as a buying-guide and product-comparison topic map.
- `about.html` — rewrite as a modest site story with clear purpose and scope.
- `authors.html` — replace inflated team bios with one believable editor profile.
- `contact.html` — simplify contact paths and remove misleading form expectations.
- `editorial-policy.html` — explain how recommendations are chosen, reviewed, updated, and corrected.
- `privacy-policy.html`, `terms-of-service.html`, `cookie-policy.html`, `disclaimer.html`, `faq.html` — align legal and support pages with the new site identity.
- `404.html` — useful fallback page with links to core public pages.
- `sitemap.xml` — keep only final public pages and the selected strongest articles.
- `robots.txt` — keep crawl guidance simple.
- `css/style.css` — add only the minimum styles needed for the new homepage and category layout.

**Verify without editing:**
- `ads.txt` — confirm the existing publisher line remains unchanged.
- Existing article pages — only reference the ones that still support the new site direction.

---

### Task 1: Set the new site identity across shared public pages

**Files:**
- Modify: `index.html`
- Modify: `about.html`
- Modify: `authors.html`
- Modify: `categories.html`
- Modify: `contact.html`
- Modify: `editorial-policy.html`
- Modify: `privacy-policy.html`
- Modify: `terms-of-service.html`
- Modify: `cookie-policy.html`
- Modify: `disclaimer.html`
- Modify: `faq.html`
- Modify: `404.html`

- [ ] **Step 1: Replace the old brand name and team framing everywhere in the public pages**

Use a consistent, modest brand voice like this:

```html
<a href="index.html" class="logo">Practical<span>Tech</span></a>
```

Use this footer tone where a site summary appears:

```html
<h3>About Practical Tech Guide</h3>
<p>Practical Tech Guide publishes clear, independent advice for choosing products, comparing tools, and understanding everyday technology.</p>
```

- [ ] **Step 2: Update shared navigation to a shorter, more credible set**

Use this nav on all public pages:

```html
<ul class="nav-links">
    <li><a href="index.html">Home</a></li>
    <li><a href="categories.html">Buying Guides</a></li>
    <li><a href="authors.html">Author</a></li>
    <li><a href="about.html">About</a></li>
    <li><a href="editorial-policy.html">Editorial Policy</a></li>
    <li><a href="contact.html">Contact</a></li>
</ul>
```

- [ ] **Step 3: Remove obvious fake-scale claims**

Replace inflated homepage and footer claims such as `150+ Published Articles`, `12 Expert Contributors`, and `Real Team` with modest language about one editor, regular updates, and a correction path.

- [ ] **Step 4: Check for leftover old-brand text in edited pages**

Run:

```bash
python - <<'PY'
from pathlib import Path
for p in Path('.').glob('*.html'):
    text = p.read_text(encoding='utf-8', errors='ignore')
    if 'TechPulse' in text:
        print(p)
PY
```

Expected: no output from the edited public pages.

---

### Task 2: Rebuild the homepage around reviews and buying advice

**Files:**
- Modify: `index.html`
- Modify: `css/style.css`

- [ ] **Step 1: Replace the homepage metadata with a cleaner, more specific title and description**

Use:

```html
<title>Practical Tech Guide - Product Reviews, Buying Advice, and Tech Picks</title>
<meta name="description" content="Clear product reviews, buying advice, and practical technology guides for readers comparing devices, software, and everyday tech tools.">
```

- [ ] **Step 2: Rewrite the hero section so it sounds like a real editorial site, not a generic news portal**

Use copy in this shape:

```html
<section class="hero">
    <p class="eyebrow">Practical advice for choosing the right tech</p>
    <h1>Compare products, understand trade-offs, and buy with more confidence.</h1>
    <p>Practical Tech Guide is a small editorial site focused on useful product comparisons, straightforward recommendations, and plain-language explanations that help readers make better decisions.</p>
</section>
```

- [ ] **Step 3: Replace broad news sections with a small set of useful topic tracks**

Keep only the categories that match the new direction:

- AI tools and productivity software
- Phones and mobile devices
- Home and everyday tech
- Security and privacy
- Cloud and work technology

Link these sections only to existing articles that still fit the new site direction.

- [ ] **Step 4: Rework the trust block so it sounds believable**

Use a modest trust section that says:

- recommendations are selected independently
- the site updates pages when products change
- readers can request corrections
- the site does not sell a fake newsroom identity

Avoid numbers that imply a large team or massive archive unless they are true.

- [ ] **Step 5: Add only the minimum CSS needed for the new homepage sections**

Append these classes if they do not already exist:

```css
.eyebrow {
    text-transform: uppercase;
    letter-spacing: 0.08em;
    font-size: 0.85rem;
    font-weight: 700;
    opacity: 0.85;
    margin-bottom: 0.75rem;
}

.topic-note {
    color: var(--text-light);
    max-width: 760px;
    margin-bottom: 1.5rem;
}
```

---

### Task 3: Turn the category page into a buying-guide map

**Files:**
- Modify: `categories.html`

- [ ] **Step 1: Update the page title and description to match the new purpose**

Use:

```html
<title>Buying Guides - Practical Tech Guide</title>
<meta name="description" content="Browse practical buying guides and product comparisons for AI tools, phones, home tech, security, and work software.">
```

- [ ] **Step 2: Replace the broad tech taxonomy with a smaller set of focused buying-guide cards**

Use exactly these cards:

1. AI Tools and Productivity Software
2. Phones and Mobile Devices
3. Home and Everyday Tech
4. Security and Privacy
5. Cloud and Work Technology
6. Emerging Tech to Watch

Each card should include a short scope statement and 2-4 article links that actually exist.

- [ ] **Step 3: Remove placeholder links and dead category actions**

Do not leave `href="#"` links in the final page.

If a category does not have a real destination page, omit the action link instead of faking one.

- [ ] **Step 4: Remove the old broad-category feel**

Drop category groups that make the site look scattered, especially if they are thinly populated or do not fit the buying-guide direction.

---

### Task 4: Rewrite About and Authors for a believable single-editor site

**Files:**
- Modify: `about.html`
- Modify: `authors.html`

- [ ] **Step 1: Rewrite `about.html` around site purpose, scope, and update policy**

Keep these sections:

- Why the site exists
- What the site covers
- How guides are chosen
- What the site does not do
- Corrections and updates

Use plain language and avoid claiming a large editorial operation.

- [ ] **Step 2: Rebuild `authors.html` as one clear editor page**

Use one editor profile and keep the bio modest.

Example structure:

```html
<article class="author-card">
    <h2>Alex Morgan</h2>
    <p class="author-title">Editor, Practical Tech Guide</p>
    <p class="author-bio">Alex Morgan edits Practical Tech Guide and writes practical reviews, comparisons, and buying advice for readers who want straightforward guidance before they choose a product or tool.</p>
</article>
```

Do not claim degrees, employers, awards, or certifications unless the site can prove them.

- [ ] **Step 3: Remove the feel of a large fabricated staff list**

Delete or replace the multiple-author grid, contributor stats, and “join our team” pitch if they are no longer consistent with the new editorial model.

---

### Task 5: Simplify Contact and Editorial Policy pages

**Files:**
- Modify: `contact.html`
- Modify: `editorial-policy.html`

- [ ] **Step 1: Rewrite `contact.html` so it gives readers real contact paths**

Keep these channels:

- General feedback
- Corrections
- Privacy requests
- Copyright concerns
- Editorial suggestions

If the form has no backend, make that clear or remove the form so it does not imply a working submission flow that does not exist.

Use these email addresses if they already fit the domain setup:

- `hello@aicoolgames.com`
- `corrections@aicoolgames.com`
- `privacy@aicoolgames.com`
- `copyright@aicoolgames.com`

- [ ] **Step 2: Rewrite `editorial-policy.html` to explain how recommendations are made**

The page should state:

- how products and tools are selected
- how reviews are researched and updated
- that paid placement does not control rankings
- how corrections work
- that AI assistance, if used, is reviewed by a human before publication
- the page’s last updated date

Use this last-updated date:

```html
<p class="last-updated">Last Updated: May 12, 2026</p>
```

---

### Task 6: Align the legal and support pages with the new site identity

**Files:**
- Modify: `privacy-policy.html`
- Modify: `terms-of-service.html`
- Modify: `cookie-policy.html`
- Modify: `disclaimer.html`
- Modify: `faq.html`
- Modify: `404.html`

- [ ] **Step 1: Replace all old site identity references with the new brand**

Change page titles, headings, footer text, and metadata so they all match `Practical Tech Guide`.

- [ ] **Step 2: Tighten the disclaimer language so it sounds natural and specific**

Use a simple explanation that the site provides general informational and educational content, not professional advice.

Add a clear note that technology products, pricing, availability, and features can change quickly, so readers should verify current details on the official provider site before deciding.

- [ ] **Step 3: Make the FAQ and 404 pages useful instead of decorative**

The FAQ should answer common reader questions about updates, recommendations, and contact paths.

The 404 page should link to:

- Home
- Buying Guides
- Author
- Editorial Policy
- Contact

---

### Task 7: Rebuild sitemap and keep robots.txt simple

**Files:**
- Modify: `sitemap.xml`
- Modify: `robots.txt`
- Verify: `ads.txt`

- [ ] **Step 1: Rebuild `sitemap.xml` with only the pages that support the final site story**

Include:

- homepage
- buying-guide categories page
- about
- authors
- contact
- editorial policy
- privacy policy
- terms of service
- cookie policy
- disclaimer
- 404 page
- only the strongest matching articles

Exclude scattered or weak pages that do not support the new direction.

- [ ] **Step 2: Simplify `robots.txt` to a minimal crawl policy**

Use this exact content:

```txt
User-agent: *
Allow: /

Sitemap: https://aicoolgames.com/sitemap.xml
```

Remove extra comments and crawl-delay rules unless there is a specific reason to keep them.

- [ ] **Step 3: Confirm `ads.txt` still contains the existing publisher line**

Verify this line is still present and unchanged:

```txt
google.com, pub-8306112973766890, DIRECT, f08c47fec0942fa0
```

Do not replace it unless the publisher account itself changes.

---

### Task 8: Run a final quality pass for AdSense-facing signals

**Files:**
- All edited public pages

- [ ] **Step 1: Check for placeholder links and obvious broken markup**

Run:

```bash
python - <<'PY'
from pathlib import Path
for p in Path('.').glob('*.html'):
    text = p.read_text(encoding='utf-8', errors='ignore')
    if 'href="#"' in text or '�?' in text:
        print(p)
PY
```

Expected: no output in the final edited public pages.

- [ ] **Step 2: Check for leftover old-brand language**

Run:

```bash
python - <<'PY'
from pathlib import Path
terms = ['TechPulse', 'daily source for technology news', 'expert contributors', 'real team', '150+ published articles']
for p in Path('.').glob('*.html'):
    text = p.read_text(encoding='utf-8', errors='ignore')
    hits = [t for t in terms if t.lower() in text.lower()]
    if hits:
        print(p, hits)
PY
```

Expected: no hits in the edited public pages.

- [ ] **Step 3: Open the homepage locally and confirm the site reads as a real, modest editorial publication**

Check that the page:

- looks like a focused technology review site
- does not read like a generic news dump
- does not overclaim scale or authority
- has working navigation and no empty links

---

## Self-Review

- Spec coverage: homepage, categories, about, authors, contact, editorial policy, legal pages, sitemap, robots, ads.txt, and validation are all covered.
- Placeholder scan: no TBD/TODO placeholders remain.
- Scope check: this stays within one cohesive site-redesign plan.
- Consistency check: brand name, contact paths, and page roles are aligned with the new editorial direction.
