# First-Apple-Stock
**Apple Stock Analysis:**
The provided dataset contains historical stock data for Apple Inc. from the past year. It features daily records with essential attributes such as Date, Open, High, Low, Close, and Volume. For this task, your primary focus should be on the Close price, which indicates the stock’s final trading price at the end of each day. The time-series nature of the dataset makes it ideal for sequential modeling, and its numerical structure is well-suited for regression analysis.

**Problem Statement / Objective :**
The primary objective is to develop a predictive model capable of accurately forecasting Apple Inc.’s stock prices for the next 10 days. Due to the complexity of stock market data, which can display both short-term sequential dependencies and broader trends, relying on a single model type may be insufficient. The challenge is to effectively capture these intricate patterns. Therefore, a hybrid modeling approach is required, combining LSTM (to capture time dependencies and short-term trends) and Linear Regression (to capture long-term trends).

# Importing Libraries 
import pandas as pd 
file_path = "C:\Users\yz\Desktop\Data Analyst" 
df = pd.read_xls(file_path) 
print(df.head())

df.dtypes # Here we can see that Date is in object format, we need to change it into datetime format 
df['Date'] = pd.to_datetime(df['Date']) # Changing Date into datetime format 
df.set_index('Date', inplace=True) # Setting Date as index
data = df[['Close']] # Selecting Close column as data, because we are going to predict Close column. 
