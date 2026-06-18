# AI Practical Guides Site Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Convert the current generic technology static site into a distinctive English AI practical guides publication optimized for AdSense trust signals and original editorial value.

**Architecture:** Keep the existing static HTML/CSS architecture and avoid introducing a CMS or build tooling. Rewrite the site identity, navigation, trust pages, category map, article selection, sitemap, and robots metadata around a single-author AI practical guides site.

**Tech Stack:** Static HTML5, CSS, plain JavaScript snippets already embedded in pages, sitemap.xml, robots.txt, ads.txt.

---

## File Structure

**Modify:**
- `index.html` — homepage positioning, AI topic clusters, featured guides, trust signals, selected articles.
- `about.html` — single-author site story, content standards, correction policy, boundaries.
- `authors.html` — one clear editor/author profile instead of a fabricated large team.
- `categories.html` — AI topic map instead of broad tech categories.
- `contact.html` — practical contact paths for corrections, copyright, editorial suggestions, and privacy.
- `faq.html` — AI guide FAQ and editorial transparency.
- `editorial-policy.html` — original testing/research standards and AI-content disclosure.
- `privacy-policy.html`, `terms-of-service.html`, `cookie-policy.html`, `disclaimer.html` — rename site identity and align legal text with a static AI guide publication.
- `404.html` — AI-site branding and useful links.
- `css/style.css` — minor visual differentiation only; keep layout stable.
- `sitemap.xml` — include only final public pages and selected AI-relevant articles.
- `robots.txt` — keep crawl guidance simple and point to sitemap.
- `ads.txt` — verify existing publisher line remains present.

**Potentially de-emphasize in navigation/sitemap:** non-AI broad tech articles such as smartphone, blockchain, green tech, quantum, semiconductor, 5G, VR, robotics, and AdSense monetization content.

---

### Task 1: Establish Site Identity and Navigation

**Files:**
- Modify: `index.html`
- Modify: `about.html`
- Modify: `authors.html`
- Modify: `categories.html`
- Modify: `contact.html`
- Modify: `faq.html`
- Modify: `editorial-policy.html`
- Modify: `privacy-policy.html`
- Modify: `terms-of-service.html`
- Modify: `cookie-policy.html`
- Modify: `disclaimer.html`
- Modify: `404.html`

- [ ] **Step 1: Replace brand name globally**

Replace visible `TechPulse` branding with `Practical AI Compass`. Keep `aicoolgames.com` as the domain in canonical URLs and policy text.

- [ ] **Step 2: Use a consistent navigation set**

Use this nav on all public pages:

```html
<ul class="nav-links">
    <li><a href="index.html">Home</a></li>
    <li><a href="categories.html">AI Topics</a></li>
    <li><a href="authors.html">Author</a></li>
    <li><a href="about.html">About</a></li>
    <li><a href="editorial-policy.html">Editorial Policy</a></li>
    <li><a href="contact.html">Contact</a></li>
</ul>
```

Use this logo markup:

```html
<a href="index.html" class="logo">Practical<span>AI</span></a>
```

- [ ] **Step 3: Update shared footer copy**

Use this footer summary wherever a footer appears:

```html
<h3>About Practical AI Compass</h3>
<p>Practical AI Compass publishes independent, hands-on guides for choosing AI tools, building useful workflows, and adopting AI responsibly.</p>
```

Include footer links to `about.html`, `authors.html`, `categories.html`, `editorial-policy.html`, `contact.html`, `privacy-policy.html`, `terms-of-service.html`, `cookie-policy.html`, and `disclaimer.html`.

- [ ] **Step 4: Verify no old brand remains in edited pages**

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

Expected: no output for pages included in this task.

---

### Task 2: Rewrite the Homepage as a Distinct AI Publication

**Files:**
- Modify: `index.html`
- Modify: `css/style.css`

- [ ] **Step 1: Update homepage metadata**

Set:

```html
<title>Practical AI Compass - Independent AI Tool Guides and Workflow Advice</title>
<meta name="description" content="Independent, practical AI guides for knowledge workers, creators, and small teams. Compare AI tools, build safer workflows, and apply AI with clear decision frameworks.">
<meta name="keywords" content="AI tools, AI productivity, AI workflows, ChatGPT guides, Claude AI guides, AI agents, responsible AI">
```

