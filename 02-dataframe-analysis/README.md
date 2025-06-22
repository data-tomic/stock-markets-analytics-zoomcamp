# Module 2: DataFrame Analysis with Pandas

## Overview

This module focuses on practical data analysis using the `pandas` library. The notebooks within this directory demonstrate the process of fetching data from web sources and financial APIs, cleaning and transforming it, and performing quantitative analysis to answer specific business questions related to Initial Public Offerings (IPOs).

The primary skills showcased here are advanced DataFrame manipulation, feature engineering, and the application of financial calculations to real-world data.

## Files in this Directory

-   **`homework_q1.ipynb`**: Contains the solution for Question 1 of the assignment. This notebook covers:
    -   Web scraping withdrawn IPO data from StockAnalysis.com.
    -   Classifying companies into categories based on their names.
    -   Calculating the total withdrawn IPO value for each company class.

-   **`homework_q2_q3.ipynb`**: Contains the solutions for Questions 2 and 3. This notebook focuses on analyzing the performance of recent IPOs and includes:
    -   Fetching IPO data for a specific year.
    -   Downloading historical stock price data for a list of tickers using `yfinance`.
    -   Calculating risk-adjusted performance metrics like the Sharpe Ratio.
    -   Backtesting a "buy-and-hold" strategy to find the optimal holding period.

## Key Concepts & Techniques Covered

-   Web scraping of tabular data using `pandas.read_html` and `requests`.
-   Data cleaning and type conversion (`to_numeric`, `to_datetime`).
-   Advanced DataFrame manipulation and feature engineering using custom functions with `.apply()`.
-   Fetching bulk financial data for multiple tickers using the `yfinance` API.
-   Time-series analysis with `pandas`, including `rolling()` for volatility and `shift()` for future returns.
-   Calculation of key financial metrics (e.g., annualized volatility, Sharpe Ratio).
-   Data aggregation and summarization using `groupby()`.

## How to Use

To replicate the analysis, ensure you have the required libraries installed (as specified in the main project `README.md`). Open the notebooks in a Jupyter environment and run the cells sequentially. The notebooks are designed to be self-contained and fetch the necessary data dynamically.