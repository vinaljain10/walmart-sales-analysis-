# Walmart Sales Data Analysis

## About

This project aims to explore Walmart Sales data to understand top-performing branches and products, sales trends of different products, and customer behavior. The goal is to study how sales strategies can be improved and optimized. The dataset was obtained from the [Kaggle Walmart Sales Forecasting Competition](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting).

> "In this recruiting competition, job-seekers are provided with historical sales data for 45 Walmart stores located in different regions. Each store contains many departments, and participants must project the sales for each department in each store. To add to the challenge, selected holiday markdown events are included in the dataset. These markdowns are known to affect sales, but it is challenging to predict which departments are affected and the extent of the impact." [source](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting)

## Purpose Of The Project

The major aim of this project is to gain insight into the sales data of Walmart to understand the different factors that affect sales in different branches.

## About Data

The dataset contains sales transactions from three different branches of Walmart, respectively located in Mandalay, Yangon, and Naypyitaw. The data contains 17 columns and 1000 rows:

| Column                  | Description                             | Data Type      |
| :---------------------- | :-------------------------------------- | :------------- |
| invoice_id              | Invoice of the sales made               | VARCHAR(30)    |
| branch                  | Branch at which sales were made         | VARCHAR(5)     |
| city                    | The location of the branch              | VARCHAR(30)    |
| customer_type           | The type of the customer                | VARCHAR(30)    |
| gender                  | Gender of the customer making purchase  | VARCHAR(10)    |
| product_line            | Product line of the product sold        | VARCHAR(100)   |
| unit_price              | The price of each product               | DECIMAL(10, 2) |
| quantity                | The amount of the product sold          | INT            |
| VAT                     | The amount of tax on the purchase       | FLOAT(6, 4)    |
| total                   | The total cost of the purchase          | DECIMAL(10, 2) |
| date                    | The date on which the purchase was made | DATE           |
| time                    | The time at which the purchase was made | TIMESTAMP      |
| payment_method          | The total amount paid                   | DECIMAL(10, 2) |
| cogs                    | Cost Of Goods Sold                      | DECIMAL(10, 2) |
| gross_margin_percentage | Gross margin percentage                 | FLOAT(11, 9)   |
| gross_income            | Gross Income                            | DECIMAL(10, 2) |
| rating                  | Rating                                  | FLOAT(2, 1)    |

### Analysis List

1. **Product Analysis**
   > Conduct analysis on the data to understand the different product lines, the products lines performing best, and the product lines that need to be improved.

2. **Sales Analysis**
   > This analysis aims to answer the question of the sales trends of products. The result of this can help us measure the effectiveness of each sales strategy the business applies and what modifications are needed to gain more sales.

3. **Customer Analysis**
   > This analysis aims to uncover the different customer segments, purchase trends, and the profitability of each customer segment.

## Approach Used

1. **Data Wrangling**
   > Inspection of data to detect **NULL** values and missing values and applying data replacement methods.

2. **Feature Engineering**
   > Generating new columns from existing ones.
   > - `time_of_day`: Insight into sales in the Morning, Afternoon, and Evening.
   > - `day_name`: Extracted days of the week for each transaction.
   > - `month_name`: Extracted months of the year for each transaction.

3. **Exploratory Data Analysis (EDA)**
   > Exploratory data analysis to answer the listed questions and aims of this project.

4. **Machine Learning Model**
   > Build a model to predict total sales based on various features.

## Tech Stack

- **Programming Language:** Python
- **Data Manipulation and Analysis:** pandas, numpy
- **Data Visualization:** matplotlib, seaborn
- **Machine Learning:** scikit-learn
- **Tools:** Jupyter Notebook

### Machine Learning Libraries and Tools Used

- **pandas**: For data manipulation and analysis
- **numpy**: For numerical operations
- **matplotlib**: For data visualization
- **seaborn**: For statistical data visualization
- **scikit-learn**: For building and evaluating machine learning models

## Business Questions and Answers

1. **How many unique cities does the data have?**
   - There are 3 unique cities: Mandalay, Yangon, and Naypyitaw.

2. **In which city is each branch?**
   - Branch A: Yangon
   - Branch B: Mandalay
   - Branch C: Naypyitaw

3. **How many unique product lines does the data have?**
   - There are 6 unique product lines.

4. **What is the most common payment method?**
   - The most common payment method is Ewallet.

5. **What is the most selling product line?**
   - The most selling product line is Fashion accessories.

6. **What is the total revenue by month?**
   - Total revenue varies by month, with December having the highest revenue.

7. **What month had the largest COGS?**
   - December had the largest Cost of Goods Sold (COGS).

8. **What product line had the largest revenue?**
   - Fashion accessories had the largest revenue.

9. **What is the city with the largest revenue?**
   - Yangon is the city with the largest revenue.

10. **Which branch sold more products than the average product sold?**
    - Branch A (Yangon) sold more products than the average.

## Revenue And Profit Calculations

```markdown
COGS = unit_price * quantity

VAT = 5% * COGS

VAT is added to the COGS and this is what is billed to the customer.

total(gross_sales) = VAT + COGS

grossProfit(grossIncome) = total(gross_sales) - COGS

Gross Margin is gross profit expressed as a percentage of the total(gross profit/revenue)

Gross Margin = (gross income / total revenue) * 100
