---
title: Governance
read_when: The wiki is decaying or has no owners; setting up governance; running a content audit; managing stale content; diagnosing a failing wiki.
key_rules:
  - Every published page has exactly one named owner.
  - Define lifecycle states + review cadences; archive (with redirects), don't delete.
  - Keep governance lean — a short style guide, not a 50-page policy.
---

# Governance

The rules, roles, and processes that keep a wiki accurate, organized, and trustworthy. Without governance, wikis decay: pages go stale, duplicates appear, labels drift, no one feels responsible, and stale content outranks current content.

## Core governance elements

1. **Page ownership** — every substantive page has an owner responsible for accuracy; owner decides archival/deletion. Make Owner a required template field at publication.
2. **Review cycles** — add "Last Reviewed" + "Review Due" metadata; report overdue pages.
3. **Lifecycle states** — status field on every page; search boosts Active, excludes Archived.
4. **Editorial standards** — short style guide covering structure, voice, required metadata, link conventions, media. Not a 50-page doc.
5. **Contribution workflow** — high-stakes wikis: Author → Draft/Under Review → owner approval → Active. Low-stakes: open editing + review-on-demand.
6. **Versioning** — track history for rollback and audit trail; it's a safety net, not a process.

### Review cadence

| Content type | Cadence |
|---|---|
| How-To / Procedures | Every 6 months or after system changes |
| Policies | Annually or on change |
| Reference (config, specs) | Triggered by system changes |
| Concepts / Explainers | Annually |
| Meeting Notes | Archive after 12 months; no active review |

### Lifecycle states

| State | Meaning | Action |
|---|---|---|
| Draft | WIP, not for general use | Not yet published |
| Active | Current, maintained | Maintain |
| Under Review | Being updated; may be partly outdated | Owner updating |
| Outdated | Known inaccurate | Owner notified; update or archive |
| Archived | Historical, read-only | Not for active use |

### Roles

| Role | Responsibility |
|---|---|
| Wiki Owner | Strategy, structure, governance policy |
| Section Owner | Taxonomy + organization within their area |
| Page Owner | Accuracy/freshness of specific pages |
| Moderator / Curator | Find orphaned/outdated content; enforce standards |
| Contributor | Create/update content in their domain |

Small teams combine roles. **Scale governance to wiki size — don't over-govern a small wiki.**

### Governance cadence

| Frequency | Activity |
|---|---|
| Continuous | New pages follow templates; owner assigned before publish |
| Monthly | Review search analytics; create content for zero-result queries |
| Quarterly | Audit outdated/orphaned pages; review taxonomy + vocabulary |
| Annually | Full content audit; review IA; update standards |

## Content inventory & audit

**Inventory** (know what you have) — capture per page: URL/ID, Title, Location, Owner, Status, Last Reviewed, Page Type, Quality Score (1–5). Run before restructures/migrations, when establishing governance, and annually. Export from the wiki tool + manual quality scoring into a shared spreadsheet.

**Audit** (evaluate quality, decide action) dimensions: **Accuracy, Completeness, Currency, Findability, Duplication, Ownership.** Quantitative scan = counts by section, pages without owners, pages not reviewed in 12+ months, broken links. Qualitative = read a sample per section, rate quality, flag for update/merge/archive. **Prioritize** high-traffic pages, search-found pages, and high-stakes pages (policies, onboarding, procedures).

### Lifecycle triggers

| Trigger | Action |
|---|---|
| Review due date passes | Notify owner; set "Under Review" |
| System/process change | Unscheduled review of related pages |
| Owner leaves | Reassign; flag for review |
| Not viewed in 12 months | Review for archival |
| User reports inaccuracy | Flag "Outdated"; notify owner |

### Archive vs. delete

**Archive** when content has historical value, has inbound links, or may be externally referenced. **Delete** only when entirely wrong/misleading, with no inbound links, where archiving would confuse. **Always redirect** a deleted URL to a relevant current page.

### Editorial quality checklist

- [ ] Title descriptive and matches search terms
- [ ] Has summary/intro
- [ ] Follows page-type template
- [ ] Owner populated · [ ] Status set · [ ] Last Reviewed set
- [ ] Key terms match controlled vocabulary
- [ ] Cross-links present · [ ] Images have alt text · [ ] No broken links

### Governance reporting targets

% pages with owner = 100% · % reviewed in 12 months ≥ 90% · % with Status populated = 100% · time to update flagged page < 2 weeks · broken-link rate < 1%.

## Anti-patterns (structure · governance · content)

**Structure**
- *Build it and they will come* → seed quality content + communicate purpose before launch.
- *Org-chart navigation* → organize by topic/task; attribute teams via metadata.
- *One mega-page* → split via a content model; link through hubs.
- *Duplicate pages* → keep canonical; archive/redirect; link not copy.
- *Deep hierarchies (5+)* → flatten to 3; use facets.
- *Wiki as file system* → flatten; add hubs + cross-links; classify via metadata.

**Governance**
- *No page owners* → require owner at publish.
- *Frozen taxonomy* → quarterly reviews; let structure evolve.
- *Governance longer than the wiki* → a 1-page style guide + schema + ownership is enough.

**Content**
- *Copy-paste instead of link* → link to canonical; extract shared content.
- *Vague titles ("Misc Notes")* → title must answer "what will I find here?".
- *Outdated content left Active* → lifecycle states; search demotes Outdated/Archived; quarterly audits.
- *Writing for the author* → define the audience and the question the page answers first.
