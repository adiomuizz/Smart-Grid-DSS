# Smart Grid Decision Support System (SG-DSS)

### A Data-Driven Framework for Optimising Power Distribution and Reducing ATC&C Losses in Nigeria

![Python](https://img.shields.io/badge/Python-3.13-blue?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-orange?logo=jupyter&logoColor=white)
![Power Systems](https://img.shields.io/badge/Power%20Systems-pandapower-green)
![Analytics](https://img.shields.io/badge/Analytics-Statistical%20Modelling-purple)
![Status](https://img.shields.io/badge/Project-Research%20Prototype-yellow)

## Overview

The **Smart Grid Decision Support System (SG-DSS)** is a data-driven research project designed to support evidence-based decision-making in Nigeria's electricity sector. It focuses on characterising Aggregate Technical, Commercial and Collection (ATC&C) losses, examining their relationship with revenue losses, evaluating transmission loss trends, and prioritising potential interventions across electricity distribution companies (DisCos).

The project combines statistical analysis, data visualisation, regression modelling, power-system simulation and anomaly-detection techniques to demonstrate how data analytics can support electricity-sector planning and loss-reduction strategies.

The initial analysis covers Nigeria's eleven electricity distribution companies and selected quarterly sector-level indicators from 2024 to the second quarter of 2026. A Smart Grid Intervention Priority Index (SGIPI) is introduced to rank DisCos according to their relative ATC&C loss performance.

> **Research objective:** To design and implement a data-driven Smart Grid Decision Support System for optimising power distribution and reducing ATC&C losses in the Nigerian electricity sector.

## Research Objectives

The project seeks to:

1. Characterise ATC&C loss performance across Nigeria's eleven DisCos.
2. Quantify variations in loss performance using descriptive statistics.
3. Examine the relationship between quarterly ATC&C losses and reported revenue losses.
4. Analyse quarterly trends in ATC&C losses and transmission losses.
5. Develop the Smart Grid Intervention Priority Index (SGIPI) for intervention prioritisation.
6. Demonstrate power-system simulation techniques for evaluating technical-loss reduction scenarios.
7. Explore data-driven anomaly detection as a potential approach to identifying unusual electricity-consumption patterns.
8. Provide an analytical foundation for a decision-support framework that can be extended with validated operational data.

## Study Scope

The research focuses on the Nigerian electricity transmission and distribution context, with particular attention to:

- **Distribution performance:** ATC&C loss comparisons across the eleven DisCos.
- **Revenue analysis:** Quarterly relationships between ATC&C loss rates and reported revenue losses.
- **Transmission performance:** Transmission Loss Factor (TLF) trends relative to the selected benchmark.
- **Intervention prioritisation:** SGIPI-based classification of relative DisCo performance.
- **Technical-loss simulation:** Illustrative distribution-network scenarios using pandapower.
- **Anomaly detection:** Exploratory identification of unusual consumption patterns using machine-learning methods.

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

The findings are preliminary and should be interpreted alongside the underlying source data, reporting definitions, benchmark applicability and methodological limitations.

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

**Important:** SGIPI measures relative priority within the observed dataset. It is not a direct measure of absolute technical losses, financial viability or the expected impact of an intervention. Its rankings may change when the comparison population or observation period changes.

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

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/Smart-Grid-DSS.git
cd Smart-Grid-DSS
```

Replace `YOUR-USERNAME` with the appropriate GitHub username.

### 2. Create and activate a virtual environment

On Windows PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

### 3. Install dependencies

```powershell
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

### 4. Register the Jupyter kernel

```powershell
python -m ipykernel install --user --name smart-grid-dss --display-name "Python (Smart Grid DSS)"
```

Open the repository in Visual Studio Code, open a notebook and select **Python (Smart Grid DSS)** as the kernel.

### 5. Run the analyses

Execute the notebooks in the `notebooks/` directory. Run their cells sequentially to reproduce the available statistical results and charts.

Some analyses may require additional source datasets that are not included in the repository. Ensure those inputs are available and their file paths are correctly configured before running the relevant notebook.

## Data Sources and Research Integrity

The research uses publicly reported electricity-sector indicators, including data attributed to the Nigerian Electricity Regulatory Commission (NERC) and the Transmission Company of Nigeria (TCN), subject to the availability and scope of each dataset.

Before publication or reuse, users should consult the original reports and verify the figures, reporting periods, definitions and benchmark values used in the analysis.

The repository distinguishes between:

- **Reported data:** Observations extracted from identified reports or other documented sources.
- **Derived results:** Statistics, indices, regression estimates and visualisations calculated from the input data.
- **Simulated data:** Synthetic observations and illustrative electrical-network scenarios created for testing and demonstration.

Simulated results must not be interpreted as actual field measurements. Data provenance and transformations should be documented so that results can be independently reproduced.

## Methodological Considerations

The analytical framework has several limitations:

1. Quarterly regression analysis based on four observations is exploratory and does not establish causality.
2. A normalised SGIPI is sensitive to the minimum and maximum observations in the comparison dataset.
3. ATC&C is an aggregate performance indicator and should not be interpreted as a direct measurement of technical network losses alone.
4. Transmission-loss benchmarks must be matched to the relevant regulatory methodology, period and definition before comparison.
5. Simulated network performance depends on the assumed network parameters, load conditions and operating scenarios.
6. Anomaly-detection performance must be validated against reliable labelled data before operational deployment.
7. Conclusions are constrained by the coverage, quality and consistency of the available source data.

## Future Development

Planned extensions include:

- Integrating additional validated transmission and distribution datasets.
- Developing a modular decision-support architecture.
- Expanding power-flow simulations to evaluate feeder, transformer and network-configuration interventions.
- Improving anomaly detection using appropriately validated consumption and metering data.
- Conducting sensitivity and robustness analyses of SGIPI rankings.
- Developing an interactive dashboard for monitoring loss performance and intervention priorities.
- Evaluating the framework using operational data and domain-expert feedback.

## Project Status

**Status:** Research prototype under development.

The current repository establishes the statistical analysis and visualisation foundation. Further development is required to integrate validated operational data, complete the simulation and anomaly-detection modules, and evaluate the decision-support framework.

## Author

**Adio Muizz Adeniyi**

Business Intelligence & Data Analytics | Power Systems Analytics | Decision Support Systems

Portfolio: https://muizzportfolio.vercel.app

GitHub: https://github.com/adiomuizz

## Acknowledgement

This research draws on publicly available electricity-sector reporting and open-source scientific computing tools. All source data and external materials should be credited to their respective owners.

## Licence

A licence has not yet been specified. Reuse and redistribution should follow the applicable data-source terms and any licence subsequently selected for this repository.
