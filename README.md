# Pay Isn't the Problem: IBM Employee Attrition Analysis

IBM's voluntary attrition rate (16.1%) is approximately 2× the U.S. tech sector benchmark, costing an estimated $9.25M annually. This project investigates *why* employees leave and models which interventions are self-funding on a total-cost basis.

## Approach

Descriptive analysis of attrition patterns across department, role, level, tenure, and compensation, followed by a multivariate logistic regression with SMOTE class balancing to identify drivers that hold up after controlling for confounders, followed by a Monte Carlo simulation of four combined policy interventions.

## Key finding

Three drivers each independently predict attrition: **workload** (overtime), **career stage** (job level + role tenure), and **engagement** (job involvement + relationship satisfaction). Compensation drops out of the final model — pay is correlated with job level at r=0.95 and is addressed through the career stage lever rather than as a separate driver.

## Recommendation

A **75% overtime reduction** paired with **accelerated L1→L2 promotion** (1 year). Projected to reduce attrition from 16.1% to 11.8% — below the U.S. cross-industry benchmark — with $0.39M in net annual savings under a salaried-exempt workforce assumption.

## Results at a glance

| Scenario | Attrition rate | Δ vs baseline | Net savings | Notes |
|---|---|---|---|---|
| Baseline (no change) | 16.1% | — | — | $9.25M annual cost continues |
| 25% OT + L1 promo | ~14.4% | −10.6% | −$0.82M | Doesn't pay for itself |
| 50% OT + L1 promo | ~12.8% | −20.5% | −$0.21M | Approaches break-even |
| **75% OT + L1 promo** ⭐ | **11.8%** | **−26.9%** | **+$0.39M** | **First self-funding option** |
| 100% OT + L1 promo | ~10.9% | −32.3% | +$0.99M | Largest savings; operationally aggressive |

## Caveats and assumptions

- **Observational data.** Findings show association, not causation. The simulation projects directional impact, not a guaranteed forecast.
- **Workforce-type assumption.** Net savings assume a salaried-exempt workforce (no OT premium). Under an hourly-workforce assumption, net savings at 75% OT rise to $1.62M, and the recommendation flips at 50% OT.
- **Replacement cost assumption.** Cost-per-departure model uses a 50% salary replacement cost; break-even occurs at 130%. Sensitivity tested across 30–130%.
- **Pay correlation.** Monthly income was excluded from the final model due to multicollinearity with job level (r=0.95). The career stage lever is interpreted as also addressing compensation; this is a modeling choice rather than a claim that pay doesn't matter.
- **Class imbalance.** Original data was 16% positive class; SMOTE oversampling was applied during training to address imbalance. Probability calibration was checked on holdout data.
- **Residual population.** Even with both levers applied, a residual high-risk group remains (L2–L3 R&D mid-tenure employees below median income, not on overtime). The recommended policies do not reach this group; they are flagged as the next intervention frontier.

## Stack

Python · pandas · scikit-learn · imbalanced-learn (SMOTE) · matplotlib · numpy

