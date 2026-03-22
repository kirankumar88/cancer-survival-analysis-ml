# Breast Cancer Survival Analysis and Risk Prediction using Survival Analysis and Machine Learning

## Overview
This project focuses on survival analysis and survival risk prediction for breast cancer patients using clinical and protein biomarker data. The study integrates traditional survival analysis methods with machine learning models to understand survival patterns, identify risk factors, and predict patient survival risk. The workflow combines Kaplan–Meier survival analysis, log-rank tests, Cox proportional hazards regression, hazard ratio forest plots, machine learning model comparison, hyperparameter tuning, cross-validation, and model evaluation using ROC and Precision–Recall curves.

---

## Objectives
The main objectives of this project are:
- Perform survival analysis using Kaplan–Meier method
- Compare survival between tumor stages
- Identify risk factors using Cox proportional hazards model
- Visualize hazard ratios using forest plots
- Build machine learning models to predict survival risk
- Perform hyperparameter tuning and cross-validation
- Evaluate model performance using ROC and Precision–Recall curves
- Compare survival analysis methods with machine learning approaches

---

## Dataset
The dataset contains clinical and protein biomarker data for breast cancer patients. The dataset includes the following features:
- Age
- Gender
- Tumour Stage
- Histology
- ER status
- PR status
- HER2 status
- Surgery type
- Protein biomarkers (Protein1–Protein4)
- Date of Surgery
- Date of Last Visit
- Patient Status (Alive/Dead)
- Survival Time (calculated)

The dataset is imbalanced with more surviving patients than deceased patients.

---

## Methodology
### Data Preprocessing
- Handling missing values
- Converting date columns
- Calculating survival time
- Creating event variable
- Encoding categorical variables

### Survival Analysis
- Kaplan–Meier survival curve
- Survival probability estimation
- Survival comparison by tumor stage
- Log-rank test

### Cox Proportional Hazards Model
- Hazard ratio estimation
- Identification of risk factors
- Forest plot of hazard ratios
- Concordance index evaluation

### Machine Learning Models
The following machine learning models were trained and compared:
- Logistic Regression
- Random Forest
- Support Vector Machine (SVM)
- XGBoost

### Hyperparameter Tuning and Validation
- GridSearchCV for SVM
- Stratified cross-validation
- ROC-AUC used as tuning metric

### Model Evaluation
The models were evaluated using:
- Accuracy
- ROC AUC
- Precision
- Recall
- F1 Score
- PR AUC
- Confusion Matrix
- ROC Curve
- Precision–Recall Curve
- Learning Curve

---

## Results
### Survival Analysis
- Median survival ≈ 1455 days (~4 years)
- Survival probability decreases over time
- Higher tumor stage associated with lower survival probability

### Cox Model
- Tumor stage associated with increased risk
- Protein biomarkers showed small effects
- Concordance index ≈ 0.57

### Machine Learning Model Performance

| Model | Accuracy | ROC AUC | Recall (Dead) |
|------|---------|---------|--------------|
| Logistic Regression | 0.50 | 0.51 | 0.54 |
| Random Forest | 0.80 | 0.46 | 0.00 |
| SVM | **0.62** | **0.59** | **0.38** |
| XGBoost | 0.77 | 0.49 | 0.23 |

Final Model: **Hyperparameter Tuned Support Vector Machine**

### Final Model Performance
- Accuracy: 0.62
- ROC AUC: 0.59
- PR AUC: 0.25
- Cross-validation ROC AUC: ~0.56

---

## Repository Structure

breast-cancer-survival-analysis-ml/
│
├── data/
│ └── breast_cancer_survival.csv
│
├── notebooks/
│ └── cancer_survival_analysis.ipynb
│
├── figures/
│ ├── cox model_hazard ratios.png
│ ├── Kaplan-Meier Survival Curve.png
│ └── Kaplan-Meier_Survival_by_tumour_stage.png
│
├── README.md
├── requirements.txt
├── .gitignore
└── LICENSE



---

## Conclusion
This project demonstrates an integrated workflow combining survival analysis and machine learning for breast cancer survival modeling. Kaplan–Meier survival analysis and Cox regression provided meaningful clinical insights into survival patterns and risk factors, while machine learning models showed moderate predictive performance due to small dataset size and class imbalance. The study highlights the importance of survival analysis methods for clinical datasets and the potential of machine learning for survival risk prediction.

---

## Future Work
- Use larger datasets (e.g., TCGA)
- Include genomic or transcriptomic data
- Use survival machine learning models (Random Survival Forest, DeepSurv)
- Perform external validation
- Build survival risk score model

---

## Requirements
Install dependencies using:

pip install -r requirements.txt

Required libraries:
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- lifelines
- xgboost
- joblib