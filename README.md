# EPL Competitiveness Analysis

Analyzing whether financial inequality is driving competitive decline in the Premier League (2000-2024) using Databricks, PySpark, and Delta Lake.

## Research Question
**"Is the Premier League becoming less competitive, and is financial inequality driving this change?"**

## Tech Stack
- **Platform**: Databricks (Spark 4.0.0)
- **Languages**: Python, PySpark, SQL
- **Storage**: Delta Lake
- **Visualization**: Plotly (coming soon)
- **Data Source**: Transfermarkt (web scraping with BeautifulSoup)

## Project Structure
| Notebook | Purpose |
|----------|---------|
| `01_data_ingestion` | Scrape squad values, transfer spending, and league tables from Transfermarkt (2000-2024) |
| `02_data_processing` | Standardize club names across 46 clubs, join into unified dataset |
| `03_metric_calculations` | Calculate Gini coefficients, HHI, correlations, regressions, era comparisons |
| `04-08 dashboards` | Interactive Plotly dashboards (in progress) |

## Key Findings So Far
- **Points Gini rising** (0.15 → 0.22): The league is becoming less competitive
- **Money explains 67-89% of results**: Squad value strongly predicts final position
- **The Paradox**: Financial concentration is decreasing but competitive inequality is increasing
- **No trend in title margin** (p=0.92): The title race itself hasn't gotten worse — inequality is in the middle and bottom of the table

## Data Coverage
- 25 seasons (2000/01 - 2024/25)
- 500 club-season records
- Squad market values available from 2004/05
- Transfer spending available for all seasons

## Delta Lake Tables
| Table | Records | Description |
|-------|---------|-------------|
| `squad_market_values` | 500 | Squad valuations per club per season |
| `transfer_spending` | 500 | Transfer income/expenditure per club per season |
| `league_tables` | 500 | Final standings, points, wins, goals |
| `unified_season_data` | 500 | Joined dataset with era labels |
| `competitiveness_metrics` | 21-25 | All metrics per season |
| `era_comparison` | 5 | Average metrics by financial era |