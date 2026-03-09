# SP500 SVM Trading Strategy

This Jupyter notebook implements a Support Vector Machine (SVM) based trading strategy for the SPY ETF (SPDR S&P 500 ETF Trust).

## Overview

The notebook downloads historical SPY data for the past 5 years (from March 9, 2021, to March 9, 2026), processes it to create technical indicators, trains an SVM classifier to predict next-day price movements, and evaluates the strategy's performance through backtesting.

## Features

- **Data Acquisition**: Downloads SPY historical data using yfinance
- **Feature Engineering**: Creates Open/Close and High/Low ratios as predictors
- **Machine Learning**: Uses SVM to classify bullish/bearish signals
- **Backtesting**: Evaluates strategy performance with accuracy metrics and cumulative returns
- **Visualization**: Plots cumulative returns over time

## Requirements

- Python 3.x
- Required packages:
  - scikit-learn
  - pandas
  - numpy
  - matplotlib
  - yfinance
  - seaborn (for matplotlib style)

Install dependencies with:
```bash
pip install scikit-learn pandas numpy matplotlib yfinance seaborn
```

## How to Run

1. Ensure all required packages are installed
2. Open the notebook `sp500svm.ipynb` in Jupyter Lab or Jupyter Notebook
3. Run all cells in order
4. The notebook will:
   - Download SPY data (this may take a moment)
   - Process the data
   - Train the SVM model
   - Display accuracy and plot cumulative returns

## Data Processing

- **Input Data**: Daily OHLC (Open, High, Low, Close) prices for SPY
- **Features**:
  - Open/Close ratio
  - High/Low ratio
- **Target**: Binary classification (1 for next day close > current close, -1 otherwise)

## Model

- **Algorithm**: Support Vector Classifier (SVC) with default parameters
- **Training Split**: 80% of data for training, 20% for testing
- **Evaluation**: Accuracy score on test set

## Output

- Test accuracy percentage
- Cumulative returns plot
- Final cumulative returns value

## Notes

- The strategy uses a simple SVM with default hyperparameters
- Results are for backtesting purposes only and should not be considered financial advice
- The notebook downloads data each time it's run; consider caching for repeated use
- The date range is hardcoded to 2021-03-09 to 2026-03-09

## File Structure

- `sp500svm.ipynb`: Main notebook
- `spy_5years.csv`: Downloaded SPY data (created when notebook runs)
