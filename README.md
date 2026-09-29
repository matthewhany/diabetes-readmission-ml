# 🏥 Diabetes 30-Day Hospital Readmission Prediction

An end-to-end Machine Learning pipeline designed to predict early hospital readmission (within 30 days) for diabetic patients using clinical encounter data. The system addresses extreme class imbalance, prevents data leakage using patient-level splitting, and is deployed via **FastAPI** and **Streamlit Cloud**.

---

## 📌 Project Overview & Problem Statement

* **Clinical Objective:** Identify high-risk diabetic patients likely to be readmitted within 30 days of discharge, allowing healthcare teams to prioritize post-discharge interventions and reduce avoidable readmissions.
* **Task Type:** Binary Classification.
  * `Class 1` (Positive): Readmitted in $< 30$ days (~11.4% of encounters).
  * `Class 0` (Negative): Readmitted in $> 30$ days or Not readmitted (~88.6%).
* **Core Challenge:** Severe class imbalance. Accuracy alone is clinically misleading, so optimization focuses on **Recall, Precision-Recall AUC (PR-AUC), and F1-Score**.

---

## 📊 Dataset Summary

* **Source:** Diabetes 130-US Hospitals Dataset (1999–2008).
* **Volume:** 101,766 hospital encounters across 50 initial features.
* **Feature Categories:**
  * **Demographics:** Age group, gender, race.
  * **Encounter Details:** Admission type, source, discharge disposition, time in hospital.
  * **Clinical Measures:** Lab procedures, clinical procedures, medications count, number of diagnoses.
  * **Diabetic Management:** 23 specific diabetes medications, dosage adjustments, and treatment changes.
  * **Historical Utilization:** Previous inpatient, outpatient, and emergency visits.

---

## ⚙️ ML Pipeline & Methodology
محادثة مع Gemini

عايز ارفعه لاكتبايه

لرفع مشروع توقع إعادة دخول مرضى السكري إلى المستشفى (Diabetes Hospital Readmission) على حساب GitHub الخاص بك من الشاشة الموضحة في الصورة، اتبع الخطوات التالية:
أولاً: ملء بيانات صفحة GitHub (المعروضة في الصورة)

    Repository name (اسم المستودع):

        اكتب اسماً معبراً، مثل:
        Plaintext

        diabetes-readmission-ml

    Description (الوصف - اختياري):

        اكتب وصفاً مختصراً للمشروع، مثل:
        Plaintext

        End-to-end ML pipeline for predicting 30-day diabetes hospital readmission, deployed with FastAPI and Streamlit.

    Choose visibility:

        اختر Public إذا أردت إتاحته للجميع واستخدامه في معرض أعمالك (Portfolio).

    تنبيه هام جداً في الإعدادات المتبقية:

        لا تقم بتفعيل Add README.

        لا تقم بإضافة .gitignore أو License من هذه الصفحة، لأن ملفات المشروع المحلية لديك تحتوي بالفعل على هذه الملفات، وتفعيلها هنا قد يُنشئ تعارضاً (Conflict) أثناء الرفع.   
        ZIP

    اضغط على الزر الأخضر في الأسفل: Create repository.

ثانياً: رفع الملفات عبر الـ Terminal في VS Code

افتح مشروعك في برنامج VS Code، ثم افتح الـ Terminal (Ctrl + ~) وتأكد أنك داخل مجلد المشروع الرئيسي، ثم نفذ الأوامر التالية بالترتيب:   
PPTX
Bash

# 1. تهيئة مستودع Git محلي
git init

# 2. إضافة جميع ملفات المشروع
git add .

# 3. حفظ التغييرات (Commit)
git commit -m "Initial commit: Complete diabetes readmission ML pipeline"

# 4. تعيين الفرع الأساسي إلى main
git branch -M main

# 5. ربط المستودع المحلي بمستودع GitHub (استبدل الرابط برابط المستودع بعد إنشائه)
git remote add origin https://github.com/matthewhany/diabetes-readmission-ml.git

# 6. رفع الملفات إلى GitHub
git push -u origin main

    ملاحظة حول الملفات الكبيرة:
    يضع GitHub حداً أقصى للملف الواحد قدره 100 ميجابايت. تأكد أن ملف البيانات diabetic_data.csv وملف النموذج final_readmission_ensemble.joblib يقل حجم كلٍ منهما عن 100 ميجابايت، وإذا تجاوز أحدهما ذلك الحد يمكنك إدراجه ضمن ملف .gitignore أو رفعه باستخدام Git LFS.   
    IPYNB+ 2

عايز اضيف اعمليREADME.md علي مشروع دا

