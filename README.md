# Module 4 Challange: pandas-challenge-1

## Problem Statement
This challenge consists of analyzing the dataset of a fictitious e-commerce company. After getting some basic understanding of the dataset, the task is to identify
popular product categories and top customers of the company. The following measures are used to identify top customers:
* Number of orders placed,
* Number of units ordered in one order,
* Total revenue over all orders placed, and
* Total profits over all orders placed.

## Solution
The analysis proceeds through the following steps:
1. Read the dataset into a dataframe.
2. Define the following utility functions.

   a. A function that checks whether a given input is a data series containing floating point or integer values.

   b. A function that returns the measures of central tendency, mean, median, and mode.

   c. A function that finds lower and upper bounds of a data series based on the inter-quartile range. Lower and upper bounds define values beyond which data points are considered outliers.

   d. A function that finds the outliers of a data series.

3. Ensure that the dataset is clean, i.e., does not contain any 'NaN' values.

   This is done by comparing the number of records before and after removing potential 'NaN' values. It turns out that both numbers of record are the same which means the original dataset is clean.

4. Get a basic understanding of the dataset.

   Looking at a sample of the dataset one finds that each record corresponds to one order. For each order, the following information is provided:
   * Customer first name, last name, job, phone number, email address, and client ID.
   * Order ID, date, week, and year.
   * Item ID, category, subcategory, price, cost, and weight.
   * The quantity ordered and a line number.

   The Pandas `describe` function is used to get a basic understanding of the staistical properties of the item price, item cost, item weight, and the item quantity ordered. It turns out that the mean and median differ appreciably hinting at a skewed distribution. This is to be expected since item price, item cost, item weight, and the item quantity ordered all have zero as a lower bound but no upper bound.
   
   This is confirmed by a more detailed analysis of the item price and qantitity ordered distributions.

5. Find popular categories and subcategories.

   It is found that the most popular categories in descending order are
   * Consumables with 23,538 orders,
   * Furniture with 11,915 orders, and
   * Software with 8,400 orders.

   Within consumables, bathroom supplies is the most popular subcategory with 6,424 orders.

6. Find the top five customers by number of orders placed.
   
   The following customers placed the most orders:
   | Customer ID | Customer Name   | Number of Orders |
   |-------------|-----------------|------------------|
   | 33615       | Jessica Reyes   | 220              |
   | 66037       | Angela Everett  | 211              |
   | 46820       | Bryan Myers     | 209              |
   | 38378       | Alexandra Young | 207              |
   | 24741       | Kendra Garrett  | 207              |

7. Out of the top customers by number of orders placed determine which customer provided the most total revenue and total profits.

   Out of those customers Kendra Garrett provided the most total revenue and profit with $82.27 million and $36.58 million, respectively.

8. Make sure the calculation of total revenue is correct.

   This was done by comparing the calculated total revenue for three orders with their given email receipts. Except for a rounding error, they match.

9. Find the customer that ordered the most units in one order and determine their total revenue and total profit. Compare those numbers with the total revenue and total profit provided by the customers from the top five list of customers by number of orders placed.

   The customer that ordered the most units in one order, 3,958,244, is Julie Anderson, client ID 78965. They provided a total revenue and profit of $655.92 million and $247.35 million, respectively. This exceed the total revenue and profit of Kendra Garrett that provided the most total revenue and profit out of the custoemrs with the most orders.

10. Find the customer with the largest total revenue and total profit and compare it to the total revenue and total profit of the customer that ordered the most units.

    It turns out that the customer with the largest overall total revenue and profit is again Julie Anderson, client ID 78965.

## Conclusion
Out of the five customers that placed the most orders, the one that placed orders for the most units provides the company with the most total revenue and profit. That customer is not the same as the one that placed the most orders. In addition, the customer with the highest total revenue and profit out of the five custoemrs that placed the most order is not the same customer that provided the highest revenue and profit overall. That customer turned out to be the one that paced the order with the most units. That customer is not part of the five customers that placed the most orders. Therefore, the number of units placed per order is a better predictor of total revenue and profit than the number of orders placed.