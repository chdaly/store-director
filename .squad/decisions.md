# Squad Decisions

## Active Decisions

### 2026-09-03T18:27:50-05:00: Simulation framing decisions
**By:** Chris Daly (accepted, via Squad Coordinator)
**Context:** Four open questions raised by Lead in `docs/simulation-plan.md` §8.

- **Audience:** Mixed Innovation Hub audience — retail credibility comes first.
- **Time claim:** No quantified time-saved number. Use only the documented ~12 projects / ~50 dates proof point.
- **Store health:** Four pillars (Guest, Team, Operations, Financials), with pickup as the highlighted issue.
- **Naming:** Neutral "Store Director" in body copy; "Target" reserved for research context only.

**Why:** Keeps the artifact credible with a retail audience, avoids inventing metrics the research does not support, and reduces brand sensitivity in a shared file.

### 2026-09-03T18:27:50-05:00: Simulation scope and interaction model
**By:** Lead (Experience Lead)
**What:** Guided scripted interaction — a small set of deliberate click prompts that advance scenes and synchronize narrative with visuals.

**Rejected alternatives:** open fake chat input (brittle on unmatched prompts), full dashboard explorer (becomes a BI product demo), five-feature carousel (capability tour).

**Scope IN:** use cases 1, 5 (flagship), 6, 7, 8, 9 — with the store-specific morning brief as the artifact's center.
**Scope OUT:** use cases 2, 3, 4, 10, 11, 12.

**Constraints:** one self-contained `.html` file; zero external dependencies; runs from `file://` offline; all data synthetic and visibly labeled; no Microsoft or Target logos or trade dress.

## Governance

- All meaningful changes require team consensus
- Document architectural decisions here
- Keep history focused on work, decisions focused on direction
