## Introduction
This repository provides an end-to-end solution for historical Risk Analytics based on daily stock prices. The objective is to calculate the magnitude of decline in the value of assets over time (drawdowns) and to capture their temporal performance. This solution is designed for portfolio managers and risk analysts to help diversify portfolios and reduce overall volatility.

## Features
1. **Data Capture**:
   - A web-based interface to input equity tickers, start and end dates.
   - Integration with the Yahoo Finance API to fetch daily historical 'Adj Close' prices for selected tickers and a benchmark.
   - Display of the latest 5 news headlines for a selected ticker.

2. **Risk Analytics Calculations**:
   - **Daily Returns**:
     - Formula: `(Current Day Adj Close - Previous Day Adj Close) / Previous Day Adj Close`
   - **Drawdowns**:
     - Formula: `(Peak - Trough) / Peak`
     - Visualization: Drawdown charts for all tickers, including the benchmark.
   - **Logarithmic Relative Returns**:
     - Formula: `Log(rt / rgeo)`
     - Visualization: Line charts for logarithmic relative returns.

3. **Dashboard**:
   - Consolidates metrics (daily returns, drawdowns, logarithmic relative returns) into an interactive and downloadable report.
   - Includes authentication mechanisms (login-password) for secure access.

## Data Overview
- **Tickers**: Apple (AAPL), NVIDIA (NVDA), Exxon Mobil Corp (XOM), Amazon (AMZN), Meta (META)
- **Benchmark**: Nasdaq-100 (^NDX)
- **Period**: January 1, 2022 – December 31, 2022 (including December 31, 2021 for initial calculations)

## Technical Details
### Backend
- Programming Language: Your choice (Python, JavaScript)
- Libraries: React, Pandas, NumPy, yfinance
- Database: MongoDB for secure storage of stock data and user credentials

### Frontend
- Framework: React, Node
- Tools: Excel for data manipulation, PowerBI for data visualizations

### APIs
- Yahoo Finance API: For fetching historical stock prices
- News API: For displaying news headlines

### Authentication
- User login with password hashing (e.g., bcrypt)
- Session management for secure access

## Deployment
- **Steps**:
  1. Clone the repository: `git clone <repo-url>`
  2. Install dependencies: `npm install` or `pip install -r requirements.txt`
  3. Set up the database: Run `setup.sql` script
  4. Start the server: `npm start` or `python app.py`

- **Environment Variables**:
  - `API_KEY_YAHOO`: Yahoo Finance API key
  - `API_KEY_NEWS`: News API key

## Visualization
### Drawdown Chart
- X-axis: Dates
- Y-axis: Drawdown percentage

### Logarithmic Relative Return Chart
- X-axis: Dates
- Y-axis: Logarithmic relative return values

## Example Outputs
1. **Daily Returns**:
   | Date       | Ticker | Return |
   |------------|--------|--------|
   | 2022-01-03 | NVDA   | 3.84%  |

   ![Image](https://github.com/user-attachments/assets/39a8987a-7c3e-4185-8a41-9c71757e1c29)

2. **Drawdown Chart**:
   ![Image](https://github.com/user-attachments/assets/4d551b8d-88a7-4ad3-83d1-3014f5665965)

3. **Logarithmic Relative Return Chart**:
   ![alt text](image-1.png)

## Notes
- Ensure data security for user authentication and financial data.
- Support exporting the dashboard as a PDF.

## Future Enhancements
1. Add support for multiple benchmarks.
2. Extend the dashboard with machine learning-based risk prediction.
3. Enable real-time stock data updates.
