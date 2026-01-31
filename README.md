# Stock-Price-Prediction-LSTM
This project implements an end-to-end stock price prediction system using Long Short-Term Memory (LSTM) neural networks on historical NSE TATA stock data.The goal is to model and predict the closing price of a stock using time-series deep learning techniques and to visualize results through an interactive dashboard.

The project progresses from a baseline univariate model (V1) to an improved version (V2) with proper validation, regularization, and performance evaluation.

## 🧠 **Key Objectives**
- Understand stock price behavior using historical data
- Apply LSTM networks for time-series forecasting
- Prevent data leakage using correct train/validation splits
- Evaluate model performance using multiple metrics
- Visualize predictions and trends via a Dash dashboard

## Project Structure 
```text
Stock-Price-Prediction_LSTM/
│
├── NSE/
│   └── TATA Data.csv
│
├── stock_data/
│   └── stock_data.csv
│
├── src/
│   ├── stock_pred_v1.ipynb
│   ├── stock_pred_v2.ipynb
│   ├── dash_app.py
│   └── saved_lstm_model.keras
│
├── Screenshots/
│   └── dashboard_main.png
│
├── requirements.txt
└── README.md

```

## Methodology
### 1.Data Preprocessing
- Converted dates to time-series format
- Sorted data chronologically
- Removed missing values
- Normalized prices using MinMaxScaler

### 2.Train–Validation Split
- Data split by time, not randomly
- Scaler fitted only on training data to avoid leakage
- Validation sequences include historical context

### 3️.Model Architecture
- LSTM (2 layers)
- Dropout for regularization
- Dense output layer for price prediction

### 4️.Training Strategy
- EarlyStopping (monitored on validation loss)
- ReduceLROnPlateau for adaptive learning rate
- Mean Squared Error (MSE) loss
- Adam optimizer


## Model Performance (Validation Set)
| Metric | Value |
|------|------|
| RMSE | ₹9.12 |
| MAE | ₹6.58 |
| MAPE | 2.55% |
| R² Score | 0.898 |

## Dashboard Preview
![actual_vs_predicted](https://github.com/user-attachments/assets/be00b524-4d88-4fd0-b3d1-8e1d0eb066b7)
![model_metrices](https://github.com/user-attachments/assets/042ca1c6-ca96-4254-b3fd-0d0c1a35b58d)



### How to Run the Project

- Clone the repository
```bash
git clone https://github.com/pabhor/Stock-Price-Prediction-LSTM.git
```

- Install dependencies
```bash
pip install -r requirements.txt
 ```

- Run notebooks (V1 / V2) from src/

- Launch dashboard
```bash
python src/dash_app.py
```

### Disclaimer!
This project is for educational and research purposes only.
It should not be used for real financial trading or investment decisions.
