# **Personal Finance Analysis** - Detailed Report
## 1. **Project Background**
This project analyzes personal financial data (2023-2025) to track cash flow, income, expenses, and spending behaviour.
- Built as both a personal finance tool and a portfolio project to demonstrate data analysis, visualization, and statistical inference.
- **Dataset:** daily transactions logged since 2023.
- **Privacy:** only a sanitized snapshot is shared here.

## 2. **Data Overview**
**Format:** `.csv`, stored in MySQL, cleaned with pandas.
| Column Name | Data Type | Description |
| ------------|-----------|-------------|
| trans_no    | `int64`     | Transaction number |
| date        | `datetime64[ns]`| Transaction date |
| details     | `object`    | Raw transaction details |
| amount      | `int64`     | Transaction amount |
| transaction | `object`    | Type (income, expenses, etc.)
| transaction_mode | `object` | Payment source (bank, G-cash, etc.) |
| month       | `int32`     | Numerical detail of month ($1$ = $\text{Jan}$., $2$ = $\text{Feb}$., etc.) |
| day         | `int32`     | Numerical detail of date (example: the $1$ in $\text{Dec.}\: 1, 2024$) |
| year        | `int32`     | Numerical detail of year |
| detail_clean| `object`    | Cleaned description |
| y/m         | `object`    | String year-month format ($\text{"24-12"}$ = $\text{Dec.}\: 2024$) |
| y/m/d       | `object`    | String format of date ($\text{"2024-12-01"}$ = $\text{Dec.}\: 1, 2024$)|
| month sort no. | `object` | Month number ordering |

## 3. **Key Findings**
### **Net Income**
<img src='images\Net Income.png' alt='Net Income Table and Graph'>

- **Median net income:** ₱9,373 above the 20% target savings threshold.
- **Trend:** Increasing from mid-2024, with seasonal dips (holidays, bonuses).
- **Net income ratio:** ~44% (target: 20%).
- **Insight:** Savings are consistently above target despite seasonal expense spikes.

### **Monthly Expenses**
<img src='images\Monthly Expenses Trend.png' alt='Monthly Expenses Trend Graph'>

- **Average expenses:** ₱17,458/month.
- **Variation:** ~₱6,500, driven by Christmas and fiesta events.
- **Highest spike:** Dec 2023 (₱32k), due to laptop repairs + upgrades.
- **Long-term trend:** Slightly increasing.
- **Statistical test:** Bootstrap CI (95%) places true mean expenses between ₱14.4k–₱20.7k. No evidence expenses are “excessive” vs. benchmark (₱18k).

### **Monthly Income**
<img src='images\Monthly Income Trend.png' alt='Monthly Income Trend Graph'>

- **Median monthly income:** ₱30,278.
- **Variation:** ~₱5,000.
- **Trend:** Gradually increasing (~₱293/month since Apr 2024).
- **Seasonal peaks:** Nov–Dec (bonuses, incentives).
- **Statistical test:** No significant evidence that ₱21k (2021 teacher starting salary) is lower than observed post-adjustment income.

### **G-cash Transactions**
<img src='images\G-cash Monthly Expenses Trend.png' alt='G-cash Monthly Expenses Trend'>

- **Average:** ₱2,036/month (~12% of expenses).
- **Trend:** Declining since Oct 2024.
- **High-frequency items:**
    - Supa (15 months, 5x/month average purchases).
    - Wifi loads — "family access" plan is more cost-efficient than “magic data”.
- **Insight:** Frequent micro-purchases, not large single expenses, drive GCash totals.

# 4. **Conclusions**
- **Income growth** is outpacing expenses → sustainable net savings.
- **Expenses** have seasonal spikes but remain within reasonable ranges.
- **GCash usage** highlights behavioral spending patterns that can be optimized.
- **Statistical tests** confirm observed trends are not random fluctuations.
