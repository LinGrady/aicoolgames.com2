# AdSense Site Restructure Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Rework Practical Tech Guide into a focused, credible technology buying-guide site for AdSense review.

**Architecture:** Keep static HTML and existing CSS. Rebuild public entry pages around buying decisions, add recent guides, and update sitemap links without touching `ads.txt`.

**Tech Stack:** Static HTML, existing `css/style.css`, XML sitemap, Git.

---

### Task 1: Rebuild Core Guide Pages

**Files:**
- Modify: `index.html`
- Modify: `categories.html`
- Modify: `about.html`
- Modify: `authors.html`
- Modify: `editorial-policy.html`
- Modify: `contact.html`

- [ ] Replace broad news framing with buyer decision tracks.
- [ ] Use one believable editor identity, Alex Morgan.
- [ ] Explain editorial independence, updates, corrections, and limitations.
- [ ] Remove weak public emphasis from generic future-trend articles.

### Task 2: Add Current Practical Guides

**Files:**
- Create: `article-budget-laptop-checklist-2026.html`
- Create: `article-ai-tool-privacy-checklist.html`
- Create: `article-home-wifi-troubleshooting-before-upgrade.html`

- [ ] Add three practical guides with specific selection criteria and internal links.
- [ ] Avoid hype, unverifiable claims, and fake testing language.

### Task 3: Update Discovery and Verify

**Files:**
- Modify: `sitemap.xml`

- [ ] Add new public guide URLs to `sitemap.xml` with `2026-06-22` lastmod.
- [ ] Verify no `ads.txt` changes.
- [ ] Run a local link check for missing internal HTML targets.
