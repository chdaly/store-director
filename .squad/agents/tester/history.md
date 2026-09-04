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


## 2026-09-03T19:45:00-05:00 — Simulation QA rejection and re-review
- Performed initial QA and issued NO-GO for dark-theme contrast, heading hierarchy, and Scene 2 ARIA tabs defects while confirming other runtime, fidelity, and offline checks passed.
- Re-reviewed Lead's non-author revision and issued GO after all defects were fixed with no regressions.
- Learning: dark-theme contrast was a real accessibility failure that light-theme-only testing completely missed; include theme-specific contrast checks in future demo QA.
- Propagated learning: independently parse and sum agent-produced numeric data where drill-down levels must reconcile; computation caught failures prose did not.

## 2026-09-03T22:30:00-05:00 — Copilot UI QA pass #1
- First QA pass for `store-director-copilot.html` issued NO-GO: interaction rewiring mostly passed, all Recent items loaded full prior conversations, self-containment/runtime-network/console checks passed, and numeric integrity including 14h/9h reconciliation passed.
- Blocking learnings: fixed-height disclosures are unsafe on mobile even when computed contrast is excellent; always visually inspect the smallest viewport for trust/safety text clipping or overlap.
- Responsive learning: document-level horizontal-scroll checks can pass while a clipped overflow-hidden parent hides content; inspect element bounding boxes against viewport and screenshots.
- Accessibility learning: state feedback/popovers do not replace a visible focus ring on the focused control; expander patterns need explicit `aria-expanded` and `aria-controls`.

## 2026-09-03T22:55:00-05:00 — Copilot UI QA re-review GO
- Re-reviewed Lead's non-author fixes to `store-director-copilot.html` and issued GO. All four prior findings resolved: mobile disclosure, 1024 KPI clipping, composer focus ring, and prompt-tray ARIA.
- Re-ran full click-response audit: no dead controls. The only prior “mostly works” exception was the composer input, which now responds with near feedback, opens the tray, flips aria-expanded, and has a visible focus-within ring.
- Learning: citation-looking chips should be explicitly classified in QA. Here they are non-interactive spans with no pointer cursor and no tab stop, so they are not dead controls.
