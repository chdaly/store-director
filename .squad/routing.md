# Work Routing

How to decide who handles what.

## Routing Table

| Work Type | Route To | Examples |
|-----------|----------|----------|
| Scope, scenario arc, demo structure | Lead | "What does the demo show first?", cutting scope, final review |
| Copilot response copy, SD dialogue, persona voice | Narrative | Morning brief text, chat prompts, microcopy, insight framing |
| Synthetic metrics, chart specs, PBI visual grammar | Data | Store dataset, KPI definitions, trend consistency, variance math |
| HTML/CSS/JS implementation, SVG charts, packaging | Frontend | Building the page, inlining assets, interactions, animation |
| Portability, offline, a11y, cross-browser verification | Tester | `file://` checks, external-request audit, contrast, keyboard nav |
| Research grounding, claim verification, devil's advocate | Fact Checker | "Does the research support this?", pre-mortem on the demo narrative |
| Content safety, synthetic-data disclosure, fairness | Rai | Illustrative-data labeling, persona representation, harmful patterns |

Add or edit rows here only when their agent names also exist in the casting registry.

## Issue Routing

| Label | Action | Who |
|-------|--------|-----|
| `squad` | Triage: analyze issue, assign `squad:{member}` label | Lead |
| `squad:{name}` | Pick up issue and complete the work | Named member |

### How Issue Assignment Works

1. When a GitHub issue gets the `squad` label, the **Lead** triages it — analyzing content, assigning the right `squad:{member}` label, and commenting with triage notes.
2. When a `squad:{member}` label is applied, that member picks up the issue in their next session.
3. Members can reassign by removing their label and adding another member's label.
4. The `squad` label is the "inbox" — untriaged issues waiting for Lead review.

## Rules

1. **Eager by default** — spawn all agents who could usefully start work, including anticipatory downstream work.
2. **Scribe always runs** after substantial work, always as `mode: "background"`. Never blocks.
3. **Quick facts → coordinator answers directly.** Don't spawn an agent for "what port does the server run on?"
4. **When two agents could handle it**, pick the one whose domain is the primary concern.
5. **"Team, ..." → fan-out.** Spawn all relevant agents in parallel as `mode: "background"`.
6. **Anticipate downstream work.** If a feature is being built, spawn the tester to write test cases from requirements simultaneously.
7. **Issue-labeled work** — when a `squad:{member}` label is applied to an issue, route to that member. The Lead handles all `squad` (base label) triage.
