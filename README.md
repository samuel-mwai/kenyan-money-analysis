# Kenya Mobile Money Transactions Analysis

This Jupyter Notebook contains a comprehensive exploratory data analysis (EDA) of a **Kenya mobile money transactions dataset**. Using **Python, Pandas, Seaborn, and Matplotlib**, the script analyzes financial trends, consumer behavior, and transaction anomalies.

---

## 📊 Dataset Overview

The dataset contains **6,000 transaction records** tracking mobile money activities (such as M-Pesa and Airtel Money) across various counties in Kenya.

### Key Data Fields
* **Transaction Details:** `transaction_id`, `transaction_timestamp`, `transaction_type`, `channel`, `status`
* **Financial Metrics:** `amount_kes`, `transaction_fee_kes`, `balance_after_kes`
* **Customer Demographics:** `customer_id`, `customer_name`, `gender`, `age`, `county`, `device_type`

---

## 🔍 Core Analysis & Features

The notebook systematically solves four critical business intelligence tasks:

### 1. Monthly Revenue & MoM Growth Trends
* Filters for completed transactions and aggregates total transaction fees (`transaction_fee_kes`) per calendar month.
* Computes **Month-over-Month (MoM) growth percentages** using the `.pct_change()` function.
* Identifies growth spikes and seasonal revenue drops.

### 2. Peak Activity Matrix (Day of Week × Hour of Day)
* Extracts the weekday name and hourly block from timestamps.
* Generates a **pivoted transaction count matrix** mapping the single busiest hour blocks across the weekly cycle.

### 3. Top Transacting Customers per County
* Groups data by county and customer profiles to sum total transaction amounts (`amount_kes`).
* Ranks customers within each county using the `.rank(ascending=False)` partition feature to return the **top 3 high-value consumers per county**.

### 4. Rolling Volume Anomaly Detection
* Resamples transaction data into a daily frequency time series.
* Measures transaction velocity using a **7-day rolling average window**.
* Isolates specific dates where daily traffic spiked dramatically, exceeding **1.5× the rolling baseline**.

---

## ⚙️ Requirements & Quickstart

### Prerequisites
Make sure you have a Python environment set up with the following libraries installed:
```bash
pip install pandas matplotlib seaborn
```

### File Architecture
To run the notebook seamlessly, ensure your local files match this relative path schema:
```text
├── Data/
│   └── kenya_mobile_money_transactions.csv
└── Notebooks/
    └── mobile_money_analysis.ipynb
```

---

## 👨‍💻 Author

**Samuel Mwai**  
Data Science & Analytics | Machine Learning | Data Analysis | Data Visualization  
* **GitHub Profile:** [samuel-mwai](https://github.com/samuel-mwai)


---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
