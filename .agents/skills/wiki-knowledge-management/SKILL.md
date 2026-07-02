---
name: wiki-knowledge-management
description: 'Use when user ask for doing knowledge management, like managing wiki, books, files and anything that can be used as knowledge source'
---

# Wiki Knowledge Management

Act as an expert information architect and KM consultant to help users compile the given material into a curated wiki that everyone with access can browse — and that other AI agents can use as a **grounding source**. By default, keep as many useful source details as possible: facts, examples, decision rules, caveats, named entities, checklists, thresholds, procedures, and actionable links. Retain, organize, and contextualize source information instead of compressing it into a brief summary unless the user specifically asks for summarization or a lightweight outline. Use the sources to create a structured, findable, and governed knowledge base.

**The goal of every wiki is to do wiki-based knowledge management of the items in its source folder** — turning raw source material into a structured, findable, governed knowledge base. See [wiki_tools.md](references/wiki_tools.md) for the CLI that supports this lifecycle.

## Default Detail Level

Default to detailed source retention and organization: generated wiki pages must be standalone and practically usable, not merely navigational outlines.

When building a wiki from source files, do not create placeholder pages, thin summaries, or table-of-contents-only pages unless the user explicitly asks for a lightweight outline.

Each generated page should be useful on its own and should preserve the source's substantive details, especially actionable details, named concepts, checklists, decision rules, thresholds, examples, caveats, and links.

Even when sources are long, try your best to keep the details from those sources. Omit or compress details only when they are duplicate, irrelevant to the wiki goal, obsolete, privacy-sensitive, or explicitly excluded by the user.

If a detail is important enough that a reader would need to reopen the source to act correctly, keep it in the wiki page or explicitly account for why it was not included.

## Default delivery target: final version

Unless the user explicitly asks for an MVP, scaffold, outline, sample, or "core usable" version, target a final-version wiki. The expected outcome is a polished, source-covered knowledge base that users can rely on directly, not merely a minimally useful entry point.

Do not treat "core usable" as the completion standard. Core usability can be an intermediate milestone during a large build, but the final response must not present it as done unless the source coverage, page completeness, navigation, metadata, indexes, and maintenance records meet the wiki's Definition of Done.

When time or context prevents a final version, be explicit: label the result as scaffold created or partial incorporation, record the remaining work by source/chunk/topic, and avoid language such as complete, final, comprehensive, or ready unless the coverage matrix supports it.

## Book and reference source knowledge retention

For book-like, manual-like, encyclopedia-like, course-like, or reference-like sources, the main knowledge must be retained in the wiki. The value of the wiki is that readers can use the organized knowledge without reopening the original book for ordinary understanding, decision-making, or action.

Preserve the source's main concepts, definitions, taxonomies, relationships, procedures, decision rules, thresholds, warnings, exceptions, recurring questions, practical implications, and high-value examples in transformed wiki form. Do not reduce a book to highlights, chapter summaries, a table of contents, or a reading guide unless the user explicitly asks for that lighter output.

This does not require copying the book's expressive text or preserving every anecdote, rhetorical passage, or stylistic explanation. It does require covering the major knowledge from each chapter or chunk so the wiki can stand as the practical knowledge base derived from the source.

If a book source cannot be fully incorporated in one pass, mark the result as partial incorporation, keep a visible backlog by chapter/chunk/topic, and do not record the source as incorporated until its main knowledge is covered, excluded, or deferred with reasons.

## Copyright-aware source transformation

When a source is a copyrighted or likely copyrighted book, article, manual, paid course, or similar long-form work, transform the learned knowledge into original wiki content instead of copying the source's expressive text.

Do not reproduce large passages, chapter-length paraphrases that closely track the original wording, distinctive anecdotes, or a substitute version of the book. Short quotations are allowed only when necessary for precision, and they should be minimal, clearly attributed, and not used as the main content.

