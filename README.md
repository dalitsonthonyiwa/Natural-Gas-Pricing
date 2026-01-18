# 🔥 Natural Gas Storage Pricing Model 📈

This project implements a **Natural Gas Storage Pricing model** using historical natural gas price data.
It evaluates the profitability of **injecting and withdrawing natural gas** over time, accounting for price dynamics, storage constraints, and operational costs.

The notebook demonstrates a simplified but practical framework commonly used in **energy trading, commodities analytics, and financial engineering**.

---

## 🚀 Project Overview

The model answers a core energy-trading question:

> **Is it profitable to inject natural gas at one point in time and withdraw it later, given prices, storage limits, and costs?**

### Key Components

* Load and preprocess historical natural gas price data
* Define injection and withdrawal periods
* Apply a pricing function that:

  * Computes spread between injection and withdrawal prices
  * Incorporates storage capacity constraints
  * Accounts for storage costs
* Estimate the net value of a storage strategy

---

## 📊 Data

* **Source:** Excel file (`Nat1Gas.xlsx`)
* **Index:** Date
* **Frequency:** Daily (can be extended)
* **Primary Variable:** Natural gas price

Data is loaded and indexed using pandas time series functionality.

---

## 🧮 Pricing Function

The core logic is implemented in a function:

```python
Pricing(
    inj_date,
    wit_date,
    inj_price,
    wit_price,
    inj_rate,
    wit_rate,
    max_storage,
    Storage_cost,
    data
)
```

### Parameters

* **inj_date** (`YYYY-MM-DD`) – Injection start date
* **wit_date** (`YYYY-MM-DD`) – Withdrawal date
* **inj_price** – Price at which gas is injected
* **wit_price** – Price at which gas is withdrawn
* **inj_rate** – Injection rate multiplier
* **wit_rate** – Withdrawal rate multiplier
* **max_storage** – Maximum storage capacity
* **Storage_cost** – Fixed storage cost
* **data** – Historical price DataFrame

### Output

* Net value of the storage strategy
* Profitability assessment after costs

---

## 🛠️ Tools & Libraries

* **Python**
* **pandas** – Data handling and time series indexing
* **NumPy** – Numerical computations

---

## 📈 Example Use Case

```python
Pricing(
    inj_date="2020-10-31",
    wit_date="2024-01-01",
    inj_price=10,
    wit_price=20,
    inj_rate=1,
    wit_rate=1,
    max_storage=1_000_000,
    Storage_cost=10_000,
    data=data
)
```

This simulates a long-term storage strategy where gas is injected at lower prices and withdrawn at higher prices.

---

## 💡 Key Insights

* Natural gas storage value is driven by **price spreads over time**
* Storage constraints and costs materially affect profitability
* The model reflects real-world **commodity storage valuation logic**
* Easily extensible to:

  * Rolling strategies
  * Seasonal spreads
  * Stochastic price models

---

## 📌 Future Improvements

* Incorporate stochastic price simulations (GBM / Mean Reversion)
* Add daily injection and withdrawal constraints
* Discount cash flows for time value of money
* Extend to full **storage optimization** using dynamic programming
* Integrate ARIMA/GARCH price forecasts

---

---

## 👤 Author

**Dalitso Nthonyiwa**
*MSc Financial Engineering | Energy Markets & Quantitative Modeling*

---

⭐ If you find this project useful, feel free to star the repository!
