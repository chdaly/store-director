# 🔴 Red — RAI review for high-fidelity Copilot UI mockup

**Reviewer:** Rai, Responsible AI Reviewer  
**Date:** 2026-09-03T21:54:58-05:00  
**Artifact:** `store-director-copilot.html`  
**Review type:** Fresh review of the first-person M365 Copilot-style Store Director morning brief. Prior Green for `store-director-simulation.html` does **not** apply.

## Verdict

🔴 **Red** — do not ship this artifact until the simulation/product-status disclosure is made persistent, mobile-safe, and explicit that this is not a live M365 Copilot capability or Microsoft roadmap commitment.

**Reviewer lockout:** original author is Frontend, so Frontend is locked out of the next revision cycle for this rejected artifact.  
**Recommended fix agent:** **Lead** — the defect is primarily structural/responsive disclosure architecture, with minor copy updates. Narrative can later review wording if Lead requests it, but the revision owner should be non-Frontend.

## Evidence reviewed

- Source: `store-director-copilot.html` lines 109, 124-151, 711-717, 720-742.
- Screenshots/text captured with Playwright from `file:///C:/GitHub/store-director/store-director-copilot.html` into `.squad/.scratch/visual-qa/rai-copilot/`.
- Viewed screenshots for: morning brief, composer tray, five suggested-prompt responses, six Recent entries, light theme, dark theme, and mobile/narrow viewports.
- Key evidence screenshots:
  - `01-morning-light.png` — desktop disclosure visible.
  - `14-morning-dark.png` and `15-composer-tray-dark.png` — dark disclosure visible on desktop.
  - `16-mobile-morning-light.png` / `18-mobile-morning-dark.png` — mobile top disclosure text is clipped/truncated while high-fidelity Copilot chrome remains visible.
  - `17-mobile-composer-tray-light.png` — mid-scroll mobile screenshot contains operational claims and Microsoft-like Copilot chrome with no visible simulation/product-status disclosure or reliability footer.

## 🔴 Critical finding 1 — Disclosure is not persistent or mobile-safe enough for high-fidelity Microsoft trade dress

**What is wrong**

The artifact uses deliberately high-fidelity Microsoft/Copilot trade dress: Copilot name in the top chrome, Copilot-style gradient mark, chat history rail, Work tenant affordance, assistant avatar treatment, composer, prompt chips, and inline Power BI-style visuals. Desktop views show a simulation banner and footer note, but the disclosure fails the stated bar for this higher-risk artifact:

- On narrow mobile (`390px`), the top disclosure is horizontally clipped/truncated. The `Simulation` badge remains visible, but the explanatory text is not fully readable.
- On mobile after scrolling (`17-mobile-composer-tray-light.png`), the top disclosure has scrolled away and the footer note is not visible. A forwarded screenshot can show the Copilot-like UI and operational recommendations without any visible label that it is synthetic or non-product.
- The primary banner says the data is synthetic and not Target operational data, but it does **not** explicitly say this is not a real/live M365 Copilot product capability, prototype commitment, or Microsoft roadmap promise.

**Why it matters**

Because the mockup is first-person and intentionally resembles a live M365 Copilot surface, viewers may reasonably interpret a screenshot as a shipping Microsoft capability or committed roadmap item. The risk is materially higher than the prior presentation artifact: the UI itself appears to be speaking directly to a Store Director, not a narrator explaining a concept.

**How to fix**

Lead should make the disclosure persistent and responsive, not merely present at page top/footer. Concrete requirements:

1. Keep a visible disclosure in **every viewport and scroll position**. On mobile, use `position: sticky`/`fixed` or a persistent in-app simulation pill that does not scroll away.
2. Shorten/wrap the mobile disclosure so it remains readable at ~390px width.
3. Add explicit product-status wording near the Copilot brand/chrome and in the footer/composer area.
4. Ensure the disclosure is visible in light and dark theme with sufficient contrast.
5. Ensure the message survives cropped screenshots of any single state.

