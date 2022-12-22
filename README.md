# Business Challenge - Price Leader and Follower Detection, Popularity Index

## Introduction 

In the business world, it is often important to identify the price leaders and followers in a market. Price leaders are the companies that set the prices for products or services, while price followers are the companies that follow the pricing set by the leaders. In this project, we aim to develop a Python program to detect price leaders and followers in a given market, and create a popularity index based on the pricing data.

## Exploratory Data Analysis

Inputs of this project are 7 dataset that contains information about different insight of clients and product sales:
- <b>Sales_data</b> : contains data about sales of our client (that is identified as seller 24);
- <b>Product_Catalog </b>: contains information about all the products in the catalog;
- <b>Prices_competitor </b>: contains information about the prices that the different competitors in the market assign to each product in different period;
- <b>Stock </b>: contains information about stock level;
- <b>Clicks_regular and click_biddings</b>: basically these two datasets contains same information about the click that a product receive in a specific days. The main     difference between these datasets is that click_biddings refers to clicks received by product that have some sponsorships (e.g. advertinsing in order to appear as first in the catalog).

A first step was to analyse the variables in our datasets, in order to understand the relationships present, whether there were _null values, duplicates or outliers_. 
In order to detect outlier values, the Tukey Method was applied. Tukey’s technique is used to detect outliers in skewed or non bell-shaped data since it makes no distributional assumptions. However, Tukey’s method may not be appropriate for a small sample size. The general rule is that anything not in the range of (Q1 - 1.5 IQR) and (Q3 + 1.5 IQR) is an outlier, and can be removed.
Inter Quartile Range (IQR) is one of the most extensively used procedure for outlier detection and removal.


Then, five different time windows were obtained in order to perform a trend analysis at different times of the year.

## Price Leader and Followers detection

Price leaders are often considered to be influential in shaping the overall direction of prices in a market, while followers may be more reactive to changes in prices. By analyzing the behavior of these different types of players, businesses and investors can gain insights into market dynamics and make informed decisions.
In order to perform this analysis, only a sample of product is selected; in particular, the focus was on the <b> top 10 most-sold products </b>. The aim of this, is to identify leader and followers for this specific products in each time interval.

The approach that this project follows is to analyse the performance of a specific product, in various time windows. Then, through the support of certain statistical properties (such as correlation and cointegration), observe the existence of leaders and followers within the market and verify these observations through the <b>Granger Test</b>. 
Basically, the Granger causality test is based on the idea that if one time series (X) is useful in forecasting another time series (Y), then past values of X should be able to improve the accuracy of predictions about future values of Y. It is often used in economics and finance to study the relationships between different economic variables. In this case, the Granger test was used to verify the existence of a relationship between the sales performance of a product for the different sellers, according to the principle that if a seller is a leader, through the performance of the product's historical series, it is possible to predict the performance of the same product, sold, however, by a seller who will be identified as a follower.
The same strategy was used to check whether some followers were using automating pricing systems. 

One of the main findings of this research, is that there are not only one leader and also followers are not always the same. In some time windows, a leader could decide to apply another strategy and so became a follower of another seller. In particular, this occurs very often during the black friday period.

![immagine](https://user-images.githubusercontent.com/93279084/209137136-aac9f77f-f2bc-4a79-959f-9409d08e9b92.png)

## Popularity Index
Product segmentation involves using data to identify and understand the different segments of a product or product line. 
Furthermore, by segmenting your product catalogue according to variables such as profit, quantity sold and stock, you can develop a popularity index for each product.
For this task, the main concept for performing this task was to consider a customer segmentation method, i.e. the RFM, and 'revise' it for our case. In other words, we transferred the basic concepts of <b>RFM</b> into an inventory management problem, applying an <b>ABC analysis</b> (i.e., a method used in inventory management to categorize inventory based on its importance. It’s based on the Pareto principle—the idea that 20% of your top-performing products account for 80% of your store’s total revenue), in which products were divided into classes of importance:
- A, _most important_. All products where the cumulative percentage of contribution is up to 80%;
- B, _moderately important_. Those where the cumulative percentage contribution is between 80% and 90%;
- C, _least important-. All the remaining products that have small contribution. They require attention.


