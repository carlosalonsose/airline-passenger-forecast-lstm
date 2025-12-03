# Airline Passenger Forecasting for Operational Optimization

![Python](https://img.shields.io/badge/Python-3.11-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-Keras-orange)
![Business Intelligence](https://img.shields.io/badge/Focus-Business%20Intelligence-green)

## Overview

This repository contains a **Business Intelligence and Analytics** project developed during my Erasmus exchange. The core objective is to apply Deep Learning techniques—specifically **Long Short-Term Memory (LSTM)** networks—to forecast airline passenger traffic.

By accurately predicting passenger flow, airports can transition from reactive to proactive management, optimizing resource allocation to maximize efficiency and profitability.

## Business Case: Airport Resource Optimization

Airports operate on thin margins and require precise logistics. An inaccurate forecast leads to either bottlenecks (bad user experience) or wasted resources (high costs).

**Project Goal:** To create a predictive model that allows airport management to optimize:
* **Retail & Stock:** Adjust inventory in Duty-Free and restaurants based on expected footfall.
* **Staffing & Security:** Dynamically open/close security lanes and waiting areas to reduce queues.
* **Facility Management:** Schedule cleaning services (restrooms, terminals) during predicted lulls to minimize disruption.
* **Energy Consumption:** Optimize HVAC and lighting in specific terminal zones based on occupancy predictions.

## Technical Methodology

The project leverages **Time Series Analysis** on the classic Airline Passengers dataset. The technical pipeline includes:

1.  **Data Preprocessing:**
    * **Train-Test Split:** The dataset was first split into training (80%) and testing (20%) sets to ensure proper validation.
    * **Normalization:** Applied `MinMaxScaler` (0,1 range) *after* the split to fit on the training data and transform the test data, preventing data leakage.
    * **Reshaping:** Converted data into a supervised learning format using a sliding window approach (Look-back).

2.  **Model Architecture:**
    * **Framework:** TensorFlow / Keras.
    * **Layer 1:** LSTM layer (32 units) to capture temporal dependencies.
    * **Layer 2:** Dropout (0.05) for regularization.
    * **Layer 3:** Dense Output layer for regression.

3.  **Training:**
    * Optimization using `Adam` optimizer.
    * Implementation of **EarlyStopping** to prevent overfitting.

## 📊 Results

The LSTM model successfully captures the trend and seasonality of the passenger data. The final performance metrics indicate a strong predictive capability:

| Metric | Score (RMSE) |
| :--- | :--- |
| **Train RMSE** | 19.42 |
| **Test RMSE** | 28.11 |

*Note: RMSE (Root Mean Squared Error) measures the average magnitude of the forecast error.*

<img width="1000" height="500" alt="business_LTSM_EN" src="https://github.com/user-attachments/assets/338420dc-388e-46e2-836f-d1079b473b06" />
> *Visualization of Model Predictions (Training & Test sets) vs. Actual Traffic.*

## Tech Stack

* **Language:** Python
* **Deep Learning:** TensorFlow, Keras
* **Data Manipulation:** Pandas, NumPy
* **Visualization:** Matplotlib
* **Preprocessing:** Scikit-learn

## How to Run

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/carlosalonsose/your-repo-name.git](https://github.com/carlosalonsose/your-repo-name.git)
    cd your-repo-name
    ```

2.  **Install dependencies:**
    It is recommended to use a virtual environment (venv or conda).
    ```bash
    pip install -r requirements.txt
    ```

3.  **Run the Jupyter Notebook:**
    ```bash
    jupyter notebook Passenger_Forecasting_LSTM.ipynb
    ```

---
*Developed by [Carlos Alonso](https://github.com/carlosalonsose) as part of the BSc Economics curriculum.*
