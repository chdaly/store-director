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

### 2026-09-03: Rebuild as a first-person M365 Copilot UI, not a narrated deck
**By:** Squad (Coordinator), on user direction (Chris Daly)

**What:** The 8-scene guided presentation (`store-director-simulation.html`) is scrapped. The artifact is rebuilt as a full-screen, high-fidelity simulation of the M365 Copilot chat app, seen from the Store Director's own screen. Confirmed parameters:

- **Surface:** M365 Copilot standalone chat app
- **Fidelity:** HIGH — recognizably the real Copilot UI
- **Shape:** Single landing view. The morning brief is already present on open; no intro, no scene navigation, no progress bar
- **Interaction:** Clickable suggested prompts driving canned responses
- **Visuals:** Power BI-style charts and cards inline within Copilot responses
- **Salvage:** Reuse the verified dataset and the RAI-cleared narrative content; rebuild only the UI

**Why:** The prior artifact was a presentation *about* the Store Director's morning. The user asked for the Store Director's *screen* — what they actually see in M365 Copilot as they start the day. Third-person framing was the core defect, not the visuals.

### 2026-09-03: Trade-dress constraint superseded for Microsoft only
**By:** Squad (Coordinator), on user direction (Chris Daly)

**What:** The earlier binding constraint "no Microsoft or Target logos or trade dress" is relaxed for **Microsoft/Copilot UI only**, to permit a high-fidelity Copilot look: Copilot gradient accent, Fluent-style surfaces, Segoe UI system font, and standard Copilot chat chrome.

**Still binding:** No Target logos or trade dress. No real Target data. All data synthetic and visibly disclosed.

**Why:** The user chose high fidelity, which cannot be achieved while avoiding all Microsoft visual identity.

**Consequence — raises RAI risk:** A convincing Copilot mockup makes it materially easier for a viewer to believe this is a shipping capability. The synthetic-data and simulation disclosure therefore becomes MORE load-bearing, not less, and must remain visible in the primary view without scrolling. Requires a fresh Rai pass; prior 🟢 Green does not carry over to the new artifact.

### 2026-09-03: Data RAI metadata revision
**By:** Data
**What:** Neutralized residual causal-claim language in the embedded `STORE_DATA` metadata and synchronized `docs/simulation-dataset.md` to the same hypothesis-signal framing without changing dataset numbers or user-visible simulation copy.
**Why:** Rai's second Red found metadata prose that contradicted the visible guardrail that Guest and Operations are a signal worth testing, not proven causation.

### 2026-09-03: Clarify chart evidence for visual QA fixes
**By:** Data
**What:** Revised the simulation chart presentation so Saturday afternoon gap-hour cells are labeled as all-department totals, with Fulfillment/Pickup surfaced as the 9h share of the 14h total. Also separated chart legends/annotations from plotted lines and let the Scene 4 brief panel size to revealed content.
**Why:** Retail operators need the highlighted evidence to reconcile with the spoken/narrative 9h Fulfillment/Pickup signal without mental arithmetic, while preserving the approved STORE_DATA values and locked narrative wording.

### 2026-09-03: Store Director simulation fact-check findings
**By:** Fact Checker
**What:** The core Store Director story in `store-director-simulation.html` is supported by the background research, and the permitted quantified proof point (~12 projects / ~50 dates) is accurate. No contradictory claims or extra quantified real-world time-saved claims were found. However, several operational details are unverified against the research: exact first-hour clock times, 95% pickup service goal, specific source-system labels, daypart vocabulary, metric terms such as earned hours/call-outs/guest score/backroom task completion, and detailed pickup handoff/process language. Product docs support Copilot/Power BI report summarization and semantic-model assistance, but the cross-source prescribed morning brief requires validation of data estate, connectors, permissions, licensing, and governance.
**Why:** The demo is strongest when it stays at the researched level of fragmentation, translation/orchestration, and observation/coaching capacity. Invented retail precision could be read by client stakeholders as hallucinated realism and damage credibility.

### 2026-09-03: M365 Copilot landing view
#### Frontend decision: M365 Copilot landing view

**By:** Frontend
**Date:** 2026-09-03T21:22:30-05:00

##### Decision
Rebuilt the rejected presentation as a first-person M365 Copilot standalone chat surface in `store-director-copilot.html`. The morning brief is present on load, with suggested prompt chips adding grounded canned responses.

