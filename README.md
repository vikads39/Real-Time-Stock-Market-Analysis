📈 NSE Stock Market Analytics & Power BI Pipeline

Welcome to the NSE Stock Market Analytics repository! This project transforms raw National Stock Exchange (NSE) CSV data into an enterprise-grade, Power BI-optimized data model. We leverage Python for complex time-series feature engineering and data integrity checks, ensuring your financial dashboards are both fast and accurate.

🚀 The Mission

To turn raw stock price movements into actionable financial intelligence. This pipeline focuses on:

Ensuring Data Integrity: Validating logical price rules (High ≥ Open/Close ≥ Low).

Time-Series Engineering: Calculating daily returns, volatility, and moving averages (MA7, MA21).

Power BI Optimization: Structuring data into a Star Schema (Fact and Dimension tables) to minimize DAX complexity.

🛠️ The Tech Stack

Data Source: nse_all_stock_data.csv

Processing Engine: Python (Pandas, NumPy)

Environment: Quadratic AI / Jupyter / VS Code

Visualization: Microsoft Power BI

📊 The 5-Step Pipeline

1. Discovery & Inspection

We start by auditing the raw CSV to detect column naming issues, data type mismatches (e.g., prices stored as text), and general dataset shape.

2. Standardization & Cleaning

Column Formatting: All headers converted to snake_case (Power BI friendly).

Missing Data: Prices are handled using Forward Fill (ffill) to maintain time-series continuity; Volumes are filled with 0.

Type Conversion: Converting date columns to datetime objects and price/volume to numeric.

3. Integrity & Outlier Management

Duplicate Removal: Eliminating ghost records that inflate metrics.

Price Validation: Dropping rows where High is lower than Low (data corruption check).

Outlier Capping: Using the IQR (Interquartile Range) method to cap extreme spikes while preserving market-real volatility.

4. Feature Engineering (The Alpha)

We create the metrics traders care about:

Daily Returns (%): The primary measure of gain/loss.

Volatility (7-Day): Rolling standard deviation to measure risk.

Moving Averages (7 & 21 Days): To identify short-term vs. long-term trends.

Trend Signals: Automatic flags for Uptrend or Downtrend.

5. Power BI Modeling (Star Schema)

The dataset is split into three tables to ensure high performance:

Fact_Market: Contains all daily price metrics and engineered features.

Dim_Date: A dedicated calendar table for Time Intelligence (YTD, YoY calculations).

Dim_Stock: A unique list of symbols for filtering and slicers.

📈 Dashboard Layout Ideas

Stock Performance Overview: Line charts comparing Price vs. MA7 vs. MA21.

Risk Assessment: Scatter plot of Daily Return vs. Volatility.

Trend Heatmap: A matrix showing which sectors are currently in an Uptrend.

⚙️ How to Rename this Repo on GitHub

Go to your repository on GitHub.com.

Click Settings (top menu).

Change the name under Repository name.

Click Rename.

🔗 Useful Links

Tool: Quadratic Spreadsheet

Financial Terms: Investopedia - Moving Averages

Project Lead: Analytics Pro
Status: ✅ Data Model Ready | 🚀 Power BI Ready
