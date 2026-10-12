# Russia Ukraine-War's Impact on the Cost of a Healthy Diet

## Overview

## Data Sources

The analysis uses data from the World Bank's two datasets:

- **[Food Prices for Nutrition (FPN)](https://datacatalog.worldbank.org/search/dataset/0061222/food-prices-for-nutrition-fpn):** Country-level data on the cost of a healthy diet.
- **[World Development Indicators (WDI)](https://datacatalog.worldbank.org/search/dataset/0037712/world-development-indicators):** Country-level socioeconomic and development indicators.

## Countries and Variables

### Countries

- **Treated country:** Egypt
- **Donor pool:** Brazil, Colombia, India, Indonesia, Kazakhstan, Malaysia, Mexico, Peru, the Philippines, South Africa, and Thailand.

### Variables

- **Outcome variable:** Cost of a healthy diet (per person per day, PPP USD).
- **Predictor variables:**
  - GDP per capita
  - Inflation (%)
  - Exchange rate
  - Agriculture, forestry, and fishing value added (% of GDP)
  - Trade (% of GDP)
  - Total population
  - Urban population (%)
  - Lagged cost of a healthy diet (per person per day, PPP USD)

### Study Period

- **Pre-treatment period:** 2017–2021
- **Post-treatment period:** 2022-2024, following the onset of the Russia–Ukraine war.

## Methodology

This study uses the Synthetic Control Method (SCM) to estimate the impact of the Russia–Ukraine war on the cost of a healthy diet in Egypt. 
The method constructs a synthetic version of Egypt as a weighted combination of comparable countries to approximate Egypt's pre-treatment outcome trajectory.

Egypt is the treated country, and the donor pool consists of 11 countries with comparable economic and demographic characteristics. 
The outcome variable is the cost of a healthy diet per person per day (PPP USD). Predictors include GDP per capita, inflation, exchange rate, 
agriculture, forestry, and fishing value added as a percentage of GDP, trade as a percentage of GDP, total population, urban population, and lagged diet costs.

The model is fitted using the pre-treatment period (2017–2021), with 2022 designated as the start of the treatment period. 
The observed cost of a healthy diet in Egypt is then compared with the estimated synthetic counterfactual for 2022–2024. 
The difference between the two trajectories represents the estimated treatment effect.

## Results

## Robustness Checks


## Repository Structure

```text
Russia-Ukraine-War-Diet-Cost/
├── README.md
├── egypt-healthy-diet-synthetic-control.Rmd
├── egypt-healthy-diet-synthetic-control.pdf
├── Russia-Ukraine-War-Diet-Cost.Rproj
├── data/
│   ├── price_of_healthy_diet_clean.csv
│   └── world_bank_indicators.csv
├── figures/
│   ├── actual-vs-synthetic-egypt.pdf
│   ├── gap-plot.pdf
│   └── placebo-plot.pdf
└── .gitignore
```

## Skills Demonstrated
