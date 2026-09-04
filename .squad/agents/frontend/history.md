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


## 2026-09-03T19:45:00-05:00 — Initial single-file simulation build
- Built `store-director-simulation.html` as a self-contained offline HTML artifact with inline CSS, JavaScript, SVG charts, embedded STORE_DATA, and guided interactions.
- Tester rejected the first build factually for one Major dark-theme contrast defect and two Minor accessibility defects. Under reviewer protocol, Frontend was locked out from revising the authored artifact; Lead owned the repair.
- Learning: run dark-theme contrast checks and complete ARIA interaction patterns before QA handoff, especially for persistent trust/disclosure text.
- Propagated learning: data embedded in the artifact should be mechanically reconciled because cross-level arithmetic errors can survive prose review.
