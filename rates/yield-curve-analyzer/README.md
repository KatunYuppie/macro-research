# Yield Curve Analyzer

A quantitative tool for analyzing the US Treasury yield curve using live data from the Federal Reserve Economic Data (FRED) API.

---

## Overview

This notebook pulls daily US Treasury yield data across 10 maturities and provides a structured analysis of curve shape, key spreads, and inversion signals. The analysis is grounded in fixed income fundamentals and designed to support macro research workflows.

---

## Features

- Current yield curve visualization across all key maturities
- Key spread analysis: 2Y10Y, 3M10Y, 2Y30Y
- Inversion detection with flat curve warnings
- Clean, reproducible data pipeline from FRED to output

---

## Data Source

All data is sourced from the [FRED API](https://fred.stlouisfed.org/) maintained by the Federal Reserve Bank of St. Louis. The following series are used:

| Maturity | FRED Series ID |
|----------|---------------|
| 3-Month | DGS3MO |
| 6-Month | DGS6MO |
| 1-Year | DGS1 |
| 2-Year | DGS2 |
| 3-Year | DGS3 |
| 5-Year | DGS5 |
| 7-Year | DGS7 |
| 10-Year | DGS10 |
| 20-Year | DGS20 |
| 30-Year | DGS30 |

---

## Setup & Installation

**1. Clone the repository**
```bash
git clone https://github.com/KatunYuppie/macro-research
cd macro-research/rates/yield-curve-analyzer
```

**2. Install dependencies**
```bash
pip install -r requirements.txt
```

**3. Get a FRED API key**
Register for a free API key at [fred.stlouisfed.org](https://fred.stlouisfed.org/docs/api/api_key.html) and add it to the notebook where indicated.

---

## Usage

Open `yield_curve_analyzer.ipynb` in VS Code or Jupyter and run all cells in order. The notebook is self-contained and pulls live data on each run.

---

## Output

- **Yield Curve Chart**: current curve shape across all 10 maturities with yield labels
- **Spread Table**: current values for 2Y10Y, 3M10Y, and 2Y30Y spreads
- **Inversion Status**: flags any inverted or flat segments of the curve

---

## Methodology

Spreads are calculated as the difference between long and short maturity yields. A negative spread indicates inversion. A spread below 25 basis points triggers a flat curve warning, which historically precedes inversion.

---

## Future Development

- Interactive date picker for historical curve comparison
- Real yield analysis using TIPS data
- Breakeven inflation rate calculation
- Multi-country curve comparison — US, UK, Germany, Japan

---

*Part of the [macro-research](https://github.com/KatunYuppie/macro-research) repository.*
