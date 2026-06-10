# TechMint Owner Console — Reference Guide

The Owner Console is a private dashboard separate from the team-facing Mint Board. It gives you the business-level view of the Mint Marks program — costs, trends, and controls — without putting sensitive numbers on the wall for everyone to see.

---

## Sections

**Cost & Budget Tracker**
Shows the running program cost for the current month (calculated at the ~$0.05 per Mark exchange rate), total rewards redeemed and their dollar value, remaining monthly budget, and a projected end-of-month figure. A progress bar shows how close spending is to the monthly cap. This is the fastest way to answer the question: "what is this program costing me right now?"

To update the budget cap or exchange rate, locate the `BUDGET_CAP` and `MARKS_TO_DOLLAR` constants near the top of the file's script section and change the values there.

**ROI Signal Panel**
Tracks customer return rate this month versus last month, with a trend arrow showing whether returns are going up or down and by how much. Also shows a "returns prevented" estimate based on no-return bonuses awarded — a rough proxy for how much rework the program may be discouraging. These numbers are the beginning of the business case for the program.

The return rate data and prior-month figures are placeholder values in the current version. When connected to a live repair system, this section can be fed real ticket data automatically.

**Per-Tech Efficiency View**
A table showing every technician with four columns: jobs completed, Marks earned, Marks per job, and quality score (perfect inspections as a percentage of total jobs). The top performer in each column is highlighted subtly. This lets you see the difference between volume and quality — a tech doing fewer but harder jobs will look different here than one running up the count on quick repairs.

Nothing in this table needs to be configured. When connected to live data, it populates automatically from the same repair system feed that drives the Mint Board.

**Redemption History**
A log of every reward claimed — who redeemed, what reward, how many Marks were spent, and the date. A summary at the top shows the most popular reward and the total value paid out this quarter. If a reward is never showing up here, that's a signal to replace it in the catalog.

**Dispute & Flag Log**
A record of any contested point events. Each row shows the technician's name, what was disputed, the date filed, the current status (pending or resolved), and the manager's ruling once one is made. This is the audit trail that keeps the program fair and transparent — every decision is logged, nothing happens silently.

**Multiplier Controls**
A panel for activating limited-time point bonuses. Three pre-built options are included: Double Mark December, 2× Refurb Week, and Speed Bonus Fortnight. Each has an on/off toggle and a date range field. There is also a field to create a custom multiplier with a name, multiplier value, and date range.

To add a new pre-built multiplier option, find the multipliers array in the script section of the file and add an entry following the same format as the existing three.

---

## Changing the Placeholder Data

All data in the current version is hardcoded for demonstration. Every figure — technician names, job counts, redemption history, dispute log — lives in clearly labeled data objects near the top of the file's script section. Swap those values with real numbers before showing the console to the team, or leave them as-is for demo purposes.

When a live integration is in place (see the Integration Brief), this file's data layer can be replaced with API calls without touching the layout or logic. The structure was built with that handoff in mind.

---

## Access

The console is a standalone HTML file. Open it in any browser — no server required. Because it runs locally and isn't password-protected in its current form, keep the file off shared drives. A login screen or simple password gate can be added when the program moves to a hosted environment.
