# Simulation Dataset and Chart Specifications

**Prepared by:** Data, BI Simulator  
**Generated:** 2026-09-03T18:27:50-05:00  
**Scope:** Numeric foundation only — no HTML, CSS, JavaScript, or Copilot narrative copy.

## Illustrative-data disclosure

**Exact wording:** Illustrative simulation data only. Store, sales, labor, guest, and operations values are synthetic and are not Target operational data.

**Recommended placement:** Persistent footer below the dashboard title and repeated in the final details panel; use 12px text minimum, #374151 on white, with an info icon.

## Store profile

| Field | Value |
|---|---|
| Fictional store ID | SIM-TGT-9001 |
| Fictional store name | Bullseye Bay Innovation Store |
| Fictional-store note | SIM-TGT-9001 is an obviously fictional identifier and is not a real Target store number. |
| Format | Full-line big-box with grocery, apparel, order pickup, drive-up, and same-day fulfillment |
| Selling square feet | 128,000 |
| Backroom square feet | 38,000 |
| Weekly sales volume | $2,535,000 |
| Rostered team headcount | 214 |
| Scheduled daily headcount range | 132-178 |
| Leadership structure | 1 Store Director, 5 Executive Team Leaders, 17 Team Leaders |

## Systems represented

Outlook / email, MyDayComms, Excel, UKG, Power BI, Copilot, Store fulfillment/pickup system, POS/guest feedback.

## Human-readable daily data

### Financials

| Day | Sales | Forecast/Plan | Variance $ | Variance % | Comp % | GM % | Actual/Earned payroll hrs | Payroll vs earned |
|---|---|---|---|---|---|---|---|---|
| Monday | $320,000 | $315,000 | $5,000 | +1.6% | +3.9% | 29.8% | 1,952/1,960 | -8 |
| Tuesday | $305,000 | $310,000 | -$5,000 | -1.6% | +1.7% | 29.5% | 1,882/1,875 | +7 |
| Wednesday | $315,000 | $320,000 | -$5,000 | -1.6% | +2.9% | 29.9% | 1,931/1,925 | +6 |
| Thursday | $340,000 | $345,000 | -$5,000 | -1.4% | +3.3% | 29.6% | 2,051/2,040 | +11 |
| Friday | $385,000 | $400,000 | -$15,000 | -3.8% | +3.5% | 28.8% | 2,251/2,270 | -19 |
| Saturday | $550,000 | $575,000 | -$25,000 | -4.3% | +2.8% | 27.9% | 2,982/3,040 | -58 |
| Sunday | $320,000 | $335,000 | -$15,000 | -4.5% | +3.2% | 28.4% | 1,989/1,990 | -1 |

### Guest

| Day | Guest score | Checkout wait min | Recovery incidents | Pickup complaints | Guest transactions |
|---|---|---|---|---|---|
| Monday | 82 | 3.1 | 7 | 2 | 1,560 |
| Tuesday | 81 | 3.3 | 8 | 3 | 1,485 |
| Wednesday | 83 | 3.0 | 6 | 2 | 1,510 |
| Thursday | 80 | 3.6 | 10 | 4 | 1,625 |
| Friday | 76 | 4.7 | 17 | 8 | 1,830 |
| Saturday | 69 | 6.2 | 31 | 18 | 2,480 |
| Sunday | 74 | 5.1 | 19 | 10 | 1,540 |

### Operations

| Day | In-stock | On-shelf availability | Pickup on-time | Pickup orders | Backroom tasks | MyDayComms complete |
|---|---|---|---|---|---|---|
| Monday | 97.2% | 96.5% | 96.8% | 312 | 94% | 96% |
| Tuesday | 96.9% | 96.1% | 95.9% | 286 | 92% | 95% |
| Wednesday | 97.0% | 96.2% | 96.3% | 301 | 93% | 96% |
| Thursday | 96.8% | 96.0% | 95.1% | 335 | 91% | 94% |
| Friday | 95.9% | 94.8% | 92.6% | 421 | 84% | 88% |
| Saturday | 94.6% | 92.7% | 88.4% | 618 | 76% | 79% |
| Sunday | 95.4% | 93.8% | 91.2% | 376 | 82% | 85% |

### Team

Coverage gap tuple is `opening / midday / afternoon / close` critical coverage gap hours.

| Day | Scheduled HC | Actual HC | Call-outs | Gap hrs total | Gap hrs by daypart | Training complete |
|---|---|---|---|---|---|---|
| Monday | 138 | 137 | 1 | 3 | 0/1/2/0 | 91% |
| Tuesday | 132 | 131 | 1 | 4 | 0/2/1/1 | 91% |
| Wednesday | 135 | 133 | 2 | 5 | 1/1/2/1 | 92% |
| Thursday | 142 | 141 | 1 | 7 | 0/2/3/2 | 92% |
| Friday | 155 | 149 | 6 | 15 | 1/4/7/3 | 90% |
| Saturday | 178 | 166 | 12 | 27 | 2/6/14/5 | 88% |
| Sunday | 145 | 141 | 4 | 13 | 1/3/6/3 | 89% |