Suggested replacement wording for the persistent banner/pill:

> **Simulation — not a live M365 Copilot product or Microsoft commitment. Synthetic retail data only; verify sources before action.**

If a retailer disclaimer remains needed, prefer neutral wording in the visible UI:

> **Synthetic retail data only — not real retailer operational data.**

## 🟡 Advisory finding 1 — Visible Target reference is riskier in this first-person/high-fidelity frame

**What is wrong**

The visible banner currently says values are “not Target operational data.” Prior `SIM-TGT-9001` / “Bullseye Bay” items were explicitly deferred under Option A and are not re-litigated as Critical. However, in this new artifact the brand reference appears in the persistent visible chrome of a Microsoft-like first-person screen.

**Why it matters**

Even a negative disclaimer can anchor viewers to a specific retailer when screenshots are forwarded. This conflicts with the active naming decision that body copy should use neutral “Store Director” language and reserve “Target” for research context.

**How to fix**

Replace visible UI wording with “real retailer operational data” or “customer operational data.” If the team must retain the Target-specific disclaimer for internal Innovation Hub clarity, document that exception explicitly in decisions.

## Passed checks

### Causal overreach

Pass. I reviewed rendered text in the morning brief, all Recent entries, all five suggested-prompt responses, and composer-tray states. The primary Guest/Operations relationship is framed as “signals,” “observation target,” “watchpoint,” or “testing,” not proven causation. The main morning brief includes the guardrail on the same desktop view as the causal-risk language: “This simulation treats the Guest and Operations relationship as a signal worth testing. It does not assert proven causation.” Prompt responses also use “not a proven single cause,” “test in person,” and “testing the pickup handoff signal.”

### AI reliability / human judgment

Partial pass, subject to Critical finding 1. The artifact includes “Copilot can make mistakes,” source chips, and human-in-the-loop language such as “walk,” “watch,” “check,” “test in person,” and “verify role clarity.” These are meaningful, not merely decorative, on desktop. They are not sufficient on mobile because the persistent product/simulation label disappears in scrolled states.

### Labor and workforce implications

Pass. The artifact discusses payroll, coverage gaps, call-outs, and leaders without naming individuals or blaming hourly workers. Recommendations remain framed as human observation, role clarity, and leader follow-up rather than automated scheduling or worker surveillance.

### Guest / employee PII

Pass. I found no real guest names, employee names, phone numbers, email addresses, employee IDs, or realistic personal identifiers. Role labels like “Closing Team Leader” are not individually identifying.

### Credentials / injection / inline JavaScript

Pass for RAI/security scope. I found no hardcoded secrets, API keys, tokens, passwords, network calls, external dependencies, `eval`, command execution, or storage of user input. `innerHTML` is used with hardcoded scripted response constants, not arbitrary user input; the composer clears free text and routes only to scripted prompts.

## Final gate

🔴 **Red.** Fix the persistent disclosure/product-status issue before ship. Recommended revision owner: **Lead**. Frontend is locked out for the next revision cycle for this artifact.

---

# 🟡 Yellow — RAI re-review after Lead disclosure fix

**Reviewer:** Rai, Responsible AI Reviewer  
**Date:** 2026-09-03T22:16:19-05:00  
**Artifact:** `store-director-copilot.html`  
**Review type:** Re-review of prior Critical after Lead revision. Frontend remained locked out per reviewer protocol.

## Verdict

🟡 **Yellow** — the prior 🔴 Critical is resolved. Work may proceed from the RAI gate with one non-blocking Advisory still open: the pinned disclosure still names Target in visible UI.

## Evidence reviewed

