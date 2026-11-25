# Customer Transaction Prediction

## Project Overview

Customer Transaction Prediction is a Machine Learning project developed to predict whether a banking customer will perform a future transaction. The project uses historical customer data and classification algorithms to identify potential future transactions and support data-driven banking decisions.

The notebook covers data analysis, preprocessing, model development, performance evaluation, and prediction generation.

## Problem Statement

The objective is to build a predictive model that identifies whether a customer is likely to make a transaction in the future, irrespective of the transaction amount.

- **Target = 0:** Customer is not expected to make a future transaction.
- **Target = 1:** Customer is expected to make a future transaction.

## Dataset Description

The dataset contains:

- `ID_code` – Unique customer identifier.
- `var_0` to `var_199` – 200 anonymized numerical features.
- `target` – Binary target variable indicating future transaction status.

**Note:** The feature names are anonymized, so individual business meanings cannot be directly interpreted.

## Technologies Used

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Joblib

## Project Workflow

### Task 1: Data Analysis

- Loaded and explored the dataset.
- Checked dataset dimensions, data types, and missing values.
- Identified duplicate records and unique customer IDs.
- Generated descriptive statistical summaries.
- Analyzed target distribution and class imbalance.
- Visualized selected numerical features.
- Examined correlations between numerical variables.

### Task 2: Machine Learning Model Development

**1. Data Preprocessing**
- Separated input features and target variable.
- Removed the customer ID from model training.
- Handled infinite and missing values.
- Applied median imputation.
- Used feature scaling for Logistic Regression.
- Split the dataset into training and testing sets using stratified sampling.

**2. Models Implemented**

| Algorithm | Purpose |
|---|---|
| Logistic Regression | Baseline classification |
| Random Forest | Ensemble-based classification |
| Extra Trees | Tree-based ensemble classification |

**3. Model Evaluation**

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC
- PR-AUC

The best-performing model was selected based on ROC-AUC and further evaluated using a classification report, confusion matrix, and ROC curve.

## Model Saving

The trained model is saved as:

`customer_transaction_model.pkl`

This file can be reused for predictions without training the model again, provided the required preprocessing pipeline and input features are maintained.

## Prediction Output

The notebook generates customer transaction predictions containing:

- `ID_code`
- `Transaction_Probability`
- `Predicted_Target`
- `Actual_Target` (for validation results)

The prediction results are exported as:

`future_customer_predictions.csv`

**Note:** Predictions generated from the validation dataset are used for model evaluation. Predictions for genuinely unseen customers require the original `test.csv` file containing the same input features used during training.

## Challenges Faced

- **Anonymized Features:** Used statistical analysis and correlation techniques to understand feature patterns.
- **Missing Values:** Applied median imputation to handle missing numerical data.
- **Class Imbalance:** Used stratified sampling and class-weighted models.
- **Feature Scaling:** Applied StandardScaler for Logistic Regression.
- **Model Selection:** Compared multiple algorithms using classification evaluation metrics.
- **Feature Interpretation:** Business-level interpretation was limited because feature names were anonymized.

## Project Conclusion

This project demonstrates the application of Machine Learning techniques to predict future banking customer transactions. Logistic Regression, Random Forest, and Extra Trees were implemented and compared using multiple evaluation metrics. The best-performing model was selected based on ROC-AUC, providing a foundation for identifying customers with a higher likelihood of future transactions.

## How to Run the Project

1. Clone the repository:

   ```bash
   git clone https://github.com/YOUR_USERNAME/Customer-Transaction-Prediction.git
   ```

2. Navigate to the project folder:

   ```bash
   cd Customer-Transaction-Prediction
   ```

3. Install Dependencies:

   ```bash
   pip install -r requirements.txt
   ```

4. Open Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

5. Open the project notebook and run the cells sequentially.

## Repository Structure

```text
Customer-Transaction-Prediction/
│
├── Customer_Transaction_Prediction.ipynb
├── train.csv
├── test.csv                  # If available
├── customer_transaction_model.pkl
├── future_customer_predictions.csv
├── requirements.txt
├── .gitignore
└── README.md
```

*The repository structure may vary depending on the files included in the final submission.*

## Author

**Naveen Gnanavel**

- GitHub: https://github.com/Naveen0625
- LinkedIn: https://www.linkedin.com/in/naveen-gnanavel-a570a1301/

---

**Project Domain:** Banking  
**Project Type:** Machine Learning – Binary Classification  
**Primary Objective:** Future Customer Transaction Prediction
