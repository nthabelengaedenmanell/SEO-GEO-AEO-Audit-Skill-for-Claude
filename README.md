# SearchLayer — SEO, GEO & AEO Audit Skill for Claude

> Audit any website for traditional SEO, AI search visibility, and answer engine readiness — and get a downloadable agency-quality report in minutes.

Most SEO tools only look at one layer of search visibility. SearchLayer covers all three. Point Claude at any URL and it will crawl your site, score it across SEO, GEO, and AEO, analyze it signal by signal, and deliver a polished audit report — complete with color-coded findings, a priority recommendations matrix, and a "what's working well" section — as a downloadable Word doc and PDF.

No API keys. No integrations. No separate dashboard. Just give Claude a URL and ask it to audit your site.

---

## Table of contents

- [What it audits](#what-it-audits)
- [Why three dimensions](#why-three-dimensions)
- [How to use it](#how-to-use-it)
- [Audit modes](#audit-modes)
- [What you get](#what-you-get)
- [Report structure](#report-structure)
- [Scoring rubric](#scoring-rubric)
- [Signal reference](#signal-reference)
- [What it can and can't assess](#what-it-can-and-cant-assess)
- [Installation](#installation)
- [Repository structure](#repository-structure)
- [Version history](#version-history)
- [About](#about)

---

## What it audits

### SEO — Traditional Search Engine Optimization

SEO is the foundation. It covers everything that determines how well Google and Bing can discover, understand, and rank your pages. SearchLayer analyzes:

- **Title tags** — presence, length (optimal: 50–60 characters), keyword inclusion, and whether they're duplicated across pages
- **Meta descriptions** — presence, length (optimal: 150–160 characters), and whether they contain a call to action
- **Heading hierarchy** — is there a single H1? Are H2/H3s logical, keyword-relevant, and free of stuffing?
- **URL structure** — clean and readable? Contains keywords? Avoids stop words and excessive parameters?
- **Canonical tags** — present and correctly self-referencing?
- **Robots meta tags** — indexable? Any accidental noindex directives?
- **Viewport and mobile meta** — present for mobile friendliness?
- **Image alt text** — descriptive and keyword-relevant?
- **Internal linking** — are key pages linked to from other pages? Is anchor text descriptive?
- **Open Graph and Twitter Card tags** — og:title, og:description, og:image present? Appropriate for social sharing?
- **Content quality** — word count, keyword signals, semantic coverage, content freshness signals, and readability
- **Structured data** — JSON-LD and microdata schema types detected (Organization, LocalBusiness, Article, Product, FAQ, HowTo, BreadcrumbList, etc.) and whether the markup appears syntactically valid

---

### GEO — Generative Engine Optimization

GEO is the emerging discipline of optimizing for AI-powered search engines — Perplexity, ChatGPT Search, Google AI Overviews, and Gemini. These engines don't just rank pages; they synthesize answers from multiple sources and cite the ones they trust. Getting cited is the new getting ranked.

AI engines reward authority, clarity, and factual richness. They tend to favour pages that clearly establish who is behind the content, make specific and verifiable claims, and use clean, crawlable HTML that doesn't rely entirely on JavaScript to render.

SearchLayer analyzes GEO across three sub-dimensions:

**E-E-A-T (Experience, Expertise, Authoritativeness, Trustworthiness)**
- Named authors with visible credentials
- About page quality — does it explain who runs the site, their background, and qualifications?
- Contact information accessibility (phone, address, email)
- Trust signals — testimonials, awards, certifications, press mentions
- Organization schema — does the site declare its brand entity clearly with name, logo, URL, and social profiles?

**Content for AI Synthesis**
- Factual density — specific facts, statistics, and data that AI engines can cite
- Clear claims — is the core argument stated plainly at the top of the page?
- Source citations — does the content reference external authoritative sources?
- Comprehensiveness — does the content fully address its topic, or leave key questions unanswered?
- Entity clarity — is the brand, person, or place named consistently throughout (helps AI engines recognize the entity)?
- Originality signals — is there a clear point of view, original data, or unique perspective that AI engines would prefer to cite over generic content?

**Technical GEO**
- Structured data depth — beyond basic schema, does the page use richer types like Author, Dataset, ClaimReview, or SpeakableSpecification?
- HTTPS and security — is the site served over HTTPS? (a trust signal for AI engines)
- Clean crawlability — no robots.txt blocks or excessive JavaScript-only rendering that might prevent AI crawlers from reading the page
- Brand entity links — social profile links pointing from the site, which strengthen the entity graph

---

### AEO — Answer Engine Optimization

AEO is about winning the zero-click real estate: featured snippets, People Also Ask boxes, and voice search results. These placements require content that's structured so a search engine or AI assistant can extract a direct, concise answer without needing to read the whole page.

SearchLayer analyzes AEO across three sub-dimensions:

**Featured Snippet Eligibility**
- Direct answer paragraphs — is the key question answered in a concise paragraph (40–60 words) directly below a question-phrased heading?
- Definition patterns — does the page define its core topic with a clear "X is..." sentence?
- List content — numbered steps or bulleted lists that could become list snippets
- Table content — comparison tables that could become table snippets

**Structured Answer Formats**
- FAQ schema — is FAQ schema present and correctly structured?
- HowTo schema — is step-by-step process content marked up with HowTo schema?
- Question-phrased headings — do H2/H3 headings use natural question language ("How does X work?", "What is Y?")?
- Speakable schema — is SpeakableSpecification markup present for voice-friendly sections?

**Voice Search Readiness**
- Conversational language — does the content use natural, conversational phrasing rather than stiff, keyword-stuffed prose?
- Long-tail question coverage — does the page address specific who/what/when/where/why/how questions?
- Local signals (where applicable) — NAP data (Name, Address, Phone), local schema, and location mentions

---

## Why three dimensions

Search has fractured. Optimizing for Google alone is no longer enough — a growing share of search queries are answered by AI assistants that never send users to a website at all. If your site isn't structured to be cited by those engines, you're invisible to them regardless of your Google ranking.

The three dimensions map to three different "judges" your content is evaluated by:

| Dimension | Optimizes for | Primary goal |
|-----------|--------------|-------------|
| SEO | Google, Bing | Rank on the results page |
| GEO | Perplexity, ChatGPT Search, AI Overviews, Gemini | Be cited in AI-generated answers |
| AEO | Featured snippets, PAA boxes, voice assistants | Be the extracted answer |

These aren't mutually exclusive — a well-optimized site tends to score well across all three. But the signals that matter differ enough that they need to be analyzed separately. A site can have strong traditional SEO and near-zero GEO readiness. A site can rank well organically and still never win a featured snippet because its content isn't structured for direct extraction.

SearchLayer scores each dimension independently so you know exactly where your gaps are.

---

## How to use it

Once installed, give Claude a URL and describe what you need. You don't have to use any specific phrasing — Claude will recognize the intent and trigger the skill automatically.

**Example prompts that work:**

```
"Audit burningstickcreative.com for SEO"
"Why isn't my site ranking? Check example.com"
"Run a full SEO, GEO, and AEO audit on my website: example.com"
"Is my site showing up in AI search? Audit example.com"
"Check the SEO health of freewebsiteguy.co.za"
"Do a quick audit of mybusiness.com — just the top issues"
"Audit this site and tell me what to fix first: example.com"
```

Claude will confirm whether you want a Quick or Full audit, then begin crawling. You'll see it working in real time — fetching pages, analyzing signals, building the report.

---

## Audit modes

### Quick Audit — 1 to 2 minutes

Crawls the homepage plus up to 6 high-signal pages, typically: About, Services, Blog index, a recent blog post, Contact, and any FAQ page. Surfaces the top priority issues and scores across all three dimensions.

Best for:
- A fast health check before a client meeting
- A first pass before commissioning a full audit
- Sites you've recently updated and want to spot-check
- Getting a score benchmark to track over time

### Full Audit — 5 to 10 minutes

No page cap. Crawls every meaningful page on the site, discovered via the sitemap, navigation menus, footer links, and internal links found during crawling. This includes individual blog posts and service pages, not just index pages. Pages are crawled in priority order:

1. About / Team / Our Story
2. Services / What We Do / Solutions
3. Case Studies / Portfolio / Work
4. Blog / Resources / Insights (index + individual posts)
5. Contact / Location
6. FAQ / Help
7. Individual service or product pages
8. All remaining content-rich pages discovered via sitemap or internal links

The only pages skipped are genuinely low-signal: Privacy Policy, Terms of Service, login and account pages, thank-you and confirmation pages, and paginated archive pages beyond page 2.

The more pages crawled, the more accurate and specific the findings. A Full Audit is the right choice when you need a complete picture — before a site redesign, as part of new client onboarding, or when organic traffic has dropped and you need to understand why.

Full Audits also include a glossary of SEO, GEO, and AEO terms, useful for sharing reports with clients who may not be familiar with the terminology.

---

## What you get

### In-chat summary

A brief, scannable scorecard delivered directly in the conversation while the report generates:

```
🔍 example.com — Full SEO/GEO/AEO Audit
Pages reviewed: 14   Audit date: 2025-06-01

Dimension   Score   Status
SEO         7/10    On Track
GEO         4/10    Needs Work
AEO         5/10    Needs Work

Top 3 priorities:
1. Add author schema and named author bylines to all blog posts (GEO)
2. Restructure service page headings to use question format (AEO)
3. Meta descriptions are missing on 6 of 14 pages (SEO)

Biggest strength: Strong heading hierarchy and clean URL structure throughout.

Full findings and recommendations are in the report below.
```

### Downloadable report (Word + PDF)

A premium audit document generated automatically after every audit — no extra prompt needed. Both formats are available for download immediately after the audit completes.

The report uses a structured design system with a navy and blue color palette, color-coded score cells (green for strong, amber for on track, red for needs work), alternating table row shading, and clear typographic hierarchy. It's built to be handed directly to a client or stakeholder without modification.

Every finding references something actually observed during the crawl — specific page URLs, actual title tag text, real schema types found or missing. There's no boilerplate. If a signal is good, it says so. If something is missing, it names which page and why it matters.

---

## Report structure

Every report is built in the same order:

| Section | Contents |
|---------|----------|
| Cover page | Domain, audit type, color-coded scores at a glance |
| Executive summary | Site-specific 3–5 sentence overview, scores table with key takeaways per dimension |
| Pages audited | Every URL crawled, with page type and key notes |
| SEO analysis | Signal-by-signal findings across Technical On-Page, Content Quality, and Structured Data |
| GEO analysis | Signal-by-signal findings across E-E-A-T, Content for AI Synthesis, and Technical GEO |
| AEO analysis | Signal-by-signal findings across Featured Snippet Eligibility, Structured Answer Formats, and Voice Search Readiness |
| Priority recommendations | Every issue ranked Critical / High / Medium / Quick Win, with effort and impact ratings |
| What's working well | Genuine strengths with specific evidence from the crawl — not filler |
| Glossary | Plain-English definitions of SEO, GEO, and AEO (Full Audit only) |

The analysis sections use a three-column Signal / Finding / Status table format throughout, with status cells color-coded green (Good), amber (Needs Attention), or red (Missing). The priority recommendations matrix uses a five-column format: Priority / Issue / Dimension / Effort / Impact, with priority cells color-coded from Critical (red) through Quick Win (green).

---

## Scoring rubric

Each of the three dimensions is scored independently on a 1–10 scale:

| Score | Rating | What it means |
|-------|--------|---------------|
| 1–3 | Critical | Serious issues — site is likely penalized or invisible in this dimension |
| 4–5 | Below average | Significant missed opportunities — foundational work needed |
| 6–7 | Decent | A working foundation exists — specific targeted improvements needed |
| 8–9 | Strong | Well-optimized — minor refinements available |
| 10 | Exemplary | Model implementation — holds up as a best-practice example |

Scores are calibrated to be honest. If a site is genuinely in good shape, the report says so. Problems aren't manufactured to make the audit look more thorough. If a site has serious issues, the report communicates urgency without being alarmist.

---

## Signal reference

### SEO signals

| Signal | What's checked |
|--------|---------------|
| Title tag | Present, 50–60 chars, contains primary keyword, not duplicated across site |
| Meta description | Present, 150–160 chars, contains a call to action |
| H1 | Present, singular, keyword-relevant |
| H2/H3 hierarchy | Logical structure, no keyword stuffing |
| URL structure | Clean, keyword-containing, no excessive parameters |
| Canonical tag | Present, self-referencing correctly |
| Robots meta | Indexable, no accidental noindex directives |
| Viewport meta | Present for mobile friendliness |
| Image alt text | Descriptive and keyword-relevant |
| Internal links | Present with descriptive anchor text |
| Open Graph | og:title, og:description, og:image all present |
| Twitter Card | Configured for social sharing |
| Word count | 500+ words for standard pages, 1500+ for pillar content |
| Schema markup | JSON-LD or microdata present, schema types identified |
| Schema validity | Markup appears syntactically correct and complete |

### GEO signals

| Signal | What's checked |
|--------|---------------|
| Author information | Named authors with visible credentials |
| About page | Explains who runs the site, their background and qualifications |
| Contact information | Phone, address, email accessible |
| Trust signals | Testimonials, awards, certifications, press mentions |
| Organization schema | Name, logo, URL, social profiles declared |
| Factual density | Specific facts, stats, or data present and citable |
| Clear claims | Core value proposition stated plainly at the top of the page |
| Source citations | References to external authoritative sources |
| Comprehensiveness | Topic fully addressed, key questions not left unanswered |
| Entity clarity | Brand/person/place named consistently throughout |
| Originality signals | Unique point of view, original data, or distinct perspective |
| Structured data depth | Author, Dataset, ClaimReview, SpeakableSpecification types used |
| HTTPS | Site served securely over HTTPS |
| Clean crawlability | No robots.txt blocks, not JS-only rendered |
| Brand entity links | Social profiles linked from the site |

### AEO signals

| Signal | What's checked |
|--------|---------------|
| Direct answer paragraphs | 40–60 word answer directly below a question-phrased heading |
| Definition patterns | Clear "X is..." sentences for core topics |
| List content | Numbered steps or bullets eligible for list snippets |
| Table content | Comparison tables eligible for table snippets |
| FAQ schema | Present and correctly structured |
| HowTo schema | Step-by-step content marked up with HowTo |
| Question-phrased headings | H2/H3 use natural question language |
| Speakable schema | SpeakableSpecification markup present |
| Conversational language | Natural, non-keyword-stuffed phrasing throughout |
| Long-tail question coverage | Who/what/when/where/why/how questions addressed |
| Local signals | NAP data, local schema, location mentions (where applicable) |

---

## What it can and can't assess

SearchLayer works by fetching and analyzing your site's HTML — the same way a search engine crawler reads a page. This gives it access to everything in the page source: meta tags, schema markup, headings, body content, internal links, robots directives, and more.

Some signals require dedicated external tools and are outside what an HTML-based audit can assess. Where these gaps are relevant, the report names the right tool to use rather than guessing.

| Signal | Why it's out of scope | Recommended tool |
|--------|----------------------|-----------------|
| Core Web Vitals | Requires browser rendering and performance measurement | Google PageSpeed Insights |
| Actual page speed | Server response times vary and can't be measured via fetch | Google PageSpeed Insights |
| Mobile rendering | Requires a real browser viewport | Google Search Console |
| JavaScript-rendered content | Fetch reads raw HTML, not JS-executed DOM | Screaming Frog with JS rendering |
| Backlink profile | External link data requires index access | Ahrefs, Semrush, or Moz |
| Domain authority | Proprietary third-party metric | Moz DA or Ahrefs DR |
| Keyword rankings | Requires live SERP data | Google Search Console, Semrush |
| Index coverage | Requires Search Console access | Google Search Console |

---

## Installation

SearchLayer is distributed as a ZIP archive for use with Claude's Skills feature.

### Step-by-step

1. Download the ZIP from this repository — click **Code → Download ZIP** on GitHub
2. Open [claude.ai](https://claude.ai) in your browser, or open the Claude desktop app
3. Click your profile icon and go to **Customize**
4. Select **Skills** from the left menu
5. Click the **+** icon
6. Upload the ZIP file — no unzipping required

The skill installs immediately and stays active across sessions. You'll know it's working when Claude automatically asks you to choose between a Quick or Full audit after you provide a URL and ask about search performance.

### Compatibility

| Platform | Supported |
|----------|-----------|
| Claude.ai (web) | ✅ |
| Claude.ai (mobile) | ✅ |
| Claude desktop app (Cowork) | ✅ |
| Claude API | ✅ — pass SKILL.md content as a system prompt |

### Updating

To update to a newer version, delete the existing skill from the Skills menu and re-upload the new ZIP. Your previous audit reports are unaffected.

---

## Repository structure

```
SearchLayer/
├── SKILL.md        ← Full audit instructions (Claude reads this at runtime)
└── README.md       ← This file
```

The `SKILL.md` file is the source of truth. It contains the complete audit methodology, crawl strategy, signal checklist, scoring rubric, report design specification, and output instructions that Claude follows when running an audit.

If you want to customise the skill's behaviour — for example, to change the report branding, adjust the crawl depth, add custom signals, or modify the output format — edit `SKILL.md` directly. Changes take effect immediately the next time the skill is used.

---

## Version history

### 1.1.0 — Current
- Renamed to SearchLayer
- README rewritten with full documentation, signal reference tables, compatibility matrix, and detailed section descriptions
- Quick Audit page limit corrected to 6 pages (was incorrectly documented as 15 in v1.0.0)
- Glossary scoped to Full Audit only; plain-English dimension explainers now present in all audit types
- Attribution updated to Aeden Manell

### 1.0.0 — Initial release
- Quick and Full audit modes
- Multi-page site crawl (up to 6 pages for Quick, unlimited for Full)
- SEO, GEO, and AEO scoring with priority recommendations matrix
- Downloadable audit report as Word (.docx) and PDF

---

## About

Built by Aeden Manell. Designed to produce audit reports good enough to hand directly to a client.

**Why this exists:** Most SEO audits are either too shallow (a score out of 100 with generic tips) or too expensive (agency retainers that price out small businesses). SearchLayer was built to close that gap — a genuinely thorough, signal-by-signal audit that anyone can run for free, with output that holds up to professional scrutiny.

If you find a bug, notice a signal that should be added, or want to suggest an improvement, open an issue or submit a pull request.
