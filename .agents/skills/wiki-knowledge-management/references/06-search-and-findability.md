---
title: Search & Findability
read_when: Users can't find existing content, search returns poor/zero results, or you want to use search logs to improve.
key_rules:
  - Fix structure before optimizing search; search complements navigation.
  - Every important page needs multiple access paths (browse AND search).
  - Synonym expansion from real logs is the highest-ROI search fix.
---

# Search & Findability

Findability is the degree to which content can be located, discovered, and returned to. Search complements navigation — never a substitute for structure.

## The findability test

For any important page: 1) Can users **locate** it (nav, search, link)? 2) **Discover** it without knowing it exists (browse, related links)? 3) **Return** to it (stable URL/title)? If "no", fix structure.

## Multiple access paths

| Path | Description |
|---|---|
| Hierarchy browse | Broad → specific categories |
| Search | Query-based retrieval |
| Faceted filters | Filter by topic/type/audience |
| Related links | Discover adjacent content in-page |
| Topic index / A–Z | Lookup by known term |
| Hub pages | Curated entry points |

Important pages should be reachable via **≥ 3** of these.

## Findability heuristics

- **2-click rule** — key pages reachable in 2–3 clicks from home.
- **Progressive disclosure** — overviews first, detail on demand.
- **Recognition over recall** — consistent labels, breadcrumbs, obvious current location.
- **Information scent** — every label/title/link lets users predict the destination.

## When users search vs. browse

| Behavior | Implication |
|---|---|
| Known-item ("I know what I want") | Fast, precise search; stable titles; exact metadata match |
| Exploratory ("not sure what I need") | Synonym expansion; related results; tolerate vague queries |
| Refinding ("saw it before") | Consistent URLs/titles; search history |
| Research ("everything on a topic") | Faceted filters; comprehensive cross-linking |

## Improving search quality

A good search returns relevant results for common queries, handles synonyms, surfaces important pages, shows useful snippets, handles zero results gracefully, and supports filtering.

- **Index weighting** — titles highest, then headings, then body; metadata powers filters.
- **Synonym expansion** — map abbreviations/synonyms/spellings to canonical terms ("2FA"→"Two-Factor Authentication"). *Highest bang-for-buck.*
- **Boost** Active over Archived/Draft, recently-reviewed over stale, popular pages.
- **Curated "Best Bets"** — manually pin the canonical page for the most common/ambiguous queries.

Each result should show title (linked), one-line excerpt with matching context, metadata chips (Topic/Status/Owner), and last-reviewed date.

### Diagnosing search problems

| Symptom | Likely cause | Fix |
|---|---|---|
| Can't find an existing page | Title ≠ search terms | Add synonyms; rename |
| Zero results for common query | Missing content or synonyms | Create page; add synonym |
| Too many irrelevant results | Over-broad synonyms; poor ranking | Tighten synonyms; boost canonical |
| Users search instead of browse | Key pages buried in nav | Promote to nav; add to hubs |
| Find once, can't return | Unstable title/URL | Stabilize URL; redirect old |
| Search returns duplicates | Duplicate pages on a topic | Merge/remove; boost canonical |

## Search analytics

Search logs are the most honest findability signal — what users actually need.

**Primary metrics:** top queries · zero-result queries · click-through rate per query · failed searches (results shown, no click) · long sessions (users working too hard) · short sessions (found fast or gave up). **Secondary:** page views, category-page bounce rate, entrance pages, search-volume trends.

**Monthly review (~1 hr):** export top ~50 queries → fix zero-result queries (create pages/add synonyms) → check top queries land on the right page → check failed searches → identify vocabulary gaps → update synonym mappings → report findings with recommended actions.

| Finding | Action |
|---|---|
| Search X but browse to Y | Rename/cross-link; add X to Y's title/metadata |
| Zero results for common term | Create page OR add synonym |
| High volume, low click-through | Improve title and description |
| Repeated search after visiting a page | Page doesn't answer the question; improve content |
| Search volume for a topic rising | Emerging content gap |

**Vocabulary mining:** logs reveal real user words (acronyms, jargon, misspellings, synonyms) — add unrecognized terms as synonyms and update titles. **Privacy:** analyze in aggregate only; never track individuals. **Analytics tell *what*, not *why*** — use tree testing/usability sessions to diagnose, fix structure, then re-measure.

## Findability anti-patterns

| Anti-pattern | Why it fails |
|---|---|
| "They'll search for it" | Search needs good titles + indexing |
| One deep path per page | Different users start from different places |
| Navigation built for authors | Readers don't think like authors |
| Add content without fixing structure | More content makes a bad structure worse |
| Rely on bookmarks | Users forget; bookmarks break; new users lack them |