##### Rationale
The user rejected third-person guided scenes. The new artifact keeps the verified dataset and narrative substance but reframes the experience as the Store Director's own Copilot screen. It preserves the synthetic-data disclosure, Guest/Operations causality guardrail, and 14h vs 9h reconciliation inside the landing brief.

##### Implementation notes
Single self-contained HTML with inline CSS, inline JavaScript, inline SVG/CSS visuals, no external assets, and light/dark theme support.

### 2026-09-03: Copilot mockup left-menu interactions repaired
**By:** Frontend
**What:** `store-director-copilot.html` now treats chat history as real navigation: Morning brief is the default active conversation, and Weekend recap, Payroll variance, Q3 remodel timeline, Drive-up observations, and Leader huddle notes each load distinct grounded prior conversations. Out-of-scope rail, new-chat, and composer controls now show anchored local popovers or open scripted prompts instead of a distant generic hint.
**Why:** Clickable chrome that only changed low-contrast text far from the clicked control read as broken. The artifact now gives every visible interactive control a perceptible, local response while preserving the single-file offline constraint and the verified STORE_DATA object.

### 2026-09-03: Copilot mockup QA fixes preserve disclosure and accessibility controls
**By:** Lead
**What:** Fixed the remaining QA findings in `store-director-copilot.html`: the 1024px KPI strip now scales all five KPI cards into the available content width, keyboard focus uses a theme-aware 3px visible ring including the composer input, and the prompt tray expander now exposes `aria-controls` plus synchronized `aria-expanded` state.
**Why:** The high-fidelity Copilot mockup needs executive-laptop readability and keyboard/screen-reader affordances without changing approved synthetic data, causal guardrail language, offline behavior, or the persistent disclosure control.

### 2026-09-03: Persistent simulation disclosure for high-fidelity Copilot mockup
**By:** Lead
**What:** The top synthetic-data disclosure in `store-director-copilot.html` is now fixed at the top of the viewport, with the app offset by a shared disclosure-height variable and a taller mobile reserve so the full banner is visible at 390x844 without covering the Copilot header.
**Why:** The artifact intentionally uses high-fidelity M365 Copilot styling, so every screenshot at every scroll position must remain unmistakably labeled as a simulation.

### 2026-09-03: RAI causality revision for simulation
**By:** Narrative
**What:** Applied Rai Critical 1 and Critical 2 only: added a visible Scene 4 causality guardrail, reframed Scene 4 Stage 1 and Stage 3 as hypothesis/observation language, and renamed/reworded embedded narrative metadata from causal/root-cause claims to hypothesis signals.
**Why:** Keeps the Store Director simulation within the binding claim boundary that Guest and Operations relationships are signals worth testing, not proven causation, while preserving the approved synthetic dataset and deferred advisory/fact-check items.

### 2026-09-03: Neutralized persistent retailer reference in disclosure copy
**By:** Narrative
**What:** Replaced the persistent disclosure banner wording “not Target operational data” with “not real retailer operational data” in `store-director-copilot.html`, and aligned the embedded disclosure wording plus the store disclosure string to avoid naming the retailer while leaving `SIM-TGT-9001` and “Bullseye Bay Innovation Store” unchanged.
**Why:** The fixed disclosure banner appears in every viewport, scroll position, and theme. Neutral wording preserves synthetic-data force without pairing a named retailer with high-fidelity Copilot chrome in forwarded screenshots.

### 2026-09-03: Copilot UI requires persistent product-simulation disclosure
**By:** Rai
**What:** Rejected `store-director-copilot.html` until the high-fidelity Copilot-style UI has a persistent, mobile-safe disclosure that states it is a simulation, not a live M365 Copilot product or Microsoft commitment, with synthetic data only.
**Why:** The first-person, high-fidelity Microsoft trade dress can be mistaken for a shipping capability when screenshots are forwarded, especially on mobile/scrolled views where the existing disclosure disappears or truncates. Frontend authored the current artifact and is locked out of the next revision cycle; Lead is the recommended fix owner.

### 2026-09-03: RAI review decision — Store Director simulation
**By:** Rai
**What:** Rejected `store-director-simulation.html` pending visible causal-framing guardrails in the staged morning brief and softer embedded metadata that avoids asserting root cause or causal chains as fact.

#### Required revision ownership

Reviewer protocol requires a non-author revision owner for rejected work.

#### Why

