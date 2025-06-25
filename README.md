

````markdown
# ☀️ A Time-Aware Random Forest Regression Model for High-Accuracy AC Power Forecasting in Indian Solar Farms

![Python](https://img.shields.io/badge/Python-3.9-blue)
![Machine Learning](https://img.shields.io/badge/MachineLearning-RandomForest-green)
![Status](https://img.shields.io/badge/Status-Research%20Prototype-yellow)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

> A robust and interpretable machine learning-based framework for forecasting AC power using time-series and meteorological data from Indian solar farms.

---

## 📖 Abstract

Accurate solar power forecasting is essential for ensuring power grid stability, energy market efficiency, and optimal resource scheduling—especially under India’s renewable energy expansion goals. This project proposes a **Time-Aware Random Forest Regression (RFR)** model using 15-minute resolution plant-level and sensor data to forecast **AC Power** with exceptionally low error rates:

- 📉 **MAE**: `9.07e-05`
- 📉 **RMSE**: `0.00048`
- ✅ **Explained Variance Score (EVS)**: `0.99996`

---

## 📌 Key Features

- 🌤️ Uses weather sensor data (irradiation, module temperature) and PV generation logs (DC power, yield)
- 📅 Extracts time-aware features (hour, day, month, weekday) for temporal learning
- ⚙️ Integrates Random Forest with GridSearchCV for hyperparameter tuning and cross-validation
- 🔍 Explains predictions with **feature importance** and **residual plots**
- 🇮🇳 Trained on **real operational Indian solar plant datasets**

---

## 🧠 Methodology Overview

```mermaid
graph TD
    A[Raw Solar Plant Data] --> B[Preprocessing & Merge]
    B --> C[Feature Engineering: Time & Weather]
    C --> D[MinMax Scaling]
    D --> E[Train-Test Split (80:20)]
    E --> F[Random Forest Regressor]
    F --> G[Prediction & Evaluation]
````

---

## 🗃️ Dataset Details

* **Generation Data**: `Plant_1_Generation_Data.csv`
* **Weather Data**: `Plant_1_Weather_Sensor_Data.csv`
* **Combined Records**: 68,774 entries with 15-min interval
* **Merged on**: `PLANT_ID` and `DATE_TIME`

---

## 🔬 Feature Engineering

| Feature                           | Description                        |
| --------------------------------- | ---------------------------------- |
| `DC_POWER`                        | Direct current power output        |
| `AC_POWER`                        | Target: AC power output (forecast) |
| `IRRADIATION`                     | Solar radiation (W/m²)             |
| `MODULE_TEMPERATURE`              | Temperature of PV modules          |
| `HOUR`, `DAY`, `MONTH`, `WEEKDAY` | Time-aware cyclic features         |

---

## ⚙️ Model & Evaluation

**Model Used**: `RandomForestRegressor`
**Tuning Method**: `GridSearchCV`
**Cross-Validation**: 5-Fold
**Error Metrics**:

| Metric | Value    |
| ------ | -------- |
| MAE    | 9.07e-05 |
| RMSE   | 0.00048  |
| MAPE   | 0.069%   |
| EVS    | 0.99996  |

---

## 📊 Results Summary

* ✅ **Superior Performance**: Outperformed Linear Regression, SVR, Decision Tree, and LSTM
* ✅ **No Overfitting**: Residuals centered around zero
* ✅ **Interpretability**: Feature importance confirms `DC_POWER` as most influential
* ✅ **Robust**: Generalizes well across folds and metrics

---

## 📈 Model Comparison Table

| Model                    | MAE          | RMSE        | MAPE (%)  | EVS         | Overfit |
| ------------------------ | ------------ | ----------- | --------- | ----------- | ------- |
| Linear Regression        | 0.00143      | 0.00277     | 1.37      | 0.953       | Yes     |
| Decision Tree            | 0.00089      | 0.00191     | 0.88      | 0.981       | Yes     |
| SVR                      | 0.00041      | 0.00112     | 0.43      | 0.993       | No      |
| LSTM                     | 0.00031      | 0.00096     | 0.28      | 0.995       | No      |
| **Random Forest (Ours)** | **9.07e-05** | **0.00048** | **0.069** | **0.99996** | **No**  |

---

## 🧩 Visualizations (in `/figures/`)

* 📈 `feature_importance.png`
* 📊 `residual_plot.png`
* 🔄 `actual_vs_predicted.png`

---

## 🔮 Future Scope

* 🌍 Incorporate **spatial data** using Graph Neural Networks (GNNs)
* 🔗 Integrate **satellite cloud cover & pollution data**
* 🧠 Explore hybrid RFR + LSTM/Transformer models
* ⚡ Edge-based deployment with compressed models
* 📊 Build explainable AI dashboards with SHAP

---

## 👨‍💻 Authors

* **Simer Khurmi** – B.Tech ECE, AI/ML, IGDTUW
* ✉️ [simer.live@gmail.com](mailto:simer.live@gmail.com) | 📞 +91 9818933256
* Co-authors: \[To be listed with affiliation]

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

---

## ⭐ Star this repo

If you find this work helpful, please consider ⭐ starring the repo to support further research in **sustainable AI for India** 🌱.

```

---

Let me know if you’d like:

- A GitHub repository structure to go with this (e.g. `/src`, `/figures`, `/notebooks`, etc.)
- A `.bib` citation file for IEEE/ACM paper linking
- A formatted LaTeX version of the abstract or future work section

Would you also like this exported as a ready-to-use `README.md` file with a GitHub-style preview?
```