Still preserve the knowledge value: extract and organize concepts, facts, definitions, taxonomies, relationships, decision rules, thresholds, procedures, warnings, exceptions, checklists, and practical implications in your own words. Convert source material into tables, checklists, decision trees, topical pages, and cross-links where useful.

For examples or cases from copyrighted books, prefer generalized scenarios that retain the lesson without copying the original narrative details unless the exact wording or case facts are essential and brief.

Copyright limits are not a reason to create thin summaries or omit the book's main knowledge. If the source contains important actionable or conceptual knowledge, capture the knowledge in transformed form and track it in the coverage matrix; if a detail cannot be included because it would require excessive verbatim reproduction, mark it as excluded or deferred with that reason.

## Source-to-wiki completion levels

Do not describe a wiki as complete, comprehensive, or fully built from its sources unless source coverage has been checked against the source inventories.

Use honest completion labels:

- **Scaffold created** — IA, navigation, parent pages, or sample pages exist, but source coverage has not been completed.
- **Partial incorporation** — some sources, chapters, chunks, or topic groups are incorporated, but meaningful source material remains.
- **Source-covered wiki** — every substantive topic, discriminating entity, actionable detail, threshold, warning, exception, example, or procedure from the preprocessing inventories is covered, explicitly excluded, or tracked as deferred work.

If the user asks for a full wiki or a good guide, a scaffold is not enough. Say it is a scaffold or partial incorporation unless the coverage check proves otherwise.

## Source Incorporation Definition of Done

A source is not incorporated, and the wiki is not complete for that source, until all of these are true:

1. The source has a persisted topic inventory and discriminating entity list.
2. Large or complex sources have been split into bounded chunks before final writing.
3. Every inventory item has a wiki destination: page, section, tag, link target, explicit exclusion, or tracked follow-up.
4. Wiki pages are standalone enough for readers to act without reopening the source for ordinary use.
5. The coverage matrix has been checked after writing.
6. Deferred or excluded topics are reported to the user and recorded in wiki maintenance notes.

Do not run `wiki_tools sources add` for a source merely because you read it or summarized it. Record a source as used only after its substantive inventory items are represented or explicitly accounted for.

## Large Source Protocol

A source is large or complex if it is over roughly 1,000 lines, contains multiple chapters, is a book/manual/reference, mixes many topics, or would require readers to act from detailed rules.

For each large or complex source:

1. Split by chapter, heading range, page range, source section, or semantic topic cluster.
2. Extract for each chunk:
    - topics and subtopics
    - procedures and care/action steps
    - decision rules and thresholds
    - warnings, red flags, exceptions, contraindications, and caveats
    - examples, cases, recurring questions, and edge conditions
    - named entities, terms, variants, and synonyms
    - suggested wiki destination
3. Merge chunk inventories before writing final wiki pages.
4. Do not replace chunk extraction with a whole-source summary.
5. If there is not enough time or context to incorporate every chunk, create a visible backlog and state that the wiki is incomplete.

## Coverage Matrix Required

Before finalizing source incorporation, create or update a persisted coverage matrix under `.wiki/`, such as `.wiki/source-coverage.md` or `.wiki/source-inventories/<source-name>.md`.

Use this schema:

| Source | Chunk / Section | Inventory Item | Type | Wiki Destination | Status | Reason |
|---|---|---|---|---|---|---|
| path | chapter/page/heading | topic/entity/detail | topic/entity/rule/example/warning | page/section/tag/follow-up | Covered/Deferred/Excluded | one-line reason |

Treat this matrix as acceptance criteria. If an item is missing from the wiki and has no reason, the source incorporation is not done.

## No Thin Pages Rule

A page is too thin if it mostly contains broad category descriptions, source table-of-contents entries, generic advice without source-specific details, or topic lists with no procedures, thresholds, examples, caveats, warnings, exceptions, or decision rules.

For book-like, manual-like, encyclopedia-like, or guide-like sources, create child topic pages when one page would force important details to be compressed. Prefer parent pages plus detailed child pages over a few broad overview pages. A parent page may summarize and route, but child pages must carry the details readers need.

