# Store Director Copilot UI QA — Pass #1

**Reviewer:** Tester (QA Engineer)  
**Artifact:** `store-director-copilot.html`  
**Run time:** 2026-09-03 21:54–22:30 CT  
**Verdict:** **NO-GO**

This is the first QA pass for `store-director-copilot.html`. Prior reports for the deleted `store-director-simulation.html` were treated as precedent only.

## Evidence captured

- Automated Playwright audit script: `C:\Users\chdaly\.copilot\session-state\84d4d27f-5f48-433f-98fe-e9e098aa8cb9\files\pw\qa-copilot.js`
- Raw results: `.squad\.scratch\visual-qa\tester-copilot\qa-results.json`
- Screenshots inspected with the `view` tool:
  - `1440x900-light-load.png`
  - `1440x900-dark-load.png`
  - `1024x768-light-load.png`
  - `1024x768-dark-load.png`
  - `390x844-light-load.png`
  - `390x844-dark-load.png`
  - `input-focus-popover.png`
  - `weekend-recap-chat.png`
  - `saturday-prompt-response.png`

## Summary verdict

**NO-GO.** The recent click-response fix mostly worked: all visible buttons responded distinctly, and Recent history items load prior conversations. However, the artifact fails two load-bearing QA requirements:

1. The synthetic-data disclosure is visually clipped/overlapped at 390px mobile width.
2. At 1024x768, the KPI strip overflows the visible viewport and clips the Payroll card.

There are also accessibility defects in focus indication and expander ARIA.

---

## 1. Click-response audit

Fresh page load at `file:///C:/GitHub/store-director/store-director-copilot.html?scoutTheme=light`, 1440x900. Each listed visible control was clicked from a fresh load unless noted. Hidden composer tray prompt chips were then tested after opening the tray.

| Element label | Status | What changed | Near clicked element? |
|---|---:|---|---|
| Chat active | RESPONDS | Local popover: “Chat is the active simulation surface.” | Yes, 147px |
| Agents | RESPONDS | Local popover: “Not part of this simulation. Use the chat history or guided prompts.” | Yes, 155px |
| Notebooks | RESPONDS | Local popover: “Not part of this simulation. Use the chat history or guided prompts.” | Yes, 155px |
| Search | RESPONDS | Local popover: “Not part of this simulation. Use the chat history or guided prompts.” | Yes, 155px |
| New chat | RESPONDS | Local popover explaining free-form chats are outside the scripted simulation | Yes, 245px |
| Morning brief — today | RESPONDS | Local popover: already viewing current chat | Yes, 245px |
| Weekend recap | RESPONDS | Active Recent item changes; conversation changes from 1 to 2 messages | Conversation body updates |
| Payroll variance | RESPONDS | Active Recent item changes; conversation changes from 1 to 2 messages | Conversation body updates |
| Q3 remodel timeline | RESPONDS | Active Recent item changes; conversation changes from 1 to 2 messages | Conversation body updates |
| Drive-up observations | RESPONDS | Active Recent item changes; conversation changes from 1 to 2 messages | Conversation body updates |
| Leader huddle notes | RESPONDS | Active Recent item changes; conversation changes from 1 to 2 messages | Conversation body updates |
| Why is pickup the priority? | RESPONDS | Adds user + assistant response; disables matching prompt chips | Conversation response below prompt |
| Show me Saturday's drill-down | RESPONDS | Adds user + assistant response with Saturday table; disables matching prompt chips | Conversation response below prompt |
| What should I say in the huddle? | RESPONDS | Adds user + assistant response; disables matching prompt chips | Conversation response below prompt |
| What can I defer today? | RESPONDS | Adds user + assistant response; disables matching prompt chips | Conversation response below prompt |
| Which initiatives collide this week? | RESPONDS | Adds user + assistant response; disables matching prompt chips | Conversation response below prompt |
| Attach content | RESPONDS | Opens composer prompt tray; local scripted-demo popover | Yes, 213px |
| Message Copilot input | RESPONDS WITH ACCESSIBILITY ISSUE | Opens composer prompt tray and distinct free-text-disabled popover | Popover appears by composer left edge; focus indicator is missing |
| Voice input | RESPONDS | Opens composer prompt tray; local scripted-demo popover | Yes, 213px |
| Open suggested prompts | RESPONDS | Toggles composer prompt tray; local opened/collapsed popover | Yes, 213px |
| Send unavailable in scripted mockup | RESPONDS | Opens composer prompt tray; local scripted-demo popover | Yes, 213px |
| Composer tray: Why is pickup the priority? | RESPONDS | Adds user + assistant response; disables matching prompt chips | Tested after tray opened |
| Composer tray: Show me Saturday's drill-down | RESPONDS | Adds user + assistant response; disables matching prompt chips | Tested after tray opened |
| Composer tray: What should I say in the huddle? | RESPONDS | Adds user + assistant response; disables matching prompt chips | Tested after tray opened |
| Composer tray: What can I defer today? | RESPONDS | Adds user + assistant response; disables matching prompt chips | Tested after tray opened |
| Composer tray: Which initiatives collide this week? | RESPONDS | Adds user + assistant response; disables matching prompt chips | Tested after tray opened |
| Composer tray prompt chips at initial load | HIDDEN | Hidden until `Open suggested prompts` or input focus opens `#composerPrompts` | Acceptable if ARIA is fixed |

