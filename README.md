# Rapid Roofing Gross Profit Pacing

Shows where the quarter stands on gross profit against the GM comp plan: where we should be today,
actual gross profit, the estimate for jobs not closed yet, the bonus lines, the two gates
(team close rate and gross profit %), and what has to be sold and installed to reach each bonus line.

## How the numbers work
- Gross profit counts jobs installed this quarter (Completed date in AccuLynx).
- **Actual** = profit on installed jobs that are Closed (final profit).
- **Estimate** = installed jobs not Closed yet, at the margin the closed ones are running. Always labeled.
- When a month's P&L closes, enter its revenue and gross profit in `gp_plan.json` under `pl_months`.
  That month then uses the P&L and its estimate goes away. The bonus is paid on the P&L.
- Close rate gate = approvals / demos for the sales team roster, quarter to date.
- Every count comes from `rules/rr_metrics.py` in `rapidhsg/rr-metrics-data`. No counting logic lives here.

## Files
- `index.html` the board (Rapid Roofing Design System V2). Reads `data/gp.json`.
- `build_gp.py` builds `data/gp.json` from rr-metrics-data and `gp_plan.json`.
- `gp_plan.json` quarterly goals, base salary, bonus tiers, gates, closed P&L months. Joe sets goals at quarterly planning.
- `.github/workflows/refresh.yml` rebuilds every 15 minutes.