## Narrative hook baked into the numbers

**What the dashboard shows:** Saturday is red across Guest and Operations: guest score **69**, checkout wait **6.2 minutes**, pickup on-time **88.4%**, and backroom task completion **76%**.

**What it does not explain by itself:** The weekly payroll card is only **-62 hours vs earned (-0.4%)**, which looks nearly balanced. The problem is not total weekly labor; it is labor landing in the wrong department and daypart.

**Hypothesis signals for Narrative:**

1. Saturday afternoon Fulfillment/Pickup lost **9 critical hours** from **four call-outs after partial backfill**.
2. Pickup orders peaked in the same daypart while pickup on-time fell to **82.1%** from 14:00-18:00.
3. Fulfillment/Pickup had **11** department/daypart recovery incidents recorded; Front End wait reached **8.4 minutes** while backup calls overlapped the pickup rush.
4. Guest score for the daypart fell to **61**, pulling Saturday's daily score down to **69**.
5. Backroom task completion ended Saturday at **76%**; Sunday's on-shelf availability was **93.8%**.

### Drill-down level 1 — Saturday by daypart

| Daypart | Time | Guest score | Wait min | Pickup on-time | Pickup orders | Recovery incidents | Gap hrs | Primary gap |
|---|---|---|---|---|---|---|---|---|
| Opening | 06:00-10:00 | 78 | 3.9 | 95.2% | 86 | 4 | 2 | Front End meal-break stacking |
| Midday | 10:00-14:00 | 72 | 5.8 | 90.5% | 157 | 3 | 6 | Fulfillment pick queue + Grocery pulls |
| Afternoon | 14:00-18:00 | 61 | 8.4 | 82.1% | 241 | 18 | 14 | Fulfillment/Pickup call-outs not visible in sales plan |
| Close | 18:00-22:00 | 68 | 6.5 | 86.9% | 134 | 6 | 5 | Recovery queue carried into close |

### Drill-down level 2 — Saturday afternoon by department

| Department | Scheduled hrs | Actual hrs | Gap hrs | Call-outs | Service metric | Recovery incidents | Dept-handled pickup orders | Observable signal |
|---|---|---|---|---|---|---|---|---|
| Fulfillment / Pickup | 52 | 43 | 9 | 4 | Pickup on-time 82.1% | 11 | 164 picked/staged by Fulfillment out of 241 afternoon pickup orders | Pickup queue exceeded staffed pick capacity by 14:40. |
| Front End | 64 | 61 | 3 | 2 | Checkout wait 8.4 min | 5 | 77 handoff/drive-up orders handled outside Fulfillment pick queue | Backup cashier calls overlapped drive-up rush. |
| Grocery | 48 | 46.5 | 1.5 | 1 | OSA 89.6% | 2 | n/a | Cooler replenishment tasks deferred after 15:00. |
| Style | 36 | 35.5 | 0.5 | 1 | Task completion 78% | 0 | n/a | Reshop queue grew, but it is not the primary signal in this observation hypothesis. |

Department-handled pickup orders are intentionally a subset allocation, not a second daypart total: Fulfillment/Pickup picked or staged **164** of the **241** Saturday afternoon pickup orders; the remaining **77** were handoff/drive-up orders handled outside the Fulfillment pick queue. `missingItemComplaints` in JSON is also a subset measure: Fulfillment's **7** missing-item complaints are part of Saturday's **18** total pickup complaints, not a parent total that department rows must sum to.

## Reconciliation notes

- Daily actual sales sum: 320000 + 305000 + 315000 + 340000 + 385000 + 550000 + 320000 = 2,535,000.
- Daily forecast sum: 315000 + 310000 + 320000 + 345000 + 400000 + 575000 + 335000 = 2,600,000.
- Weekly sales variance: $2,535,000 - $2,600,000 = -$65,000; -$65,000 / $2,600,000 = -2.5%.
- Last-year sales sum: 2,460,000; comp dollars: 2,535,000 - 2,460,000 = 75,000; comp % = +3.0%.
- Prior-week sales sum: 2,525,000; week-over-week dollars: 2,535,000 - 2,525,000 = 10,000; WoW % = +0.4%.
- Gross margin dollars: sum of daily rounded actual sales × gross margin % = 735,370; weekly margin % = 735,370 / 2,535,000 = 29.0%.
- Payroll earned hours: 15,100; scheduled: 15,345; actual: 15,038. Actual vs earned = -62 hours / 15,100 = -0.4%.
- Guest score is transaction-weighted: sum(score × guest transactions) / 12,030 = 77.1.
- Checkout wait is transaction-weighted: sum(wait × guest transactions) / 12,030 = 4.3 minutes.
- Pickup on-time is order-weighted: sum(on-time % × pickup orders) / 2,649 = 93.0%.
- Team call-outs reconcile to 27 total; critical coverage gap hours reconcile to 74 total.
- Saturday daypart pickup orders reconcile to the Saturday daily total: 86 + 157 + 241 + 134 = 618.
- Saturday afternoon department drill-down gap hours reconcile to Level 1: 9 + 3 + 1.5 + 0.5 = 14; scheduled vs actual hours also reconcile: 200 scheduled - 186 actual = 14.
- Artifact chart labels explicitly distinguish all-department daypart gap-hour totals from department shares: the Scene 4 coverage matrix and Scene 5 daypart drill-down label Saturday afternoon as **14h total across departments**, with **9h** in Fulfillment/Pickup plus **3h** Front End, **1.5h** Grocery, and **0.5h** Style.
- Saturday afternoon department drill-down recovery incidents reconcile to Level 1: 11 + 5 + 2 + 0 = 18.
- Saturday afternoon pickup-order drill-down is labeled as a subset allocation, not a parent/child total: 164 Fulfillment-picked/staged orders + 77 Front End handoff/drive-up orders = 241 Level 1 afternoon pickup orders.
- Fulfillment missing-item complaints are labeled as a subset measure: 7 missing-item complaints are included within Saturday's 18 pickup complaints, but no department-level complaint total is implied.

