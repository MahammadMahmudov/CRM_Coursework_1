# CRM Coursework 1: S&P 500 Market Analysis and Stock Segmentation Using RFM

Mahammad Mahmudov (w2098243), 6BUIS017W CRM & CM with Business Intelligence

## Contents

| File | What it is |
|---|---|
| `CRM_Coursework.ipynb` | Full analysis for Tasks 1 to 3, run top to bottom with all outputs saved |
| `sp500_constituents.csv` | Ticker list with company name and GICS sector, from Wikipedia |
| `adj_close_raw.csv`, `close_raw.csv`, `volume_raw.csv` | Raw daily data for all tickers, before exclusions |
| `benchmark_raw.csv` | Raw daily data for the ^GSPC benchmark |
| `exclusion_log.csv` | Excluded tickers and the reason for each |
| `inclusion_log.csv` | Step-by-step share count from 503 tickers to 486 shares |
| `validation_checks.csv` | Results of the data validation checks |
| `feature_table.csv` | One row per share: sector, mean weekly return, beta, Recency, Frequency, Monetary |
| `feature_table_common.csv` | The common set of 486 shares used for all clustering |
| `cluster_assignments.csv` | Feature table plus Ward and K-means labels, and the R and F only sensitivity labels |

## How to run

1. Open `CRM_Coursework.ipynb` in Google Colab.
2. Create the folder `MyDrive/CRM_Coursework` in Google Drive.
3. Choose Runtime, then Run all. The notebook mounts Google Drive, downloads the data and saves every output CSV to that folder.

## Data and reproducibility

- Ticker list: Wikipedia S&P 500 constituents, retrieved 19 November 2026 (503 tickers).
- Prices and volume: yfinance with auto_adjust=False, 2021-01-01 to 2025-01-01 (end date exclusive), benchmark ^GSPC.
- RFM observation date: 31 December 2024.
- Final common set: 486 shares (see `exclusion_log.csv` and `inclusion_log.csv`).
- Re-running the notebook downloads fresh data. The Wikipedia list and Yahoo's adjusted prices change over time, so a re-run can differ slightly. The CSV files in this repository are the exact data snapshots used in the report.

## Package versions

Python 3.13 (Google Colab), pandas 2.2.3, numpy 2.4.6, yfinance 0.2.66, scikit-learn 1.6.1, SciPy 1.16.3, matplotlib 3.10.0.
