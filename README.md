# Financial Analysis Project — SEC Filings & Investment Intelligence

End-to-end financial analysis of 58 US public companies using 
real SEC EDGAR quarterly filing data. Calculates 8 key financial 
ratios and identifies top-performing and most stable companies 
for investment screening.

## Dashboard

**[View Full Dashboard (PDF) →](./Investment_project_dashboard.pdf)**

![Dashboard Preview](./dashboard_preview.png)

> Built in Power BI · Data sourced from SEC EDGAR quarterly filings

---

## Business Context

Investment analysts and portfolio managers need a fast way to 
screen hundreds of companies across key financial health metrics. 
This project automates that process — ingesting raw SEC filings, 
calculating standardized ratios, and surfacing the top and 
bottom performers across multiple dimensions.

**The core question:** Which companies are genuinely performing 
well across profitability, efficiency, and financial stability — 
and which ones are outliers worth investigating?

---

## What I Did

### Data Engineering (Python)
- Ingested 5 batches of SEC EDGAR quarterly filing CSVs
- Filtered 10 key financial tags from thousands of XBRL fields
- Pivoted company-level data for ratio calculation
- Cleaned infinite values, nulls, and incomplete filings
- Exported investor-ready dataset for Power BI

### Financial Ratios Calculated

| Ratio | Formula | What It Measures |
|-------|---------|-----------------|
| Net Margin | Net Income / Revenue | Profitability after all costs |
| Gross Margin | Gross Profit / Revenue | Core business efficiency |
| R&D to Revenue | R&D Expense / Revenue | Innovation investment intensity |
| ROA | Net Income / Total Assets | Asset utilization efficiency |
| ROE | Net Income / Stockholders Equity | Return on shareholder investment |
| Debt-to-Equity | Total Liabilities / Equity | Financial leverage and risk |
| Current Ratio | Current Assets / Current Liabilities | Short-term liquidity |
| ROS | Operating Income / Revenue | Operational efficiency |

### Power BI Dashboard
- Built interactive dashboard with dark professional theme
- KPI cards for trimmed mean metrics across all 58 companies
- Top 5 rankings for ROE, Net Margin, Revenue, ROA
- Debt-to-Equity analysis highlighting financial risk
- Outlier detection and honorable mention feature

---

## Key Findings

### Overall Market (58 Companies)

| Metric | Trimmed Mean |
|--------|-------------|
| Net Margin | 0.44 |
| ROE | 0.10 |
| ROA | 0.03 |
| Debt-to-Equity | 22.24 |

### Top Performers

**Top 5 by ROE:**
1. Pfizer Inc — 19.65
2. Voya Retirement Insurance — 7.14
3. Bristol Myers Squibb — 6.09
4. FRP Holdings Inc — 5.68
5. Cheniere Energy Inc — 3.36

**Top 5 by Net Margin:**
1. Kingston Company Inc — 25.40
2. Alexandria Inc — 13.59
3. Ingles Markets Inc — 4.38
4. Hartford Insurance Group — 1.48
5. Textron Inc — 0.35

**Top 10 by Revenue:**
Public Storage, Boeing, Hartford, and 7 others
(see full dashboard)

### Notable Finding — The Outlier
**SEI Investments Co** flagged as statistical outlier:
- ROE = 121.51 (12x above trimmed mean)
- Net Margin = 13,774.27 (extreme outlier)

This finding demonstrates the value of outlier detection 
in financial screening — extreme values often indicate 
data anomalies, accounting differences, or genuinely 
exceptional business models that warrant deeper investigation.

### Debt Risk Flags
Companies with highest negative Debt-to-Equity ratios 
(indicating liabilities exceed equity — financial risk signal):
- Lincoln National Life: -203.10
- GATX Corp: -91.86
- Voya Retirement Insurance: -90.86
- Selective Insurance: -58.76
- Boeing Co: -48.07

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python (pandas, numpy) | Data ingestion, cleaning, ratio calculation |
| SEC EDGAR | Source data (quarterly XBRL filings) |
| Power BI | Interactive dashboard and visualization |
| Google Colab | Development environment |

---

## Files

| File | Description |
|------|-------------|
| `Financial analysis project.ipynb` | Full Python pipeline: ingest, clean, calculate ratios, export |
| `Investment_project_dashboard.pdf` | Power BI dashboard export |
| `README.md` | This file |

*Note: Raw SEC filing CSV batches not included due to file size.*

---

## Data Source

**SEC EDGAR** — The U.S. Securities and Exchange Commission's 
Electronic Data Gathering, Analysis, and Retrieval system. 
All data is publicly available at `data.sec.gov`.

The dataset covers quarterly financial statements (10-Q filings) 
from US public companies, extracted using XBRL financial tags.

---

## What I Would Add Next

1. **Time series analysis** — track ratio trends across quarters 
   for each company instead of a single snapshot
2. **Sector benchmarking** — compare companies within their 
   industry rather than across all sectors
3. **Automated screening tool** — input criteria and get 
   a ranked watchlist automatically
4. **Integration with live SEC data** — pull real-time 
   quarterly filings via the SEC EDGAR API

--- 
