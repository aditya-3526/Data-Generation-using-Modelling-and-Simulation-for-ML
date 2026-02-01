# Data Generation using Modelling and Simulation for Machine Learning

## 📌 Project Overview

In many real-world machine learning applications, collecting large, high-quality datasets is expensive, time-consuming, or impractical. Simulation-based data generation provides an effective alternative by allowing controlled experimentation and synthetic data creation.

This project demonstrates how **modelling and simulation** can be used to generate a dataset, which is then used to train and evaluate multiple **machine learning regression models**. A discrete-event simulation of a **queueing system** is implemented using the **SimPy** library, and the generated data is analyzed using various ML algorithms.

---

## 🎯 Objectives

- Identify and explore a suitable simulation tool  
- Generate synthetic data using simulation  
- Define parameters with valid lower and upper bounds  
- Run **1000 simulation experiments**  
- Train and compare **multiple ML models**  
- Evaluate models using standard performance metrics  
- Identify the best-performing model  

---

## 🛠 Simulation Tool Used

- **SimPy (Python)**
- Type: Discrete Event Simulation
- Application Domain: Queueing systems, process modeling, resource utilization

SimPy allows event-based simulation using Python generators, making it suitable for modeling real-world systems like service queues, servers, and waiting times.

---

## 🧩 Simulation Model Description

A **single-stage queueing system** is simulated where:
- Customers arrive randomly
- Servers process customers
- Waiting times and queue lengths are recorded

This setup mimics real-world systems such as:
- Call centers  
- Server request handling  
- Bank or hospital queues  

---

## ⚙️ Simulation Parameters & Bounds

| Parameter        | Description                         | Lower Bound | Upper Bound |
|------------------|-------------------------------------|-------------|-------------|
| arrival_rate     | Rate of customer arrivals           | 1           | 5           |
| service_rate     | Rate of customer service            | 1           | 5           |
| sim_time         | Total simulation time               | 50          | 100         |
| num_servers      | Number of service servers           | 1           | 3           |

Random values within these bounds are generated for each simulation run.

---

## 🔁 Data Generation Methodology

1. Randomly generate simulation parameters within defined bounds  
2. Run the SimPy queue simulation  
3. Record output metrics  
4. Repeat the process **1000 times**  
5. Store all results in a structured dataset  

---

## 📊 Generated Dataset Description

### Input Features
- `arrival_rate`
- `service_rate`
- `sim_time`
- `num_servers`

### Output Variables
- `avg_wait` – Average customer waiting time  
- `max_queue` – Maximum queue length observed  
- `served` – Total number of customers served  

The target variable used for ML prediction is **average waiting time (`avg_wait`)**.

---

## 🔬 Exploratory Data Analysis

A **correlation heatmap** is used to understand relationships between simulation parameters and output variables.

Key observations:
- Higher arrival rates increase waiting time  
- Higher service rates reduce waiting time  
- Number of servers significantly impacts queue performance  

---

## 🤖 Machine Learning Models Used

The following regression models were trained and evaluated:

1. Linear Regression  
2. Ridge Regression  
3. Lasso Regression  
4. Decision Tree Regressor  
5. Random Forest Regressor  
6. K-Nearest Neighbors (KNN)  
7. Support Vector Regressor (SVR)  
8. Gradient Boosting Regressor  
9. Extra Trees Regressor  
10. XGBoost Regressor  

---

## 📈 Evaluation Metrics

Each model was evaluated using:

- **MAE (Mean Absolute Error)**  
- **MSE (Mean Squared Error)**  
- **RMSE (Root Mean Squared Error)**  
- **R² Score (Coefficient of Determination)**  


---

## 📋 Model Comparison Results

| Model | MAE | MSE | RMSE | R² |
|------|-----|-----|------|----|
| Linear Regression | Moderate | Moderate | Moderate | Low |
| Decision Tree | Low | Low | Low | High |
| Random Forest | Very Low | Very Low | Very Low | Very High |
| Gradient Boosting | Low | Low | Low | High |
| XGBoost | **Lowest** | **Lowest** | **Lowest** | **Highest** |

*(Exact values may vary due to randomness in simulation.)*

---

## 🏆 Best Performing Model

### ✅ **XGBoost Regressor**

**Reasons:**
- Highest R² score  
- Lowest RMSE  
- Strong ability to capture non-linear relationships  
- Robust against noise in synthetic data  

---

## 📊 Visualization Summary

The following plots were generated:
- R² Score comparison across models  
- RMSE comparison across models  
- Actual vs Predicted waiting time (best model)  
- Feature importance using Random Forest  
- Correlation heatmap of dataset

  <img width="754" height="590" alt="image" src="https://github.com/user-attachments/assets/198aba8c-1d7d-4fa8-b445-47f196996a67" />
  <img width="989" height="490" alt="image" src="https://github.com/user-attachments/assets/ca91b07e-31cd-40b0-810e-03f84db03aae" />
  <img width="989" height="490" alt="image" src="https://github.com/user-attachments/assets/8bb4cb2c-0afd-4b4b-b7c3-26a9881cc9be" />
  <img width="590" height="590" alt="image" src="https://github.com/user-attachments/assets/98546fea-5c05-4ada-974c-0e6965159b97" />
  <img width="590" height="390" alt="image" src="https://github.com/user-attachments/assets/9dbe425d-8619-42c0-bf4f-247408e4152e" />
  
These visualizations support quantitative evaluation and model selection.

---

## 📌 Conclusion

This project successfully demonstrates how simulation-based modeling can be used to generate synthetic datasets for machine learning applications. The combination of **SimPy-based simulation** and **advanced ML models** enables effective prediction of system performance metrics such as waiting time.

Simulation-driven ML is especially valuable when real-world data is unavailable, expensive, or unsafe to collect.