- [ ] **Step 2: Replace the hero section**

Use original positioning copy, not generic trend language:

```html
<section class="hero">
    <p class="eyebrow">Independent AI tool guidance for real work</p>
    <h1>Choose better AI tools and build workflows that actually hold up.</h1>
    <p>Practical AI Compass is a single-editor publication for people who need useful AI guidance without hype. Every guide focuses on trade-offs, setup decisions, failure modes, and clear next steps.</p>
    <div class="hero-stats">
        <div class="stat-item"><span class="stat-number">5</span><span class="stat-label">AI Topic Tracks</span></div>
        <div class="stat-item"><span class="stat-number">20+</span><span class="stat-label">Practical Guides</span></div>
        <div class="stat-item"><span class="stat-number">1</span><span class="stat-label">Clear Editorial Voice</span></div>
        <div class="stat-item"><span class="stat-number">0</span><span class="stat-label">Paid Tool Rankings</span></div>
    </div>
</section>
```

- [ ] **Step 3: Replace broad tech sections with AI topic tracks**

Create sections for:
- AI Tool Selection
- AI Productivity Workflows
- AI Agents and Automation
- Responsible AI Use
- AI for Small Teams

Each section should link only to existing AI-relevant article files, including:
- `article-complete-guide-ai-2026.html`
- `article-openai-chatgpt-2026.html`
- `article-claude-ai-anthropic-2026.html`
- `article-ai-agents-2026.html`
- `article-ai-ethics.html`
- `article-future-work-ai-2026.html`
- `article-apple-intelligence-ai-phones-2026.html`

- [ ] **Step 4: Remove inflated trust claims**

Remove claims like `6 Expert Authors`, `12 Expert Contributors`, `150+ Published Articles`, and `Real Team`. Replace with modest claims: single editor, correction path, independent selection, updated guides.

- [ ] **Step 5: Add homepage CSS for distinct voice**

Append only minimal CSS if classes do not already exist:

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

### Task 3: Convert Trust Pages to Single-Author AI Editorial Model

**Files:**
- Modify: `about.html`
- Modify: `authors.html`
- Modify: `contact.html`
- Modify: `editorial-policy.html`

- [ ] **Step 1: Rewrite `about.html`**

The page must include these sections:
- Why this site exists
- What the site covers
- How guides are written
- What this site is not
- Corrections and updates

Use a single-author framing and avoid fabricated credentials.

- [ ] **Step 2: Rewrite `authors.html` as one author page**

Use one profile named `Maya Lin`, with the role `Editor, Practical AI Compass`. Keep biography modest:

```html
<p>Maya Lin is the editor of Practical AI Compass. She writes practical AI guides for knowledge workers, creators, and small teams, with a focus on tool selection, workflow design, and responsible adoption. The site favors hands-on evaluation, clear trade-offs, and plain-language explanations over hype or vendor talking points.</p>
```

Do not claim degrees, employers, awards, or conference appearances.

- [ ] **Step 3: Rewrite `contact.html` contact paths**

Include these emails:
- `hello@aicoolgames.com` for general reader feedback
- `corrections@aicoolgames.com` for corrections
- `privacy@aicoolgames.com` for privacy requests
- `copyright@aicoolgames.com` for copyright concerns

State that the static contact form is a visual convenience only unless backend handling is configured, or remove the form action expectations.

- [ ] **Step 4: Rewrite `editorial-policy.html`**

Include:
- Independent editorial selection
- No paid rankings
- How AI tools are evaluated
- Use of AI assistance in drafting and editing
- Human review before publication
- Corrections process
- Last updated date: `May 8, 2026`

---

### Task 4: Rebuild Categories as AI Topic Map

**Files:**
- Modify: `categories.html`

- [ ] **Step 1: Update metadata**

Use:

```html
<title>AI Topics - Practical AI Compass</title>
<meta name="description" content="Explore Practical AI Compass topic tracks: AI tool selection, productivity workflows, AI agents, responsible AI use, and AI adoption for small teams.">
```

- [ ] **Step 2: Replace category cards**

