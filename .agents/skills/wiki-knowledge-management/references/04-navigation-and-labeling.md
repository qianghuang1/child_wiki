---
title: Navigation & Labeling
read_when: Designing/fixing menus, breadcrumbs, hub pages, cross-links, or page/menu/category labels that are vague or inconsistent.
key_rules:
  - Labels must be clear, specific, consistent, in user vocabulary, and self-sufficient.
  - One term per concept everywhere; every page reachable in ≤3 clicks.
  - Provide global + local + contextual navigation; make current location obvious.
---

# Navigation & Labeling

Labels are the single biggest driver of findability; navigation makes the architecture usable.

## What makes a good label

| Quality | Meaning | Example |
|---|---|---|
| Clear | User knows what they'll find | "Setting Up Two-Factor Authentication" (not "Auth Docs") |
| Specific | Distinguishes from other pages | "PostgreSQL Backup Guide" (not "Database Guide") |
| Consistent | Same concept = same label | Not "User" here, "Customer" there |
| User vocabulary | Words the audience uses | No internal acronyms/codenames |
| Scannable | Evaluable at a glance | Front-load the key word |

Apply at every level — page titles (descriptive/specific), section headings (action/topic), nav items (1–3 distinct words), tags (controlled vocabulary), link text (names the destination, never "here").

## Labeling principles

- **One term per concept** everywhere (use the controlled vocabulary).
- **Reflect user language** — use words users would search; test by asking "what do you expect behind this link?"; mine search logs.
- **Broad at category level, specific at leaf level;** avoid near-identical sibling titles.
- **Self-sufficient labels** — must work standalone in search results, breadcrumbs, and cross-links.

### Style conventions (pick and document)

Page titles: Title Case, specific · Nav items: Title Case, 1–3 words · Section headings: sentence case · Tags/categories: lowercase, hyphens · Acronyms: spell out on first use + glossary.

**Consistency audit:** look for the same concept under different names, overlapping nav items, vague "Other/Misc" buckets, many titles starting with the same word. Remedy: collect all nav items + titles, find duplicates/synonyms/ambiguities, standardize via the controlled vocabulary.

## Navigation levels

- **Global** — top menu on every page; 5–8 clear, distinct, **stable** items.
- **Local** — section-specific menus for large areas, to avoid cluttering global nav.
- **Contextual** — in-body "See Also"/related links to genuinely related content; 3–7 max.
- **Supplementary** — site map, A–Z index, breadcrumbs. These supplement structure, not replace it.

## Navigation patterns

- **Breadcrumbs** on all pages with 3+ levels (`Home > Section > Page`).
- **Category/hub pages** at each section level — link to all children; navigational, not informational.
- **Sequential** Previous/Next for ordered content (tutorials, onboarding).
- **Search** complements browsing — see [06-search-and-findability.md](06-search-and-findability.md).

## Navigation checklist

- [ ] Each page reachable in ≤ 3 clicks from home
- [ ] Every page has a clear parent/home link
- [ ] Search-arrival pages give enough context to orient
- [ ] Labels match user vocabulary
- [ ] Deep pages have breadcrumbs
- [ ] No dead-end pages
- [ ] Category pages list all their children

## Anti-patterns

| Problem | Fix |
|---|---|
| Global nav with 15+ items | Consolidate; move rare items to local nav |
| No navigation on deep pages | Add breadcrumbs + parent link |
| Link text "click here" | Descriptive destination text |
| Navigation mirrors org chart | Reorganize by user tasks |
| Every page shows full site structure | Progressive disclosure — show section nav only |
| Ambiguous label ("Resources") | Specific ("Security Templates & Tools") |
| Internal jargon ("Project Phoenix Docs") | User-facing name ("Customer Portal Documentation") |
| Overlapping labels ("Users" vs "Customers") | Merge via controlled vocabulary |