## Source folder & wiki_tools (always apply)

Every wiki is backed by a **source folder** of raw material; the wiki retains, organizes, and contextualizes that material for knowledge management. Use the `wiki_tools` CLI (see [wiki_tools.md](references/wiki_tools.md)) to keep the wiki and its sources in sync:

1. **Every wiki is associated with a source folder.** Configure it with `wiki_tools config add-source <path>`. The wiki exists to manage knowledge derived from items in that folder.
2. **Whenever you incorporate a source, record it.** After its substantive inventory items are represented or explicitly accounted for, run `wiki_tools sources add <path> --source-root <root>`. Use `wiki_tools sources exclude <path> --reason "…"` for sources you deliberately skip. If you only read a source for triage or create a thin summary, do not mark it incorporated.
3. **After making changes, record them.** Log every edit with `wiki_tools changes add --title "…" --author "…" --why "…" --what-changed "…"`, then run `wiki_tools build` to regenerate `change-log.md` and per-directory `index.md` files.
4. **Use staleness-check to generate the to-do list.** Run `wiki_tools staleness-check` (add `--json` for machine output) to find new or changed sources; turn each reported source into a to-do item for updating the wiki.
5. Treat this loop — *associate sources → record use → make changes → record changes → re-check staleness* — as the standing maintenance cycle for the wiki.

## .wiki folder and long term Mantainance
The `.wiki` folder is the default storage folder for `change-log.json`, `config.json`, `used-sources.json`, and other wiki metadata.
Leverage the `.wiki` folder to store user preferences and the information architecture (IA) of the wiki and anything helps to maintain a consistent structure and governance over time. Name it as `IA.md` Everytime, when you try to change structure of wiki, you need to read and understand existing IA and update it accordingly. The IA.md file should be updated whenever the structure of the wiki changes, and it should be used as a reference for future changes to ensure consistency and maintainability.

## Inner Page Link
Use Obsidian-style `[[Wiki Page Name]]` links to other wiki pages. The Wiki Page Name matches the file name without `.md` extension. For example, if you have a page named `Deployment Guide.md`, link to it with `[[Deployment Guide]]`.

Prefer to use Inner Page Links over relative links (e.g. `../folder/page.md`) because they are more robust to file moves and renames. The wiki tools can automatically update inner page links when pages are moved or renamed.

## Parent Page
In wiki visualization, parent page is enhanced folder that contains all the child pages. It is used to group related pages together and provide a higher-level overview of the content. To use parent page, create a folder and a md file with exactly the same name as the folder. For example, if you have a folder named `knowledge management`, create a file named `knowledge management.md` inside that folder. This file will serve as the parent page for all the child pages within the `knowledge management` folder.

Root folder doesn't support parent page, so name it based on the topic of wiki.

## Understand source details before writing
Use preprocessing tools to understand the topics, entities, relationships, examples, rules, links, and caveats in each source before writing wiki pages. Base page structure on the wiki IA and the user's ask, but do not skip source details simply because the source is long.

For each source, create a persisted topic inventory before writing: list the substantive topics, subtopics, workflows, decision points, examples, warnings, exceptions, thresholds, and recurring questions covered by the source. Treat that topic inventory, together with the discriminating entity list, as acceptance criteria for source incorporation. Every substantive topic should appear in the wiki as content, a page, a section, a link target, metadata, or an explicitly tracked follow-up with a reason.

For long, complex, noisy, or multi-document sources, split the work by source, chapter, heading range, page range, or semantic chunk. If subagents are available, use them for bounded read-only extraction tasks and ask each subagent for topics, discriminating entities, useful details, uncertainty/OCR issues, and suggested wiki destinations. Merge the subagent outputs into one coverage plan before writing final pages so no chunk silently disappears.

## Metadata for each page
Every wiki page should have YAML frontmatter with at least a `title`, `description`, `sources` and `tags` field. The `sources` field is a list of source files that were used to create the page. This helps with traceability and governance.

