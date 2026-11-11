# AWAS_IGWM

Supporting data for the paper **"A Dynamic Bi-Level Multiagent Framework for
Long-Term Integrated Green Infrastructure and Water Resource Management"**,
submitted to *Water Resources Research*.

## What this repository contains

This repository hosts all the raw data used to generate the body-text data
figures (Figure 5 -- 8) of the paper, plus a metadata README that describes
the variables, units, and experimental setup associated with every data
series. Body-text Figures 1 -- 4 are conceptual diagrams and a study-area
map without underlying data series.

| File | Description |
| ---- | ----------- |
| `A. Data of Figures.xlsx` | Raw data series for Figure 5, 6, 7, and 8. Each sheet in the workbook corresponds to one body-text figure. |
| `B. Parameters information of Figures.txt` | Variable definitions, units, and methodological notes for every series in the workbook. |

## Quick guide to the figures

The paper reports a 10-year DBL-MAS simulation of watershed-scale integrated
green-infrastructure and water-resource management (IGWM) on a hypothetical
case study modelled after the Boulder City -- Yuma section of the Colorado
River Lower Basin.  Three water allocation schemes are compared head-to-head:

* **WTS** -- Water Trading Scheme (initial base rights + free trading)
* **WQS** -- Water Quota Scheme (binding surface-water withdrawal caps)
* **WTaS** -- Water Tariff Scheme (low-flow thresholds with progressive
  tax penalties)

Each policy--GI scenario and sensitivity setting is simulated across **ten
independent optimization runs** under identical inputs and parameter bounds;
the figures and this workbook report the ten-run sample mean, the sample
standard deviation (SD), and the observed minimum--maximum range.  Two
performance metrics are reported:

* **Mean unit cost** -- present-value cost of water supplied ($/m^3)
* **Gini coefficient** -- inter-city disparity in cost-normalized water
  supply across the seven riparian urban areas

| Sheet | Figure | Layout | Variables |
| ----- | ------ | ------ | --------- |
| `Figure 5 (lt_perf)`  | Body-text Figure 5 | 2 metrics x 3 schemes, 10-year annual ten-run mean / min / max + fixed short-term comparator | 2 metrics x 1 scenario x 3 schemes |
| `Figure 6 (g_perf)`   | Body-text Figure 6 | 2 metrics x 3 schemes, with-GIs vs. without-GIs annual contrasts | 2 metrics x 2 scenarios x 3 schemes |
| `Figure 7 (c_g_sens)` | Body-text Figure 7 | 2 metrics x 2 drivers (discount rate, combined hydroclimatic) x 3 schemes | 2 x 2 x 3 sensitivity table |
| `Figure 8 (cost_gini_synthesis)` | Body-text Figure 8 | Horizon mean unit cost vs. horizon mean Gini for 6 policy/GI combinations, mean +/- 1 SD | 2 metrics x 2 scenarios x 3 schemes |

## Data conventions

* Every repeated-run group contains ten runs; "mean" is the ten-run sample
  mean and "SD" the sample standard deviation (denominator nine).
* The present-value convention used in the manuscript is
  `horizon summary = mean(annual series) / (1 + dr)` with the baseline
  annual discount rate `dr = 0.05`.
* Values in the "Fixed ST comparator" column correspond to the equivalent
  metrics from a 1-year short-term IGWM simulation, used as the comparison
  reference for the long-term outcomes.
* In Figure 6 the shaded envelope is
  `[min(with) - max(without), max(with) - min(without)]` across the two
  scenario run ranges.
* All cost values are in US dollars per cubic metre ($/m^3); Gini
  coefficients are dimensionless and bounded on [0, 1].
