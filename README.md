# Smart Grid Decision Support System (SG-DSS)

### A Data-Driven Framework for Prioritizing Power Distribution and Reducing ATC&C Losses in Nigeria

![Python](https://img.shields.io/badge/Python-3.13-blue?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-orange?logo=jupyter&logoColor=white)
![Power Systems](https://img.shields.io/badge/Power%20Systems-pandapower-green)
![Analytics](https://img.shields.io/badge/Analytics-Statistical%20Modelling-purple)
![Status](https://img.shields.io/badge/Project-Research%20Prototype-yellow)

## Overview

The **Design and Implementation of Smart Grid Decision Support System (SG-DSS)** is a data-driven research project designed to support evidence-based decision-making in Nigeria's electricity sector. It focuses on characterising Aggregate Technical, Commercial and Collection (ATC&C) losses, examining their relationship with revenue losses, evaluating transmission loss trends, and prioritising potential interventions across electricity distribution companies (DisCos).

The project combines statistical analysis, data visualisation, regression modelling, power-system simulation and anomaly-detection techniques to demonstrate how data analytics can support electricity-sector planning and loss-reduction strategies.

The initial analysis covers Nigeria's eleven electricity distribution companies and selected quarterly sector-level indicators from 2024 to the second quarter of 2026. A Smart Grid Intervention Priority Index (SGIPI) is introduced to rank DisCos according to their relative ATC&C loss performance.

> **Research objective:** To design and implement a data-driven Smart Grid Decision Support System for optimising power distribution and reducing ATC&C losses in the Nigerian electricity sector.



The empirical analysis uses the stated reporting periods and datasets. Simulated network and anomaly-detection outputs are treated as experimental demonstrations rather than measurements of actual Nigerian electricity networks.

## Key Analytical Components

| Component | Purpose | Main techniques |
|---|---|---|
| DisCo ATC&C analysis | Compare 2025 loss performance across eleven DisCos | Descriptive statistics and bar charts |
| Quarterly ATC&C trends | Examine changes from 2024/Q1 to 2026/Q2 | Time-series visualisation |
| Revenue-loss analysis | Examine the association between ATC&C loss and revenue loss | Pearson correlation and linear regression |
| SGIPI | Rank relative intervention priority | Min-max normalisation and threshold-based classification |
| Transmission-loss analysis | Compare TLF observations with a benchmark | Trend and comparative analysis |
| Technical-loss simulation | Investigate the effect of selected network interventions | pandapower power-flow analysis |
| Consumption anomaly detection | Explore unusual consumption patterns | Isolation Forest and synthetic test data |

## Preliminary Findings

The current analytical dataset produces the following preliminary results for the 2025 DisCo-level ATC&C analysis:

| Indicator | Preliminary result |
|---|---:|
| Number of DisCos analysed | 11 |
| Mean ATC&C loss | 43.41% |
| Lowest ATC&C loss — Eko | 16.13% |
| Lowest ATC&C loss — Ikeja | 20.22% |
| Highest ATC&C loss — Kaduna | 71.88% |
| Sample standard deviation | 16.95 percentage points |
| Coefficient of variation | Approximately 39.05% |

These results indicate substantial differences in reported ATC&C performance across the eleven DisCos. The SGIPI is intended to translate such differences into a transparent, relative prioritisation framework.



## Smart Grid Intervention Priority Index (SGIPI)

The SGIPI is a normalised indicator designed to rank DisCos according to their relative ATC&C loss values.

For DisCo \(i\), the index is calculated as:

\[
SGIPI_i=\frac{L_i-L_{\min}}{L_{\max}-L_{\min}}
\]

Where:

- \(L_i\) is the ATC&C loss of DisCo \(i\).
- \(L_{\min}\) is the minimum ATC&C loss among the eleven DisCos.
- \(L_{\max}\) is the maximum ATC&C loss among the eleven DisCos.

The index ranges from 0 to 1. Higher scores indicate greater relative loss performance concerns within the study population.

### Intervention phases

| SGIPI score | Priority phase | Interpretation |
|---|---|---|
| 0.70–1.00 | Phase 1 — Immediate | Highest relative intervention priority |
| 0.40–less than 0.70 | Phase 2 — Short-term | Intermediate relative priority |
| Below 0.40 | Phase 3 — Medium-term | Lower relative priority |

**Important:** SGIPI measures relative priority within the observed dataset. 

## Technology Stack

- **Python:** Core programming and analysis.
- **Jupyter Notebook:** Reproducible analytical workflows.
- **NumPy:** Numerical computation.
- **pandas:** Data manipulation and preparation.
- **Matplotlib:** Statistical charts and visualisations.
- **scikit-learn:** Exploratory machine-learning and anomaly-detection methods.
- **pandapower:** Electrical network modelling and power-flow simulation.
- **Git and GitHub:** Version control and project collaboration.

## Repository Structure

```text
Smart-Grid-DSS/
│
├── notebooks/
│   ├── 01_atcc_disco_analysis.ipynb
│   ├── 02_quarterly_atcc_trends.ipynb
│   ├── 03_atcc_revenue_regression.ipynb
│   └── 04_transmission_loss_analysis.ipynb
│
├── src/
│   └── sgipi_analysis.py
│
├── outputs/
│
├── .gitignore
├── README.md
└── requirements.txt
```

### Directory descriptions

- `notebooks/` contains the Jupyter notebooks for the main statistical analyses and visualisations.
- `src/` contains reusable Python functions and analytical logic, including SGIPI calculations.
- `outputs/` is intended for generated charts, tables and other research outputs.
- `requirements.txt` records the Python dependencies required to reproduce the analyses.
- `.gitignore` excludes virtual environments, temporary files and other files that should not be version-controlled.


## Data Sources and Research Integrity

The research uses publicly reported electricity-sector indicators, including data attributed to the Nigerian Electricity Regulatory Commission (NERC) and the Transmission Company of Nigeria (TCN), subject to the availability and scope of each dataset but AMI consumption data used for theft detection was simulated, because no labelled Nigerian meter-tampering data is publicly available.





## Future Development

Planned extensions include:
Future research should extend the SGIPI into a multi-criteria index using the Analytic Hierarchy Process (AHP), validate the framework with feeder-level and smart-meter data from a cooperating DisCo, evaluate theft-detection performance using real labelled inspection data, and apply formal time-series forecasting when a sufficiently long and consistent quarterly dataset becomes available.

## Author

**Adio Muizz Adeniyi**

Business Intelligence & Data Analytics | Power Systems Analytics | Decision Support Systems



GitHub: https://github.com/adiomuizz


## Licence

A licence has not yet been specified. Reuse and redistribution should follow the applicable data-source terms and any licence subsequently selected for this repository.
