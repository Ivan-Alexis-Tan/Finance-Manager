# Personal Finance Analysis  
Data analysis portfolio of personal finance management.  

## Overview  
This project analyzes **personal financial data** to track cash flow, spending behavior, and long-term financial trends.  
It serves as both:  
- a **personal financial management tool**  
- a **portfolio project to showcase data analysis, statistics, and visualization skills**  

⚠️ **Privacy Note**: The full dataset is private. A sanitized **snapshot** is included for demonstration.  

---

## Executive Summary (Key Insights)  
- **Net Income:** Trend is **increasing overall**, despite seasonal dips. Latest net income ratio = **44%** (well above 20% target).  
- **Expenses:** Average = **₱17,458/month** with seasonal spikes (Christmas, fiesta). Long-term trend is **slightly increasing**.  
- **Income:** Median = **₱30,278/month** with steady growth. Seasonal bonuses (Nov–Dec) create short-term surges.  
- **G-Cash:** Avg = **₱2,036/month**, ~12% of expenses. Declining since Oct 2024. Frequent small purchases (“Supa”, Wifi loads) drive totals.  
- **Statistical Tests:**  
  - Bootstrap 95% CI suggests true monthly expenses lie between **₱14.4k and ₱20.7k**.  
  - Hypothesis testing shows spending is **not significantly higher** than benchmark average.  

📊 *Full breakdown with plots and detailed explanations can be found in* [`REPORT.md`](./REPORT.md).  

---

## Data Structure  
Dataset: single `.csv`, stored in MySQL and cleaned using **pandas**.  

| Column Name      | Data Type         | Description |
|------------------|------------------|-------------|
| trans_no         | `int64`          | Transaction number |
| date             | `datetime64[ns]` | Transaction date |
| details          | `object`         | Raw description |
| amount           | `int64`          | Transaction amount |
| transaction      | `object`         | Type (income, expenses, etc.) |
| transaction_mode | `object`         | Source (bank, GCash, etc.) |
| month, day, year | `int32`          | Numeric date parts |
| detail_clean     | `object`         | Cleaned transaction detail |
| y/m, y/m/d       | `object`         | String formats of dates |
| month_sort_no    | `object`         | Month ordering for plots |

---

## Visual Highlights  

### Dashboard  
<img src="images/Analysis Dashboard.png" alt="Dashboard" width="600">  

### Net Income Trend  
<img src="images/Net Income.png" alt="Net Income" width="600">  

### Monthly Expenses  
<img src="images/Monthly Expenses Trend.png" alt="Expenses Trend" width="600">  

### Monthly Income  
<img src="images/Monthly Income Trend.png" alt="Income Trend" width="600">  

### G-Cash Transactions  
<img src="images/G-cash Monthly Expenses Trend.png" alt="Gcash Expenses" width="600">  

---

## Installation & Reproducibility  
To explore or rerun the analysis:  

1. **Clone repo:**  
   ```bash
   git clone https://github.com/Ivan-Alexis-Tan/Finance-Manager.git
   cd Finance-Manager

2. Create and activate a virtual environment:
    ```bash
    python -m venv venv
    source venv/bin/activate    # on Mac/Linux
    venv\Scripts\activate       # on Windows

3. **Intall dependencies:**
    ```bash
    pip install -r requirements.txt

4. **Run the program:**
    ```bash
    jupyter notebook "Personal Finance Analysis.ipynb"