## Encode Pathes
If path name contains spaces, you should encode the path name in the `sources` field. For example, if the source file is `my folder/my file.md`, you should encode it as `my%20folder/my%20file.md`. This ensures that the path is correctly interpreted by the wiki tools and other systems.

## File Name Conventions
Create decent human-readable file names for the wiki pages and folders. For example, use `Deployment Guide.md` instead of `deployment_guide.md`.

## Visualize with Mermaid diagrams
When a wiki page describes something that is clearer as a picture than as prose, add a [Mermaid](https://mermaid.js.org/) diagram in a fenced ` ```mermaid ` code block. Most wiki renderers (Azure DevOps, GitHub, GitLab, many static-site generators) render Mermaid natively, so the diagram stays as plain text that is versionable, diffable, and editable alongside the content.

Reach for a Mermaid diagram when the content involves:

- **Processes, workflows, or decisions** → `flowchart` (e.g. approval flows, onboarding steps, troubleshooting/decision trees).
- **Sequences of interactions over time** → `sequenceDiagram` (e.g. API/service call flows, request/response handshakes).
- **Hierarchies, structure, or relationships** → `flowchart`, `classDiagram`, or `erDiagram` (e.g. system architecture, org structure, data models, the wiki's own information architecture).
- **State or lifecycle transitions** → `stateDiagram-v2` (e.g. content review status, ticket lifecycle).
- **Schedules or timelines** → `gantt` or `timeline` (e.g. rollout plans, roadmaps).

Guidance:

- **Pair the diagram with prose.** The diagram complements the text; it doesn't replace it. Keep enough text so the page is still useful (and searchable) without the rendered image.
- **Keep diagrams small and focused.** Split a large diagram into several smaller ones rather than one unreadable graph. Prefer ~5–15 nodes per diagram.
- **Use users' vocabulary** in node and edge labels, consistent with the wiki's taxonomy and labeling conventions.
- **Keep it maintainable.** Treat the diagram source as content that can go stale — update it (and log the change via `changes add`) when the underlying process or structure changes.

Example:

````markdown
```mermaid
flowchart LR
    Draft --> Review --> Published
    Review -->|changes requested| Draft
    Published -->|stale| Archived
```
````

## Report dropped topics and entities

You shouldn't drop any topics by default, unless you must do it.

After incorporating a source into the wiki, **report in your response every substantive topic or discriminating entity that was on the source's preprocessing inventory but did not make it into the final wiki page, and explain why.** Scope this strictly to substantive topics and discriminating entities from the post-preprocessing inventory — do not discuss ubiquitous generic terms or whole excluded sources, only the topics and entities you identified as meaningful yet left out.

- **List each dropped topic or entity with a one-line reason** (e.g. *"`rollback procedure` — deferred to a follow-up page because it needs a separate runbook"*; *"`v2.3.1` — superseded by latest version, only current kept"*).
- **Surface judgment calls.** If dropping a topic or entity was borderline, say so, so the user can override and have it added back.
- **Goal:** every substantive topic and discriminating entity is either present in the wiki page or accounted for here — nothing silently disappears.

See [09-source-preprocessing-and-entity-extraction.md](references/09-source-preprocessing-and-entity-extraction.md) for what counts as a substantive topic or discriminating entity.

## How to use

1. **Diagnose the real goal** — greenfield design, a targeted fix, or an audit/improvement.
2. **Find the root cause first.** Most "messy wiki" problems are findability, governance, or culture failures — not missing content. Don't restructure before diagnosing.
3. **Route to 1–2 reference files** (table below). Each file's frontmatter has `read_when` + `key_rules` to confirm relevance.
4. **Apply the rules and anti-patterns** to the user's situation; cite the rule you're applying.
5. **Prefer the smallest fix** that works (labels, ownership, synonyms) over full reorganization.
6. **Make decisions testable** (card sorts, tree tests, search-log review) and **close the loop** with metrics.

## Core principles (apply as defaults)

| Principle | Rule |
|---|---|
| Findability first | Fix structure → then search → then analytics. |
| User vocabulary | Label with users' words, not jargon or org-chart names. |
| Multiple access paths | Important pages reachable by browse AND search. |
| 3-level max hierarchy | Deeper nesting abandons content; use facets/metadata. |
| One owner per page | Governance starts with named accountability. |
| One term per concept | Controlled vocabulary prevents synonym drift. |
| Link, don't copy | Reuse by linking; copy-paste creates conflicting sources. |
| Archive, don't delete | Preserve links/trust; archive with redirects. |
| Design for users, not storage | Structure around how people seek information. |
| Culture beats technology | Tools are ~20% of KM success. |
| Analytics are feedback, not proof | Data finds problems; judgment fixes them. |

## Task → reference routing

| If the user wants to… | Read |
|---|---|
| Set KM goals / strategy / maturity / grow adoption | [01-strategy-and-adoption.md](references/01-strategy-and-adoption.md) |
| Organize content, choose structure, design hierarchy, fix getting-lost / naming | [02-information-architecture.md](references/02-information-architecture.md) |
| Build a taxonomy, standardize terms, add facets, design metadata, relate concepts | [03-taxonomy-and-metadata.md](references/03-taxonomy-and-metadata.md) |
| Design menus/breadcrumbs/cross-links or fix labels | [04-navigation-and-labeling.md](references/04-navigation-and-labeling.md) |
| Define page types and templates | [05-content-modeling.md](references/05-content-modeling.md) |
| Improve search, make content discoverable, use search logs | [06-search-and-findability.md](references/06-search-and-findability.md) |
| Set up ownership/review cycles, run content audits, fix stale content, diagnose a failing wiki | [07-governance.md](references/07-governance.md) |
| Validate design with users, define KPIs, measure/report value | [08-research-and-analytics.md](references/08-research-and-analytics.md) |
| Preprocess source files, extract topic inventories and discriminating entities, ensure core topics and details are retained | [09-source-preprocessing-and-entity-extraction.md](references/09-source-preprocessing-and-entity-extraction.md) |

## Workflows

- **Design from scratch:** strategy & goals (01) → research users (08) → IA + structure (02) → taxonomy + metadata (03) → content models (05) → navigation + labels (04) → governance (07) *before launch* → adoption + analytics (01, 08).
- **Fix hard-to-navigate wiki:** tree test (08) → wayfinding + navigation (02, 04) → audit labels (04) → fix structure/flatten (02).
- **Improve search:** zero-result/low-click queries (06) → synonyms + boosting (06) → multiple access paths (06).
- **Improve quality:** content audit (07) → ownership + review cycles (07) → content models/templates (05).
- **Grow adoption:** diagnose barriers (01) → demonstrate value with analytics (08) → support champions, reduce friction (01).
- **Maintain from sources:** `wiki_tools staleness-check` → turn new/changed sources into a to-do list → preprocess each source into a persisted topic inventory and entity list (09) → apply the Large Source Protocol when needed → merge inventories into a coverage matrix → incorporate details into the wiki, covering every substantive topic and discriminating entity → only then `sources add` each incorporated source → `changes add` per edit → `wiki_tools build` → report the actual completion level.

## Guardrails

- **Recommend from evidence** (audit data, search logs, research). If it doesn't exist, say so and recommend gathering it.
- **Don't over-engineer.** A 50-page wiki needs no facets, ontology, or maturity program. Match solution to scale.
- **Structure does not substitute for content coverage.** If asked to "add content" to a failing wiki, check structure/labeling/governance first; if asked to build a wiki from sources, IA and content coverage must advance together. A structure-only pass is allowed only when the user explicitly asks for an outline, scaffold, or planning phase.
- **Keep sources tracked.** Don't pull content into the wiki without recording the source (`sources add`) and logging the change (`changes add`); rely on `staleness-check` to surface work.
- **Respect privacy** with search logs and analytics — aggregate only.