**Click-response conclusion:** The specific prior defect — many controls firing one identical generic hint far from the click target — is mostly fixed. No visible button behaved as dead. The composer input still has a related accessibility problem: the state changes, but the input itself has no visible focus indicator.

---

## 2. Self-containment

### Static parse

Script scanned `src`, `href`, CSS `url()`, `import(...)`, `fetch(...)`, `Worker(...)`, raw `http://` / `https://`, and external font markers.

| Check | Result |
|---|---:|
| External `src` / `href` | 0 |
| External CSS `url()` | 0 |
| External `import` / `fetch` / `Worker` | 0 |
| Raw `http://` or `https://` strings | 0 |
| `@font-face`, Google Fonts, WOFF/TTF/OTF markers | 0 |

### Runtime network

Playwright `page.on('request')` observed **0 non-file requests** on load across all six viewport/theme combinations.

**Result:** PASS.

---

## 3. Console/page errors

| Scope | Console errors | Page errors |
|---|---:|---:|
| Initial load | 0 | 0 |
| After full click-response audit | 0 | 0 |
| Responsive/theme matrix | 0 | 0 |

**Result:** PASS.

---

## 4. Synthetic-data disclosure

| Viewport/theme | Visual result | Contrast ratio |
|---|---|---:|
| 1440x900 light | Visible above fold | 15.52:1 |
| 1440x900 dark | Visible above fold | 10.81:1 |
| 1024x768 light | Visible above fold | 15.52:1 |
| 1024x768 dark | Visible above fold | 10.81:1 |
| 390x844 light | **Clipped/overlapped** | 15.52:1 computed, but visual fails |
| 390x844 dark | **Clipped/overlapped** | 10.81:1 computed, but visual fails |

**Finding CRITICAL-1:** The load-bearing synthetic-data disclosure is not fully visible at mobile width.  
**Where:** `.disclosure`, screenshots `390x844-light-load.png` and `390x844-dark-load.png`.  
**What:** The disclosure text wraps beyond the fixed 40px disclosure height and is clipped/overlapped by the header area. In the inspected 390px screenshots, only part of the sentence is cleanly readable.  
**Why it matters:** This mockup deliberately uses high-fidelity Microsoft-style UI. The disclosure is the main trust/safety control that prevents it from reading as a shipping product or real Target operational data. The requirement explicitly says the disclosure must remain visible/reachable in every viewport.  
**How to fix:** Let the disclosure height grow on small screens (`height:auto; min-height:40px`), stack/wrap the badge and text safely, and make `.app` height account for the actual disclosure height instead of `calc(100vh - 40px)`.

---

## 5. Numeric integrity

`docs/simulation-dataset.md` was treated as authoritative. Rendered/embedded values checked against it:

| Dataset value | HTML result |
|---|---:|
| Weekly sales actual `$2.535M` | PASS |
| Weekly sales plan `$2.600M` | PASS |
| Weekly variance `-$65K` | PASS |
| Comp `+3.0%` | PASS |
| Weighted guest score `77.1` | PASS |
| Weighted pickup on-time `93.0%` | PASS |
| Payroll vs earned `-62h` / `-62 hours` | PASS |
| Saturday guest score `69` | PASS |
| Saturday pickup on-time `88.4%` | PASS |
| Saturday afternoon guest score `61` | PASS |
| Saturday afternoon pickup on-time `82.1%` | PASS |
| Saturday afternoon wait `8.4 minutes` | PASS |
| Saturday afternoon pickup orders `241` | PASS |
| Saturday afternoon total critical gap `14h` | PASS |
| Fulfillment/Pickup share `9h` | PASS |
| Fulfillment/Pickup picked/staged orders `164` | PASS |
| Front End handoff/drive-up orders `77` | PASS |

### 14h / 9h reconciliation

Checked all visible adjacencies found in initial brief, prompted Saturday table, Recent weekend, payroll, drive-up, and huddle conversations. Each occurrence reconciles `14h` as the all-department Saturday afternoon total and `9h` as the Fulfillment/Pickup share.

Examples verified:

- Initial brief caption: “14h total critical gap across departments, including 9h in Fulfillment/Pickup.”
- Initial coverage card: “14h total / 9h F/P” plus reconciliation box.
- Saturday prompt response: “14h total / 9h F/P” plus caption breaking down 9 + 3 + 1.5 + 0.5.
- Weekend recap: “14h total ... across departments, with 9h ... 3h ... 1.5h ... 0.5h.”