The simulation may use synthetic retail signals to guide investigation, but it must not imply proven causality or operational certainty beyond the documented scenario evidence.

### 2026-09-03: Store Director simulation
#### RAI re-review decision — Store Director simulation

**By:** Rai  
**Date:** 2026-09-03T19:51:38-05:00  
**Artifact:** `store-director-simulation.html`  
**Decision:** 🔴 Red — prior Critical 1 is fixed; prior Critical 2 is partially fixed and still blocks ship.

##### Per-Critical status

| Prior Critical | Status |
|---|---|
| Critical 1 — Scene 4 guardrail prominence and visible causal framing | Fixed |
| Critical 2 — Embedded metadata asserts root cause / causal chain | Partially Fixed |

##### What

Scene 4 now has the required visible guardrail before the staged morning brief, and the visible copy no longer asserts the Guest↔Operations relationship as proven causation. The requested metadata key rename and two exact softened metadata strings are present.

The full embedded `STORE_DATA` re-scan still found causal/root-cause phrasing in metadata:

- one string says a pickup metric was "generating" guest recovery incidents;
- one string says Saturday backroom task completion was "leaving" Sunday on-shelf availability depressed;
- one department signal says reshop did not "drive" the primary guest dip.

##### Reviewer protocol impact

This is a second Red on the artifact. `Frontend`, `Lead`, and `Narrative` are now locked out of revising this artifact. Escalate to the user for next-owner direction rather than assigning a locked-out author.

##### Scope notes

The deferred `SIM-TGT-9001` / `Bullseye Bay Innovation Store` advisory remains open by user choice and is not a defect in this pass. No unauthorized change to that deferred item was found.

### 2026-09-03: RAI re-review #2 decision — Store Director simulation
**By:** Rai
**What:** Re-reviewed the Store Director simulation after the second RAI revision pass. The remaining causal/root-cause language blocker was cleared; deferred identity and precision advisories remained accepted internal-audience risks rather than ship blockers.

#### Per-Critical status

Previously blocking causal-overreach findings were cleared.

#### Scope notes

The deferred `SIM-TGT-9001` / Bullseye Bay identity item and other accepted internal-audience advisories remain open for any client-facing use.

#### Gate

RAI no longer blocked the internal Innovation Hub simulation after this pass.

### 2026-09-03: Store Director Copilot UI QA re-review verdict
**By:** Tester
**What:** Re-reviewed Lead's fixes to `store-director-copilot.html`. Verdict: **GO**. The prior Critical disclosure clipping, Major 1024px KPI clipping, Major composer focus-indicator defect, and Minor prompt-tray ARIA defect are resolved. Regression checks passed for click-response behavior, self-containment, zero runtime network requests, zero console/page errors, numeric integrity, 14h/9h reconciliation, responsive/theme rendering, and keyboard traversal.
**Why:** The artifact now meets the offline, self-contained, high-fidelity simulation QA bar at the required viewports and themes.

### 2026-09-03: Store Director Copilot UI QA pass #1
**By:** Tester
**What:** Rejected `store-director-copilot.html` with a NO-GO after first QA pass. Click-response rewiring mostly passes, self-containment/runtime/network checks pass, console errors are zero, and numeric reconciliation passes. Blocking defects: mobile synthetic-data disclosure clipping, 1024x768 KPI clipping, missing composer input focus indicator, and missing prompt-tray expander ARIA.
**Why:** The disclosure is load-bearing for trust/safety in a high-fidelity mockup, and the artifact must work at required viewport/theme combinations with basic keyboard and ARIA accessibility.

### 2026-09-03: Simulation rendered visual QA verdict
**By:** Tester
**What:** Completed rendered Playwright visual QA for `store-director-simulation.html` across projector, laptop, and narrow viewports in light/dark themes. Verdict: **Ship with noted issues**. Scene 4 highlight synchronization mostly lands visually, but projector delivery has noted issues: Scene 4's final decision payoff falls below the first fold, Scene 5 chart labels collide, Scene 6 table is too dense for back-row legibility, and Scene 4 KPI cards wrap awkwardly at projector/narrow widths.
**Why:** Prior verification was headless DOM/contrast only. Real screenshots show the artifact is polished and dark mode looks intentional, but projector pacing/legibility needs Data-owned compression if this is presented without scrolling.

## Governance

- All meaningful changes require team consensus
- Document architectural decisions here
- Keep history focused on work, decisions focused on direction
