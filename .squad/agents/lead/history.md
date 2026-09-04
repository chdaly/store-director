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


## 2026-09-03T19:45:00-05:00 — Store Director simulation planning and QA revision
- Planned the approved 8-scene guided walkthrough and resolved scope defaults around retail credibility, time claims, four-pillar store health, and neutral naming.
- Took non-author ownership of the QA revision after reviewer lockout and fixed only the approved accessibility defects.
- Learning: reviewer lockout works best when the revision owner preserves source data/copy constraints and changes only rejected defects.
- Propagated learning: verify agent-produced numeric data by computation; prose review missed cross-level arithmetic defects twice.
- Propagated learning: dark-theme contrast must be tested directly; light-theme-only testing missed a real accessibility failure.

## 2026-09-03T22:01:35-05:00 — Copilot mockup disclosure persistence fix
- Took independent non-author revision ownership after Rai's red verdict locked Frontend out of `store-director-copilot.html`.
- Learning: for high-fidelity product mockups, the synthetic-data disclosure must be viewport-fixed or equivalently persistent; a static banner can pass desktop QA while failing mobile screenshots.
- Learning: mobile disclosure checks must measure child text geometry, not just the banner box; a fixed-height flex banner can have a visible container while its wrapped text is clipped above the viewport.
- Learning: visual contact-sheet review remains mandatory even after geometry, console, network, and contrast checks pass.

## 2026-09-03T22:09:46-05:00 — Copilot UI QA follow-up fixes
- Fixed Tester's remaining `store-director-copilot.html` QA findings as the independent lockout owner: tablet KPI clipping, composer focus visibility, and prompt tray ARIA state.
- Learning: after wrapping responsive content, verify both axes; a horizontal clipping fix can accidentally push required executive-viewport content below the visible viewport.
- Learning: focus-ring contrast must be checked per theme and per adjacent surface; the light-theme purple ring passed while the same ring failed dark active rail surfaces.
- Learning: expander ARIA must be runtime-verified through actual toggles, not just static attributes in source.

📌 Team update (2026-09-03T19:45:00-05:00): Reviewer lockout worked: Lead owned revisions after Frontend-authored Copilot UI was rejected, fixing persistent disclosure, KPI reflow, focus indicators, and prompt tray ARIA wiring.

📌 Team update (2026-09-03T19:45:00-05:00): Verification must combine computation with rendered-output inspection; do not accept prose self-reports when UI perception, geometry, data arithmetic, RAI language, or screenshots are the actual risk.
