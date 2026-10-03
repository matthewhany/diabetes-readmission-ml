# 🏥 Diabetes 30-Day Hospital Readmission Prediction

An end-to-end Machine Learning pipeline designed to predict early hospital readmission (within 30 days) for diabetic patients using clinical encounter data. The system addresses severe class imbalance, uses patient-level splitting to reduce data leakage, and includes an interactive Streamlit web application.

---

## 📌 Project Overview & Problem Statement

* **Clinical Objective:** Predict whether a diabetic patient is likely to be readmitted to the hospital within 30 days of discharge.
* **Task Type:** Binary Classification.

  * **Class 1:** Readmitted within 30 days (~11.4% of encounters).
  * **Class 0:** Readmitted after 30 days or not readmitted (~88.6%).
* **Core Challenge:** Severe class imbalance. Therefore, model evaluation focuses on Recall, Precision, PR-AUC, and F1-Score rather than accuracy alone.

---

## 📊 Dataset Summary

* **Dataset:** Diabetes 130-US Hospitals Dataset
* **Period:** 1999–2008
* **Encounters:** 101,766
* **Initial Features:** 50

### Main Feature Categories

* **Demographics:** Age, gender, race
* **Encounter Details:** Admission type, admission source, discharge disposition, time in hospital
* **Clinical Measures:** Laboratory procedures, clinical procedures, medications, diagnoses
* **Diabetes Management:** Diabetes medications, dosage changes, treatment changes
* **Historical Utilization:** Previous inpatient, outpatient, and emergency visits

---

## ⚙️ ML Pipeline & Methodology

```text
Raw Data
   ↓
Data Cleaning & Missing Value Handling
   ↓
Patient-Level Data Splitting
   ↓
Feature Engineering
   ↓
Preprocessing
   ↓
Model Training
   ↓
Class Imbalance Handling
   ↓
Threshold Optimization
   ↓
Final Ensemble Model
   ↓
Deployment
```

### 1. Data Cleaning

* Converted `?` values into missing values.
* Removed the `weight` feature due to very high missingness.
* Excluded encounters where patients had expired or were receiving hospice care because they could not be readmitted.
* Reviewed outliers while considering their potential clinical meaning.

### 2. Leakage-Free Splitting

Patient-level splitting was used to prevent encounters belonging to the same patient from appearing across different datasets.

The workflow included:

* `GroupShuffleSplit`
* `StratifiedGroupKFold`
* Separate validation and test sets
* Final evaluation on an untouched test set

### 3. Feature Engineering

Additional features were created to capture healthcare utilization and clinical activity:

* `total_previous_visits`
* `hospital_utilization`
* `total_clinical_activity`
* `medications_per_day`
* `labs_per_day`
* `procedures_per_day`
* `diagnosis_burden`

Interaction features were also created from previous inpatient, emergency, and outpatient visits.

### 4. Model Selection & Optimization

Several machine learning approaches were evaluated, including:

* Logistic Regression
* Random Forest
* XGBoost
* LightGBM
* SMOTE-based approaches
* Class-weighted models

The final ensemble combines:

* **60% Tuned LightGBM**
* **40% XGBoost**

A decision threshold of **0.13** was selected using the validation Precision-Recall curve to increase sensitivity toward the positive class.

---

## 📈 Evaluation Results

The final model was evaluated on an unseen test set.

| Metric                  |      Score |
| ----------------------- | ---------: |
| **Recall (Class 1)**    | **49.86%** |
| **Precision (Class 1)** | **19.68%** |
| **F1-Score (Class 1)**  | **0.2822** |
| **ROC-AUC**             | **0.6768** |
| **PR-AUC**              | **0.2390** |
| **Accuracy**            | **71.61%** |

### Test Set Confusion Matrix

|                     | Predicted Negative | Predicted Positive |
| ------------------- | -----------------: | -----------------: |
| **Actual Negative** |             13,075 |              4,511 |
| **Actual Positive** |              1,111 |              1,105 |

---

## 🚀 Deployment & Demo

The project includes an interactive Streamlit application for testing the trained machine learning model.

### 🌐 Live Demo

👉 **[Open the Streamlit Web Application](https://diabetes-readmission-ml-ehkdw6rnzrjqcbfugsenjz.streamlit.app/)**

The application allows users to enter patient information and receive a predicted 30-day hospital readmission risk through an interactive web interface.

---

## 🖥️ Screenshots

The repository includes screenshots demonstrating the project interface and results.

---

## 📁 Repository Contents

```text
diabetes-readmission-ml/
│
├── README.md
├── hospital_readmission_documented 3.ipynb
├── diabetes_readmission_presentation.pptx
├── diabetes_readmission_presentation.zip
├── diabetes+130-us+hospitals+for+years+1999-2008.zip
│
├── Screenshot 2026-10-03 172344.png
├── Screenshot 2026-10-03 172429.png
├── Screenshot 2026-10-03 172459.png
└── Screenshot 2026-10-03 172513.png
```

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* LightGBM
* XGBoost
* Matplotlib
* Machine Learning
* Feature Engineering
* Streamlit
* Jupyter Notebook
* Git & GitHub

---

## 🎯 Key Machine Learning Concepts

This project demonstrates practical experience with:

* Binary Classification
* Imbalanced Classification
* Data Cleaning
* Exploratory Data Analysis
* Feature Engineering
* Patient-Level Data Splitting
* Cross-Validation
* Ensemble Learning
* Probability Threshold Optimization
* Model Evaluation
* Precision-Recall Analysis
* Machine Learning Deployment

---

## ⚠️ Clinical Disclaimer

This project is developed for educational and experimental machine learning purposes.

It is **not a certified medical diagnostic device** and should not be used as a substitute for professional medical judgment or clinical decision-making.
