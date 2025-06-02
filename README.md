# 🏨 Hotel Bar Inventory Forecasting

**AI Engineer Take-Home Project**
Author: **Bhargav Simha**

## 📌 Problem Statement

A growing hotel chain operating multiple bars is experiencing frequent **stockouts of high-demand items** and **overstocking of low-demand items**, leading to increased operational costs and poor guest experience.

🔍 **Objective:**
Forecast item-level demand and recommend daily **inventory (par) levels** to ensure optimal stock across locations.

---

## 📊 Assumptions

* Historical data is indicative of future demand.
* Data has daily granularity; weekly seasonality is minimal.
* A 15% buffer in par levels accounts for natural variability.
* A separate model is built for each item/location.
* Forecasting horizon is 5 days for responsiveness.

---

## 🧠 Models & Rationale

### ✅ Models Tried:

* Linear Regression
* Decision Tree
* Random Forest
* **XGBoost**
* **CatBoost**
* **LightGBM**
* **Facebook Prophet** (for interpretable forecasts)

### 🌟 Best Performing Approach:

An **ensemble model** combining **Gradient Boosting**, **CatBoost**, and **LightGBM**.

---

## 📈 Evaluation Metrics

| Metric | Ensemble Model |
| ------ | -------------- |
| MAE    | 152.99         |
| RMSE   | 184.26         |
| R²     | 0.072          |

📌 Final inventory recommendation:

```python
par_level = predicted_demand * 1.15
```

---

## 🛠 System Functionality

* Ingests daily POS data
* Runs forecasts and suggests quantities
* Triggers alerts for upcoming stockouts
* Tracks performance via MAE and forecast errors

---

## 🔄 Real-World Integration

* Designed for daily forecasting and restocking decisions
* Can integrate into POS systems or internal dashboards
* Supports weekly retraining and can include event/calendar effects

---

## 🚀 Scaling & Production Challenges

* Handling real-time demand shifts and external events
* Data latency and automation for retraining
* Pipeline scalability for multi-location deployment

---

## 🧪 Challenges Faced

* Preprocessing noisy and incomplete historical data
* Trade-off between model complexity and interpretability
* Low R² due to natural demand variability
* Tuning ensemble models and selecting forecast horizons

---

## 🔮 Future Work

* Use real-time and external data (e.g., events, weather)
* Dynamic par levels with reinforcement learning
* Automated feedback loops to refine predictions
* Granular SKU-level forecasts and category-based insights

---

## 📷 Visuals

* Histogram, Boxplot, and Correlation heatmaps
* Prophet forecasts with uncertainty bands
* Model evaluation and performance comparisons

---

## 📁 Repository Structure

```
├── data/                  # Input and sample datasets
├── notebooks/             # EDA, model building & evaluation
├── src/                   # Scripts for modeling, forecasting, utils
├── outputs/               # Forecast results and visualizations
├── README.md              # Project overview and instructions
```