**Result:** PASS.

---

## 6. Responsive + theme

### Screenshots inspected

All required viewport/theme screenshots were captured and visually inspected.

| Viewport | Light | Dark | Result |
|---|---|---|---|
| 1440x900 | `1440x900-light-load.png` | `1440x900-dark-load.png` | PASS |
| 1024x768 | `1024x768-light-load.png` | `1024x768-dark-load.png` | **FAIL: clipped KPI** |
| 390x844 | `390x844-light-load.png` | `390x844-dark-load.png` | **FAIL: disclosure clipped** |

### Contrast ratios

| Theme | Body text | Muted/caption text | Disclosure text |
|---|---:|---:|---:|
| Light | 14.15:1 | 6.69:1 | 15.52:1 |
| Dark | 8.28:1 | 4.62:1 | 10.81:1 |

**Contrast result:** PASS. Ratios exceed 4.5:1 for the sampled body, muted, and disclosure text. Visual inspection still found disclosure failure at 390px due clipping, not contrast.

**Finding MAJOR-1:** 1024x768 clips the rightmost KPI card.  
**Where:** `.kpi-grid`, screenshots `1024x768-light-load.png` and `1024x768-dark-load.png`; automated overflow detected `.kpi` Payroll card from x=933 to x=1059 in a 1024px viewport.  
**What:** The five-column KPI strip remains in one row at 1024px because the responsive breakpoint does not collapse until `max-width:900px`. With the 300px sidebar, the content area is too narrow and the Payroll card/text overflows the visible viewport. Document-level horizontal scroll remains false because the parent layout clips overflow, so the content is simply hidden.  
**Why it matters:** Requirement says no clipped/overlapping text and no horizontal scroll at 1024x768. This loses a core KPI in a required executive-laptop viewport.  
**How to fix:** Base the KPI collapse on available content width, not full viewport width. Raise the breakpoint or use `grid-template-columns: repeat(auto-fit, minmax(...))` so the cards wrap before clipping.

---

## 7. Accessibility basics

| Check | Result |
|---|---:|
| Heading levels | PASS: no skipped levels (`h2` sidebar heading appears before `h1`, but no level skip) |
| Keyboard reachability | PASS: tab traversal reached controls and returned to first control; no focus trap observed |
| Enter/Space activation | PASS for visible buttons; input Space opened scripted prompts, Enter did not submit (acceptable for disabled free text) |
| Visible focus indicator | **FAIL for composer input** |
| Tabs/list/expander ARIA | **FAIL for prompt tray expander** |
| Button accessible names | PASS: no unnamed buttons |

**Finding MAJOR-2:** Composer input has no visible focus indicator.  
**Where:** `#composerInput`, screenshot `input-focus-popover.png`; computed focus style reported `outline: none`. CSS sets `.composer input{outline:0}`.  
**What:** Keyboard focus lands on the input, but the input itself has no visible focus ring. The popover/tray appears, but that is state feedback, not a reliable focus indicator around the active control.  
**Why it matters:** Requirement explicitly asks for visible focus indication on all interactive elements. Keyboard users need to know where focus is before operating the control.  
**How to fix:** Preserve or add a visible `:focus-visible` style for `#composerInput`, or move the focus ring to the containing `.composer` with `:focus-within`.

**Finding MINOR-1:** Suggested-prompt tray expander lacks ARIA state.  
**Where:** `#promptMenu` toggling `#composerPrompts`; HTML line with `aria-label="Open suggested prompts"`; JS toggles `.open` without `aria-expanded` or `aria-controls`.  
**What:** The chevron button opens/collapses a prompt panel visually, but the button does not expose expanded/collapsed state or the controlled element to assistive technology. Automated scan found zero `[aria-expanded]` elements.  
**Why it matters:** Requirement explicitly asks for correct ARIA on expander patterns. Screen-reader users cannot tell whether the tray is open.  
**How to fix:** Add `aria-controls="composerPrompts"` and maintain `aria-expanded="true|false"` on `#promptMenu` whenever `.open` changes.

---

## Finding list

### Critical

1. **Synthetic-data disclosure clips/overlaps at 390px mobile width** — `.disclosure`; `390x844-light-load.png`, `390x844-dark-load.png`.

### Major

1. **1024x768 clips the Payroll KPI card** — `.kpi-grid`; `1024x768-light-load.png`, `1024x768-dark-load.png`.
2. **Composer input lacks a visible focus indicator** — `#composerInput`; `input-focus-popover.png`.

### Minor

1. **Prompt tray expander lacks `aria-expanded` / `aria-controls`** — `#promptMenu` / `#composerPrompts`.

## Final recommendation

**NO-GO until the Critical disclosure defect and Major responsive/accessibility defects are fixed and re-tested.** The interaction rewiring itself is largely successful, self-containment passes, runtime/network checks pass, console errors are zero, and numeric integrity is sound.