## Power BI-style chart specifications

### Accessible semantic palette

| Token | Hex | Use |
|---|---:|---|
| background | #FFFFFF | Dashboard background |
| textPrimary | #111827 | Primary text and high-contrast labels |
| textSecondary | #374151 | Secondary text on white |
| good | #0F7B0F | Positive status on white |
| warning | #8A5A00 | Warning status on white |
| bad | #B42318 | Negative status on white |
| target | #2563EB | Forecast/plan series |
| prior | #6B7280 | Prior-period comparison |
| neutralFill | #F3F4F6 | Card and matrix neutral fills |
| gridline | #E5E7EB | SVG gridlines |
| focusOutline | #7C3AED | Keyboard focus outline |

Use text labels, icons, or signs in addition to color. These colors are selected for readable use as text/lines on a white background; if used as filled backgrounds, render labels in `#111827` unless contrast is checked at implementation time.

```json
[
  {
    "visualId": "kpi-executive-strip",
    "type": "KPI card with variance",
    "title": "Today/Week Store Health",
    "fields": [
      "weeklySummary.actualSales",
      "weeklySummary.forecastSales",
      "weeklySummary.salesVsForecastPct",
      "weeklySummary.compPct",
      "weeklySummary.guestScoreWeighted",
      "weeklySummary.fulfillmentPickupOnTimeWeightedPct",
      "weeklySummary.payrollVsEarnedHours"
    ],
    "values": [
      "Sales $2,535,000 vs plan $2,600,000 (-$65,000 / -2.5%)",
      "Comp +3.0% vs last year",
      "Guest score 77.1",
      "Pickup on-time 93.0%",
      "Payroll -62 hours vs earned"
    ],
    "sortOrder": "Fixed: Sales, Comp, Guest, Pickup, Payroll",
    "colorSemantics": "Sales vs plan: good >=0%, warning -2.0% to -0.1%, bad < -2.0%. Comp: good >=+2%, warning 0% to +1.9%, bad <0%. Guest: good >=80, warning 75-79.9, bad <75. Pickup: good >=95%, warning 92-94.9%, bad <92%. Payroll: good within +/-1% of earned; warning beyond +/-1% if service metrics green; bad when under-earned and service metric is warning/bad.",
    "labels": [
      "Wk Sales vs Plan",
      "Comp %",
      "Guest Score",
      "Pickup On-Time",
      "Payroll vs Earned"
    ]
  },
  {
    "visualId": "sales-plan-sparkline",
    "type": "Line/sparkline trend",
    "title": "Sales vs Forecast and Prior Week",
    "xAxis": "daily.dayIndex / daily.dayName",
    "series": [
      {
        "name": "Actual sales",
        "field": "daily.financials.actualSales",
        "color": "#111827"
      },
      {
        "name": "Forecast",
        "field": "daily.financials.forecastSales",
        "color": "#2563EB"
      },
      {
        "name": "Prior week",
        "field": "daily.financials.priorWeekSales",
        "color": "#6B7280",
        "stroke": "dashed"
      }
    ],
    "valueLabelFormat": "$0.0a",
    "sortOrder": "dayIndex ascending Monday-Sunday",
    "colorSemantics": "Actual below forecast uses bad marker #B42318 on the point; at/above forecast uses good marker #0F7B0F.",
    "labels": [
      "Mon",
      "Tue",
      "Wed",
      "Thu",
      "Fri",
      "Sat",
      "Sun"
    ]
  },
  {
    "visualId": "four-pillar-daily-matrix",
    "type": "Matrix",
    "title": "Four Pillars by Day",
    "rows": [
      "Financials",
      "Guest",
      "Operations",
      "Team"
    ],
    "columns": "daily.dayName sorted by daily.dayIndex",
    "values": {
      "Financials": "daily.financials.salesVsForecastPct",
      "Guest": "daily.guest.guestScore",
      "Operations": "daily.operations.fulfillmentPickupOnTimePct",
      "Team": "daily.team.callOuts plus daily.team.coverageGapHoursByDaypart total"
    },
    "cellLabels": {
      "Financials": "Sales vs plan %",
      "Guest": "Guest score",
      "Operations": "Pickup on-time %",
      "Team": "Call-outs / critical gap hrs"
    },
    "colorSemantics": "Use the metric-specific thresholds from KPI strip. Team cells: good <=2 call-outs and <=5 gap hours; warning 3-5 call-outs or 6-12 gap hours; bad >=6 call-outs or >12 gap hours. Include text value in every cell; do not rely on color alone.",
    "sortOrder": "Pillar order: Guest, Team, Operations, Financials if mirroring research pillars; day columns Monday-Sunday."
  },
  {
    "visualId": "coverage-gap-stacked-bar",
    "type": "Stacked bar",
    "title": "Critical Coverage Gap Hours by Daypart",
    "xAxis": "daily.dayName sorted Monday-Sunday",
    "yAxis": "Hours",
    "stacks": [
      {
        "label": "Opening",
        "field": "daily.team.coverageGapHoursByDaypart.opening",
        "color": "#93C5FD"
      },
      {
        "label": "Midday",
        "field": "daily.team.coverageGapHoursByDaypart.midday",
        "color": "#60A5FA"
      },
      {
        "label": "Afternoon",
        "field": "daily.team.coverageGapHoursByDaypart.afternoon",
        "color": "#B42318"
      },
      {
        "label": "Close",
        "field": "daily.team.coverageGapHoursByDaypart.close",
        "color": "#8A5A00"
      }
    ],
    "colorSemantics": "Afternoon uses bad color because the hook is concentrated there. Other dayparts use distinguishable blues/brown with numeric labels inside or beside segments.",
    "labels": [
      "Critical gap hours",
      "Opening",
      "Midday",
      "Afternoon",
      "Close"
    ]
  },
  {
    "visualId": "pickup-guest-drilldown",
    "type": "Matrix with drill-down",
    "title": "Why Did Saturday Guest Score Drop?",
    "level1": {
      "rows": "narrativeHook.drilldownLevel1SaturdayDaypart.daypart sorted Opening, Midday, Afternoon, Close",
      "values": [
        "guestScore",
        "checkoutWaitMinutes",
        "pickupOnTimePct",
        "pickupOrders",
        "guestRecoveryIncidents",
        "criticalCoverageGapHours",
        "primaryGap"
      ]
    },
    "level2": {
      "trigger": "Click Level 1 row = Afternoon",
      "rows": "narrativeHook.drilldownLevel2AfternoonDepartment.department sorted by gapHours descending",
      "values": [
        "scheduledHours",
        "actualHours",
        "gapHours",
        "callOuts",
        "pickupOnTimePct or checkoutWaitMinutes or onShelfAvailabilityPct",
        "guestRecoveryIncidents",
        "observableSignal"
      ]
    },
    "colorSemantics": "Guest score and pickup on-time use KPI thresholds; gapHours: good 0-2, warning 3-7, bad >=8. Highlight Fulfillment/Pickup row with #B42318 left rule and accessible text label 'Primary driver'.",
    "labels": [
      "Daypart",
      "Guest score",
      "Wait",
      "Pickup on-time",
      "Pickup orders",
      "Recovery incidents",
      "Gap hours",
      "Primary gap"
    ]
  },
  {
    "visualId": "operations-task-trend",
    "type": "Line/sparkline trend",
    "title": "Operations Signal: Pickup, OSA, Backroom Tasks",
    "xAxis": "daily.dayName sorted by daily.dayIndex",
    "series": [
      {
        "name": "Pickup on-time %",
        "field": "daily.operations.fulfillmentPickupOnTimePct",
        "color": "#2563EB"
      },
      {
        "name": "On-shelf availability %",
        "field": "daily.operations.onShelfAvailabilityPct",
        "color": "#0F7B0F"
      },
      {
        "name": "Backroom task completion %",
        "field": "daily.operations.backroomTaskCompletionPct",
        "color": "#8A5A00"
      }
    ],
    "valueLabelFormat": "0.0%",
    "sortOrder": "dayIndex ascending",
    "colorSemantics": "Use warning/bad markers when pickup <95/<92, OSA <95/<93, task completion <90/<80.",
    "labels": [
      "Pickup on-time",
      "On-shelf availability",
      "Backroom task completion"
    ]
  }
]
```

