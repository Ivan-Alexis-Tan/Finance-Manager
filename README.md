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
| trans_no    | `int64`     | Transaction number |
| date        | `datetime64[ns]`| Transaction date |
| details     | `object`    | Transaction details or description |
| amount      | `int64`     | Transaction amount |
| transaction | `object`    | Transaction type (income, expenses, etc.)
| transaction_mode | `object` | Payment source or reservoir (bank, mobile bank, etc.) |
| month       | `int32`     | Numerical detail of month ($1$ = $\text{Jan}$., $2$ = $\text{Feb}$., etc.) |
| day         | `int32`     | Numerical detail of date (example: the $1$ in $\text{Dec.}\: 1, 2024$) |
| year        | `int32`     | Numerical detail of year |
| detail_clean| `object`    | Cleaned detail for smoother detail analysis |
| y/m         | `object`    | String year-month format ($\text{"24-12"}$ = $\text{Dec.}\: 2024$) |
| y/m/d       | `object`    | String format of date ($\text{"2024-12-01"}$ = $\text{Dec.}\: 1, 2024$)|
| month sort no. | `object` | Sorting number of monthly transactions |

## Executive Summary
### Overview of Findings
As the latest record is December 2025, the net income is increasing. Especially in the latest record, the month of $\text{Nov.}\: 2024\: \text{(24/11)}$ to $\text{Jan.}\: 2025\: \text{(25/1)}$, the average monthly income is increasing. Expenses are also needed to be monitored, though the data suggests that the monthly expenditures are not necessarily more than necessary. Knowing the behavior of expenses could help handle monthly expenditures better.

The dashboard below shows the overall findings of the analysis.

<img src='images\Analysis Dashboard.png' alt='Data Analysis Dashboard'>

### Net Income  
<img src='images\Net Income.png' alt='Net Income Table and Graph'>

- The trend net income from $\text{Mar.}\: 2024\: \text{(24/3)}$ to $\text{Jul.}\: 2024\: \text{(24/7)}$ shows approximately neither growth nor drop of net income.
    - This is due to lesser to typical or usual range amount of expenses during these months.
        - The average net income of these months is just $4$% $(\text{Php}\: 683)$ below from the median.
        - It is declining but too little to say there's signicant declination of net income.
    - There is $46$% net income ratio (remaining money gained after all expenditures) during these months, making it $\text{Php}\: 89,486$.
        - This is too far from target $20$% for saving/investing.

- Meanwhile, the net income from $\text{Aug.}\: 2024\: \text{(24/8)}$ to $\text{Jan.}\: 2025\: \text{(25/1)}$ is increasing.
    - The growth is $51$% above the median, which means the average growth of net income of these months is about $\text{Php}\: 8,127$.
    - The net income ratio of these months is $58.26$% $(\text{Php}\: 143,675)$.
    

- Growth rate for the last two months dropped by $81$%.
    - The drop was affected by christmas and new years seasonal expenses, and an income paired with pay of incentives (13th month pay, Christmas bonus, etc.).
    - Despite the huge drop, **the net income for the last two months is still higher than its target amount** by $19$%.

### Monthly Expenses Transaction

<img src='Images of Plots and Graphs\Line and Bar Graph - Monthly Expenses.png' alt='Monthly Expenses Line and Bar Graph'>

- Average monthly expenses is around $\text{Php}\: 17,458.33$.
    - This monthly average could vary between $\text{Php}\: 10,918.22$ and $\text{Php}\: 23.998.44$ because of seasonal expenditures and non-constant expenditure behavior.
    - The inconsistency of monthly expenses causes the varying spikes of expenses like in $\text{Dec.}\: 2023\: \text{(23/12)}$ because it is Christmas season, and some occational even like fiesta celebration in $\text{Oct.}\: 2024\: \text{(24/10)}$.

- The **highest monthly expenses is in $\text{Dec.}\: 2023\: \text{(23/12)}$** reaching $\text{Php}\: 32,023$.
    - The bar graph below shows the transactions and things purchased during this month, further detailing what caused this high spike of expenses.
<img src='Images of Plots and Graphs\Bar Graph - Total Amount and Count of Transactions.png' alt='December 2023 Expenses Details Bar Graph'>
- By eliminating the transactions that is less than $\text{Php}\: 1,000$ expenses, we left with mostly computer parts and repair costs.
    - This indicates that the reason why $\text{Dec.}\: 2023\: \text{(23/12)}$ has the highest monthly expenses is **because of laptop repairs and upgrade expenses** on the top of monthly necessities.


<img src='images\Monthly Expenses Trend.png' alt='Monthly Expenses Trend Graph'>  

- The trend seems to be below the middle value, but as of $\text{Jan.}\: 2025\: \text{(23/12)}$ it has **growth rate of $8$%**.
    - $8$% is so little that's hard notice, but monthly expenses grows about $\text{Php}\: 1,660$.
    - This growth is caused by the christmas and new year's seasonal expenditures.
    - The current christmas season expenses is approximately $5$% $(\text{Php}\: 2,010)$ higher than the previous christmas season.

<img src='Images of Plots and Graphs\Histogram adn Box Plot - Bootstrap Sampling Distribution of the Means (Bootstrapping Visualization).png' alt='Bootstrap CI Visualization'>

