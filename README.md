# Equitable AI for Early Detection of Pediatric Type 2 Diabetes

This repository contains the full analytic pipeline for the study:

**“Equitable AI for Early Detection: A Fairness-Aware Machine Learning Model for Pediatric Type 2 Diabetes Risk Prediction in Underserved U.S. Populations Using Multi-Cycle NHANES Data.”**

The project develops and evaluates machine-learning screening models for pediatric dysglycemia using nationally representative NHANES data, with a specific focus on fairness across race/ethnicity, income, and sex.

---

## 📊 Data Source

- **Dataset:** National Health and Nutrition Examination Survey (NHANES)
- **Cycles:** 2013–2018 (H, I, J)
- **Population:** Pediatric participants
- **Modules Used:**
  - Demographics (DEMO)
  - Body Measures (BMX)
  - Blood Pressure (BPX)
  - Glycohemoglobin (GHB)
  - Plasma Glucose (GLU)
  - Diabetes Questionnaire (DIQ)
  - Diet Behavior (DBQ)
  - Physical Activity (PAQ)

NHANES data are publicly available from the CDC:
https://www.cdc.gov/nchs/nhanes/

---

## 🎯 Study Objective

To develop a **high-sensitivity early-risk screening model** for pediatric dysglycemia and to evaluate whether such models exhibit disparities across underserved populations. The study further examines whether **fairness-aware post-processing** can mitigate observed inequities.

---

## 🧠 Methods Overview

- **Primary Outcome:**  
  HbA1c-defined dysglycemia (HbA1c ≥ 5.7%)

- **Models Evaluated:**
  - Logistic Regression (baseline, interpretable)
  - Random Forest (primary model)

- **Screening Strategy:**
  - Threshold selected to prioritize sensitivity (~88%) rather than default 0.5 classification

- **Fairness Metrics:**
  - Demographic Parity Difference
  - Equalized Odds Difference
  - Group-wise TPR and FPR

- **Mitigation Approach:**
  - Equalized Odds post-processing using Fairlearn
  - Evaluated across 5-fold cross-validation

---

## 📁 Repository Structure

```text
├── 01_NHANES_Fairness_PedsT2D.ipynb
│   └─ Data ingestion, cleaning, harmonization, and analytic dataset creation
│
├── 02_NHANES_Fairness_PedsT2D.ipynb
│   └─ Model training, performance evaluation, fairness analysis, and mitigation
│
├── 03_NHANES_Fairness_PedsT2D.ipynb
│   └─ Publication-ready tables, figures, and results assembly
│
└── README.md