- Source reviewed: `store-director-copilot.html` disclosure/layout and interaction code around lines 16-113, 124-152, and 715-748.
- Screenshots and rendered text captured to `.squad/.scratch/visual-qa/rai-rereview/`.
- Playwright geometry validation covered **108 disclosure samples**: 3 viewports (`1440x900`, `1024x768`, `390x844`) × 2 themes × 6 Recent conversations × 3 scroll positions (`top`, `mid`, `bottom`). Relevant disclosure failures: **0**.
- Prompt paths were also captured for five top prompt chips and five composer-tray prompt activations across desktop/mobile and light/dark themes.
- Console errors: **0**. Prompt tray ARIA check passed: `aria-controls="composerPrompts"`; `aria-expanded` toggles `false → true → false`.

## Prior 🔴 Critical — Fixed

**Prior issue:** The high-fidelity Copilot-style UI could be screenshotted on mobile/scrolled states without a complete visible simulation label.

**Current status:** Fixed. The disclosure banner is fixed at the top of the viewport, remains legible in desktop/tablet/mobile and light/dark themes, and does not scroll away in Recent conversations, prompt responses, or composer-tray states. I visually inspected representative top/mid/bottom screenshots, including mobile mid-scroll and dark-theme states, and confirmed the banner remains unmissable.

**New-overlap check:** Pass. At top-of-page load, the fixed banner does not cover the Copilot header or first conversation line. In scrolled mobile states, content can pass underneath the fixed banner, but the banner remains readable and the current viewport still presents content below it; I found no new RAI issue from overlap/crowding.

## Regression checks

### Causal overreach — Pass

No regression found. The morning brief still places the causal guardrail on the same view as the Guest/Operations relationship:

> This simulation treats the Guest and Operations relationship as a signal worth testing. It does not assert proven causation.

Rendered prompt and Recent states continue to use signal/testing language rather than proven causation:

- `priority`: “observation target, not a proven single cause.”
- `saturday`: “the afternoon row is the one to test in person.”
- `huddle`: “testing the pickup handoff signal.”
- `weekend`: “watchpoint,” not root cause.
- `payroll`: explicitly warns not to overread the weekly payroll card.
- `driveup`: “Use the staffing lens carefully.”

### AI reliability / human judgment — Pass

No regression. The footer still says “Copilot can make mistakes,” source chips remain visible, and recommendations are framed as human observation and verification: walk, watch, check, test in person, and verify role clarity.

### Labor and workforce implications — Pass

No regression. Payroll and coverage language remains operational without blaming or surveilling named workers. The artifact recommends human leader review, not automated scheduling or discipline.

### Guest / employee PII — Pass

No real guest or employee identifiers found. Role labels and aggregate synthetic operational metrics are not individually identifying.

### Credentials / injection — Pass

No hardcoded secrets, network calls, `eval`, command execution, or unsanitized user input path found. `innerHTML` remains limited to hardcoded scripted content; free-text composer input is immediately cleared and does not flow into rendered HTML.

## 🟡 Advisory — Visible Target reference is now more prominent

**What is wrong**

The pinned disclosure still says the values “are not Target operational data.” This is not a Critical under the accepted Option A scope and internal Innovation Hub audience, and the prior `SIM-TGT-9001` / “Bullseye Bay” item remains deferred. However, the Target reference is now pinned to every screen and every scroll position, so the Advisory is more salient than before.

**Why it matters**

A persistent retailer-specific disclaimer can anchor forwarded screenshots to a real retailer even when the statement is negative. That increases brand sensitivity in a high-fidelity Microsoft-style first-person interface.

**How to fix**

Recommended replacement wording:

> **Illustrative simulation data only. Store, sales, labor, guest, and operations values are synthetic and are not real retailer operational data.**

Alternative if the team wants to preserve the product-status caveat in the same banner:

> **Simulation only. Not a live M365 Copilot product or Microsoft commitment. Synthetic retail data; not real retailer operational data.**

If the user chooses to retain the Target wording for internal Innovation Hub clarity, document that as an explicit exception and proceed.

## Final gate

🟡 **Yellow.** Prior Critical fixed; no new Critical found. Only the Target wording Advisory remains, pending user decision.
