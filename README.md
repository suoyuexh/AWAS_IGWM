# AWAS_IGWM

Supporting data for the paper **"A Dynamic Bi-Level Multiagent Framework for
Long-Term Integrated Green Infrastructure and Water Resource Management"**
by Mengxiang Zhang and Ting Fong May Chui (Department of Civil Engineering,
The University of Hong Kong), submitted to *Water Resources Research*.

## What this repository contains

This repository hosts all the raw data used to generate the body-text
figures (Figure 4 -- 6) of the paper, plus a metadata README that describes
the variables, units, and experimental setup associated with every data
series.

| File | Description |
| ---- | ----------- |
| `A. Data of Figures.xlsx` | Raw data series for Figure 4, 5, and 6. Each sheet in the workbook corresponds to one body-text figure. |
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

Four performance metrics are tracked:

* **Unit Cost** -- mean present-value cost of water supplied ($/m^3)
* **Gini coefficient** -- equity of water allocation across the seven
  riparian urban areas
* **Available surface water ratio** -- monthly available surface water
  storage for withdrawal, normalised by the maximum theoretical storage
* **Water cycle ratio** -- total water supplied divided by total urban
  stored water in a year (an indicator of stored-water utilisation)

| Sheet | Figure | Layout | Variables |
| ----- | ------ | ------ | --------- |
| `Figure 4 (lt_perf)`  | Body-text Figure 4 | 4 metrics x 3 schemes, 10-year annual series + LT mean + ST baseline | 4 metrics x 1 scenario x 3 schemes |
| `Figure 5 (g_perf)`   | Body-text Figure 5 | 4 metrics x 3 schemes, with-GIs vs. without-GIs 10-year series | 4 metrics x 2 scenarios x 3 schemes |
| `Figure 6 (c_g_sens)` | Body-text Figure 6 | 2 metrics (cost, Gini) x 2 drivers (discount rate, hydroclimatic) x 3 schemes | 2 x 2 x 3 sensitivity table |

## Methodological summary

* **Framework** -- Dynamic Bi-Level Multiagent System (DBL-MAS) grounded in
  Stackelberg game theory.  The WM (watershed manager) sets policies; the
  seven UWMs (urban water managers) choose water supply portfolios and
  green-infrastructure (GI) construction.  Inter-urban streamflow is
  routed with the Muskingum-Cunge equation.
* **GI portfolio** -- three GI types per urban area: infiltration-based
  GIs (e.g., infiltration trenches, porous pavements), rainwater
  harvesting systems, and stormwater harvesting systems.
* **Objective** -- minimise the present-value total IGWM cost (GI
  construction + water supply + wastewater drainage) subject to demand
  satisfaction, GI area limits, water-supply capacity, and the chosen
  allocation scheme's constraints.
* **Solution** -- nested simulation-based adaptive particle swarm
  optimisation (S-APSO) algorithm.  Discount rate dr = 0.05 in the
  baseline run.
* **Case study** -- 7 urban areas (Boulder City, Bullhead City/Laughlin,
  Needles, Lake Havasu City/Desert Hills, Parker/Bluewater/Parker
  Strip/Big River, Blythe/Ehrenberg, Yuma/Somerton/.../Winterhaven)
  along a 145 km stretch of the Colorado River Lower Basin.
* **Sensitivity sweeps** (Figure 6 only):
  * Discount rate: 0%, 2.5%, **5%** (baseline), 7.5%, 10%
  * Hydroclimatic forcing (upstream inflow & rainfall): 50%, 75%,
    **100%** (baseline), 125%, 150%

## Data conventions

* The present-value convention used in the manuscript is
  `LT_mean = mean(annual series) / (1 + dr)` with `dr = 0.05`.
* Values reported in the "ST baseline" column correspond to the
  equivalent metrics from a 1-year short-term IGWM simulation, used as
  the comparison reference for the long-term outcomes.
* All cost values are in US dollars per cubic metre ($/m^3).
* Gini coefficients, available surface water ratios, and water cycle
  ratios are dimensionless and bounded on [0, 1].

## How to cite

If you reuse the data, please cite the original paper:

> Zhang, M. and Chui, T. F. M. (in review). A Dynamic Bi-Level Multiagent
> Framework for Long-Term Integrated Green Infrastructure and Water
> Resource Management. *Water Resources Research*.

## Contact

For questions about the data, please contact:

* Mengxiang Zhang -- mxzhang6@connect.hku.hk
* Ting Fong May Chui -- maychui@hku.hk