## Clean JSON dataset for Frontend

Inline this as a single JavaScript object value. It is strict JSON: no comments and no trailing commas.

```json
{
  "generatedAt": "2026-09-03T18:27:50-05:00",
  "dataScope": "One fictional full-line big-box store, one retail week, all values synthetic for simulation.",
  "storeProfile": {
    "storeId": "SIM-TGT-9001",
    "storeName": "Bullseye Bay Innovation Store",
    "fictionalStoreDisclosure": "SIM-TGT-9001 is an obviously fictional identifier and is not a real Target store number.",
    "format": "Full-line big-box with grocery, apparel, order pickup, drive-up, and same-day fulfillment",
    "sellingSquareFeet": 128000,
    "backroomSquareFeet": 38000,
    "weeklySalesVolumeDollars": 2535000,
    "teamHeadcountRostered": 214,
    "typicalDailyScheduledHeadcountRange": "132-178",
    "leadershipStructure": "1 Store Director, 5 Executive Team Leaders, 17 Team Leaders"
  },
  "retailWeek": {
    "weekId": "FY26-W35-SIM",
    "startDate": "2026-08-24",
    "endDate": "2026-08-30",
    "weekEnding": "2026-08-30"
  },
  "sourceSystemsRepresented": [
    "Outlook / email",
    "MyDayComms",
    "Excel",
    "UKG",
    "Power BI",
    "Copilot",
    "Store fulfillment/pickup system",
    "POS/guest feedback"
  ],
  "weeklySummary": {
    "actualSales": 2535000,
    "forecastSales": 2600000,
    "salesVsForecastDollars": -65000,
    "salesVsForecastPct": -2.5,
    "lastYearSales": 2460000,
    "compDollars": 75000,
    "compPct": 3.0,
    "priorWeekSales": 2525000,
    "weekOverWeekDollars": 10000,
    "weekOverWeekPct": 0.4,
    "grossMarginDollars": 735370,
    "grossMarginPct": 29.0,
    "payrollEarnedHours": 15100,
    "payrollScheduledHours": 15345,
    "payrollActualHours": 15038,
    "payrollVsEarnedHours": -62,
    "payrollVsEarnedPct": -0.4,
    "guestTransactions": 12030,
    "guestScoreWeighted": 77.1,
    "checkoutWaitWeightedMinutes": 4.3,
    "guestRecoveryIncidents": 98,
    "pickupOrders": 2649,
    "fulfillmentPickupOnTimeWeightedPct": 93.0,
    "inStockSalesWeightedPct": 96.1,
    "onShelfAvailabilitySalesWeightedPct": 94.9,
    "backroomTaskCompletionSalesWeightedPct": 86.3,
    "scheduledHeadcount": 1025,
    "actualHeadcount": 998,
    "callOuts": 27,
    "criticalCoverageGapHours": 74,
    "onboardingTrainingCompletionWeightedPct": 90.3
  },
  "daily": [
    {
      "date": "2026-08-24",
      "dayName": "Monday",
      "dayIndex": 1,
      "financials": {
        "actualSales": 320000,
        "forecastSales": 315000,
        "lastYearSales": 308000,
        "priorWeekSales": 312000,
        "grossMarginPct": 29.8,
        "markdownRatePct": 3.1,
        "payrollEarnedHours": 1960,
        "payrollScheduledHours": 1975,
        "payrollActualHours": 1952,
        "salesVsForecastDollars": 5000,
        "salesVsForecastPct": 1.6,
        "compPct": 3.9,
        "weekOverWeekPct": 2.6,
        "grossMarginDollars": 95360,
        "payrollVsEarnedHours": -8,
        "payrollVsEarnedPct": -0.4
      },
      "guest": {
        "guestTransactions": 1560,
        "guestScore": 82,
        "checkoutWaitMinutes": 3.1,
        "guestRecoveryIncidents": 7,
        "pickupComplaints": 2
      },
      "operations": {
        "inStockPct": 97.2,
        "onShelfAvailabilityPct": 96.5,
        "fulfillmentPickupOnTimePct": 96.8,
        "pickupOrders": 312,
        "backroomTaskCompletionPct": 94,
        "myDayCommsCompletionPct": 96
      },
      "team": {
        "scheduledHeadcount": 138,
        "actualHeadcount": 137,
        "callOuts": 1,
        "coverageGapHoursByDaypart": {
          "opening": 0,
          "midday": 1,
          "afternoon": 2,
          "close": 0
        },
        "onboardingTrainingCompletionPct": 91
      }
    },
    {
      "date": "2026-08-25",
      "dayName": "Tuesday",
      "dayIndex": 2,
      "financials": {
        "actualSales": 305000,
        "forecastSales": 310000,
        "lastYearSales": 300000,
        "priorWeekSales": 298000,
        "grossMarginPct": 29.5,
        "markdownRatePct": 3.4,
        "payrollEarnedHours": 1875,
        "payrollScheduledHours": 1890,
        "payrollActualHours": 1882,
        "salesVsForecastDollars": -5000,
        "salesVsForecastPct": -1.6,
        "compPct": 1.7,
        "weekOverWeekPct": 2.3,
        "grossMarginDollars": 89975,
        "payrollVsEarnedHours": 7,
        "payrollVsEarnedPct": 0.4
      },
      "guest": {
        "guestTransactions": 1485,
        "guestScore": 81,
        "checkoutWaitMinutes": 3.3,
        "guestRecoveryIncidents": 8,
        "pickupComplaints": 3
      },
      "operations": {
        "inStockPct": 96.9,
        "onShelfAvailabilityPct": 96.1,
        "fulfillmentPickupOnTimePct": 95.9,
        "pickupOrders": 286,
        "backroomTaskCompletionPct": 92,
        "myDayCommsCompletionPct": 95
      },
      "team": {
        "scheduledHeadcount": 132,
        "actualHeadcount": 131,
        "callOuts": 1,
        "coverageGapHoursByDaypart": {
          "opening": 0,
          "midday": 2,
          "afternoon": 1,
          "close": 1
        },
        "onboardingTrainingCompletionPct": 91
      }
    },
    {
      "date": "2026-08-26",
      "dayName": "Wednesday",
      "dayIndex": 3,
      "financials": {
        "actualSales": 315000,
        "forecastSales": 320000,
        "lastYearSales": 306000,
        "priorWeekSales": 308000,
        "grossMarginPct": 29.9,
        "markdownRatePct": 3.0,
        "payrollEarnedHours": 1925,
        "payrollScheduledHours": 1940,
        "payrollActualHours": 1931,
        "salesVsForecastDollars": -5000,
        "salesVsForecastPct": -1.6,
        "compPct": 2.9,
        "weekOverWeekPct": 2.3,
        "grossMarginDollars": 94185,
        "payrollVsEarnedHours": 6,
        "payrollVsEarnedPct": 0.3
      },
      "guest": {
        "guestTransactions": 1510,
        "guestScore": 83,
        "checkoutWaitMinutes": 3.0,
        "guestRecoveryIncidents": 6,
        "pickupComplaints": 2
      },
      "operations": {
        "inStockPct": 97.0,
        "onShelfAvailabilityPct": 96.2,
        "fulfillmentPickupOnTimePct": 96.3,
        "pickupOrders": 301,
        "backroomTaskCompletionPct": 93,
        "myDayCommsCompletionPct": 96
      },
      "team": {
        "scheduledHeadcount": 135,
        "actualHeadcount": 133,
        "callOuts": 2,
        "coverageGapHoursByDaypart": {
          "opening": 1,
          "midday": 1,
          "afternoon": 2,
          "close": 1
        },
        "onboardingTrainingCompletionPct": 92
      }
    },
    {
      "date": "2026-08-27",
      "dayName": "Thursday",
      "dayIndex": 4,
      "financials": {
        "actualSales": 340000,
        "forecastSales": 345000,
        "lastYearSales": 329000,
        "priorWeekSales": 332000,
        "grossMarginPct": 29.6,
        "markdownRatePct": 3.6,
        "payrollEarnedHours": 2040,
        "payrollScheduledHours": 2060,
        "payrollActualHours": 2051,
        "salesVsForecastDollars": -5000,
        "salesVsForecastPct": -1.4,
        "compPct": 3.3,
        "weekOverWeekPct": 2.4,
        "grossMarginDollars": 100640,
        "payrollVsEarnedHours": 11,
        "payrollVsEarnedPct": 0.5
      },
      "guest": {
        "guestTransactions": 1625,
        "guestScore": 80,
        "checkoutWaitMinutes": 3.6,
        "guestRecoveryIncidents": 10,
        "pickupComplaints": 4
      },
      "operations": {
        "inStockPct": 96.8,
        "onShelfAvailabilityPct": 96.0,
        "fulfillmentPickupOnTimePct": 95.1,
        "pickupOrders": 335,
        "backroomTaskCompletionPct": 91,
        "myDayCommsCompletionPct": 94
      },
      "team": {
        "scheduledHeadcount": 142,
        "actualHeadcount": 141,
        "callOuts": 1,
        "coverageGapHoursByDaypart": {
          "opening": 0,
          "midday": 2,
          "afternoon": 3,
          "close": 2
        },
        "onboardingTrainingCompletionPct": 92
      }
    },
    {
      "date": "2026-08-28",
      "dayName": "Friday",
      "dayIndex": 5,
      "financials": {
        "actualSales": 385000,
        "forecastSales": 400000,
        "lastYearSales": 372000,
        "priorWeekSales": 390000,
        "grossMarginPct": 28.8,
        "markdownRatePct": 4.8,
        "payrollEarnedHours": 2270,
        "payrollScheduledHours": 2335,
        "payrollActualHours": 2251,
        "salesVsForecastDollars": -15000,
        "salesVsForecastPct": -3.8,
        "compPct": 3.5,
        "weekOverWeekPct": -1.3,
        "grossMarginDollars": 110880,
        "payrollVsEarnedHours": -19,
        "payrollVsEarnedPct": -0.8
      },
      "guest": {
        "guestTransactions": 1830,
        "guestScore": 76,
        "checkoutWaitMinutes": 4.7,
        "guestRecoveryIncidents": 17,
        "pickupComplaints": 8
      },
      "operations": {
        "inStockPct": 95.9,
        "onShelfAvailabilityPct": 94.8,
        "fulfillmentPickupOnTimePct": 92.6,
        "pickupOrders": 421,
        "backroomTaskCompletionPct": 84,
        "myDayCommsCompletionPct": 88
      },
      "team": {
        "scheduledHeadcount": 155,
        "actualHeadcount": 149,
        "callOuts": 6,
        "coverageGapHoursByDaypart": {
          "opening": 1,
          "midday": 4,
          "afternoon": 7,
          "close": 3
        },
        "onboardingTrainingCompletionPct": 90
      }
    },
    {
      "date": "2026-08-29",
      "dayName": "Saturday",
      "dayIndex": 6,
      "financials": {
        "actualSales": 550000,
        "forecastSales": 575000,
        "lastYearSales": 535000,
        "priorWeekSales": 560000,
        "grossMarginPct": 27.9,
        "markdownRatePct": 6.2,
        "payrollEarnedHours": 3040,
        "payrollScheduledHours": 3125,
        "payrollActualHours": 2982,
        "salesVsForecastDollars": -25000,
        "salesVsForecastPct": -4.3,
        "compPct": 2.8,
        "weekOverWeekPct": -1.8,
        "grossMarginDollars": 153450,
        "payrollVsEarnedHours": -58,
        "payrollVsEarnedPct": -1.9
      },
      "guest": {
        "guestTransactions": 2480,
        "guestScore": 69,
        "checkoutWaitMinutes": 6.2,
        "guestRecoveryIncidents": 31,
        "pickupComplaints": 18
      },
      "operations": {
        "inStockPct": 94.6,
        "onShelfAvailabilityPct": 92.7,
        "fulfillmentPickupOnTimePct": 88.4,
        "pickupOrders": 618,
        "backroomTaskCompletionPct": 76,
        "myDayCommsCompletionPct": 79
      },
      "team": {
        "scheduledHeadcount": 178,
        "actualHeadcount": 166,
        "callOuts": 12,
        "coverageGapHoursByDaypart": {
          "opening": 2,
          "midday": 6,
          "afternoon": 14,
          "close": 5
        },
        "onboardingTrainingCompletionPct": 88
      }
    },
    {
      "date": "2026-08-30",
      "dayName": "Sunday",
      "dayIndex": 7,
      "financials": {
        "actualSales": 320000,
        "forecastSales": 335000,
        "lastYearSales": 310000,
        "priorWeekSales": 325000,
        "grossMarginPct": 28.4,
        "markdownRatePct": 5.1,
        "payrollEarnedHours": 1990,
        "payrollScheduledHours": 2020,
        "payrollActualHours": 1989,
        "salesVsForecastDollars": -15000,
        "salesVsForecastPct": -4.5,
        "compPct": 3.2,
        "weekOverWeekPct": -1.5,
        "grossMarginDollars": 90880,
        "payrollVsEarnedHours": -1,
        "payrollVsEarnedPct": -0.1
      },
      "guest": {
        "guestTransactions": 1540,
        "guestScore": 74,
        "checkoutWaitMinutes": 5.1,
        "guestRecoveryIncidents": 19,
        "pickupComplaints": 10
      },
      "operations": {
        "inStockPct": 95.4,
        "onShelfAvailabilityPct": 93.8,
        "fulfillmentPickupOnTimePct": 91.2,
        "pickupOrders": 376,
        "backroomTaskCompletionPct": 82,
        "myDayCommsCompletionPct": 85
      },
      "team": {
        "scheduledHeadcount": 145,
        "actualHeadcount": 141,
        "callOuts": 4,
        "coverageGapHoursByDaypart": {
          "opening": 1,
          "midday": 3,
          "afternoon": 6,
          "close": 3
        },
        "onboardingTrainingCompletionPct": 89
      }
    }
  ],
  "narrativeHook": {
    "hookMetric": "Saturday guest score dropped to 69 and pickup on-time dropped to 88.4% despite weekly sales comp remaining positive at +3.0%.",
    "hypothesisSignals": [
      "Saturday afternoon Fulfillment/Pickup lost 9 critical hours from four call-outs after partial backfill.",
      "The store was already scheduled above earned hours for the week, but the lost hours landed in the wrong daypart, so the week-level payroll card hides the service-risk pattern.",
      "Pickup on-time fell to 82.1% during 14:00-18:00, and 11 pickup-related guest recovery incidents were recorded in that department/daypart.",
      "Front End backup calls overlapped the pickup rush while checkout wait reached 8.4 minutes and the guest-score dip was visible.",
      "Backroom task completion closed Saturday at 76%; Sunday on-shelf availability was 93.8%."
    ],
    "dashboardShowsButDoesNotExplain": "A Power BI view can show the red Saturday Guest and Operations cells, but the observation hypothesis comes from connecting UKG call-outs, pickup queue timing, and MyDayComms/task completion.",
    "drilldownLevel1SaturdayDaypart": [
      {
        "date": "2026-08-29",
        "daypart": "Opening",
        "timeRange": "06:00-10:00",
        "guestScore": 78,
        "guestFeedbackResponses": 42,
        "checkoutWaitMinutes": 3.9,
        "pickupOnTimePct": 95.2,
        "pickupOrders": 86,
        "guestRecoveryIncidents": 4,
        "criticalCoverageGapHours": 2,
        "primaryGap": "Front End meal-break stacking"
      },
      {
        "date": "2026-08-29",
        "daypart": "Midday",
        "timeRange": "10:00-14:00",
        "guestScore": 72,
        "guestFeedbackResponses": 61,
        "checkoutWaitMinutes": 5.8,
        "pickupOnTimePct": 90.5,
        "pickupOrders": 157,
        "guestRecoveryIncidents": 3,
        "criticalCoverageGapHours": 6,
        "primaryGap": "Fulfillment pick queue + Grocery pulls"
      },
      {
        "date": "2026-08-29",
        "daypart": "Afternoon",
        "timeRange": "14:00-18:00",
        "guestScore": 61,
        "guestFeedbackResponses": 76,
        "checkoutWaitMinutes": 8.4,
        "pickupOnTimePct": 82.1,
        "pickupOrders": 241,
        "guestRecoveryIncidents": 18,
        "criticalCoverageGapHours": 14,
        "primaryGap": "Fulfillment/Pickup call-outs not visible in sales plan"
      },
      {
        "date": "2026-08-29",
        "daypart": "Close",
        "timeRange": "18:00-22:00",
        "guestScore": 68,
        "guestFeedbackResponses": 51,
        "checkoutWaitMinutes": 6.5,
        "pickupOnTimePct": 86.9,
        "pickupOrders": 134,
        "guestRecoveryIncidents": 6,
        "criticalCoverageGapHours": 5,
        "primaryGap": "Recovery queue carried into close"
      }
    ],
    "drilldownLevel2AfternoonDepartment": [
      {
        "date": "2026-08-29",
        "daypart": "Afternoon",
        "department": "Fulfillment / Pickup",
        "scheduledHours": 52,
        "actualHours": 43,
        "gapHours": 9,
        "callOuts": 4,
        "pickupOnTimePct": 82.1,
        "guestRecoveryIncidents": 11,
        "missingItemComplaints": 7,
        "observableSignal": "Pickup queue exceeded staffed pick capacity by 14:40.",
        "pickupOrdersPickedByDepartment": 164,
        "pickupOrdersRelationship": "Subset allocation: Fulfillment/Pickup picked or staged 164 of the 241 Saturday afternoon pickup orders; the remaining 77 were handoff/drive-up orders handled outside the Fulfillment pick queue.",
        "missingItemComplaintsRelationship": "Subset measure: 7 missing-item complaints are included in Saturday daily pickupComplaints = 18; department rows do not represent a complaint-total breakdown."
      },
      {
        "date": "2026-08-29",
        "daypart": "Afternoon",
        "department": "Front End",
        "scheduledHours": 64,
        "actualHours": 61,
        "gapHours": 3,
        "callOuts": 2,
        "checkoutWaitMinutes": 8.4,
        "guestRecoveryIncidents": 5,
        "observableSignal": "Backup cashier calls overlapped drive-up rush.",
        "pickupOrdersHandledOutsideFulfillmentPickQueue": 77,
        "pickupOrdersRelationship": "Subset allocation: these 77 handoff/drive-up orders complete the 241 Saturday afternoon pickup orders when added to Fulfillment/Pickup's 164 picked/staged orders."
      },
      {
        "date": "2026-08-29",
        "daypart": "Afternoon",
        "department": "Grocery",
        "scheduledHours": 48,
        "actualHours": 46.5,
        "gapHours": 1.5,
        "callOuts": 1,
        "onShelfAvailabilityPct": 89.6,
        "guestRecoveryIncidents": 2,
        "observableSignal": "Cooler replenishment tasks deferred after 15:00.",
        "pickupOrdersRelationship": "Not applicable; this department row explains staffing/task effects, not pickup-order volume allocation."
      },
      {
        "date": "2026-08-29",
        "daypart": "Afternoon",
        "department": "Style",
        "scheduledHours": 36,
        "actualHours": 35.5,
        "gapHours": 0.5,
        "callOuts": 1,
        "taskCompletionPct": 78,
        "guestRecoveryIncidents": 0,
        "observableSignal": "Reshop queue grew, but it is not the primary signal in this observation hypothesis.",
        "pickupOrdersRelationship": "Not applicable; this department row explains staffing/task effects, not pickup-order volume allocation."
      }
    ]
  },
  "semanticPalette": {
    "background": "#FFFFFF",
    "textPrimary": "#111827",
    "textSecondary": "#374151",
    "good": "#0F7B0F",
    "warning": "#8A5A00",
    "bad": "#B42318",
    "target": "#2563EB",
    "prior": "#6B7280",
    "neutralFill": "#F3F4F6",
    "gridline": "#E5E7EB",
    "focusOutline": "#7C3AED"
  },
  "dataDisclosure": {
    "exactWording": "Illustrative simulation data only. Store, sales, labor, guest, and operations values are synthetic and are not Target operational data.",
    "recommendedPlacement": "Persistent footer below the dashboard title and repeated in the final details panel; use 12px text minimum, #374151 on white, with an info icon."
  }
}
```
