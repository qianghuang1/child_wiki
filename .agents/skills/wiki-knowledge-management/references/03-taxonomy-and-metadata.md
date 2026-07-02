---
title: Taxonomy & Metadata
read_when: Building/restructuring categories, standardizing tags/terms, designing page metadata, adding facets, or relating concepts.
key_rules:
  - One canonical term per concept; map variants as search synonyms only.
  - Categories mutually exclusive, ≤10 per level, ≤3–4 deep; validate with users.
  - Start metadata lean; use controlled values for any field used to filter/report.
---

# Taxonomy & Metadata

How to classify, tag, describe, and relate wiki content so it stays consistent and findable.

## Taxonomy design

A taxonomy is the hierarchical classification backing navigation. Four steps:

1. **Discover** — interview content owners; run free-listing; analyze search logs; inventory and cluster existing pages.
2. **Define top-level** — 5–10 concrete, recognizable categories; test labels with users; each internally coherent.
3. **Build hierarchy** — ≤3–4 levels; subcategories are more specific versions of the parent; siblings mutually exclusive where possible.
4. **Validate** — closed card sort (do pages land where expected?) and tree testing (can users find content?); adjust where users get stuck.

| Rule | Why |
|---|---|
| One canonical name per concept | Prevents synonym drift |
| Mutually exclusive categories | Reduces ambiguous placement |
| < 10 items per level | Prevents overwhelm |
| ≤ 4 levels deep | Keeps navigation tractable |
| User vocabulary for labels | Improves discoverability |

**Size management:** split categories that exceed 15–20 items; merge heavily overlapping ones; treat "Misc/Other" buckets as a signal of missing categories. **Strict vs. polyhierarchy:** default strict (one home); allow multiple parents (≤3) only when a page genuinely fits several topics — not to work around unclear boundaries.

## Controlled vocabulary

A governed term set for consistent labeling. Without it, "Customer/Client/User/End User" fragment the same concept and search misses pages.

Components:
- **Preferred term** — one canonical label per concept, in the audience's words; documented.
- **Variants (synonyms)** — abbreviations, alternate spellings, misspellings; map to the preferred term and use to power **search synonym expansion**. Don't use variants as actual metadata values.
- **Relationships** — Broader (BT), Narrower (NT), Related (RT).
- **Scope notes** — short clarification of meaning/use for ambiguous or look-alike terms. *Example:* "Security Policy — use for access controls and authentication. NOT data privacy/GDPR (see Privacy Policy)."

Build it: discover terms (pages, search logs, SMEs, free-listing) → pick preferred terms (user language; check industry thesauri) → map variants (configure search synonyms; add redirects) → define BT/NT/RT (reciprocal) → govern (named owner; quarterly review using search logs). Use **authority files** for canonical entity names (people/roles, products, teams, locations) when inconsistency breaks navigation or search.

## Semantic relationships (thesaurus & ontology)

| Relationship | Symbol | Example | Use |
|---|---|---|---|
| Broader / Narrower | BT / NT | "Database" BT "Software"; "PostgreSQL" NT "Database" | Category trees, breadcrumbs, hierarchical filtering |
| Related | RT | "Authentication" RT "Authorization" | "See Also" links (limit 3–7) |
| Equivalence | USE / UF | "User" USE "End User" | Synonyms, query expansion, redirects |

BT/NT must be reciprocal. A **thesaurus** combines all types — use for large/specialized domains where teams use different terms and search needs synonym expansion; skip it for small (<100 pages), stable-terminology wikis. Distinguish an **indexing thesaurus** (consistent tagging) from a **searching thesaurus** (query-time synonym expansion); large wikis often need both. An **ontology** (formal typed entities/relationships, machine-readable) is rarely needed — controlled vocabulary + basic thesaurus relationships suffice for most wikis.

Implementation tiers: **Simple** = preferred terms + variants in a shared page + tags. **Intermediate** = BT/NT topic hierarchy + RT links + query-time synonym expansion. **Advanced** = full thesaurus in a taxonomy tool + structured entities + auto-tagging.

## Faceted classification

Organize content along multiple **independent, orthogonal dimensions** so a page is discoverable from many angles without duplication.

| Facet | Example values |
|---|---|
| Topic | Engineering, Design, Finance, HR |
| Audience | All Staff, Engineers, Managers |
| Document Type | How-To, Policy, Reference, Template |
| Status | Draft, Active, Archived |
| Owner Team | Platform, Product, Operations |

**Use when** pages need multi-perspective discovery, content has orthogonal attributes, or a single tree forces awkward placement. **Don't use when** a simple hierarchy suffices, the wiki is small (<50 pages), or the team can't maintain consistent values.

Good facets are **independent, exhaustive, mutually-exclusive in values, manageable (5–15 values), and useful for filtering**. Start with 3–4 facets; add more only when needed. Back facets with controlled-vocabulary **metadata fields**, surface them as filter panels and "browse by X" pages, and govern approved values quarterly. Most large wikis use **both**: hierarchy for primary browse + facets for filtering.

## Metadata schema

Structured data about each page that makes the wiki searchable, filterable, and governable.

| Type | Purpose | Example fields |
|---|---|---|
| **Descriptive** | Find & understand | Title, Summary, Keywords/Tags, Topic, Audience, Document Type, Related Pages |
| **Administrative** | Govern & lifecycle | Owner, Author, Created, Last Reviewed, Status, Review Cadence, Expiry |
| **Structural** | Location & relationships | Parent Page, Child Pages, Breadcrumb Path |

Principles:
- **Start lean.** Minimum viable: Title, Owner, Status, Last Reviewed, Topic. Add fields only on proven need.
- **Required vs. optional** — keep required to 3–5 fields.
- **Controlled values** for Topic/Audience/Status/Type — not free text.
- **One field, one purpose;** don't duplicate (e.g., Topic vs. Category).
- **Don't over-engineer** — a field nobody fills is noise; build metadata into the creation template.

Per page type: Reference → Topic, Audience, Last Reviewed, Owner · How-To → Topic, Audience, Difficulty, Status · Policy → Owner, Effective/Review Date, Status · Meeting Notes → Date, Attendees, Decision Tags · Project → Status, Owner, Team, Related Pages.

**Quality signals (bad):** no owner; inconsistent/misspelled tags; blank or all-"Active" status; years-old review dates. Remedy: quarterly metadata audit sorted by last-reviewed date.

## Anti-patterns

| Anti-pattern | Fix |
|---|---|
| Taxonomy mirrors the org chart | Reorganize by topic/task |
| Abstract top-level categories | Concrete labels users recognize |
| Categories with 1–2 pages | Merge up or remove |
| Many synonyms treated as preferred terms | Pick one; map rest as variants |
| Vocabulary defined by IT, never updated | Co-design with users; quarterly review |
| Variants not in search | Configure synonym expansion |
| 20+ metadata fields | Reduce to 5–8 core; require Title/Owner/Status |
| Free-text Topic field | Controlled dropdown |
| BT/NT not reciprocal | Audit all links for consistency |
