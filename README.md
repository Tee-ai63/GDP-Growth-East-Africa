# GDP Growth and Economic Performance: Kenya in East African and Global Context (2015–2025)

Interactive Power BI dashboard and Python analysis of GDP growth, inflation, and per-capita income for Kenya versus East African and continental peers, built using World Bank World Development Indicators (WDI) data.

**AnalystLab Africa — Data Analyst Internship, Week 8 Capstone Project**

---

## 📌 Project Overview

Kenya's economic trajectory is best understood in comparison — not isolation. This project analyzes GDP growth and related macroeconomic indicators for **Kenya** alongside six comparator economies (**Burundi, Nigeria, Rwanda, South Africa, Tanzania, Uganda**), plus **Sub-Saharan Africa** and **World** benchmarks, across an eleven-year window (**2015–2025**).

The goal: identify how Kenya's growth, price stability, and wealth-per-person compare to its peers, surface any notable shocks or turning points, and turn those findings into an interactive dashboard and a set of clear, evidence-based recommendations.

## 🎯 Objective

- Apply the full data analytics workflow — cleaning, transformation, analysis, visualization — to a real-world development dataset.
- Build an interactive Power BI dashboard with KPI cards, trend analysis, and comparative visualizations.
- Generate insights and recommendations grounded in the data, not assumption.

## 🗂️ Dataset

**Source:** [World Bank — World Development Indicators (WDI)](https://datatopics.worldbank.org/world-development-indicators/)

- Full extract: 396,970 rows × 70 columns (all countries, all indicators, 1960–2025)
- Filtered to **9 geographic units** × **5 indicators** × **11 years (2015–2025)**

**Indicators used:**
| Code | Indicator |
|---|---|
| `NY.GDP.MKTP.CD` | GDP (current US$) |
| `NY.GDP.MKTP.KD.ZG` | GDP growth (annual %) |
| `NY.GDP.PCAP.CD` | GDP per capita (current US$) |
| `FP.CPI.TOTL.ZG` | Inflation, consumer prices (annual %) |
| `NE.EXP.GNFS.ZS` | Exports of goods and services (% of GDP) |

**Countries/regions:** Kenya, Burundi, Nigeria, Rwanda, South Africa, Tanzania, Uganda, Sub-Saharan Africa, World

## 🧹 Data Cleaning Process

Performed in Python (pandas), fully documented in [`notebooks/01_explore_data.ipynb`](notebooks/01_explore_data.ipynb):

1. **Filtered** the raw dataset to target countries and indicators (45 rows).
2. **Melted** from wide format (year-per-column) to long/tidy format (495 rows).
3. **Pivoted** indicators into their own columns for an analysis-ready shape (99 rows × 8 columns).
4. **Completeness check** — found 22 missing values, all confined to "Exports of goods and services (% of GDP)" for **Burundi** and **Nigeria** across every year. Left as-is (NaN) rather than estimated, and documented transparently rather than concealed.
5. Saved the cleaned dataset to `data/processed/gdp_east_africa_cleaned.csv`.

## 🔍 Key Findings

- **Kenya** ranks 3rd in GDP per capita (2025) among the peer group — behind only World and South Africa — while posting above-average, stable growth (4.63% avg, 2015–2025).
- **Kenya's COVID-19 resilience:** 2020 contraction was just -0.27%, far shallower than Nigeria, South Africa, and the Sub-Saharan Africa average (all -3% to -6%).
- **Rwanda** leads on growth (7.02% avg) but with the most volatility and the lowest GDP per capita in the set.
- **Nigeria's GDP per capita fell 52.7%** between 2015 and 2025 — a currency/FX-driven collapse, not a real-growth story, coinciding with the 2023 naira devaluation.
- **Kenya's 2024–2025 macro position** (steady growth + cooling inflation + record GDP per capita) is the healthiest combination in its own decade-long series.

Full findings, insights, and recommendations are in [`report/GDP_EastAfrica_Final_Report.pdf`](report/GDP_EastAfrica_Final_Report.pdf).

## 📊 Dashboard

Built in Power BI — two pages:
- **Page 1 (Dashboard):** 4 KPI cards (GDP Growth, GDP per Capita, Inflation, Total GDP) driven by Country/Year slicers, a GDP growth trend line, an inflation trend line, a GDP per capita ranking bar chart, and a map — all featuring Kenya, 8 peer countries/regions, and 2015–2025 coverage.
- **Page 2 (About This Dashboard):** project overview, usage instructions, and data notes.

![Dashboard Screenshot](images/dashboard_final.png)

📁 Power BI file: [`dashboard/GDP_EastAfrica_Dashboard.pbix`](dashboard/GDP_EastAfrica_Dashboard.pbix)

## 🎥 Demo Video

[Link to demo video] *(add your video link here)*

## 🛠️ Tools & Technologies

- **Python** — pandas (cleaning, transformation, analysis), matplotlib (exploratory charts)
- **Power BI Desktop** — interactive dashboard, DAX measures
- **Jupyter Notebook** — analysis documentation

## 📁 Repository Structure
GDP-Growth-East-Africa/
│
├── data/
│ ├── raw/ # Original WDI download
│ └── processed/ # Cleaned, pivoted dataset
│
├── notebooks/
│ └── 01_explore_data.ipynb # Full cleaning + exploratory analysis
│
├── dashboard/
│ └── GDP_EastAfrica_Dashboard.pbix # Power BI file
│
├── report/
│ └── GDP_EastAfrica_Final_Report.pdf
│
├── images/ # Chart exports + dashboard screenshots
│
└── README.md


## 👤 Author

**Tess Kamau**
Data Analyst | Economics & Finance | [LinkedIn](https://linkedin.com/in/tesskamau) | [Medium](https://medium.com/@wanjirutee4) | [GitHub](https://github.com/Tee-ai63)

---
*Completed as the final capstone project of the AnalystLab Africa Data Analyst Internship.
