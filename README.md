# Decision Support System for Electricity Price Guarantees

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Simulation code for the paper:

> **Aggregator electricity price guarantees for households with flexibility potential utilizing thermal building inertia**  
> Leo Semmelmann, Steven Kimbrough, Philipp Staudt

## Overview

We propose a mechanism where aggregators offer **individual low-price guarantees** to households with flexibility potential (heat pumps, PV, battery storage, thermal storage, building thermal inertia) in exchange for operational control. This transfers price risk from risk-averse households to aggregators while enabling demand response participation.


## Requirements

```bash
pip install numpy pandas matplotlib seaborn scipy statsmodels gurobipy workalendar scikit-learn
```

> ⚠️ **Note:** Requires a [Gurobi](https://www.gurobi.com/) license (free academic licenses available).

## Repository Structure

```
├── 01 Run Serial Simulations.ipynb   # Monte Carlo simulation (Gurobi optimization)
├── 02 Initial Analysis.ipynb         # Exploratory analysis 
├── 03 Final Analysis.ipynb           # Guarantee prediction and risk evaluation
├── data/
│   ├── building_parameters/          # 1R1C thermal model parameters
│   ├── weather/                       # Temperature and irradiance data - not shared publicly due to copyright
│   ├── PV/                            # PV generation profiles  - not shared publicly due to copyright
│   ├── SLP/                           # Standard load profiles  - not shared publicly due to copyright
│   └── DE DayAhead *.xlsx            # Day-ahead electricity prices 
├── results/                          # Simulation outputs (.pkl)
└── plots/                            # Generated figures and tables
```

## Usage

1. **Run simulations** — Execute `01 Run Serial Simulations.ipynb` to generate household cost data under dynamic and constant pricing scenarios
2. **Explore results** — Use `02 Initial Analysis.ipynb` for initial analysis
3. **Evaluate guarantees** — Run `03 Final Analysis.ipynb` to train the quantile regression model and assess aggregator risk

## Data Availability

Most input data cannot be shared publicly due to licensing restrictions (weather data, empirical setpoint profiles, etc.). However, all data files can be shared for collaboration on advances of the approach - feel free to get in touch via 📧 leo.semmelmann [at] kit.edu.
The building parameters from [Sperber et al. (2020)](https://doi.org/10.1016/j.enbuild.2020.110144) are included in the data folder.

