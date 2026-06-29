# 🌍 World Indicators Analysis Dashboard
### Live API Data Integration: Real-Time Global Insights with Python & Power BI

[![Python](https://img.shields.io/badge/Python-3.13-blue?logo=python&logoColor=white)](https://python.org)
[![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow?logo=powerbi)](https://powerbi.microsoft.com)
[![World Bank API](https://img.shields.io/badge/World%20Bank-Open%20API-green)](https://datahelpdesk.worldbank.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-lightgrey)](LICENSE)

---

## 📌 Project Overview

A **live, auto-refreshing Power BI dashboard** built on top of a Python ETL pipeline that pulls real-time data from the **World Bank Open API**. Covers **296 countries**, **27 indicators**, and **7 domains** — health, economy, labour, trade, environment, technology, and poverty — answering 8 global development questions.

> No manual data downloads. No stale reports. The dashboard updates automatically every time the pipeline runs.

---

## 💼 Business Problem

Global health and economic data is scattered, manually updated, and quickly outdated. This project automates the entire pipeline — from live API ingestion → Python transformation → Power BI visualization — giving analysts and researchers an always-current, multi-country dashboard.

---

## 🛠 Tech Stack

| Layer | Tools Used |
|---|---|
| Data Source | World Bank REST API (Live) |
| Data Processing | Python · Pandas · NumPy · Requests |
| Visualization (Python) | Seaborn · Matplotlib |
| BI Dashboard | Power BI Desktop · DAX · Power Query |
| Environment | Jupyter Notebook · Anaconda |

---

## ⚙️ How It Works

```
World Bank API  →  Python (Pandas ETL)  →  CSV Export  →  Power BI Dashboard
```

1. **Extract** — Paginated API loop fetches 27 indicators for 296 countries (post-2015)
2. **Transform** — `pd.json_normalize()` flattens nested JSON · inner join with country metadata · column standardization
3. **Load** — 7 category DataFrames exported as CSVs · loaded into Power BI via Python Script source
4. **Visualize** — DAX KPIs · slicers · scatter trend charts · Python seaborn heatmap inside Power BI

---

## 📊 Dashboard Highlights

| Visual | What It Shows |
|---|---|
| 5 KPI Cards | Avg GDP/capita ($19.52K) · Trade Value ($143B) · Health Spend (6.76% GDP) · GDP Growth (2.61%) · Forest Area (31.80%) |
| Bar Chart | Health expenditure comparison by region |
| Line Chart | 5 key indicator trends from 2016–2025 |
| Scatter + Trend Line | Health expenditure vs. Life expectancy |
| Top 10 Table | Countries by avg life expectancy (Monaco: 85.95 yrs) |
| Python Heatmap | Seaborn correlation matrix of 13 health indicators |

---

## 💡 Key Insights

- **Monaco, Japan & Hong Kong** lead global life expectancy (83–86 years)
- **North America** spends the highest % of GDP on healthcare across all regions
- **Higher health spending** positively correlates with longer life expectancy
- **DPT & measles immunization** rates are strongly correlated (r ≈ 0.88)
- **Internet penetration** shows a downward trend with unemployment over time
- **Sub-Saharan Africa** has the lowest health spending and lowest life expectancy — a clear investment gap

---

## ▶️ How to Run

```bash
# 1. Clone the repo
git clone https://github.com/yourusername/worldbank-api-powerbi-dashboard.git

# 2. Install dependencies
pip install pandas numpy requests seaborn matplotlib

# 3. Run the notebook
jupyter notebook API_Data.ipynb

# 4. Open dashboard_1.pbix in Power BI Desktop
# Set Python path: File → Options → Python scripting → set your env
# Click Refresh to reload all data
```

---

## 📁 Folder Structure

```
worldbank-api-powerbi-dashboard/
├── API_Data.ipynb                  # Python ETL pipeline
├── dashboard_1.pbix                # Power BI dashboard
├── docs/
│   └── dashboard_Analysis_Questions.pdf
├── data/
│   ├── health_indicators.csv
│   ├── economic_activity.csv
│   └── ... (5 more CSVs)
└── README.md

---

## 👤 Author

**Anshil Gautam** — B.Tech CSE | Data Analytics  


---

*Data: [World Bank Open Data API](https://datahelpdesk.worldbank.org) — Creative Commons Attribution 4.0*
