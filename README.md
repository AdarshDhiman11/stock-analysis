# Stock Analysis

## Introduction
### Abstract:
In this data science project we are going to make a stock analysis project in which people can get the past data of any stock to analyse and predict the future trend of that stock.This project can show the high,low,close,start of prices of stocks in a particular period of time in a graphical manner.To get the data of a particular stock 
we uses a stock ticker which takes the data from pakage pandas_datareader.

#### What Is Stock Analysis?
Stock analysis is the evaluation of a particular trading instrument, an investment sector, or the market as a whole. Stock analysts attempt to determine the future activity of an instrument, sector, or market.
Understanding Stock Analysis
Stock analysis is a method for investors and traders to make buying and selling decisions. By studying and evaluating past and current data, investors and traders attempt to gain an edge in the markets by making informed decisions.

## Libraries Used
### Pandas
Pandas is a Python library for data analysis. Started by Wes McKinney in 2008 out of a need for a powerful and flexible quantitative analysis tool, pandas has grown into one of the most popular Python libraries. It has an extremely active community of contributors.

Pandas is built on top of two core Python libraries—matplotlib for data visualization and NumPy for mathematical operations. Pandas acts as a wrapper over these libraries, allowing you to access many of matplotlib's and NumPy's methods with less code. For instance, pandas' .plot() combines multiple matplotlib methods into a single method, enabling you to plot a chart in a few lines.

Before pandas, most analysts used Python for data munging and preparation, and then switched to a more domain specific language like R for the rest of their workflow. Pandas introduced two new types of objects for storing data that make analytical tasks easier and eliminate the need to switch tools: Series, which have a list-like structure, and DataFrames, which have a tabular structure.

### Numpy
NumPy, which stands for Numerical Python, is a library consisting of multidimensional array objects and a collection of routines for processing those arrays. Using NumPy, mathematical and logical operations on arrays can be performed.

NumPy is a Python package. It stands for ‘Numerical Python’. It is a library consisting of multidimensional array objects and a collection of routines for processing of array.

Numeric, the ancestor of NumPy, was developed by Jim Hugunin. Another package Numarray was also developed, having some additional functionalities. In 2005, Travis Oliphant created NumPy package by incorporating the features of Numarray into Numeric package. There are many contributors to this open-source project.

### matplotlib.pyplot
matplotlib.pyplot is a collection of command style functions that make Matplotlib work like MATLAB. Each Pyplot function makes some change to a figure. For example, a function creates a figure, a plotting area in a figure, plots some lines in a plotting area, decorates the plot with labels, etc.

### Pandas Datareader
Pandas Datareader is a Python package that allows us to create a pandas DataFrame object by using various data sources from the internet. It is popularly used for working with realtime stock price datasets.

### Streamlit
A faster way to build and share data apps.Streamlit turns data scripts into shareable web apps in minutes.All in pure Python. No front‑end experience required.

Streamlit is an open source app framework in Python language. It helps us create web apps for data science and machine learning in a short time. It is compatible with major Python libraries such as scikit-learn, Keras, PyTorch, SymPy(latex), NumPy, pandas, Matplotlib etc.

### Code Editor
#### VS Code
Visual Studio Code, also commonly referred to as VS Code,[9] is a source-code editor made by Microsoft for Windows, Linux and macOS.[10] Features include support for debugging, syntax highlighting, intelligent code completion, snippets, code refactoring, and embedded Git. Users can change the theme, keyboard shortcuts, preferences, and install extensions that add additional functionality.

## Problem Statement
Stock market is one of the most important platforms to invest your money now a days. But to invest in stock market to get huge profit you have to study about the history of stock's. By this stock analysis system you will be able to find the past data of the stcoks in which you want to invest and can also analyze any stock you want by seeing the graph in a virtual and beautiful way.

## Proposed Solution
1. Import the libraries.
2. Declaire the start and the end dates during which you want the data of a particular stock.
3. Take input from the user in the form of stock ticker.
4. Plot the graph of stock with closing price and time chart.
5. Plot the graph of stock with closing price and time chart 100MA.
6. Plot the graph of stock with Closing Price vs Time chart with 100MA & 200MA.

### Programe:
```
# Importing the libraries
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import pandas_datareader as data
import streamlit as st

# Writing sreamlit codes of title to show our data on web app
st.title('Stock Trend Prediction')

# Declairing the start and the end dates during which you want the data of a particular stock
start = '2010-01-01'
end = '2019-12-31'

# Taking input from the user in the form of stock ticker
user_input = st.text_input('Enter Stock Ticker', 'AAPL')
df = data.DataReader(user_input, 'yahoo', start, end)

# Writing sreamlit codes of subheader and write to show our data on web app
st.subheader('Data from 2010-2019')
st.write(df.describe())

# Ploting the graph of stock with closing price and time chart
st.subheader('Closing Price vs Time chart')
fig = plt.figure(figsize = (12,6))
plt.plot(df.Close)
st.pyplot(fig)

# Ploting the graph of stock with closing price and time chart 100MA
st.subheader('Closing Price vs Time chart 100MA')
ma100 = df.Close.rolling(100).mean()
fig = plt.figure(figsize = (12,6))
plt.plot(df.Close)
plt.plot(ma100,'r')
st.pyplot(fig)

# Ploting the graph of stock with Closing Price vs Time chart with 100MA & 200MA
st.subheader('Closing Price vs Time chart with 100MA & 200MA')
ma200 = df.Close.rolling(200).mean()
fig = plt.figure(figsize = (12,6))
plt.plot(df.Close)
plt.plot(ma100,'r')
plt.plot(ma200,'g')
st.pyplot(fig)
```

## Result
![This is an image](https://github.com/AdarshDhiman11/stock-analysis/blob/master/final%20project%20images/Screenshot%20(107).png)
![This is an image](https://github.com/AdarshDhiman11/stock-analysis/blob/master/final%20project%20images/Screenshot%20(108).png)
![This is an image](https://github.com/AdarshDhiman11/stock-analysis/blob/master/final%20project%20images/Screenshot%20(109).png)
![This is an image](https://github.com/AdarshDhiman11/stock-analysis/blob/master/final%20project%20images/Screenshot%20(110).png)

## Conclusion & Future Work
This stock analysis will show you the 100 days moving average and 200 days moving average graph by which you will be able to analyze the average of stock price and can even predict by your own algorithms about the future of the stock. We can also improve this program by making it predict on its own if the price of the stock is going to be low or high in coming days. But for this we have to study the deep learning and ai.

## References

1. Youtube
2. Geeks For Geeks
3. Kaggle
4. Google
