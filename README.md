# 📊 Global Advertising Performance Intelligence

<p align="left">
  <img src="https://img.shields.io/badge/PYTHON-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/PANDAS-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas">
  <img src="https://img.shields.io/badge/NUMPY-013243?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy">
  <img src="https://img.shields.io/badge/MATPLOTLIB-11557C?style=for-the-badge" alt="Matplotlib">
  <img src="https://img.shields.io/badge/SEABORN-4C72B0?style=for-the-badge" alt="Seaborn">
  <img src="https://img.shields.io/badge/SCIKIT--LEARN-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white" alt="Scikit-learn">
  <img src="https://img.shields.io/badge/JUPYTER-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter">
</p>

An end-to-end machine learning project that analyses advertising campaign data to explore campaign performance, identify patterns associated with campaign success, and predict whether a campaign will succeed using supervised classification models.

## 📌 Project Overview

The **Global Advertising Performance Intelligence** project investigates how advertising campaign characteristics relate to campaign success.

Using Python, data analysis, and machine learning, the project performs exploratory data analysis, preprocesses numerical and categorical features, compares classification algorithms, tunes model hyperparameters, and evaluates a selected model on an unseen test set.

## 🎯 Business Problem

Advertising teams allocate budgets across different platforms, campaign strategies, objectives, industries, and audience segments. Understanding which characteristics are associated with successful campaigns can help teams evaluate campaign plans more systematically.

This project investigates:

> Can campaign characteristics be used to predict campaign success, and which features contribute most to the model's predictions?

The goal is to evaluate the predictive value of campaign data and derive insights that may support data-informed advertising decisions.

## 🚀 Objectives

- Explore advertising campaign data and identify meaningful patterns.
- Check data quality, missing values, and duplicate records.
- Analyse campaign success rates and feature relationships.
- Prepare numerical and categorical features for machine learning.
- Compare multiple classification algorithms.
- Use stratified cross-validation and hyperparameter tuning.
- Evaluate the selected model on an untouched test set.
- Interpret important features using permutation importance.

## 🛠️ Tools and Technologies

- **Python:** Programming and analysis
- **Jupyter Notebook:** Project development
- **Pandas and NumPy:** Data manipulation and numerical computing
- **Matplotlib and Seaborn:** Data visualization
- **Scikit-learn:** Preprocessing, classification, cross-validation, hyperparameter tuning, and evaluation
- **Joblib:** Saving the trained model pipeline

## 📂 Dataset

The project uses a campaign dataset containing 10,000 records and 17 columns.

| Item | Detail |
|---|---|
| Dataset file | `marketing_campaign_success_10000_70_30.csv` |
| Total records | 10,000 |
| Total columns | 17 |
| Input features | 16 |
| Target variable | `Campaign_Success` |
| Successful campaigns (`Yes`) | 7,000 (70%) |
| Unsuccessful campaigns (`No`) | 3,000 (30%) |
| Duplicate records | 0 |
| Dataset source | Appears to be synthetic; an external source is not established in the notebook |

### ⚖️ Target Distribution and Baseline

The target variable contains 70% successful campaigns and 30% unsuccessful campaigns.

A majority-class baseline that always predicts `Yes` therefore achieves approximately 70% accuracy. The project compares this baseline against the trained models to assess whether they provide more useful predictions.

## 🔄 Project Workflow

1. **Data Loading:** Load the campaign CSV dataset.
2. **Data Inspection:** Examine dimensions, data types, missing values, and duplicates.
3. **Exploratory Data Analysis:** Visualize feature distributions, correlations, and campaign success rates.
4. **Feature Preparation:** Separate the 16 input features from the target variable.
5. **Train-Test Split:** Divide the data into 80% training and 20% testing sets using stratified sampling.
6. **Preprocessing:** Standardize numerical features and one-hot encode categorical features within a scikit-learn pipeline.
7. **Baseline Evaluation:** Establish a majority-class reference model.
8. **Model Training:** Train and compare four classification algorithms.
9. **Cross-Validation and Tuning:** Use five-fold stratified cross-validation and grid search on the training data.
10. **Final Evaluation:** Select the model using cross-validated ROC-AUC and evaluate it on the untouched test set.
11. **Feature Importance:** Use permutation importance to identify features that contribute to predictive performance.
12. **Prediction Demonstration:** Test the selected model with hypothetical campaign scenarios.

