# Simulation Visual QA

**Overall visual verdict: Ship with noted issues.**  
The artifact looks credible and polished in both themes, and the Scene 4 synchronization mostly lands. It is not visually broken. The remaining risk is projector delivery: several key evidence/decision details require scrolling or become dense enough that a back-row viewer will not read them comfortably.

## Defect table

| # | Severity | Screenshot | What is visually wrong | Recommended fix / owner |
|---|---|---|---|---|
| 1 | Major | `projector-light-scene4-viewport.png`, `projector-dark-scene4-viewport.png` | Scene 4's final decision evidence is not above the first projector fold. The guardrail is visible, but by the time stage 5 is revealed the decision/initiative cards that complete the synchronized story sit below the no-scroll view. The synchronization works in the full-page screenshot, but the projector view asks the presenter/audience to scroll during the crux. | Data: restructure Scene 4 for projector use. Keep the active stage text and active evidence card in the first 720px, or use a single pinned active evidence panel instead of stacking all revealed stages. |
| 2 | Major | `projector-light-scene5.png`, `projector-dark-scene5.png` | The Scene 5 drill-down chart labels collide with bars and with each other. From a projected view, the values read as mush even though the surrounding narrative is legible. | Data: redesign the SVG chart with more label gutters, fewer labels, larger text, or a table/card alternative for the four dayparts. |
| 3 | Major | `projector-light-scene6.png`, `projector-dark-scene6.png` | Scene 6's initiative-collision table is too dense for a conference-room projector. Headers and body cells are technically readable on a monitor but not comfortably readable from the back of a room. | Data: convert the table into 3 stacked initiative cards or enlarge type and reduce columns. |
| 4 | Minor | `narrow-light-scene4-stage5.png`, `narrow-dark-scene4-stage5.png`, `projector-light-scene4-viewport.png` | Scene 4 KPI cards become skinny in the right rail; phrases like "Pickup on-time" and the KPI descriptions wrap awkwardly, making the evidence scan less polished. | Data: switch the KPI row to 2x2 earlier, or replace right-rail KPI cards with a compact horizontal summary at projector/narrow widths. |
| 5 | Minor | `projector-light-scene4-stage1.png` | Stage 1 highlights all four KPI cards. This is defensible as a "store health overview," but it is less intentional than the later one-to-one highlight changes. This is a judgment/taste issue, not an objective break. | Data / Narrative: consider highlighting Financials as de-emphasized and Team/Operations as active, or add a short visual label explaining why all pillars are lit. |
| 6 | Minor | `projector-light-scene1-viewport.png`, `projector-dark-scene1-viewport.png` | Scene 1 has a strong first impression, but the CTA and final timeline item sit below the first projector fold at 1280x720. The main point is not buried, but the first interaction is not immediately visible without scrolling. | Data: reduce hero vertical spacing or timeline row height at projector size. |

## Scene 4 highlight synchronization

**Judgment: the synchronization lands, but only when the full Scene 4 layout is visible.** The highlight is visually noticeable: blue border, outer glow, and slight elevation are strong enough to read as intentional in both light and dark modes.

- `projector-light-scene4-stage1.png`: highlights the KPI row broadly. It reads as "start with the four-pillar store view," but it is the least precise stage because every KPI appears active.
- `projector-light-scene4-stage2.png`: Guest, Operations, and the trend chart become the visual focus. This matches the narrative about Saturday guest/pickup/backroom deterioration.
- `projector-light-scene4-stage3.png`: Team/Operations and the coverage chart become the focus. This matches the labor-placement explanation and is the clearest evidence synchronization.
- `projector-light-scene4-stage4.png`: Today's decision card is highlighted and matches the narrative's "make pickup first" recommendation.
- `projector-light-scene4-stage5.png`: Initiative collision card is highlighted and matches the tradeoff recommendation. The extra Team KPI highlight slightly dilutes focus, but it does not point to the wrong thing.

The core failure risk is not the highlight styling; it is viewport management. In `projector-light-scene4-viewport.png`, the top no-scroll projector view does not show the stage 4/5 decision cards. If a presenter does not scroll, the strongest synchronization moment is below the fold.

