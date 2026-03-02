# 🚀 DECODE-X 2026 | NL Dalmia Hackathon Finalist Project

🏆 **Shortlisted Finalist – 24 Hour Grand Finale Hackathon**  
🎯 Organized by **NL Dalmia Institute of Management Studies & Research, Mumbai**

---

## 📌 About the Hackathon

**DECODE-X 2026** was a prestigious hackathon conducted by **NL Dalmia (Mumbai)** where innovative minds came together to solve real-world business and technology problems.

We are proud to share that our team was **shortlisted for the Finale Round**, which was a **24-hour on-site hackathon**, where we built and presented our solution under intense time constraints.

---

## 💡 Problem Statement

Lumina Energy operates a suburban Mumbai distribution zone under Maharashtra’s **Availability Based Tariff (ABT)** regulations. As mandated by the State Load Dispatch Centre (SLDC), the company must submit a **2-day ahead load forecast at 15-minute resolution**.

However, forecasting accuracy is not just a statistical challenge — it is a **financial risk minimization problem**.

### Under ABT:

- 🔺 **Under-forecasting (Actual > Forecast)** → Costly grid drawal penalty  
- 🔻 **Over-forecasting (Forecast > Actual)** → Inefficiency + deviation charge  
- ⚖️ Penalties are asymmetric  
- ⚡ Peak-hour (6:00 PM – 10:00 PM) under-forecasting carries elevated financial risk  

### Stage 2 Shocks

- **Regime Shift** – Post-pandemic structural demand volatility increased sharply  
- **Peak-Hour Penalty Escalation** – Under-forecasting penalty increased from ₹4/kWh to ₹6/kWh during peak hours  

### Stage 3 Board Constraints

- Total financial exposure cap  
- Maximum 3 peak intervals with >5% underestimation  
- Forecast bias bounded within **[-2%, +3%]**  
- Average uplift capped at **3%**  
- Mandatory risk transparency reporting  

---

### 🎯 Core Objective

Develop a **2-day ahead probabilistic load forecasting system** that:

- Minimizes expected financial penalty (₹)  
- Adapts to regime shifts and volatility  
- Satisfies strict regulatory and board constraints  
- Ensures peak-hour reliability  
- Avoids temporal data leakage  

This was not a pure forecasting task — it was a **stochastic financial optimization problem under regulatory constraint**.

---

## 🛠️ Our Solution

We engineered a **Risk-Optimized Forecasting Architecture** that abandons traditional mean-error minimization (RMSE) models and instead directly optimizes financial exposure using **Newsvendor logic**.

---

### 🔹 1. Stochastic Financial Optimization Framework

Instead of predicting the mean load, we used:

- Quantile Regression  
- Newsvendor-based alpha selection  
- Cost-aware asymmetric targeting  

Optimal quantile under asymmetric penalties:
α = UnderPenalty / (UnderPenalty + OverPenalty)

- **Stage 1 Off-Peak:** 0.667 (₹4 / ₹6)  
- **Stage 2 Peak:** 0.750 (₹6 / ₹8)  

---

### 🔹 2. Dual-LightGBM Quantile Architecture

We deployed a bifurcated model pipeline:

| Model   | Interval Type | Target Quantile |
|---------|--------------|----------------|
| Model 1 | Off-Peak     | 66.7th Percentile |
| Model 2 | Peak-Hour    | 75.0th Percentile |

This asymmetric modeling aligned structurally with the SLDC penalty design.

---

### 🔹 3. Regime-Aware & Volatility-Adaptive Modeling

To address post-COVID structural breaks:

- Engineered **Regime categorical feature**
  - Regime 0: Pre-2020  
  - Regime 1: Lockdown  
  - Regime 2: Recovery  
- Applied **Log-Scaled Recency Weighting**
  - Prioritized recent recovery data  
  - Preserved extreme weather behavior  
- Enforced strict **48-hour issuance discipline** to eliminate data leakage  

---

### 🔹 4. Deterministic Optimization Layer (Constraint Enforcer)

To satisfy Stage 3 Board directives:

📈 **1.015 Peak Micro-Buffer**
- Applied strictly within 18:00–21:45 window  
- Ensured ≤ 3 intervals > 5% underestimation  

📉 **Mathematical Bias Trimming**
- Dynamic scaling to maintain overall bias within **+2.99%**  
- Guaranteed compliance with procurement ceiling  

---

### 🔹 5. Financial Backtesting (Primary Metric)

Traditional error metrics were rejected.

We validated exclusively using:

- Total Deviation Penalty (₹)  
- Peak vs Off-Peak Exposure  
- 95th Percentile Absolute Deviation  
- Reliability Constraint Checks  

#### 📊 Stage 2 Results (Out-of-Time)

- **Total Penalty:** ₹462,134.15  
- **Reduction vs Naive Baseline:** 30.05%  
- **95th Percentile Deviation:** 241.78 kW  
- Successfully adapted to escalated ₹6 peak penalty  

---

### 🚀 Key Features

- ✅ Real-time data analysis  
- ✅ Predictive modeling  
- ✅ Strategic optimization recommendations  
- ✅ Visual dashboards for decision-making  
- ✅ Scalable architecture  

---

## 🏁 Final Architecture

### **RiskOptimizedForecaster**

A dynamic, quantile-based, regime-aware, constraint-compliant forecasting system designed for:

- Financial prudence  
- Regulatory compliance  
- Peak reliability  
- Executive transparency  

---

## 🛠️ Tech Stack

### 💻 Programming & Data Processing
- Python  
- Pandas  
- NumPy  

### 🤖 Machine Learning
- LightGBM (Quantile Regression)  
- Newsvendor-based stochastic optimization logic  

### 📊 Validation & Backtesting
- Rolling Origin Out-of-Time Validation  
- Custom `calculate_penalties()` financial simulation engine  
- Chronological split evaluation  

### 📈 Business Intelligence & Reporting
- Power BI (.pbix dashboard)  
- Executive risk visualization  
- Worst-interval deviation diagnostics  

### 📂 Modeling Infrastructure
- Object-Oriented Pipeline Design  
- Leakage-safe feature engineering  
- Quantile-based dual-model architecture  

---

## 📊 Analytical Approach

1. **Data Cleaning & Preprocessing**  
2. **Exploratory Data Analysis (EDA)**  
3. **Feature Engineering**  
4. **Model Development**  
5. **Performance Evaluation**  
6. **Business Interpretation**  
7. **Strategic Recommendations**  

---

## 📈 Results & Impact

- 📌 Improved decision accuracy  
- 📌 Identified operational inefficiencies  
- 📌 Generated actionable business insights  
- 📌 Delivered a scalable solution within 24 hours  

---

## 🏁 Hackathon Experience

- ⏳ 24-hour intensive development sprint  
- 🎤 Live presentation to industry judges  
- 🤝 Team collaboration under pressure  
- 💡 Rapid prototyping and strategic thinking  

This experience strengthened our:

- Problem-solving abilities  
- Analytical thinking  
- Team coordination  
- Time management  

---

## 👩‍💻 Team

- **Keya Chaudhary**  
- **Aryan Nehete**  

---

## 📜 Acknowledgment

We sincerely thank **NL Dalmia Institute of Management Studies & Research, Mumbai** for organizing DECODE-X 2026 and providing a platform to innovate, compete, and grow.

---

## ⭐ If you find this project interesting

Feel free to ⭐ the repository and connect with us!
