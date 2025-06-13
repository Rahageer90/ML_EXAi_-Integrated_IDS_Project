# 🚨 Intrusion Detection using Explainable AI (XAI) 🚨

This repository contains the implementation, evaluation, and explainability of machine learning models for **network intrusion detection**, leveraging **XGBoost**, **LightGBM**, and their **hybrid ensembles**, with local interpretability powered by **LIME** (Local Interpretable Model-agnostic Explanations).

---

## 📂 Project Structure

- `data/` — Contains the cleaned and preprocessed dataset (sourced from the Ton_IoT framework).
- `models/` — Includes training scripts and serialized models (e.g., `.pkl` files).
- `notebooks/` — Jupyter notebooks for training, evaluation, LIME visualization, and analysis.
- `results/` — Contains performance metrics, classification reports, and LIME explanation logs.
- `README.md` — This file.

---

## 📊 Dataset Overview

- **Source:** Ton_IoT Dataset
- **File Name:** `big_network_dataset_1.csv`
- **Samples:** 97,250
- **Features:** 46 (29 categorical, 17 numerical)
- **Classes:** 6
  - `0` — DDoS
  - `1` — Injection
  - `2` — Normal
  - `3` — Password attack
  - `4` — Scanning
  - `5` — XSS

Preprocessing included:
- Label encoding
- Variance thresholding
- Min-max feature scaling
- Train-test splitting
- Manual feature removal to mitigate data leakage

---

## 🧠 Models Used

### ✅ Base Models
- XGBoost
- LightGBM
- Random Forest
- Gradient Boosting
- Logistic Regression
- Naive Bayes
- SVM
- KNN
- Decision Tree

### 🔀 Hybrid Ensembles
- **Hybrid 2:** XGBoost + LightGBM
- **Hybrid 3:** XGBoost + LightGBM + Random Forest
- **Hybrid 4:** XGBoost + LightGBM + RF + Gradient Boosting

> ✅ Best Model: **Hybrid 3** — 97.25% Accuracy, 0.9726 F1-score, 0.9984 ROC AUC

---

## 🔍 Explainable AI (LIME)

LIME was used to interpret predictions of:
- XGBoost (Base)
- Hybrid 2
- Hybrid 3
- Hybrid 4

Key insights:
- Features like `packets_ratio`, `http_response_body_len`, `src_pkts`, and `http_user_agent` were top contributors to model decisions.
- Hybrid 3 offered the best balance of accuracy and interpretability.

---

## ⚙️ How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/intrusion-detection-xai.git
   cd intrusion-detection-xai