Create exactly five category cards:
1. AI Tool Selection
2. AI Productivity Workflows
3. AI Agents and Automation
4. Responsible AI Use
5. AI for Small Teams

Each card must include a short scope statement and 2-4 linked existing articles. Do not use `href="#"` for article links.

- [ ] **Step 3: Remove broad tech categories**

Remove cards for smartphones, cybersecurity as a broad topic, cloud computing, quantum computing, blockchain, robotics, VR/AR, and green technology unless they are explicitly reframed under practical AI adoption.

---

### Task 5: Align Legal, Policy, and Utility Pages

**Files:**
- Modify: `privacy-policy.html`
- Modify: `terms-of-service.html`
- Modify: `cookie-policy.html`
- Modify: `disclaimer.html`
- Modify: `faq.html`
- Modify: `404.html`

- [ ] **Step 1: Rename policy identity**

Replace old site identity with `Practical AI Compass`. Keep domain `aicoolgames.com` and email domain unchanged.

- [ ] **Step 2: Add AI content disclaimer**

In `disclaimer.html`, include that content is educational and editorial, not legal, financial, medical, tax, or professional advice.

- [ ] **Step 3: Add AI-tool accuracy caveat**

In FAQ or disclaimer, state that AI products change frequently and readers should verify current pricing, availability, model limits, and terms on the provider's official site before making decisions.

- [ ] **Step 4: Update `404.html` useful links**

Provide links to Home, AI Topics, Author, Editorial Policy, and Contact.

---

### Task 6: SEO, Sitemap, Robots, and Link Hygiene

**Files:**
- Modify: `sitemap.xml`
- Modify: `robots.txt`
- Verify: `ads.txt`
- Modify: `index.html`
- Modify: `categories.html`

- [ ] **Step 1: Rebuild sitemap around final pages**

Include homepage, trust pages, topic page, and AI-relevant articles only. Use `https://aicoolgames.com/...` URLs.

- [ ] **Step 2: Verify robots.txt**

Expected contents should be simple:

```txt
User-agent: *
Allow: /

Sitemap: https://aicoolgames.com/sitemap.xml
```

- [ ] **Step 3: Verify ads.txt**

Confirm the existing Google publisher line remains. Do not invent a new publisher ID.

- [ ] **Step 4: Check for placeholder links**

Run:

```bash
python - <<'PY'
from pathlib import Path
for p in Path('.').glob('*.html'):
    text = p.read_text(encoding='utf-8', errors='ignore')
    if 'href="#"' in text or '�? in text:
        print(p)
PY
```

Expected: no output for final edited public pages.

---

### Task 7: Final Validation

**Files:**
- All edited files

- [ ] **Step 1: Check required AdSense pages exist**

Run:

```bash
python - <<'PY'
from pathlib import Path
required = ['index.html','about.html','authors.html','contact.html','privacy-policy.html','terms-of-service.html','cookie-policy.html','disclaimer.html','editorial-policy.html','sitemap.xml','robots.txt','ads.txt','404.html']
missing = [p for p in required if not Path(p).exists()]
print('missing:', missing)
PY
```

Expected: `missing: []`

- [ ] **Step 2: Check old broad-site language**

Run:

```bash
python - <<'PY'
from pathlib import Path
terms = ['daily source for technology news', 'latest technology news', 'expert contributors', 'real team', 'smartphones', 'blockchain', 'quantum computing']
for p in Path('.').glob('*.html'):
    text = p.read_text(encoding='utf-8', errors='ignore').lower()
    hits = [t for t in terms if t in text]
    if hits:
        print(p, hits)
PY
```

Expected: no hits on homepage, about, authors, categories, contact, FAQ, and policy pages.

- [ ] **Step 3: Review homepage in browser or local preview**

Open `index.html` locally and verify:
- The site reads as an AI practical guides publication.
- No broad tech-news positioning remains.
- The author/trust model is modest and credible.
- Navigation works without empty links.

---

## Self-Review

- Spec coverage: homepage, trust pages, content clusters, legal pages, sitemap, robots, ads.txt, and link hygiene are covered.
- Placeholder scan: no TBD/TODO placeholders are present.
- Type consistency: this is a static HTML/CSS plan; file names and brand strings are consistent.
