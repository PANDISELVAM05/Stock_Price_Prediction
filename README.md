# Stock_Price_Prediction
# Stock Price Prediction using ARIMA

This project focuses on predicting stock prices using the ARIMA (AutoRegressive Integrated Moving Average) time series forecasting model. The model analyzes historical stock market data and predicts future stock price values based on past trends.

The project demonstrates how time-series analysis techniques can be applied to financial datasets to understand patterns and generate predictions.

# 📊 Dataset

The dataset contains historical stock market information with the following columns:

Column	Description
Date	Trading date
Open	Opening stock price
High	Highest price during the day
Low	Lowest price during the day
Close	Closing price
Adj_Close	Adjusted closing price
Volume	Total number of shares traded

Example dataset structure:

Date,Open,High,Low,Close,Adj_Close,Volume
2023-01-01,33.25,37,32.5,36.8,36.5,72568
2023-01-02,34.10,38,33.2,37.5,37.2,84500
# ⚙️ Technologies Used

Python

Pandas

NumPy

Matplotlib

Statsmodels

# 🧠 ARIMA Model

The ARIMA model is widely used for time series forecasting.
It works by learning patterns from historical data and predicting future values.

The ARIMA model consists of three components:

AR (AutoRegression)
I  (Integration / Differencing)
MA (Moving Average)

Example ARIMA configuration:

ARIMA(p, d, q)

Example used in this project:

ARIMA(5,1,0)
# 🔄 Project Workflow

The project follows a simple stock price prediction workflow:

Data Collection → Data Cleaning → Data Analysis → Data Processing → Model Training → Visualization → Prediction

# 📂 Project Structure
Stock-Price-Prediction
│
├── Oil_Data_Cleaned.csv
├── stock_prediction.py
├── predicted_stock_data.csv
└── README.md
# 🚀 Installation

Clone the repository:

git clone https://github.com/yourusername/stock-price-prediction.git

Move to project directory:

cd stock-price-prediction

Install required libraries:

pip install pandas numpy matplotlib statsmodels
# ▶️ Running the Project

Run the Python script:

python stock_prediction.py

The program will:

Load the stock dataset

Train the ARIMA model

Predict stock prices

Visualize the prediction results

# 💻 Example Code

Loading the dataset:

import pandas as pd

df = pd.read_csv("Oil_Data_Cleaned.csv")
df["Date"] = pd.to_datetime(df["Date"])
df.set_index("Date", inplace=True)

Training the ARIMA model:

from statsmodels.tsa.arima.model import ARIMA

data = df["Adj_Close"]

model = ARIMA(data, order=(5,1,0))
model_fit = model.fit()

Predicting the next price:

prediction = model_fit.forecast(steps=1)

print("Predicted Stock Price:", prediction.iloc[0])
# 📊 Visualization

The project also visualizes:

Historical stock prices

Predicted stock prices

Example visualization code:

import matplotlib.pyplot as plt

plt.plot(data, label="Historical Price")
plt.title("Stock Price Trend")
plt.legend()
plt.show()
# 🎯 Project Goal

The main goal of this project is to demonstrate how time series forecasting models like ARIMA can be used to analyze and predict stock prices based on historical data.

# 🔮 Future Improvements

Possible improvements for this project include:

Implementing LSTM deep learning models

Adding technical indicators (RSI, MACD, Moving Average)

Building a web dashboard for stock prediction

Automating real-time stock data collection
