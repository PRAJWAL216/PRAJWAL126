# 🌾 EDA on Agri Market Dataset

## 📘 Overview

This project performs **Exploratory Data Analysis (EDA)** on an agricultural market dataset containing information about **crop arrivals, market prices, commodities, and states/districts**.
The objective is to **understand market trends**, **clean the data**, and **find insights useful for policy, farmers, and market analysis**.

---

## 🧾 Dataset Summary

* **Rows:** ~200–1000 (varies by file version)
* **Columns:** ≥6 (including market, commodity, variety, arrival, min_price, max_price, modal_price)
* **Source:** Open agricultural data portal (e.g., data.gov.in or Kaggle)

### Key Attributes

| Column               | Description                   |
| -------------------- | ----------------------------- |
| `State`              | Name of the state             |
| `District`           | District of the market        |
| `Market`             | Local market name             |
| `Commodity`          | Crop/produce name             |
| `Variety`            | Type of crop                  |
| `Arrivals_in_Tonnes` | Quantity of produce arrived   |
| `Min_Price`          | Minimum market price (Rs/qtl) |
| `Max_Price`          | Maximum market price (Rs/qtl) |
| `Modal_Price`        | Most frequent market price    |

---

## 🧹 Data Cleaning Summary

| Issue Detected                                  | Action Taken                                        |
| ----------------------------------------------- | --------------------------------------------------- |
| Missing values in price/arrivals                | Filled with median (numeric) and mode (categorical) |
| Duplicate rows                                  | Removed                                             |
| Formatting inconsistencies (extra spaces, case) | Standardized text                                   |
| Negative or unrealistic prices                  | Treated as outliers and capped using IQR method     |

---

## 📊 Descriptive Statistics

* **Average Modal Price:** ₹X,XXX per quintal (varies by crop)
* **Average Arrivals:** XX tonnes
* **Price Range:** Min ₹___ to Max ₹___
* **Skewness:** Prices are right-skewed → few markets have very high prices.
* **Kurtosis:** Slightly leptokurtic → most prices cluster near the mean with occasional spikes.

---

## 📈 Data Visualizations & Insights

### 🔹 Univariate Analysis

* **Histogram:** Most commodities have moderate arrivals with few extremely high-volume entries.
* **Boxplot:** Several markets show high price variability, indicating inconsistent demand or quality.
* **Bar Charts:** A few commodities dominate (e.g., tomato, onion, potato), while others appear seasonally.

### 🔹 Bivariate Analysis

* **Correlation Heatmap:**

  * Strong positive correlation between `Min_Price`, `Max_Price`, and `Modal_Price` — market consistency.
  * Weak correlation between `Arrivals` and `Price` — indicates demand-supply balance varies by region.

* **Scatter Plot:**

  * High arrivals don’t always reduce price — possibly due to regional or seasonal market differences.

### 🔹 Outliers

* Some markets show **extremely high maximum prices**, possibly due to data entry errors or exceptional demand.
* Outliers were capped using IQR (Interquartile Range) method for stable analysis.

---

## 🧠 Insights & Interpretation

1. **Price Stability:**
   Modal price closely follows min and max prices, suggesting stable price distribution across markets.

2. **Commodity Trends:**
   Commodities like **onion, potato, tomato** have high arrival frequency — staple crops dominate trade.

3. **Regional Variation:**
   Certain states consistently report higher prices, indicating better infrastructure or market demand.

4. **Supply–Demand Anomaly:**
   No clear negative correlation between arrivals and price → suggests external factors (weather, transport, quality).

5. **Outlier Significance:**
   High outliers may represent **premium quality produce** or **data errors** — useful for further market modeling.

---

## 🧩 Conclusion

The dataset provides valuable insights into **agricultural price dynamics** and **market performance** across India.
Cleaned and structured data can be further used for:

* **Price prediction models**
* **Market comparison dashboards**
* **Policy analysis for supply chain optimization**

---

## 🗂️ Repository Structure

```
EDA_AgriMarket_<RollNo>/
│
├── Agri_Market_Dataset.csv
├── EDA_AgriMarket.ipynb
├── Cleaned_Agri_Market.csv
├── README.md  ← (this file)
└── /images/
    ├── hist_price.png
    ├── box_price.png
    ├── heatmap_corr.png
    └── scatter_arrivals_price.png
```
