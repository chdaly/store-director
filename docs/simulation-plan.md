# Store Director Copilot + Power BI Simulation Plan

**Prepared by:** Lead, Experience Lead  
**Requested by:** Chris Daly  
**Date:** 2026-09-03T18:27:50-05:00  
**Artifact target:** One self-contained `.html` file; no external dependencies; all data synthetic and visibly labeled.

## 1. The core moment

A Store Director starts the morning at home toggling through email, Excel-like reports, leader recaps, and scattered initiative dates; the page then snaps to the same morning with Copilot delivering a store-specific narrative brief beside Power BI-style visuals: "Your store is operationally stable, but guest friction is building at pickup and two initiative dates collide with a thin leadership coverage window; spend your first floor walk with Fulfillment and coach the closing TL on the recovery plan." The vivid before/after is not "AI makes charts." It is "the SD walks in already oriented and can spend the first hour observing and coaching instead of assembling the day." This is justified by `Target-SD-Research-Compiled.md` and `Target-SD-Innovation-Hub-Brief.md`: the flagship Tier 2 use case is the store-specific morning brief; the documented themes are at-home pre-work, translation/orchestration burden, heavy Excel analysis pulling SDs off the floor, and store observations/coaching as the work that suffers. `Target-Frontline-Leader-Research.html` reinforces the same structure and explicitly calls the 12-project/50-date burden and store observations the signature retail proof point.

## 2. Scenario arc

### Scene 1 — Executive setup: "The first hour decides the day"

- **On screen:** A single hero frame: "What if the Store Director walked in already oriented?" Subtext states that all information and data are synthetic and illustrative, not Target data. A compact day timeline shows 6:15 AM home review, 7:30 AM arrival, 8:00 AM huddle, 8:30 AM floor walk.
- **Viewer interaction:** Click **Start the morning**.
- **Point it makes:** This is an operating-rhythm story, not a capability tour.
- **Research mapping:** Through-line from all Store Director docs: time saved is the mechanism; coaching capacity and store observations are the outcome.

### Scene 2 — Today: the at-home assembly routine

- **On screen:** Split workspace showing an inbox stack, an Excel-like metric grid, a weekly recap note, and an initiative calendar list. Visual stress comes from context-switching, not incompetence: each source is credible, but no source answers "what should I do first?"
- **Viewer interaction:** Click through four tabs: **Metrics**, **Leader recap**, **Corporate reading**, **Initiative dates**. Each tab reveals one useful but incomplete fragment.
- **Point it makes:** The current state is not broken people; it is fragmented inputs. The SD is translating workstream-specific inputs into store-specific priorities.
- **Research mapping:** `Target-SD-Research-Compiled.md` themes: the day starts at home; reading arrives in the wrong shape; analysis pulls them off the floor; orchestration without coordination.

### Scene 3 — The cost: orientation crowds out observation

- **On screen:** A "time ledger" converts the clicked fragments into morning work: review metrics, reconcile recap, identify action owners, scan dates, prep huddle. A muted floor-walk card remains unchecked: "Observe pickup handoff before huddle."
- **Viewer interaction:** Toggle **Show leadership impact** to reveal that the lost block is not generic "time"; it is the first observation/coaching window of the day.
- **Point it makes:** The real cost is the feedback loop going dark. Problems become visible only later in metrics.
- **Research mapping:** `Target-SD-Innovation-Hub-Brief.md`: store observations suffer most; coaching and leadership development are where SDs want to spend time. `Target-Frontline-Leader-Research.html`: observations are the displaced work.

### Scene 4 — With Copilot + Power BI: the morning brief lands

- **On screen:** A M365 Copilot-inspired narrative panel next to Power BI-inspired visual cards. The narrative opens with a synthetic label and a plain-language summary:
  - "Overall store pulse: steady."
  - "Watch today: pickup wait time trend and front-end coverage after 2 PM."
  - "Decision needed: prioritize Fulfillment coaching before huddle; defer noncritical signing audit to closing TL."
  Visual cards show four pillars: Guest, Team, Operations, Financials, with small inline charts built in vanilla HTML/CSS/SVG.
