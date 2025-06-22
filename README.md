# Financial Data Analysis & IPO Strategy Backtesting

## Project Overview

This project is a comprehensive analysis of financial market data, focusing on Initial Public Offerings (IPOs) and quantitative strategy backtesting. The core objective was to collect, process, and merge data from diverse sources—including web pages, financial APIs, and economic databases—to create a unified dataset. This dataset was then used to perform detailed analysis, evaluate the performance of recent IPOs, and test the profitability of rule-based trading strategies.

The project demonstrates a full data analysis pipeline: from raw data ingestion and cleaning to feature engineering, and finally, to deriving actionable insights from the data.

## Key Features

- **Multi-Source Data Ingestion**: Aggregated data from various sources including web scraping (StockAnalysis.com), financial APIs (`yfinance`), and economic data providers (FRED, Eurostat).
- **Advanced Data Processing**: Utilized the `pandas` library for extensive data manipulation, including cleaning, type casting, time-series alignment, and merging heterogeneous datasets.
- **Feature Engineering**: Generated a rich set of features, including:
    - Historical and future price growth over multiple timeframes (1d to 365d).
    - Key financial metrics like annualized volatility and Sharpe Ratio.
    - Over 100 technical indicators and candlestick patterns using the `TA-Lib` library.
- **Strategy Backtesting**: Implemented and evaluated simple quantitative strategies:
    1.  A "buy-and-hold" strategy for recent IPOs to determine the optimal holding period.
    2.  An RSI-based strategy to test the profitability of buying "oversold" assets.
- **Data Integration**: Successfully combined time-series data for individual stocks with macroeconomic indicators (e.g., VIX, CPI, GDP growth, interest rates) to create a single, powerful analytical dataset.

## Data Sources

- **IPO Data**: Historical and withdrawn IPO listings from [StockAnalysis.com](https://stockanalysis.com/).
- **Stock Prices (OHLCV)**: Daily price data for US, EU, and Indian stocks from Yahoo Finance, accessed via the `yfinance` library.
- **Macroeconomic Indicators**:
    - **FRED (Federal Reserve Economic Data)**: US GDP, Core CPI, Federal Funds Rate, and Treasury Yields (`pandas-datareader`).
    - **Eurostat**: European government bond yield curve data.
- **Commodities & Other Assets**: Daily prices for Gold, WTI & Brent Crude Oil, and Bitcoin (BTC-USD) from Yahoo Finance.

## Technologies & Libraries Used

- **Programming Language**: Python 3
- **Core Libraries**:
    - `pandas`: For data manipulation and analysis.
    - `numpy`: For numerical operations.
    - `yfinance`: For downloading stock market data.
    - `TA-Lib`: For calculating technical analysis indicators.
    - `requests`: For making HTTP requests to web pages.
    - `pandas-datareader`: For fetching data from FRED.
    - `eurostat`: For fetching data from the Eurostat database.
- **Environment**: Jupyter Notebook

## Analysis Performed & Questions Addressed

This project systematically answered several key analytical questions:

1.  **Withdrawn IPO Analysis**: Identified which class of companies (e.g., 'Acq.Corp', 'Inc') had the highest total value of withdrawn IPOs, revealing underlying market trends.
2.  **IPO Performance Evaluation**: Calculated the median Sharpe Ratio for IPOs in the first five months of 2024 to assess their risk-adjusted performance one year later.
3.  **Optimal IPO Holding Period**: Determined the optimal number of months (from 1 to 12) to hold a newly-listed stock to maximize average returns, highlighting the general unprofitability of a simple buy-and-hold approach for IPOs.
4.  **RSI-Based Trading Strategy**: Backtested a simple strategy of buying stocks when their RSI falls below 25 and calculated the total net profit over a 25-year period.
5.  **Strategy Improvement**: Brainstormed data-driven methods to improve IPO investment strategies, such as using fundamental filters, market regime detection, and more advanced entry/exit signals.

## How to Run

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/data-tomic/stock-markets-analytics-zoomcamp.git
    cd stock-markets-analytics-zoomcamp
    ```

2.  **Install Dependencies**:
    This project requires several Python libraries. The most critical is `TA-Lib`, which requires a separate installation of its underlying C library.

    **a. Install the TA-Lib C Library:**
    - **On macOS**: `brew install ta-lib`
    - **On Linux (Debian/Ubuntu)**: Download from [ta-lib.org](http://prdownloads.sourceforge.net/ta-lib/ta-lib-0.4.0-src.tar.gz), then `tar -xzf`, `./configure`, `make`, `sudo make install`.
    - **On Windows**: Download the `.whl` file corresponding to your Python version and system architecture from [UCL's repository](https://www.lfd.uci.edu/~gohlke/pythonlibs/#ta-lib).

    **b. Install Python packages:**
    ```bash
    pip install pandas numpy yfinance requests pandas-datareader eurostat gdown
    pip install TA-Lib
    ```

3.  **Run the Jupyter Notebook**:
    Launch Jupyter Notebook and open the `.ipynb` file. Run the cells sequentially to replicate the analysis.
    ```bash
    jupyter notebook
    ```