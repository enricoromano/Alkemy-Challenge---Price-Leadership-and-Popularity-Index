# Business Challenge - Price Leader and Follower Detection, Popularity Index

## Introduction 

In the business world, it is often important to identify the price leaders and followers in a market. Price leaders are the companies that set the prices for products or services, while price followers are the companies that follow the pricing set by the leaders. In this project, we aim to develop a Python program to detect price leaders and followers in a given market, and create a popularity index based on the pricing data.

## Exploratory Data Analysis

Inputs of this project are 7 dataset that contains information about different insight of clients and product sales:
- Sales_data : contains data about sales of our client (that is identified as seller 24)
- Product_Catalog : contains information about all the products in the catalog
- Prices_competitor : contains information about the prices that the different competitors in the market assign to each product in different period
- Stock : contains information about stock level
- Clicks_regular and click_biddings: basically these two datasets contains same information about the click that a product receive in a specific days. The main     difference between these datasets is that click_biddings refers to clicks received by product that have some sponsorships (e.g. advertinsing in order to appear as first in the catalog).

## Methodology
To detect the price leaders and followers in the market, we will follow the following steps:
- Split dataset in five different intervals, related to 
