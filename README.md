# 🐍 Python Stock Market Analysis

A hands-on learning project for financial data analysis using Python and Jupyter Notebooks. This repository covers stock market data retrieval, exploration, visualization, and technical analysis with popular Python libraries.

## 📂 Repository Structure

```
├── 00_setup.ipynb                    # Environment check + download OHLCV + basic price/volume plots + CSV export
├── 01_stock_data_exploration.ipynb   # Deeper exploration of stock data + indicators/visuals (work-in-progress)
├── finance_knowledgebase.docx        # Finance concepts and interactive learning activities
├── requirements.txt                  # Python dependencies
├── LICENSE                           # MIT License
└── README.md                         # Project overview
```

## 📓 Notebooks

- **00_setup.ipynb**
  - Validates your environment (imports + version checks)
  - Downloads adjusted OHLCV using `yfinance`
  - Plots:
    - individual close-price charts
    - normalised close-price comparison (rebased to 100)
    - volume bar charts
  - Exports per-ticker OHLCV CSVs to `data/`

- **01_stock_data_exploration.ipynb**
  - Explores downloaded OHLCV data in more detail (inspection, cleaning, visualisation)
  - Intended place for technical indicators (e.g., RSI/MACD via `stockstats` / `ta`) and further analysis

## 🚀 Getting Started

### Prerequisites

- Python 3.11+
- Git

### Option A — venv + pip (recommended)

```bash
# from the repo root
python -m venv .venv

# activate (Git Bash)
source .venv/Scripts/activate

python -m pip install --upgrade pip
pip install -r requirements.txt

# start Jupyter
jupyter notebook
```

### Option B — conda

```bash
conda create -n stock-analysis python=3.11 -y
conda activate stock-analysis
pip install -r requirements.txt
jupyter notebook
```

## 📦 Dependencies

The project uses a small set of common Python data-science libraries:

| Library | Purpose |
|---|---|
| `pandas` | Data manipulation and tabular display |
| `numpy` | Numerical computation |
| `matplotlib` | Core plotting and visualisation |
| `seaborn` | Statistical visualisations (optional but useful) |
| `plotly` | Interactive charts (optional but useful) |
| `yfinance` | Downloading stock market data from Yahoo Finance |
| `multitasking` | Multithreading support used by `yfinance` |
| `stockstats` | Technical indicators (e.g., MACD, RSI) |
| `ta` | Additional technical analysis indicators |
| `scikit-learn` | Machine learning experiments (optional) |
| `ipykernel` | Jupyter kernel support |

## 📖 Usage Example

```python
import yfinance as yf
import pandas as pd
import matplotlib.pyplot as plt

ticker = "AAPL"
df = pd.DataFrame(yf.download(ticker, start="2025-01-01", end="2026-01-01", auto_adjust=True))

plt.figure(figsize=(14, 4))
plt.plot(df.index, df["Close"])
plt.title("AAPL adjusted close")
plt.xlabel("Date")
plt.ylabel("Price (USD)")
plt.grid(True, alpha=0.3)
plt.show()
```

## 📝 License

This project is open source and available under the **MIT License** (see `LICENSE`).
