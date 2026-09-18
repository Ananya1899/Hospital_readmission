# 🏥 Hospital Readmission Prediction

## 📌 Overview

This project focuses on predicting whether a patient is likely to be **readmitted to the hospital within 30 days** using Machine Learning.

The case study uses **Logistic Regression with L2 regularization** to perform binary classification based on patient-related information.

The model is evaluated using **ROC-AUC**, along with other classification metrics such as Accuracy, Precision, Recall, and F1-Score.

---

## 🎯 Objective

The main objective is to develop a machine learning model that can:

* Predict 30-day hospital readmission risk.
* Handle numerical and categorical patient information.
* Reduce overfitting using **L2 regularization**.
* Evaluate classification performance using **ROC-AUC**.
* Analyze the impact of different classification thresholds.
* Understand the clinical implications of false positives and false negatives.

---

## 📊 Dataset

The dataset contains patient hospital records and includes information related to:

* Patient demographics
* Medical conditions
* Diagnosis information
* Hospital visits
* Laboratory procedures
* Medications
* Previous admissions
* Other healthcare-related attributes

### Target Variable

The target variable used in this project is:

```text
readmitted_30_days
```

It represents whether the patient was readmitted within 30 days.

| Value | Meaning                       |
| ----- | ----------------------------- |
| `0`   | Not readmitted within 30 days |
| `1`   | Readmitted within 30 days     |

---

## 🧠 Machine Learning Approach

The project follows the following workflow:

```text
Patient Dataset
       ↓
Data Exploration
       ↓
Data Cleaning
       ↓
Feature Selection
       ↓
Train-Test Split
       ↓
Data Preprocessing
       ↓
Logistic Regression
       ↓
L2 Regularization
       ↓
Probability Prediction
       ↓
Model Evaluation
       ↓
ROC-AUC & Threshold Analysis
```

---

## ⚙️ Data Preprocessing

The dataset contains both numerical and categorical features.

### Numerical Features

Numerical features are processed using:

* Missing value imputation using the median
* Standardization using `StandardScaler`

### Categorical Features

Categorical features are processed using:

* Missing value imputation
* One-hot encoding using `OneHotEncoder`

The preprocessing is implemented using Scikit-learn's `Pipeline` and `ColumnTransformer`.

---

## 🤖 Model

### Logistic Regression

Logistic Regression is used because the problem is a **binary classification problem**.

The model predicts the probability that a patient will be readmitted within 30 days.

### L2 Regularization

L2 regularization is applied to reduce overfitting.

It penalizes large model coefficients and helps improve the model's generalization to unseen data.

The model uses:

```python
LogisticRegression(
    penalty="l2",
    C=1.0,
    max_iter=1000,
    solver="liblinear"
)
```

---

## 📈 Model Evaluation

The model is evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score
* ROC-AUC
* Confusion Matrix
* ROC Curve

### ROC-AUC

ROC-AUC measures the model's ability to distinguish between patients who are likely to be readmitted and those who are not.

A higher ROC-AUC generally indicates better discrimination between the two classes.

---

## 🎚️ Threshold Analysis

The default classification threshold is `0.5`.

The project evaluates multiple thresholds:

```text
0.30
0.40
0.50
0.60
0.70
```

For each threshold, Precision, Recall and F1-Score are calculated.

This demonstrates how changing the classification threshold affects the model's predictions.

---

## 🏥 Clinical Interpretation

### False Negative

A **false negative** occurs when:

> The model predicts that a patient will not be readmitted, but the patient is actually readmitted within 30 days.

False negatives can be clinically important because a high-risk patient may not receive additional monitoring or intervention.

### False Positive

A **false positive** occurs when:

> The model predicts that a patient will be readmitted, but the patient is actually not readmitted.

False positives can result in unnecessary follow-up, testing, or use of healthcare resources.

Therefore, the appropriate classification threshold depends on the clinical objective and the relative costs of different errors.

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Matplotlib
* Seaborn
* Google Colab
* Logistic Regression

---

## 📂 Project Structure

```text
Hospital-Readmission-Prediction/
│
├── Hospital_Readmission_Prediction.ipynb
└── README.md
```

---

## ▶️ How to Run

### 1. Open the Notebook

Open:

`Hospital_Readmission_Prediction.ipynb`

using Google Colab or Jupyter Notebook.

### 2. Upload the Dataset

When prompted by the notebook, upload the CSV dataset.

### 3. Run the Cells

Execute the notebook cells sequentially from top to bottom.

The notebook will:

1. Load the dataset.
2. Explore the data.
3. Preprocess the features.
4. Split the data into training and testing sets.
5. Train Logistic Regression with L2 regularization.
6. Generate predictions.
7. Calculate evaluation metrics.
8. Plot the confusion matrix.
9. Plot the ROC curve.
10. Perform threshold analysis.
11. Display feature coefficients.

---

## 📌 Results

The notebook generates the actual model performance metrics after execution.

The main metrics reported are:

| Metric    | Description                                            |
| --------- | ------------------------------------------------------ |
| Accuracy  | Overall proportion of correct predictions              |
| Precision | Proportion of predicted readmissions that were correct |
| Recall    | Proportion of actual readmissions detected             |
| F1-Score  | Balance between Precision and Recall                   |
| ROC-AUC   | Ability to distinguish between the two classes         |

**Note:** Results depend on the dataset and train-test split used when running the notebook.

---

## 🔮 Future Improvements

Possible improvements include:

* Hyperparameter tuning
* Cross-validation
* Feature selection
* Testing additional classification algorithms
* Calibration of predicted probabilities
* Cost-sensitive learning
* Evaluation on a larger and more diverse patient dataset

---

## 🎓 Case Study Information

**Course:** Machine Learning
**Case Study:** Hospital Readmission Prediction
**Model:** Logistic Regression
**Regularization:** L2
**Primary Evaluation Metric:** ROC-AUC
**Platform:** Google Colab
