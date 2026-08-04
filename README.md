# Global City Tourism Analysis
### Which cities are thriving, growing, or underperforming — and why?

## Overview

A data science project analyzing tourism health across 23 cities worldwide
using real API data, machine learning clustering, and a composite scoring
index. The project identifies which cities are thriving in tourism, which
are growing, and which are underperforming — and quantifies what drives
the difference.

**Tools:** Python, Jupyter Notebook, Plotly, XGBoost, scikit-learn
**Data sources:** Open-Meteo Archive API (weather), World Bank Open Data
API (infrastructure), Numbeo (cost of living), UNWTO (tourism momentum),
Global Peace Index (safety)

## Cities Analyzed

23 cities across 6 continents:

**USA:** Austin, New York, Chicago, Seattle, Kansas City
**Europe:** Paris, Dublin, Lisbon, Budapest, Ljubljana, Reykjavik
**Balkans and Middle East:** Mostar, Tel Aviv, Jerusalem, Baku
**Asia:** Bangkok, Singapore, Chiang Mai, Bishkek
**Africa and Americas:** Marrakech, Cape Town, Medellin, Tbilisi

## Methodology

Each city is scored across 8 dimensions:

- Digital Visibility (20%) — Google Trends estimated due to API rate limiting
- Weather Appeal (15%) — Open-Meteo Archive API real data 2023
- Affordability (15%) — Numbeo Cost of Living Index 2023
- Infrastructure (15%) — World Bank internet penetration API
- Outdoor Opportunity (10%) — AllTrails density national park access
- Urban Experience (10%) — UNESCO sites Michelin restaurants cultural institutions
- Tourism Momentum (10%) — UNWTO 2023 visitor growth data
- Safety (5%) — Global Peace Index 2023 Numbeo crime index

## Key Findings

Marrakech ranks number 1 despite being less globally recognized than Paris
or Bangkok — driven by near-perfect weather appeal (94.3), strong
affordability (70), and accelerating momentum (68).

Reykjavik ranks number 18 despite being one of the world's trendiest
destinations. Its weather score (32.0) and affordability score (12)
heavily penalize it in the composite index.

Tel Aviv fell to Underperforming — reflecting the dramatic tourism
contraction following the October 2023 conflict. Momentum score of 45
is the lowest in the dataset.

Digital visibility is king — Bishkek has a 95/100 outdoor score and
is one of the most affordable cities in the dataset, yet ranks last due
to near-zero global search interest.

XGBoost feature importance identified digital visibility as the strongest
predictor (0.243), followed by momentum (0.207) and affordability (0.162).

## Limitations

Google Trends data was manually estimated due to API rate limiting.
Affordability weighting slightly undervalues high-cost high-demand cities
like Paris, New York, and Singapore.
Country-level World Bank data was applied at city level which introduces
imprecision.
Data reflects a 2023 snapshot — geopolitical events can shift rankings rapidly.

## How to Run

1. Clone the repo
2. Install dependencies: pip install pandas numpy matplotlib seaborn scikit-learn xgboost plotly requests
3. Open tourism_analysis.ipynb in Jupyter Notebook
4. Run all cells from top to bottom

## Next Steps

- Collect live Google Trends data using a rotating proxy
- Expand to 50 or more cities for more robust clustering
- Add time-series dimension tracking score changes year over year
- Build a city recommendation engine based on traveler preferences

Data collected 2023-2024 from Open-Meteo, World Bank, Numbeo, UNWTO, and Global Peace Index.
Part of a data science portfolio.
