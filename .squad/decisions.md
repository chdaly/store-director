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


### 2026-09-03T18:27:50-05:00: Simulation dataset model and hook metric
**By:** Data
**What:** The simulation uses one fictional store (`SIM-TGT-9001`, Bullseye Bay Innovation Store) and one synthetic retail week ending 2026-08-30. The primary hook metric is Saturday Guest degradation: daily guest score 69 and pickup on-time 88.4%, with drill-down to Saturday afternoon Fulfillment/Pickup coverage loss.
**Why:** This gives Frontend implementable Power BI-style visuals and gives Narrative a non-obvious but numerically supported causal chain: weekly labor looks nearly balanced, but labor lands in the wrong daypart/department, causing pickup delays, guest recovery incidents, and next-day operations drag.

### 2026-09-03T18:27:50-05:00: Simulation copy voice and accuracy guardrails
**By:** Narrative
**What:** The simulation copy is locked to a calm Store Director peer voice: store pulse first, what changed second, decision needed third. Pickup remains the scenario priority, and any Guest/Operations connection is phrased as signals pointing to an observation target rather than proven causation. The unresolved Fulfillment/Pickup gap-hours figure is represented with `{{FULFILLMENT_GAP_HRS}}` wherever cited.
**Why:** This preserves the accepted framing decisions, avoids overclaiming the synthetic data, and gives Frontend a stable copy system for implementation and future edits.

### 2026-09-03: Single-file simulation build
**By:** Frontend
**What:** Implemented the Store Director morning simulation as one standalone HTML file with inline CSS, inline JavaScript, inline SVG charts, Data's JSON object embedded near the top of the script, guided scene navigation, keyboard-reachable controls, and no external dependencies.
**Why:** The artifact must run from file:// on unknown executive laptops with networking disabled while preserving Lead's eight-scene structure, Narrative's approved strings, and Data's synthetic dataset and accessible palette.

### 2026-09-03: Store Director simulation QA verdict
**By:** Tester
**What:** Rejected `store-director-simulation.html` for one Major accessibility/trust defect and two Minor accessibility defects. Recommended fix owner is `@copilot` Coding Agent or another non-author frontend-capable agent; original Frontend author is locked out by reviewer protocol.
**Why:** The artifact otherwise passes runtime, data fidelity, copy fidelity, replay reset, retail smell, and self-explanatory checks, but dark-theme contrast makes the persistent synthetic-data disclosure/header/footer unreadable on some unknown executive laptops.

### 2026-09-03: Lead QA revision for simulation rejection
**By:** Lead
**What:** Revised `store-director-simulation.html` as non-author owner after Tester NO-GO: fixed dark-theme semantic contrast, added a persistent visually-hidden artifact h1, and completed the Scene 2 ARIA tabs pattern without changing approved copy or STORE_DATA.
**Why:** Reviewer protocol locked Frontend out of this artifact. The changes address only the three rejected accessibility defects while preserving the offline, single-file simulation constraints.

### 2026-09-03: Store Director simulation QA re-review verdict
**By:** Tester
**What:** Re-reviewed Lead's revision to `store-director-simulation.html` after the prior NO-GO. Verdict: **GO**. Defect 1 dark-theme contrast, Defect 2 heading hierarchy, and Defect 3 Scene 2 ARIA tabs are all fixed. Regression checks passed for offline/file:// behavior, zero console errors, light-theme contrast, STORE_DATA fidelity, approved copy, interactions, replay reset, reduced-motion support, chart labels, and aria-labels.
**Why:** Independent static and headless Edge/CDP verification found no remaining blocker and no new defects. Scope-creep check found no unauthorized data/copy/offline/runtime regression; note that the HTML artifact is untracked, so no literal git baseline diff was available.

## Governance

- All meaningful changes require team consensus
- Document architectural decisions here
- Keep history focused on work, decisions focused on direction
