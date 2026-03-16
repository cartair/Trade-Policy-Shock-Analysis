# U.S. Trade Policy Shock Analysis

An empirical analysis of how major U.S. international trade relations with China have developed over the early 21st century, highlighting how policy shocks have affected bilateral trade flows, supply chain geography, and consumer import prices. Built using Python and live Federal Reserve Economic Data (FRED).

---

## Why This Project Matters

Trade policy is one of the most consequential and debated tools in macroeconomics. The U.S.-China trade war beginning in 2018,escalated in 2019, and continued with the sweeping 2025 tariff regime. These political actions represent three of the largest peacetime trade interventions in modern U.S. history. Yet the actual macroeconomic effects — on import volumes, supply chain geography, and consumer prices — are rarely visualized in an accessible, data-driven way.

This project asks a simple but important question: **did the tariffs actually work, and who paid the price?**

The findings suggest the answer is more complicated than policymakers on either side admit. #talk about findings here
---

## What the Code Does

- **Connects to the FRED API** to pull live macroeconomic data directly from the Federal Reserve, including bilateral trade flows, import price indices, and personal consumption expenditures
- **Cleans and structures the data** using pandas DataFrames, filtering to the 21st century for relevance and aligning series with different reporting frequencies
- **Generates four annotated charts** using matplotlib, each telling a distinct part of the trade policy story
- **Calculates before/after percentage changes** for each tariff shock using a 3-month window on either side of each event date, applying standard percentage change methodology
- **Builds embedded summary tables** beneath Charts 2 and 3 to display quantitative findings cleanly alongside the visualizations
- **Saves all charts as high-resolution PNGs** for sharing and presentation

---

## The Four Charts & What They Reveal

### Chart 1 — U.S.-China Trade Flows
Plots monthly U.S. imports from and exports to China from 2000 to present, with vertical markers at each major tariff event and percentage change annotations.

**Finding:** U.S. imports from China declined modestly after the July 2018 tariffs (-4.2%), more sharply after the September 2019 escalation (-15.6%), and most dramatically following the January 2025 tariff wave (-31.4%). However, the persistence of a large trade deficit even after repeated interventions raises questions about the structural effectiveness of tariffs as a rebalancing tool. Furthermore, the spike in the consumption of Chinese imports by the U.S. around 2022 reveals that tariffs, as a form of fiscal policy, often create short-lived impact. As major declines in Chinese imports follow each tariff as a shock, however the imports appear to eventually rise back to baseline levels and begin to flow with the business cycle of the economy.

### Chart 2 — Trade Diversion
Plots imports from China, Vietnam, and Mexico side by side with a summary table showing percentage changes across all three countries for each shock.

**Finding:** As Chinese imports declined with each tariff, imports from alternate trade partners such as Vietnam and Mexico yielded mixed results. In the case of trade between the U.S. and Vietnam, the tariffs placed on China seem to nurture a growing reliance upon Vietnamese imports in the U.S. economy. Trade between Mexico and the U.S. tells the same story, however in a slightly more indirect manner. Just by looking at the table, the changes in Mexican imports to the U.S. does not appear particularly substantial, however the chart reveals that in many cases, such as in the wake of each major tariff policy action, Mexican imports to the U.S. rise either at the same time or slightly after Chinese imports experience a decline, further supporting the idea of trade diversion. The economic theory of **trade diversion**: tariffs redirected supply chains rather than reshoring production to the United States. Manufacturers moved final assembly to third countries to avoid tariffs while maintaining largely the same production networks.

### Chart 3 — Import Price Effect
Plots Chinese import volume against the U.S. import price index on a dual-axis chart, with a summary table showing how both metrics moved around each shock.

**Finding:** Import volumes declined following each tariff, but it was not until the aftermath of the 2019 tariffs that import prices experienced a dramatic increase — a pattern consistent with **tariff pass-through to consumers**. Rather than China absorbing the cost through lower export prices, U.S. importers and ultimately consumers paid more for a smaller quantity of goods. This challenges the popular narrative that tariffs are primarily a cost borne by foreign exporters. This higher price index on imports appears to continue to hover at elevated levels while trade volume is about as low as it has been since 2020.

### Chart 4 — Consumer Import Dependence
Plots total domestic consumer spending (PCE) alongside imports as a share of total consumption, showing how reliant U.S. consumers are on foreign goods relative to domestic production over time.

**Finding:** Despite repeated tariff interventions, relative consumer import spending has remained structurally elevated. The tariffs produced short-term dips in import share but no sustained reduction in import dependence over a significant period of time, suggesting that the underlying consumer demand for foreign goods — particularly in electronics, apparel, and manufactured goods — is price-inelastic in the medium term.

---

## Data Sources

All data pulled live from the [Federal Reserve Economic Data (FRED)](https://fred.stlouisfed.org) API:

| Series | FRED Code |
|---|---|
| U.S. Imports from China | `IMPCH` |
| U.S. Exports to China | `EXPCH` |
| U.S. Trade Balance | `BOPGSTB` |
| Imports from Vietnam | `IMP5520` |
| Imports from Mexico | `IMPMX` |
| Import Price Index | `IR` |
| Personal Consumption Expenditures | `PCE` |

---

## Setup & Usage

1. Clone the repository
2. Install dependencies:
```
pip install fredapi pandas matplotlib python-dotenv
```
3. Create a `.env` file in the root directory:
```
FRED_API_KEY=your_key_here
```
4. Run the analysis:
```
python3 analysis.py
```

Get a free FRED API key at [fred.stlouisfed.org](https://fred.stlouisfed.org)

---

## Tech Stack

- **Python 3** — core language
- **pandas** — data manipulation and time series analysis
- **matplotlib** — data visualization
- **fredapi** — Federal Reserve Economic Data API wrapper
- **python-dotenv** — secure API key management

---

*Built as an independent macroeconomic research project. Data updated live via FRED API on each run.*
```

---

Once you paste it in, save it and then push it to GitHub with:
```
git add .
git commit -m "added README"
git push