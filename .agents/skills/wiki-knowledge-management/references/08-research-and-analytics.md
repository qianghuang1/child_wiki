---
title: Research & Analytics
read_when: Validating a design decision with users, diagnosing navigation/labeling failures, or defining KPIs and measuring/reporting wiki success.
key_rules:
  - Card sorts design structure; tree tests validate it (aim ≥70% task success).
  - 5–15 participants from real target users surface most major problems.
  - Use analytics to find problems; report outcomes, not vanity metrics.
---

# Research & Analytics

User research and analytics are the two feedback loops. Research tells you *why*; analytics tell you *what*. Use both — neither replaces the other.

## When to do user research

Before designing/reorganizing structure, when labels need validation, when search is poor and you need to know why, or when users report trouble finding information.

## Core research methods

| Method | Use for | How |
|---|---|---|
| **Free-listing** | Discover user vocabulary | "List everything you associate with [topic]." High-frequency items = high salience |
| **Open card sort** | Design a new taxonomy | Users group items and name groups; reveals mental models + candidate labels |
| **Closed card sort** | Validate a taxonomy | Users place items into predefined categories; reveals ambiguity |
| **Tree testing** | Validate navigation | Users find pages in a text-only hierarchy; measures success rate, first click, time |
| **Interviews** | Understand mental models + vocabulary | 30–45 min, semi-structured |
| **Contextual inquiry** | See real workflows | Observe actual work; high-fidelity, time-intensive |

**Running a card sort:** 30–50 representative items, 5–15 target-audience participants, ask them to group and explain; look for agreement clusters (strong) vs. scattered placement (ambiguity). *If users consistently group differently from your structure, your structure is wrong.*

**Running a tree test:** build the hierarchy in a tool (Optimal Workshop, Maze), write 5–10 realistic findability tasks, recruit 10–20 participants, analyze success rate/first click/time. *If <70% succeed, the structure or label is wrong.*

**Who to involve:** new employees (fresh from onboarding), frequent users, frequent question-askers, contributors. Recruit **actual target users**, not internal team members who already know the wiki. 5–8 finds major patterns; 10–15 for tree testing. Treat results as strong signals, then test the resulting design.

| Goal | Method |
|---|---|
| Discover vocabulary | Free-listing |
| Design new taxonomy | Open card sort |
| Validate taxonomy | Closed card sort |
| Test navigation | Tree testing |
| Understand mental models | Interviews |
| Find where users get stuck | Contextual inquiry / think-aloud |
| Find what users search | Search log analysis |

## Core KPIs

**Usage:** monthly active users (growing), page views by page, search vs. browse ratio, new vs. returning.
**Findability:** search success rate (>80%), zero-result rate (<5%), time-to-find (decreasing), 2-click reach (>90%).
**Quality:** % pages with owner (100%), % reviewed in 12 months (≥90%), user-reported inaccuracies (decreasing), broken-link rate (<1%).
**Contribution:** new pages/month, active contributors (growing), % pages updated in 90 days (≥70%).

Tools: built-in platform analytics (Confluence Space/Page Analytics, Notion, Outline) or Google Analytics/Plausible for custom wikis; export query logs from the search tool.

## Review workflows

**Monthly (~30 min):** check top 20 queries (vocabulary to add?) → review zero-result queries → review high-bounce category pages → alert owners of overdue pages → note rising search terms → share a 1-page summary.

**Quarterly (2–3 hr):** KPI trend analysis → content-audit sample → taxonomy health/growth → new vocabulary → user feedback review → governance (missing owners, overdue reviews).

## Reporting to stakeholders

1 page max; lead with **outcomes, not activity** ("users found answers 40% faster", not "added 200 pages"); 3–5 metrics with trend arrows; top 3 improvements + top 3 issues; recommended actions with owners.

## Analytics anti-patterns

| Anti-pattern | Fix |
|---|---|
| Page count = success | Report findability/usage metrics |
| Collect data, don't act | Assign an action owner to every finding |
| Individual-level tracking | Aggregate only |
| Measure only what's easy | Define KPIs before measuring |
| Optimize views on low-value pages | Focus on outcomes |