إليك نموذج احترافي وشامل لملف README.md مصمم خصيصاً لمشروعك، ومبني على جميع تفاصيل المعالجة، النماذج، ومقاييس الأداء الموجودة في العرض التقديمي وكود المشروع. يمكنك نسخه ولصقه مباشرة داخل ملف README.md في المستودع:
Markdown

# 🏥 Diabetes 30-Day Hospital Readmission Prediction

An end-to-end Machine Learning pipeline designed to predict early hospital readmission (within 30 days) for diabetic patients using clinical encounter data. The system addresses extreme class imbalance, prevents data leakage using patient-level splitting, and is deployed via **FastAPI** and **Streamlit Cloud**.

---

## 📌 Project Overview & Problem Statement

* **Clinical Objective:** Identify high-risk diabetic patients likely to be readmitted within 30 days of discharge, allowing healthcare teams to prioritize post-discharge interventions and reduce avoidable readmissions.
* **Task Type:** Binary Classification.
  * `Class 1` (Positive): Readmitted in $< 30$ days (~11.4% of encounters).
  * `Class 0` (Negative): Readmitted in $> 30$ days or Not readmitted (~88.6%).
* **Core Challenge:** Severe class imbalance. Accuracy alone is clinically misleading, so optimization focuses on **Recall, Precision-Recall AUC (PR-AUC), and F1-Score**.

---

## 📊 Dataset Summary

* **Source:** Diabetes 130-US Hospitals Dataset (1999–2008).
* **Volume:** 101,766 hospital encounters across 50 initial features.
* **Feature Categories:**
  * **Demographics:** Age group, gender, race.
  * **Encounter Details:** Admission type, source, discharge disposition, time in hospital.
  * **Clinical Measures:** Lab procedures, clinical procedures, medications count, number of diagnoses.
  * **Diabetic Management:** 23 specific diabetes medications, dosage adjustments, and treatment changes.
  * **Historical Utilization:** Previous inpatient, outpatient, and emergency visits.

---

## ⚙️ ML Pipeline & Methodology

Raw Encounter Data ➡️ Cleaning & Exclusions ➡️ Patient-Level Split ➡️ Feature Engineering
➡️ Preprocessing (One-Hot / Scaler) ➡️ Ensemble Modeling ➡️ Threshold Tuning ➡️ Deployment


### 1. Data Cleaning & Integrity
* Converted `?` missing markers into standard null representations.
* Dropped `weight` due to extreme missingness (>96%).
* Excluded encounters where discharge disposition was expired (death) or hospice care, as these patients cannot be readmitted.
* Evaluated outliers with clinical domain awareness (e.g., high past hospitalizations were kept as genuine risk indicators).

### 2. Leakage-Free Splitting Strategy
* **Patient-Level Split (`GroupShuffleSplit` / `StratifiedGroupKFold`):** Multiple encounters belonging to the same `patient_nbr` were strictly contained within the same fold to prevent cross-set identity leakage.
* **Validation First, Test Last:** Hyperparameters, imbalance strategies, and decision thresholds were selected on validation data only. The test set remained untouched until final evaluation.

### 3. Feature Engineering
Engineered utilization and intensity ratios to strengthen predictive signals:
* `total_previous_visits = outpatient + emergency + inpatient`
* `hospital_utilization = emergency + inpatient`
* `total_clinical_activity = labs + procedures + medications`
* `medications_per_day`, `labs_per_day`, `procedures_per_day`
* `diagnosis_burden = diagnoses / time_in_hospital`
* Interaction flags for previous inpatient, emergency, and outpatient history.

### 4. Model Selection & Optimization
* Tested baselines: Logistic Regression, Random Forest, and XGBoost.
* Experimented with imbalance handling: Weighted loss (`scale_pos_weight`), balanced weights in LightGBM, and SMOTE variants. (Full/partial SMOTE did not improve PR-AUC over probability tuning).
* **Final Model Architecture:** Weighted probability average of:
  * **60% Tuned LightGBM** + **40% XGBoost** (with engineered features).
* **Decision Threshold:** Shifted from default $0.50$ to **$0.13$** (optimized on validation PR-curve) to prioritize high recall for early detection.

---

## 📈 Evaluation Results (Untouched Test Set)

The final weighted ensemble achieved stable generalization on the unseen test set:

