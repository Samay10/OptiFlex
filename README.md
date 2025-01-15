# Options Pricing Analysis

This project implements a financial analysis tool for options pricing using the Black-Scholes model. It fetches historical stock data, calculates volatility, and compares theoretical options prices with market prices.

## Features

- Historical stock data retrieval using Yahoo Finance API
- Volatility calculation using rolling window method
- Black-Scholes model implementation for both call and put options
- Synthetic options data generation for testing
- Price comparison between theoretical and market prices
- Performance metrics evaluation (MAE, RMSE, Bias)

## Prerequisites

The following Python packages are required:
- yfinance
- numpy
- pandas
- scipy
- datetime

Install dependencies using:
```bash
pip install yfinance numpy pandas scipy
```

## Usage

### 1. Fetching Stock Data
```python
ticker = 'AAPL'
stock_data = fetch_stock_data(ticker, '2019-01-01', '2021-01-01')
```

### 2. Calculating Volatility
```python
stock_data = calculate_volatility(stock_data, window=30)
```

### 3. Black-Scholes Model
```python
price = black_scholes(S, K, T, r, sigma, option_type='call')
```
Parameters:
- S: Current stock price
- K: Strike price
- T: Time to maturity (in years)
- r: Risk-free interest rate
- sigma: Volatility
- option_type: 'call' or 'put'

### 4. Generating Synthetic Option Data
```python
option_data = generate_option_data(stock_data)
```

### 5. Price Comparison
```python
option_data = compare_prices(option_data, stock_data, risk_free_rate)
```

### 6. Evaluation Metrics
```python
evaluate_metrics(option_data)
```

## Functions

### `fetch_stock_data(ticker, start_date, end_date)`
Retrieves historical stock data from Yahoo Finance.

### `calculate_volatility(stock_data, window=30)`
Calculates historical volatility using a rolling window approach.

### `black_scholes(S, K, T, r, sigma, option_type)`
Implements the Black-Scholes option pricing model.

### `generate_option_data(stock_data, strike_range=0.05, days_to_expiration=30)`
Creates synthetic option data for testing purposes.

### `compare_prices(option_data, stock_data, risk_free_rate)`
Compares theoretical prices with market prices and calculates error metrics.

### `evaluate_metrics(option_data)`
Calculates performance metrics including MAE, RMSE, and Bias.

## Data Structure

The code works with two main DataFrame structures:

1. **Stock Data DataFrame:**
   - Index: Date
   - Columns: Open, High, Low, Close, Adj Close, Volume, Daily Return, Volatility

2. **Option Data DataFrame:**
   - Columns: Date, Strike Price, Stock Price, Expiration Date, Option Type, Option Price, Implied Volatility, Theoretical Price, Price Error

## Limitations

- Uses synthetic option data for demonstration
- Assumes constant risk-free rate
- Does not account for dividends in the Black-Scholes model
- Simplified volatility calculation

## Future Improvements

1. Add support for real options market data
2. Implement dividend adjustment in the Black-Scholes model
3. Add more sophisticated volatility models
4. Include Greeks calculations
5. Add visualization tools for price comparisons
6. Implement additional option pricing models

## License

This project is available under the GNU v3.0 License.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