## Projector legibility at 1280x720

1. **Scene 1 — `projector-light-scene1.png`, `projector-dark-scene1.png`:** Hero headline and lede are excellent. Timeline rows are legible. The CTA is below the no-scroll fold in `projector-light-scene1-viewport.png`.
2. **Scene 2 — `projector-light-scene2.png`, `projector-dark-scene2.png`:** Headline/tabs are legible. The leader recap bullets are monitor-readable but marginal for a back-row projector viewer.
3. **Scene 3 — `projector-light-scene3.png`, `projector-dark-scene3.png`:** Strong, clear composition. KPI-like ledger rows and the unchecked floor-walk card read well.
4. **Scene 4 — `projector-light-scene4.png`, `projector-dark-scene4.png`:** Narrative text is large enough. KPI numbers are dominant. The KPI descriptions wrap too narrowly; small chart labels are borderline. The guardrail line is above the fold and readable.
5. **Scene 5 — `projector-light-scene5.png`, `projector-dark-scene5.png`:** Narrative is readable. The drill-down chart is not projector-legible because labels collide.
6. **Scene 6 — `projector-light-scene6.png`, `projector-dark-scene6.png`:** Main heading/lede are readable. The table is too dense for room viewing.
7. **Scene 7 — `projector-light-scene7.png`, `projector-dark-scene7.png`:** Timeline comparison is projector-legible and visually clean.
8. **Scene 8 — `projector-light-scene8.png`, `projector-dark-scene8.png`:** Takeaways are legible; the scene feels lighter and clean.

## Above-the-fold observations

- The persistent top synthetic-data disclosure is visible in the first fold across tested scenes and themes.
- The repeated footer disclosure generally requires scrolling; that is acceptable because the top disclosure remains visible.
- Scene 4's RAI guardrail line is visible above the fold in `projector-light-scene4-viewport.png` and `projector-dark-scene4-viewport.png`.
- Scene 4 buries the stage 4/5 decision-card payoff below the first fold, which is the biggest projector risk.
- Scene 5 shows the main explanation and chart above the fold, but supporting signal cards are lower.
- Scene 6 shows the table first; the localized plan is visible in the full-page screenshot but competes with table density.

## Visual pacing

The 8-scene arc builds sensibly: strong hook, fragmented inputs, hidden cost, Copilot brief, drill-down, collisions, first-hour shift, executive close. Scene 4 is dramatically heavier than the others because it stacks all revealed stages plus all evidence cards. Scene 5 and Scene 6 are also data-heavy. This is acceptable for a guided artifact but needs projector-aware compression if the demo is meant to be presented without scrolling.

## Layout quality across viewports

No catastrophic overlap or broken responsive state appeared at projector, laptop, or narrow widths. Laptop views feel the most balanced. The narrow 1100px Scene 4 view (`narrow-light-scene4-stage5.png`, `narrow-dark-scene4-stage5.png`) is the weakest responsive state: right-rail KPI cards are skinny, labels wrap awkwardly, and the scene becomes very tall. Scene 7's toggle states remain clean in both laptop and narrow captures.

## Dark theme visual quality

Dark mode looks intentional, not merely contrast-compliant. Backgrounds, borders, pink CTA buttons, and blue highlights all remain readable. Charts remain generally visible, with the same Scene 5 label-collision problem as light mode. I did not see washed-out text, disappearing elements, or theme-specific layout failures.

## First-impression test

`projector-light-scene1.png`, `projector-dark-scene1.png`, `laptop-light-scene1.png`, and `narrow-light-scene1.png` make the artifact's purpose immediately clear: a Store Director arrives already oriented instead of assembling reports. It looks credible and polished, not like a rough prototype. The only first-impression issue is vertical pacing at projector height: the CTA is below the first fold.

## Screenshot inventory

