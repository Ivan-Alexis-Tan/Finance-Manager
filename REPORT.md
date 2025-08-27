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

- The median net income is $\text{Php}\: 9,373$ higher than the target amount.
    - $20$% of monthly income $(\text{Php}\: 6,446)$ is the target monthly net income.
    
- The trend net income from $\text{Mar.}\: 2024\: \text{(24/3)}$ to $\text{Jul.}\: 2024\: \text{(24/7)}$ shows approximately neither growth nor drop of net income.

    - This is due from lesser to typical or usual range amount of expenses during these months.
        - The average net income of these months is just $4$% $(\text{Php}\: 683)$ below from the median.
        - Monthly net income are canceling out, leading to typical average net income.

    - There is $46$% net income ratio (remaining money gained after all expenditures) during these months, saving $\text{Php}\: 89,486$.
        - This is too high from target $20$% total net income.
    
    - For monthly net income, since the median of these months is $\text{Php}\: 8,293$, it is $29$% more than the target $20$%.
        - **Monthly net income is greater than the $20$% target monthly net income.**

- Meanwhile, the net income from $\text{Aug.}\: 2024\: \text{(24/8)}$ and onwards is increasing.
    - 5-month moving averages is increasing by $\text{Php}\: 1,216$ on average.
        - Indicating **the trend is increasing**.

- **For the last two months, growth rate is dropping by $81$%.**
    - The drop was affected by Christmas and New Years seasonal expenses, and huge income of monthly salary and incentives (13th month pay, Christmas bonus, etc.).
    
    - Despite the huge drop, **the net income ratio is $44$%.**
        - **$24$% higher than its target amount.**

### Monthly Expenses Transaction

<img src='images\Line and Bar Graph - Monthly Expenses.png' alt='Monthly Expenses Line and Bar Graph'>

- Average monthly expenses is around $\text{Php}\: 17,458.33$.
    - Monthly expenses have average variation of $\text{Php}\: 6,540$ from the mean because of seasonal expenditures and non-constant expenditure behavior.

    - The inconsistency of monthly expenses causes the varying spikes like in $\text{Dec.}\: 2023\: \text{(23/12)}$ because it is Christmas season, and some occational even like fiesta celebration in $\text{Oct.}\: 2024\: \text{(24/10)}$.

- The **highest monthly expenses is in $\text{Dec.}\: 2023\: \text{(23/12)}$** reaching $\text{Php}\: 32,023$.
    - The bar graph below shows the transactions and things purchased during this month, further detailing what caused this high spike of expenses.
<img src='images\Bar Graph - Total Amount and Count of Transactions.png' alt='December 2023 Expenses Details Bar Graph'>
- By eliminating the transactions that is less than $\text{Php}\: 1,000$ expenses, we left with mostly computer parts and repair costs.
    - This indicates that the reason why $\text{Dec.}\: 2023\: \text{(23/12)}$ has the highest monthly expenses is **because of laptop repairs and upgrade expenses** on the top of monthly necessities.


<img src='images\Monthly Expenses Trend.png' alt='Monthly Expenses Trend Graph'>  

- In general, **monthly expenses trend is slightly increasing** on average.

- **For the last two months, monthly expenses dropped by $7$%** from $\text{Dec.}\: 2024$ to $\text{Jan.}\: 2025$.
    - Despite the drop, the *average expenses of these months is $24$% above from the median.*
    - Indicating that **monthly expenses is still high in these months.**

- Spike of monthly expenses is caused by Christmas and New Years season-related purchases.

- The Christmas and New Years season-related expenses of $\text{2024-2025}$ (the recent season) is higher than the same season in year $\text{2023-2024}$ (the previous season).


<img src='images\Histogram adn Box Plot - Bootstrap Sampling Distribution of the Means (Bootstrapping Visualization).png' alt='Bootstrap CI Visualization'>
        
- **There's $95$% confidence that the true average monthly expenses is between around $\text{Php}\: 14,400$ and around $\text{Php}\: 20,700$.**

- In *hypothesis testing*, **the data suggests that monthly expenditures are not more than necessary** (assuming that the people in the town spends $\text{Php}\: 18,000$ monthly on average).


### Monthly Income Transaction

<img src='images\Line and Bar Graph - Monthly Income.png' alt='Monthly Income Line and Bar Graph'>

- **Nov. of 2023, Nov.** and **Dec. of 2024** had higher income.   
    - Because **these are the months when incentives and other income sources comes.**

- **The middle value of monthly income is $\text{Php}\: 30,278$.**
- **Monthly income varies by $\text{Php}\: 5,083$ on average around the median.**
- The **typical $50$% of monthly income is in between $\text{Php}\: 25,466$ and $\text{Php}\: 43,465$.**

- **Monthly income is increasing**, showed by rolling averages with $\text{Php}\: 362$ average increase.

- Monthly income has been **increasing by $\text{Php}\: 293$ on average since $\text{Apr.}\: 2024\: (24/04)$ and onwards.**

<img src='images\Monthly Income Trend.png' alt='Monthly Income Trend Graph'>

- **For the last two months the growth rate is dropping by $49$% .**
    - The huge drop stems from high unusual seasonal income, to lower usual income.
    - The average of last two monthly income is $29$% higher than the median.
        - This means that on average, these months are **still higher than the typical monthly income amount.**
    - While, the latest monthly income is $13$% less than the median (typical amount).
        - Not unusually low enough to be worried about.
    - **The drop rate is basically a "return to normal" rate after a huge seasonal income surge from previous month.**
    
- In *hypothesis testing*, **the data suggests that $\text{Php}\: 21,000$ income is NOT significantly less after overall salary changes**.
    - $\text{Php}\: 21,000$ is the starting of public teacher in the year 2021.  


### G-cash Transactions

<img src='images\G-cash Monthly Expenses Trend.png' alt='G-cash Monthly Expenses Trend'>

- **The average G-cash monthly expenses is around $\text{Php}\: 2,036$.**
- **The average data despersion is $\text{Php}\: 574$ either above or below the mean.**

- **$12$% of the total expenses is coming from G-cash.**

- **Trend of G-cash Monthly Expenses:**
    - **G-cash Monthly Expenses from $\text{Oct.}\: 2024$ and onwards is declining by $\text{Php}\: 132$ on average (5-month rolling averages).**

    - **For the last two months, the growth rate is declining about $37$%.**
        - The latest month is $33$% below the mean, having $\text{Php}\: 662$ difference.
        - The expense declination rate is low but not unusually low.

<img src='images\Bar Graph - Comparison of Every G-cash Expenses Details and Counts of Monthly Active Transactions.png' alt='Bar Graphs of G-cash Transaction Details'>

- The "*Supa*" transaction may have the least amount per purchase, but it has the highest per month purchase of $15$ active purchase months.     
    - **Minding this expenditure behaviour will help lessen the total monthly expenses in G-cash.**   
    - **Among G-cash expenses, it is purchased 5 times per month.**    
        - The highest monthly purchasing frequency among the expenses.   
- "*Wifi load (family access)*" that has $\text{Php}\: 291$ is better purchase than "*Wifi load (magic data)*" in terms of total expenses overtime.