- **Viewer interaction:** Click **Generate my morning brief**. The text appears in staged paragraphs; visual cards highlight as the narrative references them.
- **Point it makes:** The visual gives evidence; the narrative turns evidence into an ordered leadership plan.
- **Research mapping:** Tier 2 use case 5, store-specific morning brief; Tier 1 use case 1, deeper email review and action extraction; Tier 7, self-serve reporting/views, but only as supporting evidence.

### Scene 5 — Drill-down: why pickup is the first walk

- **On screen:** The Guest card expands into a simple trend: pickup wait time, guest feedback themes, and staffing coverage. The narrative explains the relationship: "Wait time rose after 5 PM on two of three days; guest comments mention handoff clarity; the strongest coaching opportunity is role clarity at the pickup desk."
- **Viewer interaction:** Click **Why this first?** and then **Show supporting signals**. The page reveals synthetic source chips: Power BI sales/operations dataset, guest comments summary, leader recap, schedule snapshot.
- **Point it makes:** Copilot does not replace the dashboard; it explains which metric matters now, why it matters, and what the SD should go see.
- **Research mapping:** Guest feedback analysis already in use; possible guest/operations connection is worth testing but not asserting. This scene must phrase it as a signal to investigate, not a proven correlation.

### Scene 6 — Initiative collision: 12 projects / 50 dates in miniature

- **On screen:** A small "Today’s collisions" module shows three illustrative initiatives with owners, dates, and completion asks. One conflicts with a thin leadership coverage window.
- **Viewer interaction:** Click **Localize today's asks**. The module rewrites generic corporate tasks into store-specific assignments: owner, due date, and recommended tradeoff.
- **Point it makes:** Translation and orchestration are part of the brief, but not the whole demo. This is a supporting proof point, not a second flagship.
- **Research mapping:** Tier 2 use case 6, translation done once; Tier 3 use case 9, initiative orchestration view; documented proof point: ~12 projects, ~50 dates, multiple pyramid owners.

### Scene 7 — The after: first hour restored

- **On screen:** The same day timeline from Scene 1 now shows "7:30 arrive oriented," "7:40 observe pickup handoff," "8:00 huddle with one clear priority," "8:20 coach closing TL." A short reflective line: "The SD moved from connecting the dots to making the decisions."
- **Viewer interaction:** Toggle **Today** / **With Copilot** to compare the time ledger and leadership actions.
- **Point it makes:** The outcome is coaching capacity and store observations, not report automation.
- **Research mapping:** Project through-line in `Target-SD-Research-Compiled.md`; leadership pipeline and store observation themes in `Target-SD-Innovation-Hub-Brief.md`.

### Scene 8 — Self-explanatory close

- **On screen:** Three executive takeaways:
  1. "Synthetic Power BI-style visuals show the state of the store."
  2. "Copilot-style narrative explains what changed, why it matters, and where to lead first."
  3. "The first hour shifts from report assembly to observation and coaching."
  A footer repeats: "Illustrative simulation. No real Target data. No Microsoft or Target logos or trade dress."
- **Viewer interaction:** Optional **Replay in 90 seconds** button resets the scripted flow.
- **Point it makes:** An executive can understand the artifact without narration.
- **Research mapping:** "How to make it land" guidance: capture one vivid moment and play it back solved.

## 3. Interaction model

**Primary model: guided scripted decision path with synchronized narrative and visuals.** The viewer clicks a small number of deliberate prompts: **Start the morning**, **Generate my morning brief**, **Why this first?**, **Localize today's asks**, and **Compare first hour**. Each click advances a controlled scene, highlights the relevant chart/card, and reveals prewritten Copilot-style narrative.

This is the right model because the audience needs to grasp one executive story quickly, the artifact must be self-explanatory, and the strongest value is the transformation of a known morning routine. Scripted interaction preserves narrative quality, avoids dead-end free typing, and keeps the page reliable from `file://` with no dependencies.

**Explicitly rejected:**

- **Open fake chat input:** Rejected because unmatched prompts will expose the simulation as brittle and distract from the core moment.
- **Full dashboard explorer:** Rejected because it turns the artifact into a BI product demo and dilutes the coaching/observation outcome.
- **Five-feature carousel:** Rejected because it becomes a capability tour. The research says one vivid morning moment will land better.

## 4. Before/after framing

The "today" side must be respectful. It should show useful systems and responsible leaders doing necessary work, not chaotic incompetence. Email, Excel-like grids, recaps, and initiative lists each contain valid signal; the problem is that the SD has to assemble meaning across them before arriving. Avoid phrases like "manual mess" or "broken process." Use "fragmented inputs," "translation work," and "orientation work."