### Projector, light
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-light-scene1.png` — Scene 1 full-page hero.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-light-scene1-viewport.png` — Scene 1 no-scroll projector viewport.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-light-scene2.png` — Scene 2 with Leader recap tab selected.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-light-scene3.png` — Scene 3 with leadership-impact reveal shown.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-light-scene4.png` — Scene 4 fully revealed.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-light-scene4-viewport.png` — Scene 4 fully revealed no-scroll projector viewport.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-light-scene4-stage1.png` — Scene 4 after stage 1 reveal.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-light-scene4-stage2.png` — Scene 4 after stage 2 reveal.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-light-scene4-stage3.png` — Scene 4 after stage 3 reveal.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-light-scene4-stage4.png` — Scene 4 after stage 4 reveal.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-light-scene4-stage5.png` — Scene 4 after stage 5 reveal.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-light-scene5.png` — Scene 5 with drill-down and supporting signals shown.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-light-scene6.png` — Scene 6 with localized plan shown.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-light-scene7.png` — Scene 7 with Today comparison shown.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-light-scene8.png` — Scene 8 takeaways.

### Projector, dark
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-dark-scene1.png` — Scene 1 full-page hero in dark theme.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-dark-scene1-viewport.png` — Scene 1 no-scroll projector viewport in dark theme.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-dark-scene2.png` — Scene 2 with Leader recap tab selected in dark theme.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-dark-scene3.png` — Scene 3 with leadership-impact reveal shown in dark theme.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-dark-scene4.png` — Scene 4 fully revealed in dark theme.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-dark-scene4-viewport.png` — Scene 4 fully revealed no-scroll projector viewport in dark theme.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-dark-scene5.png` — Scene 5 with drill-down and supporting signals shown in dark theme.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-dark-scene6.png` — Scene 6 with localized plan shown in dark theme.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-dark-scene7.png` — Scene 7 with Today comparison shown in dark theme.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\projector-dark-scene8.png` — Scene 8 takeaways in dark theme.

### Laptop
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\laptop-light-scene1.png` — Laptop light Scene 1.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\laptop-light-scene2-leader-recap.png` — Laptop light Scene 2 with non-default Leader recap tab.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\laptop-light-scene4-stage5.png` — Laptop light Scene 4 fully revealed.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\laptop-light-scene7-today.png` — Laptop light Scene 7 Today state.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\laptop-light-scene7-copilot.png` — Laptop light Scene 7 With Copilot state.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\laptop-dark-scene1.png` — Laptop dark Scene 1.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\laptop-dark-scene2-leader-recap.png` — Laptop dark Scene 2 with non-default Leader recap tab.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\laptop-dark-scene4-stage5.png` — Laptop dark Scene 4 fully revealed.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\laptop-dark-scene7-today.png` — Laptop dark Scene 7 Today state.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\laptop-dark-scene7-copilot.png` — Laptop dark Scene 7 With Copilot state.

### Narrow
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\narrow-light-scene1.png` — Narrow light Scene 1.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\narrow-light-scene2-leader-recap.png` — Narrow light Scene 2 with non-default Leader recap tab.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\narrow-light-scene4-stage5.png` — Narrow light Scene 4 fully revealed.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\narrow-light-scene7-today.png` — Narrow light Scene 7 Today state.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\narrow-light-scene7-copilot.png` — Narrow light Scene 7 With Copilot state.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\narrow-dark-scene1.png` — Narrow dark Scene 1.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\narrow-dark-scene2-leader-recap.png` — Narrow dark Scene 2 with non-default Leader recap tab.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\narrow-dark-scene4-stage5.png` — Narrow dark Scene 4 fully revealed.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\narrow-dark-scene7-today.png` — Narrow dark Scene 7 Today state.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\narrow-dark-scene7-copilot.png` — Narrow dark Scene 7 With Copilot state.

### Contact sheets / review aids
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\contact-projector-light.png` — Review contact sheet for all projector light scene captures.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\contact-projector-dark.png` — Review contact sheet for all projector dark scene captures.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\contact-scene4-stages.png` — Review contact sheet for Scene 4 stage-by-stage synchronization.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\contact-responsive-light.png` — Review contact sheet for laptop/narrow light captures.
- `C:\GitHub\store-director\.squad\.scratch\visual-qa\contact-responsive-dark.png` — Review contact sheet for laptop/narrow dark captures.
