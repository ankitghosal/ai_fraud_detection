# GenAI Fraud Detection Framework

> A fraud detection framework using Generative AI (GenAI) and unsupervised machine learning to identify suspicious patterns in financial transactions.

---

## ⚠️ Caution

> **CAUTION 1 — Automated Pipeline:**
> The `.ipynb` file will automatically fetch data from the CSV and run end to end. It will generate the `GEN AI FRAUD DASHBOARD.py` file, which is responsible for the AI Dashboard on Streamlit. This process is fully automated — just keep the notebook and CSV data in the same folder.

> **CAUTION 2 — API Key:**
> Change the API key accordingly to run it correctly. If the API key is not configured properly, the AI-Reasoning outcome will not be generated. The API provider version must be aligned with the API key.
> This project uses: `gemini/2.5-flash`

---

## 1. Project Overview

This project builds a real-time fraud detection system for banking transactions. Unlike traditional systems that rely on static rules (e.g., *"flag all transactions over $10,000"*), this solution uses:

- **Unsupervised Machine Learning** to detect unknown anomaly patterns
- **Generative AI** to provide human-readable explanations for why a transaction is suspicious

---

## 2. Solution Workflow

The system follows a standard Data Science pipeline:

1. **Data Ingestion** — Loading raw transaction logs
2. **Preprocessing & Feature Engineering** — Transforming raw data into meaningful behavioral indicators
3. **Anomaly Detection** — Applying the Isolation Forest algorithm to identify outliers
4. **GenAI Contextualization** — Generating prompts for an LLM to explain the risk
5. **Visualization** — Plotting anomalies to validate findings

---

## 3. Machine Learning Model: Isolation Forest

**Why Isolation Forest?**

- **Unsupervised:** No labeled dataset with "Fraud" flags exists — the model discovers fraud on its own
- **Assumption:** Fraudulent data points are *few and different*
- **Mechanism:** The algorithm randomly selects a feature and splits the data:
  - Normal points are clustered together and require **many splits** to be isolated
  - Anomalies (Fraud) are far from the crowd and are isolated **very quickly** (few splits)
