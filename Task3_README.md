#  Task 3: Heart Disease Prediction
---
##  Objective
Build a **binary classification model** that predicts whether a patient is at risk of heart disease based on clinical health measurements. Early prediction enables timely medical intervention and can save lives.
---
##  Dataset
- **Name:** Heart Disease UCI Dataset
- **Source:** [Kaggle — Heart Disease Dataset](https://www.kaggle.com/datasets/johnsmith88/heart-disease-dataset)
- **File:** `heart.csv`
- **Size:** 303 patients × 14 columns (13 features + 1 target)
- **Target:** `target` → 1 = Heart Disease Present, 0 = No Heart Disease
### Feature Descriptions
| Feature | Description |
|---|---|
| `age` | Age of the patient (years) |
| `sex` | Sex (1 = Male, 0 = Female) |
| `cp` | Chest pain type (0–3) |
| `trestbps` | Resting blood pressure (mm Hg) |
| `chol` | Serum cholesterol (mg/dl) |
| `fbs` | Fasting blood sugar > 120 mg/dl (1=True, 0=False) |
| `restecg` | Resting ECG results (0–2) |
| `thalach` | Maximum heart rate achieved |
| `exang` | Exercise-induced angina (1=Yes, 0=No) |
| `oldpeak` | ST depression induced by exercise |
| `slope` | Slope of peak exercise ST segment (0–2) |
| `ca` | Number of major vessels colored by fluoroscopy (0–3) |
| `thal` | Thalassemia type (0=Normal, 1=Fixed, 2=Reversible defect) |
| `target` |  Heart Disease (1=Present, 0=Absent) |
---
##  Libraries Used
| Library | Purpose |
|---|---|
| `pandas` | Data loading, cleaning, manipulation |
| `numpy` | Numerical operations |
| `matplotlib` | Plotting charts |
| `seaborn` | Statistical visualizations |
| `scikit-learn` | Model training, scaling, and evaluation |
---
##  Data Cleaning Steps
- Checked for and handled **missing values** (filled with column medians if present)
- Removed **duplicate rows** if any found
- Verified class balance of the target variable
---
##  EDA Visualizations Produced
1. **Target Class Distribution** — Bar chart + Pie chart
2. **Age Distribution by Disease Status** — Histogram with KDE
3. **Key Feature Box Plots** — Age, BP, Cholesterol, Max Heart Rate, ST Depression
4. **Categorical Features vs Target** — Grouped bar charts
5. **Correlation Heatmap** — Feature relationships at a glance
---
##  Models Applied
### 1. Logistic Regression
A classic linear classification algorithm ideal for binary outcomes. Outputs a probability score for each patient. Requires feature scaling.
### 2. Decision Tree Classifier
A non-linear tree-based model that splits patients based on feature thresholds. Highly interpretable — decision rules can be visualized directly.
---
##  Evaluation Metrics
| Metric | Description |
|---|---|
| **Accuracy** | % of correct predictions overall |
| **Confusion Matrix** | Breakdown of TP, TN, FP, FN |
| **ROC-AUC Score** | Area under the ROC curve — threshold-independent performance |
| **Classification Report** | Precision, Recall, F1-score per class |
---
##  Key Results & Findings
| Metric | Logistic Regression | Decision Tree |
|---|---|---|
| Accuracy | ~85%+ | ~80%+ |
| ROC-AUC | **higher ** | lower |
- **Logistic Regression outperforms Decision Tree** on this medical dataset — linear boundaries are sufficient
- **ROC-AUC is prioritized over Accuracy** for medical problems — accounts for threshold sensitivity
- **False Negatives** (missed diagnoses) are the most dangerous error type in clinical settings
---
##  Most Important Features
| Rank | Feature | Reason |
|---|---|---|
| 1 | `cp` (Chest Pain Type) | Strongest clinical predictor |
| 2 | `thalach` (Max Heart Rate) | Exercise tolerance indicator |
| 3 | `ca` (Major Vessels) | Direct measure of arterial blockage |
| 4 | `oldpeak` (ST Depression) | Reflects cardiac stress |
| 5 | `thal` (Thalassemia) | Blood disorder linked to heart disease |
---
##  Key Takeaways
1. **Chest pain type** is the single strongest predictor of heart disease
2. Logistic Regression is highly competitive on medical tabular data — interpretable and reliable
3. ROC-AUC is a better performance metric than accuracy for medical diagnosis
4. In clinical use, minimizing **False Negatives** (missed diseases) is critical, even at the cost of more False Positives
---
##  File Structure
```
Task3_Heart_Disease_Prediction.ipynb   ← Main Jupyter Notebook
heart.csv                              ← Dataset (download from Kaggle link above)
Task3_README.md                        ← This file
```
---
##  How to Run
```bash
# Step 1: Download dataset
# Go to: https://www.kaggle.com/datasets/johnsmith88/heart-disease-dataset
# Download heart.csv and place it in the same folder as the notebook
# Step 2: Install required libraries
pip install pandas numpy matplotlib seaborn scikit-learn
# Step 3: Launch the notebook
jupyter notebook Task3_Heart_Disease_Prediction.ipynb
```
---

