# Loan Portfolio Revenue Forecast & Scenario Model (Excel)

A 12-month net interest income forecast for a small-business/professional
loan portfolio, built entirely in Excel — with a Base/Best/Stress scenario
toggle, a rate x delinquency sensitivity grid, and a one-page dashboard.
Companion to the `loan-portfolio-risk` (SQL + Python) analysis — this piece
demonstrates the Excel modeling side: pivot-style aggregation, INDEX/MATCH
lookups, SUMPRODUCT, scenario-driven formulas, and a live chart.

## What's inside

- **README tab** — how to use the model, color legend
- **Portfolio Summary** — starting balance, rate, and delinquency rate by
  credit tier (sourced from the same synthetic dataset as the SQL project)
- **Assumptions** — a scenario dropdown (Base / Best / Stress) driving
  monthly volume growth, a rate shift, and a delinquency stress multiplier,
  pulled via `INDEX`/`MATCH`
- **Revenue Forecast** — a 12-month balance rollforward and net interest
  income projection that recalculates automatically when the scenario changes
- **Sensitivity Analysis** — a 5x5 grid showing Year-1 net interest income
  across combinations of rate shift and delinquency stress
- **Dashboard** — KPI summary and a live chart of monthly NII under the
  selected scenario

## How to use it

Open `Loan_Portfolio_Forecast_Model.xlsx` in Excel. On the **Assumptions**
tab, change the yellow "Selected Scenario" cell to `Base`, `Best`, or
`Stress` — the Revenue Forecast and Dashboard tabs update automatically.

## Notes

- Built with real Excel formulas throughout (no hardcoded results) —
  `SUMPRODUCT`, `INDEX`/`MATCH`, `SUMIFS`-style aggregation, and a live chart.
- Portfolio inputs are sourced from a synthetically generated dataset (see
  the `loan-portfolio-risk` repo); this demonstrates modeling methodology,
  not real portfolio performance.
- One notable finding surfaced by the sensitivity grid: at this portfolio's
  current rate and delinquency levels, revenue is more rate-sensitive than
  delinquency-sensitive within the ranges tested — a +200 bps rate increase
  raises NII by more than a 1.6x delinquency stress erodes it.
