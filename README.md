# Personal Finance Analysis
Data analysis portfolio of personal finance management.

## Project Background
This project is a personal financial data analysis, designed to track and understand personal cash flow, financial behavior, and spending trends. It serves as both a financial management tool and a portfolio piece to demonstrate data analysis skills.

The dataset consists of daily financial records collected since 2023 and is continuously updated. The project focuses on building efficient analysis pipelines, drawing grounded statistical inferences, and extracting actionable insights to support financial decision-making.

While the **full dataset is private**, a **snapshot of the data is included** to preserve privacy while still allowing demonstration of methods, thought process, and findings. All shared insights and results are based on this provided dataset snapshot.


## Data Structure Overview
The dataset is in `.csv` file format and only have one table. It is stored in MySQL database, imported as csv file, and mainly cleaned using *pandas* library in python.

The table below shows the **column name**, its **data type**, and **short description** on what is column all about.

| Column Name | Data Type | Description |
| ------------|-----------|-------------|
| trans_no    | int64     | Transaction number |
| date        | datetime64[ns]| Transaction date |
| details     | object    | Transaction details or description |
| amount      | int64     | Transaction amount |
| transaction | object    | Transaction type (income, expenses, etc.)
| transaction_mode | object | Payment source or reservoir (bank, mobile bank, etc.) |
| month       | int32     | Numerical detail of month ($1$ = $\text{Jan}$., $2$ = $\text{Feb}$., etc.) |
| day         | int32     | Numerical detail of date (example: the $1$ in $\text{Dec.}\: 1, 2024$) |
| year        | int32     | Numerical detail of year |
| detail_clean| object    | Cleaned detail for smoother detail analysis |
| y/m         | object    | String year-month format ($\text{"24-12"}$ = $\text{Dec.}\: 2024$) |
| y/m/d       | object    | String format of date ($\text{"2024-12-01"}$ = $\text{Dec.}\: 1, 2024$)|
| month sort no. | object | Sorting number of monthly transactions |

## Executive Summary
### Overview of Findings
As the latest record is December 2025, the net income is increasing. Especially in the latest record, the month of $\text{Nov.}\: 2024\: \text{(24/11)}$ to $\text{Jan.}\: 2025\: \text{(25/1)}$, the average monthly income is increasing. Expenses are also needed to be monitored, though the data suggests that the monthly expenditures are not necessarily more than necessary, knowing the behavior of expenses could help handle monthly expenditures better.

The dashboard below shows the overall findings of the analysis.
