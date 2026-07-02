---
title: Information Architecture
read_when: Designing or repairing how content is organized, structured, named-at-the-tree-level, and navigated; users get lost or hit dead ends.
key_rules:
  - Design for how users seek information, not how it is stored or authored.
  - Hierarchy 3 levels max; use facets/metadata for extra dimensions.
  - Every page must answer where am I, what's nearby, where can I go next.
---

# Information Architecture

The structural design of the wiki: how content is organized, labeled, and navigated so users can find and use it.

## Core principle

Structure around **how users seek information**, not how it is stored or authored. Run user research before finalizing any hierarchy; use the audience's vocabulary in labels.

## Four information-seeking patterns (support all four)

1. **Known-item** — "help me find it fast" → direct navigation, stable titles, precise search.
2. **Exploratory** — "I want to learn this area" → browse hierarchy, related links, topic hubs.
3. **Exhaustive** — "I need everything" → comprehensive cross-linking, faceted filters.
4. **Refinding** — "I saw it before" → stable URLs, consistent naming, breadcrumbs.

## Three findability questions (ask before any structural decision)

1. Can users **locate** this via navigation? 2. Can they **discover** it without knowing it exists? 3. Can they **return** to it? If "no" for an important page, fix structure before adding content.

## Organization schemes

Choose the grouping logic that matches user lookup behavior:

| Scheme | Use as | Notes |
|---|---|---|
| **Topical** | Default for most wikis | Reflect user mental models; 7–10 top-level topics |
| **Task** ("How to…") | Help, onboarding, support | Pair with topical for reference wikis |
| **Audience** (roles) | When groups need substantially different content | Avoid if most content is shared (duplication) |
| **Chronological** | Changelogs, news, meeting archives | Not for reference content |
| **Alphabetical** | Glossaries, directories, known-item lookup | Secondary access path, not main structure |

**Hybrids are normal** — use one clear primary scheme per level and limit secondary schemes.

| User question | Implied scheme |
|---|---|
| Know what they want? | Alphabetical / search |
| Browse to discover? | Topical hierarchy |
| Arrive with a task? | Task-oriented |
| Different users need different things? | Audience sections |
| Content changes frequently? | Chronological for updates |

## Structure patterns

Choose the pattern **before** building pages:

| Pattern | Use when | Key rule |
|---|---|---|
| **Hierarchy** (default) | Content groups overview→detail | 3 levels max; every child has one obvious parent; siblings comparable in scope |
| **Hub-and-spoke** | Section landing page + many discrete pages | Keep spokes standalone; hub is navigational |
| **Matrix / faceted** | Content has independent attributes | Filter from any angle (see [03-taxonomy-and-metadata.md](03-taxonomy-and-metadata.md)) |
| **Linear sequence** | Tutorials, onboarding where order matters | Use only for sub-sections, not whole wiki |
| **Hybrid** | Mixed content types | Keep one clear primary scheme |

### Depth guidelines

| Wiki size | Max levels |
|---|---|
| < 50 pages | 2 |
| 50–200 pages | 3 |
| 200+ pages | 3–4; add faceted navigation instead of deeper nesting |

### Polyhierarchy (page in multiple categories)

Allow only when a page genuinely serves multiple topics/audiences, users would look in more than one place, and parents stay ≤ 3. Don't use it to paper over unclear category boundaries.

## Top-level structure & hierarchy

- Start with **5–10 top-level sections** covering the full scope; siblings form a meaningful set; label with user vocabulary, not codenames.
- A page without a clear parent doesn't belong — find a home or create the needed section.
- **Hub pages** per section: summarize the section, link to all key children, give context for users arriving from search. Keep them short and link-rich (navigational, not informational).
- **Wiki as hypertext:** add cross-links between genuinely related pages; use descriptive anchor text (never "click here"); add a "Related Pages" section to substantive pages.
- **Manage organic growth:** naming conventions + page-type guide so new pages land correctly; quarterly structure reviews for orphans/misplaced/overgrown sections; a draft/sandbox area for WIP.

### Common structural issues

| Problem | Fix |
|---|---|
| Flat wiki (everything top-level) | Add section groupings/hierarchy |
| Deep nesting (5+ levels) | Flatten; use facets |
| Orphaned pages | Link from hub pages; add to a section |
| Ghost (near-empty) sections | Merge into parent/sibling |
| Category creep ("Other" buckets) | Audit, reclassify, kill catch-alls |
| Duplicate pages | Merge; redirect duplicate to canonical |

### Page naming

Be specific ("Setting Up SSO in Okta", not "SSO Setup"); pick one case convention and keep it; don't date-stamp titles (use metadata); match the controlled vocabulary. Patterns: How-To = "How to [Action] in [System]"; Reference = "[Topic] Reference"; Policy = "[Topic] Policy"; Concept = "[Topic] Overview".

## Wayfinding

Users must always know **where they are, what's nearby, and where to go next**. Support three stages independently (users arrive from anywhere): Accessing (stable URLs, descriptive titles) · Navigating (menus, breadcrumbs, cross-links) · Identifying (titles, headings, summaries).

Essential elements:
- **Breadcrumbs** — `Home > Section > Page`; structural (where it *is*), clickable; essential at 3+ levels.
- **Page titles** — the most important element; descriptive enough to predict content; consistent; never cryptic.
- **Navigation menus** — section-specific for deep wikis; 7–10 items per level; consistent labels.
- **Landmarks** — consistent header/home link, prominent section title, consistent page structure.
- **Contextual links** — descriptive text; a "Related Pages" section; limit to 3–7 relevant links.

**Information scent** = cues that let users predict a destination before clicking. Strengthen with specific titles ("Setting Up SSO in Okta" not "SSO Docs"), headings that match search terms, one-line summaries on hub pages. **Progressive disclosure:** show overview first, reveal detail on demand; keep category pages as clean hubs.

## IA anti-patterns

| Problem | Fix |
|---|---|
| Organizing by org chart | Reorganize by topic/task; attribute teams via metadata |
| Overlapping top-level categories | Use facets or rethink boundaries |
| >10 top-level categories | Consolidate into broader themes |
| Deep hierarchies (5+) | Flatten to 3; add facets |
| No secondary access path | Add search + A–Z index |
| Relying on search to replace structure | Search works only if structure and titles are good |
| Link text "here"/"this" | Rewrite with descriptive destination text |
| Dead-end pages | Add related links + parent link |
