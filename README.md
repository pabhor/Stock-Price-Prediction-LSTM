# Stock-Price-Prediction-LSTM
This project implements an end-to-end stock price prediction system using Long Short-Term Memory (LSTM) neural networks on historical NSE TATA stock data.The goal is to model and predict the closing price of a stock using time-series deep learning techniques and to visualize results through an interactive dashboard.

The project progresses from a baseline univariate model (V1) to an improved version (V2) with proper validation, regularization, and performance evaluation.

🧠 Key Objectives

Understand stock price behavior using historical data

Apply LSTM networks for time-series forecasting

Prevent data leakage using correct train/validation splits

Evaluate model performance using multiple metrics

Visualize predictions and trends via a Dash dashboard

# Project Structure 
Stock Price Prediction/
│
├── NSE/
│   └── TATA Data.csv              # NSE TATA historical stock data
│
├── stock_data/
│   └── stock_data.csv             # Multi-stock data for dashboard
│
├── src/
│   ├── stock_pred_v1.ipynb        # Univariate LSTM model (baseline)
│   ├── stock_pred_v2.ipynb        # Improved model with validation
│   ├── dash_app.py                # Plotly Dash dashboard
│   └── saved_lstm_model.keras     # Trained LSTM model
│
├── Screenshots/                   # Output visuals
│   ├── dashboard_main.png
│   ├── actual_vs_predicted.png
│   ├── training_validation_loss.png
│   └── model_metrics.png
│
├── requirements.txt
└── README.md

⚙️ Methodology
1️⃣ Data Preprocessing

Converted dates to time-series format

Sorted data chronologically

Removed missing values

Normalized prices using MinMaxScaler

2️⃣ Train–Validation Split

Data split by time, not randomly

Scaler fitted only on training data to avoid leakage

Validation sequences include historical context

3️⃣ Model Architecture

LSTM (2 layers)

Dropout for regularization

Dense output layer for price prediction

4️⃣ Training Strategy

EarlyStopping (monitored on validation loss)

ReduceLROnPlateau for adaptive learning rate

Mean Squared Error (MSE) loss

Adam optimizer


📈 Model Performance (Validation Set)
Metric	Value
RMSE	₹9.12
MAE	₹6.58
MAPE	2.55%
Approx Accuracy	97.45%
R² Score	0.898

How to Run the Project

Clone the repository
git clone https://github.com/pabhor/Stock-Price-Prediction-LSTM.git


Install dependencies
pip install -r requirements.txt

Run notebooks (V1 / V2) from src/

Launch dashboard
python src/dash_app.py

Disclaimer![model_metrices](https://github.com/user-attachments/assets/6210654a-a52f-42ee-aa4a-b59b6d694d12)

This project is for educational and research purposes only.
It should not be used for real financial trading or investment decisions.