The "with Copilot" side should not imply the SD stops thinking. It should position Copilot as an executive briefing layer over trusted sources: it summarizes, prioritizes, explains confidence, and names tradeoffs. The SD still makes the decision and uses the recovered time for a floor observation and coaching conversation. That keeps the SD empowered rather than automated.

The contrast:

- **Current-state morning:** starts at home; four useful sources; SD translates workstream-specific inputs into store-specific priorities; huddle prep consumes the observation window.
- **Future-state morning:** starts with a store-specific brief on arrival; data and recaps are already synthesized; the first action is a targeted observation; the huddle has one clear priority and owner.

## 5. Power BI integration story

Power BI-style visuals appear as the evidence layer beside the narrative, not as decoration:

- **Store pulse card:** four-pillar status for Guest, Team, Operations, Financials.
- **Guest drill-down:** pickup wait-time trend, guest feedback themes, and service friction indicator.
- **Operations card:** fulfillment backlog and on-shelf availability signal.
- **Team card:** coverage heat strip by daypart and leader availability.
- **Financials card:** sales-to-plan or controllable expense indicator, shown as synthetic and directional.
- **Source chips:** synthetic "Power BI store metrics," "leader recap," "guest comments," and "schedule snapshot" labels to show the integration pattern without claiming real connectivity.

What the narrative adds over the visuals alone:

1. **Prioritization:** It identifies which of many metrics matters first today.
2. **Causality hypothesis:** It connects pickup trend, guest comments, and coverage as a plausible observation target, while avoiding unsupported certainty.
3. **Tradeoff guidance:** It recommends what to defer when labor/leadership attention is constrained.
4. **Action translation:** It converts a chart into "go observe pickup handoff, then coach the closing TL on role clarity."
5. **Audience fit:** It speaks in store-leadership language rather than dashboard terminology.

The page should make the integration visible: when the narrative says "pickup wait time rose after 5 PM," the corresponding visual highlights. When the viewer drills down, the visual reveals the supporting synthetic data. The crux is side-by-side evidence plus explanation.

## 6. Scope: IN and OUT

Bias: one flagship done vividly. The artifact includes only enough supporting use cases to make the morning brief credible.

### In scope

1. **Use case 1 — Deeper email review and action extraction:** In scope as the current-state input and as one source feeding the brief. Show actions, owners, and dates extracted from synthetic email/recap snippets.
2. **Use case 5 — Store-specific morning brief:** Primary flagship. This is the artifact.
3. **Use case 6 — Translation done once:** In scope lightly through one "Localize today's asks" moment. It supports the morning brief.
4. **Use case 7 — Self-serve reporting and views:** In scope only as Power BI-style supporting visuals and one drill-down. Do not make report creation the story.
5. **Use case 8 — Guest feedback analysis:** In scope as a summarized signal supporting the pickup observation recommendation.
6. **Use case 9 — Initiative orchestration view:** In scope in miniature only: a small collision/owner/date module. Do not promise end-to-end orchestration.

### Out of scope

2. **Use case 2 — Reliable multi-date calendar capture:** Out except for a small implied action/date extraction visual. It is credible but would become its own demo.
3. **Use case 3 — Best practice documentation and leadership development content:** Out. Mention only in rationale if needed; not part of the interactive flow.
4. **Use case 4 — Team map with responsibilities:** Out. Useful but would add a second concept and require a people model.
10. **Use case 10 — Closed-loop comms:** Out. MyDayComms integration is system-gated and too easy to overpromise.
11. **Use case 11 — Coverage prediction:** Out. Scheduling/UKG is a real pain point but system-gated; use only a static coverage snapshot as context.
12. **Use case 12 — Frontline answers on the handheld:** Out. It is a different surface and audience.

## 7. Work breakdown by agent

### Narrative

- Write the Copilot-style morning brief copy for Scenes 4, 5, 6, and 7.
- Keep tone executive and operational: concise, calm, store-leadership language.
- Include explicit synthetic-data labeling in the copy where appropriate.
- Draft the SD internal monologue for the before state without making the SD look disorganized.
- Produce exact strings for the guided buttons and takeaways.
- Guardrails:
  - No Microsoft or Target logos, slogans, or trade dress.
  - Do not claim real integration or real Target data.
  - Say "signals suggest where to look" rather than asserting unproven causality.

