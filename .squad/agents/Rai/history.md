# Project Context

- **Project:** store-director
- **Created:** 2026-09-03

## Core Context

Agent Rai initialized and ready for work.

## Recent Updates

📌 Team initialized on 2026-09-03

## Learnings

Initial setup complete.

## 2026-09-03 — Copilot UI high-fidelity disclosure review

- In first-person, high-fidelity product mockups, a generic data-only disclosure is not enough. The UI must also state product status: not live, not a Microsoft commitment, not for operational decisions.
- Desktop-only persistence is insufficient. Mobile/narrow screenshots and mid-scroll states must be reviewed visually because top banners can clip or scroll away even when `innerText` contains the right words.
- Causal-overreach review should include rendered prompt responses and Recent conversations; source scans alone can miss whether guardrails are actually on the same visible view.

## 2026-09-03 — Disclosure re-review after fixed banner

- Persistent disclosure fixes should be verified both by geometry checks and by visual inspection. Geometry can produce false positives for scrolled content under a fixed banner; RAI-relevant checks are whether the disclosure remains visible/legible and whether top-of-page content starts below it.
- A formerly advisory brand reference can become more salient when pinned globally, but under explicit user deferral it remains Advisory unless the content changes into a deceptive or harmful claim.

📌 Team update (2026-09-03T19:45:00-05:00): Copilot UI RAI Red became Yellow after disclosure became fixed/persistent with strong contrast and app offset; no new Criticals/regressions, with advisory to neutralize retailer wording accepted.
