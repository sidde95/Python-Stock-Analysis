# 🐍 Python Stock Market Analysis

A hands-on learning project for financial data analysis using Python and Jupyter Notebooks. This repository covers stock market data retrieval, exploration, visualization, and technical analysis with popular Python libraries.

## 📂 Repository Structure

```
├── 01_stock_data_exploration.ipynb   # Download, inspect, and visualize stock price data
├── finance_knowledgebase.docx        # Finance concepts and interactive learning activities
├── requirements.txt                  # Python dependencies
└── README.md                         # Project overview
```

## 🚀 Getting Started

### Prerequisites

- Python 3.11+
- pip

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/sidde95/python-stock-market-analysis.git
   cd python-stock-market-analysis
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```

## 📦 Dependencies

| Library | Purpose |
|---|---|
| `pandas` | Data manipulation and tabular display |
| `numpy` | Numerical computation |
| `matplotlib` | Plotting and visualization |
| `yfinance` | Downloading stock market data from Yahoo Finance |
| `multitasking` | Multithreading support for yfinance |
| `stockstats` | Technical indicators (e.g., MACD, RSI) |
| `ta` | Additional technical analysis indicators |
| `scikit-learn` | Machine learning for predictive models |
| `ipynb` | Running/importing Jupyter notebooks |

## 📊 Features

- **Stock Data Retrieval** — Fetch historical OHLCV data for any ticker using `yfinance`
- **Data Exploration** — Inspect DataFrames with `.head()`, `.tail()`, `.info()`, and index inspection
- **Price Visualization** — Plot closing prices over time using `matplotlib`
- **Finance Knowledge** — Reference document covering key financial concepts and activities

## 📖 Usage Example

```python
import yfinance as yf
import pandas as pd
import matplotlib.pyplot as plt

ticker = 'AAPL'
data = pd.DataFrame(yf.download(ticker, start='2025-01-01', end='2026-01-01'))

plt.figure(figsize=(20, 4))
plt.plot(data.index, data['Close'])
plt.xlabel('Date')
plt.ylabel('Close Price')
plt.title('Apple Stock Price')
plt.show()
```

## 📝 License

This project is open source and available under the [MIT License](LICENSE).
