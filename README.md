# Electricity Price Behavior in Italy: A Data Analysis for Trading Insights

## Project Overview and Research Objective
This project explores the behavior of the Italian electricity market between 2021 and 2025 through a data-driven analysis of energy prices, electricity demand, and generation dynamics.  
The study combines market price data from GME with generation and load data provided by Italian TSO, TERNA in order to investigate:
* supply-demand interactions
* price volatility
* seasonal and intraday patterns
* renewable generation impact

The project is entirely developed in Python using Jupyter Notebooks.

## Repository Structure
```text
energy-market-eda/
│
├── README.md
│
├── notebook/
│   ├── 01-0_data-collection.ipynb
│   ├── 02-1_prices-data-cleaning.ipynb
│   ├── 02-2_gen-data-cleaning.ipynb
│   ├── 02-3_load-data-cleaning.ipynb
│   ├── 03_dataset-merge.ipynb
│   ├── 04_exploratory-data-analysis.ipynb
│   └── ...
│
└── dataset/
    ├── clean/
    └── raw/
```

The project follows a modular analytical workflow including:
1. Data collection
2. Data cleaning and Temporal harmonization
3. Dataset merging
4. Exploratory data analysis (EDA)
5. Statistical interpretation of market dynamics

The repository structure mirrors the analytical workflow.  
Each notebook is numerically associated with a corresponding section of the README documentation.  
This modular organization improves reproducibility, readability, and project scalability.

## Data Pipeline

The raw datasets from GME and TERNA are processed through a structured pipeline that transforms heterogeneous time series into a unified analytical dataset.

The final output is an hourly aligned dataset containing:
- electricity prices (PUN index)
- electricity demand (load)
- electricity generation by source

This unified structure enables direct analysis of supply-demand interactions and market price dynamics over time.

## Data Cleaning

The data cleaning phase focuses on resolving inconsistencies across multiple datasets with different temporal resolutions and formats.

Key preprocessing tasks include:
- standardization of datetime formats
- resampling of quarter-hourly data to hourly frequency
- handling of missing or inconsistent observations
- alignment of datasets across identical time indexes

<!--
## Exploratory Data Analysis
The exploratory phase focuses on identifying key patterns in electricity market behavior, including:

- seasonal and intraday price dynamics
- correlation between demand and price levels
- impact of renewable generation on price volatility
- periods of market stress and negative pricing events


The analysis aims to uncover structural relationships between supply, demand, and price formation in the Italian electricity market.

## Future Developments

Potential extensions of this project include:
- incorporation of renewable production forecasts
- transition to 15-minute Market Time Unit data (post-2025 regulation changes)
- econometric modeling of price formation
- application of machine learning models for price forecasting
- integration of external variables such as gas prices and weather conditions
-->