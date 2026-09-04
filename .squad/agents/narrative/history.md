# Project Context

- **Owner:** Chris Daly
- **Project:** store-director — a shareable, fully self-contained HTML page that simulates how M365 Copilot integrated with Power BI transforms how Target Store Directors consume data. The core story: SDs spend significant morning effort preparing and reviewing reports that could instead be delivered as narrative in M365 Copilot.
- **Stack:** Single-file HTML/CSS/JS (no build step, no external dependencies, must run from `file://`)
- **Background research:** `docs/store-director-background/` — persona materials, compiled SD research, Innovation Hub brief, and parallel Supply Chain/Site Director findings
- **Created:** 2026-09-03T18:11:16-05:00

## Key grounding facts

- Flagship use case: the store-specific morning brief — walk in already oriented instead of digging through email at home before the shift
- Signature proof point: ~12 projects, ~50 dates, multiple pyramid owners, no upstream deconfliction
- SDs are already active Copilot users (best practices, leadership development, calendar dates, guest feedback analysis, team maps)
- One SD built their own dashboard because the standard one was not useful
- Outcome to lead with: coaching capacity and store observations. Time saved is the mechanism, not the headline
- All data in the artifact is illustrative/synthetic — never presented as real Target data

## Learnings

<!-- Append new learnings below. Each entry is something lasting about the project. -->


## 2026-09-03T19:45:00-05:00 — Simulation copy and voice system
- Produced scene copy, control/chart accessibility inventory, and voice-and-tone guidance for the Store Director walkthrough.
- Used a `{FULFILLMENT_GAP_HRS}` placeholder while Data repaired the metric, then aligned to the corrected 9-hour Fulfillment gap.
- Learning: placeholders are safe only when explicitly named and later resolved before build handoff.
- Propagated learning: numeric claims in copy should be tied to computed dataset checks, not prose interpretation alone.
- Propagated learning: synthetic-data disclosure must remain readable in dark mode because it is both an accessibility and trust requirement.

## 2026-09-03T23:19:57-05:00 — Retailer-name neutralization in persistent disclosure
- Changed the fixed synthetic-data disclosure from “not Target operational data” to “not real retailer operational data.”
- Also neutralized embedded retailer-name disclosure strings while preserving the explicitly deferred fictional identifiers `SIM-TGT-9001` and “Bullseye Bay Innovation Store.”
- Learning: fixed, always-visible disclosure copy needs brand-sensitivity review because screenshots preserve the pairing of simulated data with recognizable product chrome.
- Verification learning: geometry checks are necessary but insufficient for longer banner strings; viewport screenshots must be visually inspected, especially at 390px mobile width.

📌 Team update (2026-09-03T19:45:00-05:00): User accepted neutral retailer wording: user-visible disclosure now says "real retailer operational data" because the persistent fixed banner made brand specificity more prominent.

📌 Team update (2026-09-03T19:45:00-05:00): The six prior conversations intentionally remain single-exchange texture; do not deepen them unless the user reverses that decision.

📌 Team update (2026-09-03T19:45:00-05:00): Verification must combine computation with rendered-output inspection; do not accept prose self-reports when UI perception, geometry, data arithmetic, RAI language, or screenshots are the actual risk.