## 🤖 Machine Learning Models

The notebook implements four classification algorithms:

- Logistic Regression
- Decision Tree Classifier
- Random Forest Classifier
- Gradient Boosting Classifier

### 📈 Model Evaluation

The project evaluates classification performance using:

- Accuracy
- Precision for the `Yes` class
- Recall for the `Yes` class
- F1-score for the `Yes` class
- Confusion matrices
- ROC-AUC
- Five-fold cross-validation scores

Hyperparameter tuning uses cross-validated ROC-AUC on the training data. The selected model is subsequently evaluated on the test set.

## 🧠 Feature Importance

Permutation importance is calculated using ROC-AUC to estimate how much predictive performance decreases when an individual input feature is shuffled.

This analysis helps identify which campaign characteristics the selected model relies on most heavily. Importance rankings and business interpretations should be reported using the actual output generated by the notebook.

## 💡 Business Insights

The notebook explores the relationships between campaign success and features such as:

- Past campaign score
- Campaign strategy and campaign type
- Campaign objective
- AI and mobile measurement platform (MMP) usage
- Platform, agency, industry, country, and campaign duration

These findings represent patterns within the dataset, not proof that changing a feature will cause a campaign to succeed.

## 💾 Model Export

The notebook saves the selected preprocessing-and-model pipeline to:

`campaign_success_model.joblib`

The saved pipeline can be reused for predictions, provided the input data contains the expected feature columns and compatible values.

## ⚠️ Limitations

- The dataset appears to be synthetic, so the results may not generalize to real advertising campaigns.
- Feature importance identifies predictive associations, not causal effects.
- Model performance should be validated on independent, representative data before being used for real budget decisions.
- Hypothetical campaign predictions are demonstrations and are not guarantees of future performance.

## ▶️ How to Run the Project

1. Clone the repository:

   ```bash
   git clone https://github.com/ranjeethanaganur/global-advertising-performance-intelligence.git
   cd global-advertising-performance-intelligence
   ```

2. Install the dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Place `marketing_campaign_success_10000_70_30.csv` in the same directory as the notebook, or update `DATA_PATH` in the notebook.

4. Launch Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

5. Open the notebook and run the cells in order.

### 📦 Dependencies

Suggested `requirements.txt`:

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
joblib
jupyter
```

## 🗂️ Repository Structure

```text
global-advertising-performance-intelligence/
│
├── Global_Advertising_Performance_Intelligence.ipynb
├── README.md
├── requirements.txt
├── marketing_campaign_success_10000_70_30.csv
└── campaign_success_model.joblib
```

The CSV and saved model should be included only if you intend to distribute them and their sharing is permitted. The model file is generated when the relevant notebook cell runs.

## 🧠 Skills Demonstrated

- Python programming and data analysis
- Data cleaning and exploratory data analysis
- Data visualization
- Numerical and categorical preprocessing
- Supervised machine learning
- Stratified train-test splitting
- Cross-validation and hyperparameter tuning
- Classification metrics and model comparison
- Permutation feature importance
- Model pipeline export and prediction

## 🔮 Future Improvements

- Validate the model on real-world campaign data.
- Explore decision-threshold tuning for different campaign objectives.
- Add model-explanation visualizations.
- Build an interactive dashboard for campaign analysis.
- Deploy the trained pipeline in a simple prediction application.

## 📝 Conclusion

This project demonstrates an end-to-end supervised machine learning workflow for advertising campaign success prediction. It combines exploratory analysis, feature preprocessing, model comparison, cross-validation, hyperparameter tuning, test-set evaluation, and permutation importance.

The project aims to demonstrate how campaign data can be analysed to identify predictive patterns and support more structured advertising decisions.

## 👩‍💻 Author

**Ranjeetha Naganur**

[GitHub](https://github.com/ranjeetha19) · [LinkedIn](https://linkedin.com/in/ranjeethanaganur) · [Email](mailto:ranjeethanaganur@gmail.com)

---

**Project Category:** Data Analytics and Machine Learning

**Primary Tools:** Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn

