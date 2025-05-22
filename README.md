# SP500-Portfolio-Construction
This repository builds a sample portfolio of historical S&P500 constituents, including proportional representation of delisted tickers to mitigate survivorship bias.

## Purpose
Readily available financial datasets typically exclude companies that have been removed from the index. This results in survivorship bias, distorting risk analysis and backtesting by systematically underestimating risk. This project aims to correct for that by compiling:

- All companies listed in the S&P500 from a given sample range (31st Dec 2002 - 1st Jan 2023 on first push)
- Adjusted daily price data from Yahoo Finance (pulled using the 'yfinance' package)

## Features
- Loads a cleaned list of all S&P 500 constituents over a fixed time window
- Pulls adjusted daily prices using `yfinance`
- Handles delisted tickers gracefully (missing data tracked separately)
- Outputs a wide-format price DataFrame ready for use in modeling and backtesting

## Requirements
- Python 3.8+
- `pandas`
- `pathlib`
- `yfinance`

## Dataset Source
Constituent list sourced from [`fja05680/SP500`](https://github.com/fja05680/SP500)

## Future Work
- Add log returns and metadata
- Add automatic Multi-Index formatting (Ticker + Date) to facilitate time series analysis
- Enable stratified sampling of active vs delisted tickers to:
  - Simulate realistic portfolio scenarios
  - Reduce manage memory usage and runtime
- Automate the DataFrame cleaning process to:
  - Handle missing data
  - Ensure a uniform date range
  - Merge in metadata
  - Include log returns for full or stratified portfolio
