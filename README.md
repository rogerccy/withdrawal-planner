# Withdrawal Planner

A retirement withdrawal simulator. Enter your portfolio and assumptions to see a year-by-year projection of how long your money lasts — in both today's dollars and the nominal amounts you'll actually withdraw.

**Live:** https://rogerccy.github.io/withdrawal-planner/

## Features

- **Two withdrawal strategies** — Fixed Withdrawal (annuity formula, hits an exact end balance) and Guardrails (dynamic spending that adjusts ±10% based on portfolio performance)
- **Nominal vs real withdrawal** — table shows both the real amount (today's purchasing power) and the nominal amount you'll actually transfer each year
- **Inflation-aware** — enter nominal return and inflation separately; real return is computed automatically
- **Stress test** — guardrails mode overlays a second scenario with return −3% to simulate a prolonged bad market
- **Portfolio chart** — SVG line chart of balance over time for both base and stress scenarios, with hover tooltips
- **GitHub Gist sync** — inputs auto-save to a private Gist (`fire-settings.json`) with 1.2s debounce, syncing across devices
- **Local fallback** — works without a GitHub account via `localStorage`
- **EN / 中文** language toggle

## Inputs

| Field | Default | Notes |
|---|---|---|
| Current age | 50 | |
| Portfolio / investments | $1,000,000 | Starting balance for the simulation |
| Expected annual return (nominal) | 10% | Before inflation — e.g. broad stock index |
| Inflation rate | 3% | Subtracted to get real return used in simulation |
| Expected death age | 85 | Simulation horizon |
| **Fixed mode** — Target remaining at death | $0 | $0 = Die With Zero |
| **Guardrails mode** — Initial withdrawal rate | 5% | % of portfolio withdrawn in year one |
| **Guardrails mode** — Upper guardrail | +20% | Cut spending 10% if rate rises above IWR × 1.20 |
| **Guardrails mode** — Lower guardrail | −20% | Raise spending 10% if rate falls below IWR × 0.80 |

## Setup

1. Open the app and paste a GitHub Personal Access Token with `gist` scope ([create one here](https://github.com/settings/tokens/new?scopes=gist&description=withdrawal-planner))
2. Enter your numbers — results appear immediately
3. Settings auto-save to a private Gist after you stop typing

On a new device, enter the same token and the app restores your inputs automatically.
