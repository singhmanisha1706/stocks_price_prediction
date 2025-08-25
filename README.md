📈 Minimal Stock Price Prediction System
This project is a demonstration of how synthetic stock price data can be used with machine learning, specifically deep learning models like LSTMs and CNNs, to forecast future stock prices.

✨ Features
Synthetic stock OHLCV data generation (realistic simulation with volatility, seasonality, and trends)
Technical indicator calculations (SMA, RSI, volatility, returns, etc.)
Data scaling and sequence preparation for time-series modeling

Deep learning models:
LSTM (Long Short-Term Memory)
CNN (1D Convolutional Neural Network)
Model training with early stopping and evaluation metrics
Future price forecasting (next 30 days)
Visualizations of training history, actual vs predicted prices, and forecasts
Automatic report generation with indicators and predictions

🚀 Workflow
End-to-end process followed in this system:
Generate synthetic stock data
Add technical indicators
Prepare the dataset (scaling + lookback sequences)

Train an LSTM or CNN model
Evaluate predictions against historical test data
Forecast future stock prices (e.g., 30 days ahead)
Display results as interactive plots and textual reports

🔍 Project Structure
1. Setup and Imports
The program begins by loading key tools:
Data handling libraries
Visualization tools
Feature scaling and evaluation utilities
TensorFlow/Keras for deep learning models
Random seeds are fixed to ensure reproducible results.

2. Core Class — MinimalStockPredictor
This class handles the full pipeline:

A. Data Generation
Generates synthetic yet realistic stock market data:
Starts from a base price and adjusts day by day
Includes an upward trend, yearly seasonal cycles, random volatility, and momentum
Simulates trading volume that reacts to volatility
Produces OHLC (open, high, low, close) data

B. Adding Technical Indicators
Enhances raw data with:
Moving averages (10, 20, 50 days)
Returns and volatility
RSI (Relative Strength Index)
High–Low price range percentage
Volume-based features

C. Data Preparation
Selects key feature columns (price, volume, technical indicators)
Scales features between 0–1
Builds rolling “lookback windows” (e.g., 60 days) for time-series training

D. Model Architectures
Two supported options:

LSTM → captures long-term dependencies in time series
CNN → extracts short-term temporal patterns with convolutional filters.
Both end with Dense layers for final price prediction.

E. Training and Evaluation
Dataset split into training (80%) and testing (20%)
Models trained with early stopping (prevents overfitting)

Predictions evaluated using:
RMSE (Root Mean Squared Error)
R² Score (explains variance in predictions)

F. Future Price Predictions
Takes the latest sequence of data and predicts the next day’s price
Rolls forward and repeats iteratively to forecast multiple future days

G. Visualization
Automatically generates 4 plots:
Training & validation loss curves
Actual vs predicted scatter plot
Price chart with SMA overlay
Future predictions (next 30 days)

H. Reports
Summarizes:
Current stock price
Predicted next-day and 1-week price targets
Expected percentage changes
RSI, volatility, and SMA signals

3. Demo Function
Runs a complete demo workflow:
Tests different stock symbols (synthetic, e.g., AAPL, GOOGL, TSLA)
Compares both CNN and LSTM models
Selects the best-performing model based on R² score
Retrains the best model with more epochs
Forecasts next 30 days and generates plots + reports automatically

4. Execution
When the script is run, the demo executes end-to-end with:
Data generation
Feature engineering
Model training & evaluation
Prediction and reporting
No manual setup is required.

✅ In Essence
This system simulates stock market data, applies machine learning (LSTM & CNN) to forecast future prices, and provides clear visualizations and reports to showcase how AI can be used for time-series prediction in finance.

📌 How to Run
Clone the repository

Install required Python libraries (numpy, pandas, scikit-learn, matplotlib, tensorflow)
Run the script
View the generated plots and reports