| Metric | Score | Clinical Context |
| :--- | :---: | :--- |
| **Recall (Class 1)** | **49.86%** | Successfully captures ~50% of all actual early readmissions. |
| **Precision (Class 1)**| **19.68%** | Expected clinical trade-off due to aggressive screening threshold. |
| **F1-Score (Class 1)** | **0.2822** | Robust trade-off on imbalanced class. |
| **ROC-AUC** | **0.6768** | Solid discrimination capability across patient populations. |
| **PR-AUC** | **0.2390** | Significant lift over the baseline random rate (~0.114). |
| **Accuracy** | **71.61%** | Overall correct encounter classification. |

### Test Set Confusion Matrix
* **True Negatives:** 13,075
* **False Positives:** 4,511 (extra alerts for precautionary review)
* **False Negatives:** 1,111
* **True Positives:** 1,105

---

## 🚀 Deployment & Demo

The production pipeline is packaged as a reusable bundle (`final_readmission_ensemble.joblib`) containing the tuned estimators, categorical encoders, scalers, and decision threshold.

* **FastAPI Backend (`api.py`):** Exposes a high-performance RESTful `/predict` endpoint returning binary prediction, readmission probability, and individual model contributions.
* **Streamlit UI (`app.py`):** Interactive web application enabling clinicians to input patient parameters and view risk assessments in real-time.

---

## 📁 Repository Structure

```text
├── api.py                                 # FastAPI application serving REST endpoints
├── app.py                                 # Streamlit user interface
├── inference.py                           # Core inference and preprocessing pipeline
├── final_readmission_ensemble.joblib      # Serialized models, scalers, and pipeline
├── hospital_readmission_documented 3.ipynb# Complete analysis, modeling & evaluation notebook
├── IDS_mapping.csv                        # Admission and discharge code mappings
├── requirements.txt                       # Project dependencies
├── .gitignore                             # Git ignore rules
└── README.md                              # Project documentation

🛠️ Local Setup & Installation
1. Clone the repository
Bash

git clone [https://github.com/matthewhany/diabetes-readmission-ml.git](https://github.com/matthewhany/diabetes-readmission-ml.git)
cd diabetes-readmission-ml

2. Create and activate a virtual environment
Bash

# Windows
python -m venv .venv
.venv\Scripts\activate

# Linux / macOS
python3 -m venv .venv
source .venv/bin/activate

3. Install dependencies
Bash

pip install --upgrade pip
pip install -r requirements.txt

4. Run the REST API (FastAPI)
Bash

uvicorn api:app --reload --port 8000

    Interactive Swagger Docs: http://127.0.0.1:8000/docs

5. Run the Web Interface (Streamlit)
Bash

streamlit run app.py

⚠️ Clinical Disclaimer

This project is developed for educational and experimental machine learning research. It is not a certified medical diagnostic device and should not replace professional clinical judgment.


---

### خطوات إضافته إلى مشروعك في VS Code:
1. في متصفح الملفات داخل **VS Code**، افتح ملف `README.md` الموجود لديك.
2. استبدل محتواه بالنص أعلاه (أو اضغط `Ctrl + A` ثم الصق النص الجديد).
3. احفظ الملف (`Ctrl + S`).
4. ارفع التحديث إلى GitHub بكتابة الأوامر التالية في الـ Terminal:
   ```bash
   git add README.md
   git commit -m "docs: add comprehensive project README"
   git push origin main

اكنب جوهREADME.md

إليك المحتوى الكامل والجاهز للنسخ لوضعه داخل ملف README.md مباشرةً، منسقاً بشكل احترافي وجاهز للعرض على GitHub:   
PPTX
Markdown

# 🏥 Diabetes 30-Day Hospital Readmission Prediction

An end-to-end Machine Learning pipeline designed to predict early hospital readmission (within 30 days) for diabetic patients using clinical encounter data. The system addresses extreme class imbalance, prevents data leakage using patient-level splitting, and is deployed via **FastAPI** and **Streamlit Cloud**.

---

## 📌 Project Overview & Problem Statement

* **Clinical Objective:** Identify high-risk diabetic patients likely to be readmitted within 30 days of discharge, allowing healthcare teams to prioritize post-discharge interventions and reduce avoidable readmissions.
* **Task Type:** Binary Classification.
  * `Class 1` (Positive): Readmitted in $< 30$ days (~11.4% of encounters).
  * `Class 0` (Negative): Readmitted in $> 30$ days or Not readmitted (~88.6%).
* **Core Challenge:** Severe class imbalance. Accuracy alone is clinically misleading, so optimization focuses on **Recall, Precision-Recall AUC (PR-AUC), and F1-Score**.

---

## 📊 Dataset Summary

