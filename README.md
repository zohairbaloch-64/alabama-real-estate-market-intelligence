# Alabama Real Estate Market Intelligence

End-to-end data science project analyzing 7,805 sold residential properties across Alabama — covering market trends, geographic pricing patterns, negotiation dynamics, and two machine learning models built and validated against baselines.

## Overvie

Using a 2026 statewide dataset of sold listings, this project answers four practical questions:

1. What does the Alabama residential market look like right now — price levels, property mix, and geographic hot spots?
2. Which markets favor buyers, and which favor sellers?
3. What drives a home's final sale price, and can it be predicted reliably?
4. Can a home's negotiation outcome (sold above, at, or below asking) be predicted before it sells?

## Dataset

Alabama Sold Real Estate Intelligence 2026 — 7,805 sold listings across 418 ZIP codes and 350+ cities, covering single-family homes, condos, townhomes, and multi-family properties.

## Project Structure

| Section | Description |
|---|---|
| 1. Data Cleaning & Feature Engineering | Nulls audit, corrupted-record correction, city extraction from listing URLs |
| 2. Market Overview | Price distributions, property type mix, top markets by volume and price |
| 3. Geographic Market Map | Interactive Plotly map + static fallback of price and volume by city |
| 4. Negotiation Intelligence | Above/at/below-asking dynamics by city and price band |
| 5. Statistical Deep Dive | Correlation analysis and price-per-sqft drivers |
| 6. Price Prediction Model | Linear Regression, Random Forest, and XGBoost, benchmarked against a naive baseline with 5-fold cross-validation |
| 7. Negotiation Outcome Classifier | XGBoost model benchmarked against a majority-class baseline |
| 8. Business Insights | Actionable recommendations for sellers, buyers, and investors |

## Key Results

- **Price Prediction:** XGBoost achieves R² = 0.70 on held-out data (0.697 ± 0.021 across 5-fold cross-validation), reducing prediction error by ~39% versus a naive city-median baseline.
- **Negotiation Classifier:** Beats a majority-class baseline by 8.4 percentage points, with listing-price positioning emerging as the strongest predictive signal.
- **Geographic Insight:** Two distinct price-premium clusters identified — coastal Baldwin County (vacation/second-home demand) and Birmingham's suburbs (commuter/school-district demand) — that are not the state's highest-volume markets.

## Tech Stack

`Python` · `pandas` · `numpy` · `matplotlib` · `seaborn` · `plotly` · `scikit-learn` · `xgboost`

## Repository Contents

```
├── Alabama_Real_Estate_Market_Intelligence_2026.ipynb   # Full analysis notebook
├── alabama_real_estate_2026.csv                          # Source dataset
└── README.md
```

## Running Locally

```bash
git clone https://github.com/zohairbaloch-64/alabama-real-estate-market-intelligence.git
cd alabama-real-estate-market-intelligence
pip install pandas numpy matplotlib seaborn plotly scikit-learn xgboost jupyter
jupyter notebook Alabama_Real_Estate_Market_Intelligence_2026.ipynb
```

## Limitations

- The dataset spans a short 2026 window (primarily May–July), so seasonal trends beyond this period cannot be inferred.
- Geographic visualizations use curated city-centroid coordinates for market-level context, not per-property geocoding.
- `listPrice` is intentionally excluded from the price-prediction model to avoid circular valuation; a production AVM would typically incorporate it alongside comparable-sales data.

## Author

**Muhammad Zohair Baloch**
Data Analytics

[Kaggle](https://kaggle.com/zohairbaloch) · [GitHub](https://github.com/zohairbaloch-64) · [LinkedIn](https://linkedin.com/in/zohair-baloch-data-analyst)
