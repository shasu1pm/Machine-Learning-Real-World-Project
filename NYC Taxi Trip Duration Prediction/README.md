# 🚕 NYC Taxi Trip Duration Prediction  
### *A Real-World Machine Learning Regression Project*

---

## 📌 Project Overview

At some point, almost all of us have used **Uber, Ola, or Lyft** 🚖.  
Behind every ride is a **dispatching system** that decides *which driver* should take *which passenger* — and **when**.

👉 The **core challenge**:  
**Can we predict how long a taxi will be occupied during a trip using only information available at trip start?**

This project builds an **end-to-end Machine Learning regression solution** to solve that exact problem using **NYC Taxi Trip data**.

---

## 🎯 Business Problem

Ride-hailing platforms must optimize:

- ⏱️ Passenger wait time  
- 🚗 Driver utilization  
- 📊 Fleet efficiency  
- 💰 Operational cost  

If the system knows **when a driver will finish the current trip**, it can:
- Assign the *next* ride intelligently  
- Reduce idle time  
- Improve customer experience  

✅ **Accurate trip duration prediction = smarter dispatching**

---

## 🧠 Business Objective

> **Estimate the duration of a taxi trip (in seconds) using only features known before the trip starts.**

This ensures the model is:
- ✔️ Real-world deployable  
- ✔️ Suitable for live dispatch systems  
- ✔️ Business-aligned  

---

## 🎯 Machine Learning Objective

- 🔢 Build a **Regression Model**
- ⏱️ Predict **`trip_duration`**
- 🚫 Exclude unavailable future information
- 📉 Minimize prediction error  

### 🎯 Target Variable
- **`trip_duration`** → Duration of the trip in **seconds**

---

## 🚦 Feature Constraints (Business-Driven)

The following variables are **excluded** ❌  
(because they are unknown at trip start):

- `dropoff_datetime`
- `store_and_fwd_flag`

📌 This constraint makes the model **production-ready**.

---

## 🗂 Dataset Overview

Each record represents **one taxi trip** with the following fields:

| Column Name | Description |
|------------|------------|
| `id` | Unique trip identifier |
| `vendor_id` | Taxi provider ID |
| `pickup_datetime` | Trip start timestamp |
| `passenger_count` | Number of passengers |
| `pickup_latitude` | Pickup latitude |
| `pickup_longitude` | Pickup longitude |
| `dropoff_latitude` | Drop-off latitude |
| `dropoff_longitude` | Drop-off longitude |
| `trip_duration` | **Target (seconds)** |

📊 **Dataset Size**  
- Rows: **729,322**  
- Columns: **11**

---

## 🧪 End-to-End ML Workflow

### 🔹 Step-by-Step Execution Roadmap

---

## 🟢 Step 3: Load Libraries

All required Python libraries are imported:

- 🧮 NumPy → numerical operations  
- 📊 Pandas → data handling  
- 🕒 Datetime → time features  
- 📈 Matplotlib & Seaborn → visualization  
- 🤖 Scikit-learn → preprocessing & modeling  

🎯 *Purpose:* Set up the analytical environment.

---

## 🟢 Step 4: Load Data

- Load CSV into a Pandas DataFrame  
- Inspect shape and first rows  
- Confirm successful ingestion  

🎯 *Purpose:* Bring raw data into memory for exploration.

---

## 🟢 Step 5: File Structure & Content

- Identify numerical, categorical & datetime features  
- Confirm target variable  
- Understand schema  

🎯 *Purpose:* Decide preprocessing & feature engineering strategy.

---

## 🟢 Step 6: Treating Missing Values

- Missing value check across all columns  
- **Result:** No missing values found  

✅ No imputation required  

🎯 *Purpose:* Ensure clean and reliable data.

---

## 🟢 Step 7: Feature Consistency Check

- Recalculate trip duration using timestamps  
- Compare with provided `trip_duration`  

✅ Perfect match found  

🎯 *Purpose:* Validate target correctness.

---

## 🟢 Step 8: Target Exploration

- Convert duration from seconds → hours  
- Apply **log transformation**  

📊 Observations:
- Raw distribution is **right-skewed**
- Log-scale is near-normal
- Extreme outliers detected  

🎯 *Purpose:* Understand distribution & modeling implications.

---

## 🟢 Step 9: Univariate Analysis

### 🔹 Passenger Count
- Mostly single-passenger trips  

### 🔹 Vendor ID
- Two vendors
- Vendor 2 has more trips  

🎯 *Purpose:* Detect skewness and unusual patterns.

---

## 🟢 Step 10: Latitude & Longitude Analysis

- Remove geographic outliers  
- Replot pickup & drop-off locations  

📍 Dense clusters observed → **High traffic zones**

🎯 *Purpose:* Enable spatial understanding.

---

## 🟢 Step 11: Bivariate Analysis

- Boxplots & grouped statistics  
- Relationship between features & trip duration  

🎯 *Purpose:* Identify influential predictors.

---

## 🟢 Step 12: Trip Duration vs Weekday

📆 Key Findings:
- Weekends → shorter trips  
- Mid-week → longer trips  

🚦 Indicates traffic congestion patterns.

---

## 🟢 Step 13: Vendor ID vs Trip Duration

- Vendor 1 → fewer outliers  
- Vendor 2 → slightly longer trips  

🎯 *Purpose:* Vendor-level behavior analysis.

---

## 🟢 Step 14: Mean Trip Duration (Vendor-Wise)

- Vendor 2 shows higher **mean**
- Influenced by long-tail trips  

---

## 🟢 Step 15: Median Trip Duration (Vendor-Wise)

- Medians are nearly identical  
- Differences driven by **outliers**, not typical trips  

📌 Important modeling insight.

---

## 🟢 Step 16: Trip Duration vs Passenger Count

- No strong relationship observed  
- Higher counts → more variability  

🎯 *Purpose:* Validate passenger impact assumption.

---

## 🟢 Step 17: Pickup Hotspot Visualization 🌍

Color Coding:
- ⚪ White → 1–10 trips  
- 🟢 Green → 10–25 trips  
- 🔴 Red → 25+ trips  

📍 **Manhattan emerges as the busiest zone**

---

## 🟢 Step 18: Correlation Heatmap

📊 Key Insight:
- Latitude & longitude show strongest correlation
- Other features show weak linear relationships  

🎯 *Purpose:* Guide feature selection.

---

## 🟢 Step 19: Conclusion

✔️ Data is clean and reliable  
✔️ Strong spatial & temporal patterns exist  
✔️ Target variable is log-normally distributed  
✔️ Ready for regression modeling  

---

## 🟢 Step 20: Success Metrics

### 📐 Technical Metrics
- RMSE  
- MAE  

### 🧠 Business Metrics
- Better dispatch accuracy  
- Reduced passenger wait time  
- Improved driver utilization  

---

## 🚀 Deployment Readiness

- Uses only **pre-trip information**
- Suitable for **real-time systems**
- Scalable to production pipelines  

---

## ⭐ Key Takeaways

- 📍 Location is the strongest predictor  
- 🕒 Time & weekday matter  
- 🚫 Passenger count has minimal impact  
- 🔍 Data validation is critical before modeling  

---

## 📎 Project Type
**Regression | Real-World ML | EDA-Driven | Business-Aligned**

---

### 🙌 If you found this project helpful, give it a ⭐  
Happy Learning & Modeling! 🚀