- **There's $95$% confidence that the true average monthly expenses is between around $\text{Php}\: 14,400$ and around $\text{Php}\: 20,700$.**
- In *hypothesis testing*, **the data suggests that monthly expenditures are not more than necessary** (assuming that the population mean of spending is $\text{Php}\: 18,000$). 


-------------------------- 

- The average monthly expenses is $\text{Php}\: 17,458.33$.
    - The **average variation of monthly expenses is $\text{Php}\: 6,540.11$ either above or below $\text{Php}\: 17,458.33$.**
        - So, it is between $\text{Php}\: 10,918.22$ and $\text{Php}\: 23.998.44$.
    - The **highest monthly expenses is $\text{Dec.}\: 2023\: \text{(23/12)}$** reaching $\text{Php}\: 32,023$.
        - Comparing this against average monthly expenses, **there are $\text{Php}\: 14,540.11$ or $45.48$% difference.**
        - The reason why it is the highest **because of laptop repairs and upgrade expenses** on the top of monthly necessities.
    - **Is slightly increasing overtime.**
        - About $\text{Php}\: 131.25$ each month on average.
        
    - **There's $95$% confidence that the true average monthly expenses is between around $\text{Php}\: 14,400$ and around $\text{Php}\: 20,700$.**

    - In *hypothesis testing*, **the data suggests that monthly expenditures are not necessarily more than necessary** (assuming the population mean of spending is $\text{Php}\: 18,000$).


### Monthly Income Transaction

<img src='Images of Plots and Graphs\Line and Bar Graph - Monthly Net Income.png' alt='Monthly Income Line and Bar Graph'>

- **Nov. of 2023, Nov.** and **Dec. of 2024** had higher income.   
    - Because these are the months when incentives and other income sources comes.
    - **The middle value of monthly income is $\text{Php}\: 30,278$.**
    - **Monthly income varies from $\text{Php}\: 25,195$ to $\text{Php}\: 35,361$ around the median.**
        - The **typical $50$% of monthly income is in between $\text{Php}\: 25,466$ and $\text{Php}\: 43,465$.**
    - The estimated average monthly income change is $\text{Php}\: 551.17$.
        - Since it is positive, we can safely say it is increasing as month passes.
    
    - In *hypothesis testing*, **the data suggests that $\text{Php}\: 21,000$ income is NOT significantly less after overall salary changes**.
        - $\text{Php}\: 21,000$ is the starting of public teacher in 2021.  


### G-cash Transactions

<img src='images\G-cash Monthly Expenses Trend.png' alt='G-cash Monthly Expenses Trend'>

- **The average G-cash monthly expenses is around $\text{Php}\: 2,036$.**
    - **This could vary approximately between $\text{Php}\: 1,461.62$ and $\text{Php}\: 2,610.38$ on average.**

- The trend by using moving averages is clearly dropping.

- The average expenses from $\text{Mar.}\: 2024\: \text{(24/03)}$ to $\text{Oct.}\: 2024\: \text{(24/10)}$ are $4$% higher than the mean.
    - This means that these months spent $\text{Php}\: 87.75$ more, indicating that the trend is higher than average.

- Meanwhile in recent months of $\text{Nov.}\: 2024\: \text{(24/03)}$ to $\text{Jan.}\: 2025\: \text{(24/10)}$ are $14$% less than average.
    - This indicates that the trend is decreasing about $\text{Php}\: 291$ less on average.
    - The expenditure in these months are less focused on digital-based purchases.

- The G-cash monthly expenses drop rate is about $58$%.

- $11.66$% of the total expenses comes from G-cash expenses. Covering about $\text{Php}\: 30,540$ in total.


<img src='Images of Plots and Graphs\Bar Graph - Comparison of Every G-cash Expenses Details and Counts of Monthly Active Transactions.png' alt='Bar Graphs of G-cash Transaction Details'>

- The "*Supa*" transaction may have the least amount per purchase, but it has the highest per month purchase of $15$ active purchase months.     
    - **Minding this expenditure behaviour will help lessen the total monthly expenses in G-cash.**   
    - **Among G-cash expenses, it is purchased 5 times per month.**    
        - The highest monthly purchasing frequency among the expenses.   
- "*Wifi load (family access)*" that has $\text{Php}\: 291$ is better purchase than "*Wifi load (magic data)*" in terms of total expenses overtime.
---------------------

- **The average G-cash monthly expenses is around $\text{Php}\: 2,036$.**
    - **The standard deviation is $\text{Php}\: 574.38$.**
        - In other words, **monthly expenses in G-cash can vary approximately between $\text{Php}\: 1,461.62$ and $\text{Php}\: 2,610.38$ on average.**
    - The "*Supa*" transaction may have the least amount per purchase, but it has the highest per month purchase.
        - **Minding this expenditure behaviour will help lessen the total monthly expenses in G-cash.**
        - **Among G-cash expenses, it is purchased 5 times per month.**
            - The highest monthly purchasing frequency among the expenses. 
    - "*Wifi load (family access)*" is better purchase than "*Wifi load (magic data)*" in terms of total expenses overtime.
