# Time series analysis & Sales forecasting

## Store sales prediction

## Motivation
Why is Sales important to Business and How does sales forecasting help business ?

Sales are an important aspect for any business as it generates the revenue to keep the business running. They are also used as the basis for data driven business 
decisions such as resource allocation and promotional strategies. It is therefore very important to analyze the sales patterns to understanding the market and 
forecast sales to develop robust business strategies.


**How will the daily sales prediction benefit business ?**
Daily sales forecasting enables the business to inspect the detailed patterns of sales as well as to have a quicker reaction time in the event of change in these 
trends. For instance, a drop in total sales would be quickly identified in daily forecasting and can trigger further analysis into the causes resulting in the 
development of counter strategies to improve the sales.


**Sales forecating as a Time series problem ?**
Sales forecasting involves predicting future sales for a specified timeframe. Since the data at our disposal contains daily total sales records indexed by their 
dates, it forms the premise for a time series analysis to analyze the trend and seasonality of the data and model the fluctuation in sales happening over time.

The aim of this project is to apply machine learning algorithm into this real world problem

## Dataset
We are provided with historical sales data for more than a thousand stores all over United States. The dataset is majorly composed of two files:

  1. Sales data: The dataset consists of daily sales records of >1000 stores for a time period of 2.5 years along with details such as store 
  open/close, state holiday, promotional offers, number of customers.
  2. Store data: Each store also has additional details such as store type, promotional offers and competition details like distance, open since.
The sales data is indexed by date and is also missing records for some stores for certain dates due to refurbishment of stores.

## Goal: Explore the data and predict next 3 months of daily sales for more than a thousand stores. 

## Business Application
The daily sales forecast is used to support a variety of data driven business decisions such as:

  1. Streamlining the hiring process, training and resource allocation to provide improved customer experience.
  2. Stabilize inventory management and manage supply chain logistics.
  3. Developing promotional strategies to increase sales and total revenue .
  4. Identifying early warning signs and developing strategies to deal with unexpected and unfavorable situations.
  
## Approach
  1. Data Cleaning
  2. Data Exploration
  3. Time Series Data Preparation
  4. Data Modeling:
    A. Facebook Prophet
    B. LSTM – Deep learning RNN
  5. Evaluation: RMSE, MAE

## Environment & Libraries Used:
  The project is done on Jupyter Notebook instance on AWS and the version used is Python3(3.7). The Python libraries involved are:
  1. Pandas
  2. Numpy
  3. Statsmodel
  4. seaborn
  5. plotly
  6. matplotlib
  7. Prophet
  8. keras
  9. TensorFlow
    
## Results


| Model   | RMSE  |  MAE  |
| --------| ------|  ---- |
| Prophet | ~2041 | ~1589 |
| LSTM    | ~2469 | ~1618 |

## Model Comparison and Selection
a) It can be seen from the above metrics that Prophet model performed better than the LSTM. This can be justified because of following reasons in addition to better
performance:
  - Prophet includes yearly, weekly, monthly seasonality into account and our data had these seasonalities
  - It works best on daily level 
  - Prophet is robust to missing values and outliers
  - There are no parameters for us to tune as compared to LSTM, where number of layers, epochs have to be decided
  
## Conclusion

Interesting Findings:

Sales/Promo/Seasonality: 
a) Category of stores having highest sales actually dint have the highest sales per customer. This could be because that the store sells small lesser expensive items as compared to stores of difffernt categories. 
b) Customers tends to buy more on Mondays when there are ongoing promotional offers and on Thursdays/Fridays when there is no promotion at all. 
c) There has been seen positive Effect of availability of promotional offers(promo1) on sales. 
d) Sales tend to spike in November and December. So, there is a seasonality factor present in the data.
