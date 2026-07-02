---
title: Content Modeling
read_when: Pages of the same kind are inconsistent, or you need to define page types and templates.
key_rules:
  - Define page types with required/optional elements before authoring at scale.
  - Reuse via linking, not copying; extract content repeated on 3+ pages.
  - One page = one topic/task; keep required template fields to 5–8.
---

# Content Modeling

A content model defines the structure, fields, and relationships of each page type — the blueprint that keeps similar pages consistent and reusable. Without it, same-purpose pages look different, readers can't predict where information lives, and reuse is impossible.

A model specifies: **page types**, **content elements** (sections each type needs), **metadata fields**, and **relationships**.

## Common page types

| Page Type | Key elements |
|---|---|
| How-To / Procedure | Goal, Prerequisites, Steps (numbered, verb-first), Outcome |
| Reference | Title, Description, Parameters/Values, Examples |
| Policy | Purpose, Scope, Statement, Enforcement, Review Date |
| Concept / Explainer | Summary, Context, Key Points, Related Links |
| Project Page | Status, Owner, Objectives, Progress, Decisions |
| Meeting Notes | Date, Attendees, Agenda, Decisions, Action Items |
| Hub / Index | Overview, Child Page Links, Key Topics |

## Define elements per type

Example — **How-To**:
```
REQUIRED: Title · Goal · Prerequisites · Steps · Expected outcome
OPTIONAL: Troubleshooting · Related How-Tos · Video link
METADATA: Owner · Topic · Audience · Last Reviewed · Status
```

## Templates

Build a template per page type: prefill headings from the model, add placeholder guidance, include metadata fields with controlled-vocabulary dropdowns. Templates drive consistent structure and lower authoring effort.

## Modularity & granularity

- **Modular:** write each element as a self-contained, reusable unit. If the same content appears on **3+ pages**, extract it to a shared component and link to it (don't copy).
- **Right-size:** one page = one clear topic/task. Split pages > ~2000 words; merge multiple tiny pages on the same narrow topic. Avoid both mega-pages (unscannable, unreusable) and over-fragmentation (users bounce around).
- **Reusable components:** warning/disclaimer blocks, common prerequisites, escalation paths, version notes — store centrally and link/embed.

## Governance

Update templates when models change; train contributors on page types; audit quarterly that pages match their declared type.

## Anti-patterns

| Anti-pattern | Fix |
|---|---|
| Freeform pages, no structure | Create and enforce page-type templates |
| Same info on 5 pages | Extract to a canonical page; link |
| Template with 20+ required fields | Reduce to 5–8 truly required |
| "General" type for everything | Define specific types for recurring patterns |
