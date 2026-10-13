# Russia Ukraine-War's Impact on the Cost of a Healthy Diet

```r




```

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
Egypt was chosen as the treated country because Egypt relied on imported wheat or cereals. The donor pool was selected to include 
countries that did not rely as heavily on imported wheat or cereals, with the aim of constructing a synthetic Egypt that represents 
how Egypt's cost of a healthy diet might have been without the grain shock.

The outcome variable is the cost of a healthy diet per person per day (PPP USD). Predictors include GDP per capita, inflation, exchange rate, 
agriculture, forestry, and fishing value added as a percentage of GDP, trade as a percentage of GDP, total population, urban population, and lagged diet costs.

The model is fitted using the pre-treatment period (2017–2021), with 2022 designated as the start of the treatment period. 
The observed cost of a healthy diet in Egypt is then compared with the estimated synthetic counterfactual for 2022–2024. 
The difference between the two trajectories represents the estimated treatment effect relative to the synthetic control.

## Results

A Synthetic Egypt was created by assigning different weights to countries in the donor pool so that the synthetic unit closely follows Egypt
before 2022. The countries for creating synthetic Egypt was Indonesia (64.5%), Thailand (29.2%), South Africa (6.0%), and the Philippines (0.3%)
while the remaining countries received zero weight.
We assumed that without exposure to the grain shock, Egypt's healthy diet cost would have followed the same trajectory as synthetic Egypt. For this
interpretation to be valid, Egypt and Synthetic Egypt should have similar pre-treatment trends.

RMSPE measures the difference between the observed outcome and the synthetic control over a given period. 
The pre-treatment RMSPE was 0.141, compared with a post-treatment RMSPE of 7.47. This indicates that the 
synthetic control closely matched Egypt before 2022, while the difference between Egypt and synthetic Egypt 
became substantially larger after 2022. 

### Actual vs. Synthetic Egypt
![Actual vs. Synthetic Egypt](figures/actual-vs-synthetic-egypt.png)

During the pre-treatment period (2017–2021), the actual and synthetic series follow relatively similar trends. 
Following the onset of the treatment in 2022, the two series begin to diverge, with the actual cost of a healthy 
diet increasing more rapidly than the synthetic counterfactual. The gap remains positive through 2024, indicating 
that the cost of a healthy diet in Egypt was higher than the estimated counterfactual.

### Gap Plot
![Gap Plot](figures/gap-plot.png)

The gap plot shows the difference between Egypt's actual cost of a healthy diet and its synthetic counterfactual. 
The gap remains relatively small before 2022, then becomes positive and widens after the start of the treatment period. 
This pattern is consistent with an increase in Egypt's diet costs relative to the synthetic control.

### Placebo Analysis
![Placebo Analysis](figures/placebo-plot.png)

A placebo test was conducted to assess how Egypt's estimated gap compares with those of other countries. 
Each country in the donor pool was sequentially reassigned as the treated country. For each placebo country, 
a synthetic control was constructed using the remaining countries, and the gap between the observed and synthetic outcomes was calculated.

Compared with Egypt, all placebo countries exhibit smaller post-treatment deviations from their respective synthetic controls. 
This suggests that Egypt experienced a relatively large increase in the cost of a healthy diet compared with its synthetic control.


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
