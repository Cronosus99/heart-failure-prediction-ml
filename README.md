# Heart Failure Prediction (Machine Learning Project)

**Author:** Kevin Danh  
**Program:** Master of Data Science – Bellevue University  
**Course:** DSC 630: Predictive Analytics  

## Project Summary

This project develops machine learning models to predict the risk of heart failure using clinical patient data. Early identification of high-risk patients can help support timely medical interventions and improve patient outcomes.

The dataset originates from research by Chicco & Jurman (2020) and contains clinical indicators with a binary target variable indicating whether a death event occurred during the follow-up period.

## Project Type
Predictive Machine Learning | Healthcare Analytics | Classification

## Key Objectives

- Predict the likelihood of heart failure mortality using patient clinical data
- Compare multiple machine learning models
- Identify the most influential clinical indicators contributing to patient risk

## Dataset

- Source: Kaggle – Heart Failure Clinical Records Dataset
- 299 patient records
- 13 clinical variables

Example features include:

- Age
- Serum creatinine
- Ejection fraction
- Creatinine phosphokinase
- Serum sodium
- Follow-up time

Target variable:

**DEATH_EVENT**
- 0 = Patient survived
- 1 = Patient death during follow-up

## Data Preparation

Several preprocessing steps were applied before modeling:

- Log transformation applied to skewed features
  - creatinine_phosphokinase
  - serum_creatinine

- StandardScaler applied to continuous variables

- Binary features kept as 0/1 for interpretability

- Stratified train/test split used to preserve class distribution

## Models Implemented

Three machine learning models were used for prediction.

### Logistic Regression
- Baseline classification model
- Used `class_weight='balanced'` to address class imbalance

### Random Forest
- Captures nonlinear relationships
- Handles feature interactions automatically
- Robust to noise and outliers

### Gradient Boosting
- Sequential ensemble model
- Known for strong predictive performance in healthcare datasets

## Model Evaluation

Because the dataset contains imbalanced classes, multiple evaluation metrics were used.

| Model | Accuracy | Recall (Deaths) | Precision (Deaths) | ROC-AUC |
|------|------|------|------|------|
| Logistic Regression | 0.85 | 0.79 | 0.75 | 0.917 |
| Random Forest | 0.88 | 0.79 | 0.83 | 0.936 |
| Gradient Boosting | 0.88 | 0.79 | 0.83 | 0.946 |

## Key Findings

- Gradient Boosting achieved the highest ROC-AUC score
- Random Forest provided the most balanced performance across metrics
- Logistic Regression served as a strong baseline model

## Important Predictive Features

Tree-based models identified the following key predictors:

- Follow-up time
- Serum creatinine
- Ejection fraction

These variables are strongly associated with heart failure severity.

## Real-World Impact

This project demonstrates how predictive analytics can assist healthcare providers in identifying high-risk heart failure patients earlier.

Potential applications include:

- Supporting clinical decision-making
- Identifying patients needing closer monitoring
- Prioritizing preventative care
- Improving early intervention strategies

This model is intended for predictive insight only and should not be used as a clinical diagnostic tool.

## Skills Demonstrated

**Data Science**
- Exploratory Data Analysis (EDA)
- Feature engineering
- Handling imbalanced datasets
- Model comparison and evaluation

**Machine Learning**
- Logistic Regression
- Random Forest
- Gradient Boosting
- Stratified sampling
- Classification metrics

**Tools & Technologies**
- Python
- Jupyter Notebook
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- GitHub

## Project Structure

Heart-Failure-Prediction/

data/  
    heart_failure_clinical_records_dataset.csv  

notebook/  
    heart_failure_analysis.ipynb  

presentation/  
    heart_failure_project_presentation.pptx  

paper/  
    heart_failure_analysis_report.pdf  

README.md  

## How to Run the Project

Clone the repository:

git clone https://github.com/yourusername/heart-failure-prediction.git

Install dependencies:

pip install pandas numpy scikit-learn matplotlib seaborn jupyter

Run Jupyter Notebook:

jupyter notebook

Open:

heart_failure_analysis.ipynb

## Future Improvements

Possible enhancements for this project include:

- Hyperparameter tuning with cross-validation
- Testing additional models such as XGBoost or LightGBM
- Adding SHAP explanations for interpretability
- Expanding the dataset with additional heart failure datasets

## References

Chicco, D., & Jurman, G. (2020). Machine learning can predict survival of patients with heart failure from serum creatinine and ejection fraction alone. BMC Medical Informatics and Decision Making.
"""