* **Source:** Diabetes 130-US Hospitals Dataset (1999–2008).
* **Volume:** 101,766 hospital encounters across 50 initial features.
* **Feature Categories:**
  * **Demographics:** Age group, gender, race.
  * **Encounter Details:** Admission type, source, discharge disposition, time in hospital.
  * **Clinical Measures:** Lab procedures, clinical procedures, medications count, number of diagnoses.
  * **Diabetic Management:** 23 specific diabetes medications, dosage adjustments, and treatment changes.
  * **Historical Utilization:** Previous inpatient, outpatient, and emergency visits.

---

## ⚙️ ML Pipeline & Methodology

Raw Encounter Data ➡️ Cleaning & Exclusions ➡️ Patient-Level Split ➡️ Feature Engineering
➡️ Preprocessing (One-Hot / Scaler) ➡️ Ensemble Modeling ➡️ Threshold Tuning ➡️ Deployment


### 1. Data Cleaning & Integrity
* Converted `?` missing markers into standard null representations.
* Dropped `weight` due to extreme missingness (>96%).
* Excluded encounters where discharge disposition was expired (death) or hospice care, as these patients cannot be readmitted.
* Evaluated outliers with clinical domain awareness (e.g., high past hospitalizations were kept as genuine risk indicators).

### 2. Leakage-Free Splitting Strategy
* **Patient-Level Split (`GroupShuffleSplit` / `StratifiedGroupKFold`):** Multiple encounters belonging to the same `patient_nbr` were strictly contained within the same fold to prevent cross-set identity leakage.
* **Validation First, Test Last:** Hyperparameters, imbalance strategies, and decision thresholds were selected on validation data only. The test set remained untouched until final evaluation.

### 3. Feature Engineering
Engineered utilization and intensity ratios to strengthen predictive signals:
* `total_previous_visits = outpatient + emergency + inpatient`
* `hospital_utilization = emergency + inpatient`
* `total_clinical_activity = labs + procedures + medications`
* `medications_per_day`, `labs_per_day`, `procedures_per_day`
* `diagnosis_burden = diagnoses / time_in_hospital`
* Interaction flags for previous inpatient, emergency, and outpatient history.

### 4. Model Selection & Optimization
* Tested baselines: Logistic Regression, Random Forest, and XGBoost.
* Experimented with imbalance handling: Weighted loss (`scale_pos_weight`), balanced weights in LightGBM, and SMOTE variants.
* **Final Model Architecture:** Weighted probability average of:
  * **60% Tuned LightGBM** + **40% XGBoost** (with engineered features).
* **Decision Threshold:** Shifted from default $0.50$ to **$0.13$** (optimized on validation PR-curve) to prioritize high recall for early detection.

---

## 📈 Evaluation Results (Untouched Test Set)

The final weighted ensemble achieved stable generalization on the unseen test set:

| Metric | Score | Clinical Context |
| :--- | :---: | :--- |
| **Recall (Class 1)** | **49.86%** | Successfully captures ~50% of all actual early readmissions. |
| **Precision (Class 1)**| **19.68%** | Expected clinical trade-off due to aggressive screening threshold. |
| **F1-Score (Class 1)** | **0.2822** | Robust trade-off on imbalanced class. |
| **ROC-AUC** | **0.6768** | Solid discrimination capability across patient populations. |
| **PR-AUC** | **0.2390** | Significant lift over the baseline random rate (~0.114). |
| **Accuracy** | **71.61%** | Overall correct encounter classification. |

### Test Set Confusion Matrix
* **True Negatives:** 13,075
* **False Positives:** 4,511 (extra alerts for precautionary review)
* **False Negatives:** 1,111
* **True Positives:** 1,105

---

## 🚀 Deployment & Demo

The production pipeline is packaged as a reusable bundle (`final_readmission_ensemble.joblib`) containing the tuned estimators, categorical encoders, scalers, and decision threshold.

* **FastAPI Backend (`api.py`):** Exposes a high-performance RESTful `/predict` endpoint returning binary prediction, readmission probability, and individual model contributions.
* **Streamlit UI (`app.py`):** Interactive web application enabling clinicians to input patient parameters and view risk assessments in real-time.

---

## 📁 Repository Structure

```text
├── api.py                                 # FastAPI application serving REST endpoints
├── app.py                                 # Streamlit user interface
├── inference.py                           # Core inference and preprocessing pipeline
├── final_readmission_ensemble.joblib      # Serialized models, scalers, and pipeline
├── hospital_readmission_documented 3.ipynb# Complete analysis, modeling & evaluation notebook
├── IDS_mapping.csv                        # Admission and discharge code mappings
├── requirements.txt                       # Project dependencies
├── .gitignore                             # Git ignore rules
└── README.md                              # Project documentation