### Data

- Create a compact synthetic dataset specification, not a real data file unless Frontend requests it:
  - Four-pillar store pulse: Guest, Team, Operations, Financials.
  - Pickup wait-time trend by daypart for 3-5 days.
  - Guest comment theme counts.
  - Coverage heat strip by daypart.
  - Initiative list with owner/date/status/conflict flag.
  - Before-state source snippets: email subject lines, recap bullets, metric rows.
- Define chart specs that can be implemented with vanilla HTML/CSS/SVG:
  - Small line chart for pickup wait time.
  - Bar or pill chart for guest themes.
  - Heat-strip for coverage.
  - Status cards for four pillars.
- Use round, plausible, clearly illustrative values. Every table/visual must include "Synthetic illustrative data."
- Avoid Target-specific store numbers, real sales figures, real SKU/category names, or anything that could be mistaken for confidential data.

### Frontend

- Implement exactly one self-contained `.html` file when execution begins; no external assets, fonts, libraries, CDNs, images, iframes, or network calls.
- Build a guided scripted interaction with accessible buttons, keyboard focus, and deterministic state transitions.
- Use M365 Copilot / Power BI inspired visual language only: clean cards, subtle gradients, neutral palette, fluent-like spacing; no logos, no brand cloning.
- Create all visuals with semantic HTML, CSS, and inline SVG only.
- Make the opening and closing synthetic-data disclaimer visible.
- Ensure it works from `file://` with networking disabled.
- Keep the story readable on a projector and a laptop.

### Tester

- Verify the artifact against constraints:
  - Single `.html` file.
  - No external dependencies or network requests.
  - Opens via `file://`.
  - No real Target data, logos, or trade dress.
  - All synthetic data visibly labeled.
  - No broken interactions; replay/reset works.
- Validate story comprehension without narration:
  - Can a viewer answer "what changed for the Store Director?"
  - Can a viewer answer "what does Power BI contribute?"
  - Can a viewer answer "what does Copilot narrative add?"
- Accessibility checks:
  - Keyboard navigation.
  - Visible focus states.
  - Sufficient contrast.
  - Motion is minimal and not required for comprehension.
- Retail-audience smell test:
  - Before state feels realistic and respectful.
  - Recommendations sound like store-leadership actions, not generic AI advice.

## 8. Open questions / risks

### Decisions needed from Chris

1. **Audience emphasis:** Is the primary viewer a Target retail executive, Microsoft account team, or mixed Innovation Hub audience? The current plan assumes mixed, with retail credibility first.
2. **Time claim:** Should the artifact use a quantified time-saved number for Store Directors, or avoid quantification beyond the documented 12 projects / 50 dates? Recommendation: avoid a precise SD time-saved claim unless Chris has one.
3. **Store-health definition:** Which metrics best represent "healthy store today" for the demo: guest wait, fulfillment, on-shelf availability, sales-to-plan, staffing, or another set? Recommendation: use four pillars and make pickup the highlighted issue.
4. **Naming:** Should the page say "Target Store Director" throughout, or use a neutral "large-format retail Store Director" label to reduce brand sensitivity? Recommendation: use "Store Director" in body copy and reserve "Target" for research context only if necessary.

### Risks that could make this land badly

1. **Looks like fake BI instead of retail leadership:** If charts dominate, the executive takeaway becomes "dashboard" rather than "first hour restored."
2. **Strawman current state:** If the before state looks chaotic or incompetent, retail leaders may reject it. The problem must be fragmentation, not poor discipline.
3. **Overpromising integration:** MyDayComms, UKG, and real Power BI access are gated. The artifact must simulate the experience without implying production readiness.
4. **Unlabeled synthetic data:** Any ambiguity around data provenance is a trust killer.
5. **Brand/trade dress confusion:** Inspired visual language is acceptable; logos, exact brand palettes, and copied UI chrome are not.
6. **Unsupported causality:** The research says the guest/operations link is worth testing, not asserting. The demo should say "signals point to an observation target."
7. **Too many use cases:** Calendar capture, handheld answers, scheduling prediction, and closed-loop comms are tempting but would dilute the flagship.

