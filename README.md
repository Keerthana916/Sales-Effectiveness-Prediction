# Sales Effectiveness Prediction

 A machine learning project focused on improving lead quality by predicting whether a sales lead is **High Potential** or **Low Potential**.

---

## Project Overview

The project focuses on **improving lead quality with machine learning at FicZon Inc.**

The analysis explores sales lead data to identify patterns in lead generation, sales agents, locations, delivery modes, and lead status.

A classification model is then developed to predict the potential quality of a lead.

---

## Business Objective

The project has two main objectives:

1. Identify insights related to **sales effectiveness**.
2. Build a machine learning model to classify leads into:

   * **High Potential**
   * **Low Potential**

This can help sales teams prioritize leads and focus their efforts on prospects with a higher likelihood of conversion.

---

## Dataset

The original dataset contains **7,422 lead records and 9 columns**.

### Features

| Feature         | Description                      |
| --------------- | -------------------------------- |
| `Created`       | Lead creation timestamp          |
| `Product_ID`    | Product associated with the lead |
| `Source`        | Lead generation source           |
| `Mobile`        | Customer mobile number           |
| `EMAIL`         | Customer email                   |
| `Sales_Agent`   | Sales agent assigned to the lead |
| `Location`      | Geographic location              |
| `Delivery_Mode` | Preferred delivery mode          |
| `Status`        | Lead status / target variable    |

These definitions are documented in the notebook's domain analysis.

---

##  Target Engineering

The original `Status` variable contains multiple lead-status categories.

These were grouped into two business-oriented categories:

###  High Potential

* `CONVERTED`
* `In Progress Positive`
* `Potential`
* `Long Term`
* `Open`

###  Low Potential

* `LOST`
* `converted`
* `In Progress Negative`
* `Not Responding`
* `Junk Lead`
* `Just Enquiry`

This transformation converts the original multi-class lead status into a binary classification problem.

---

##  Exploratory Data Analysis

The project performs exploratory analysis to understand sales effectiveness across different dimensions.

### Areas explored

* Lead generation sources
* Sales agents
* Customer locations
* Delivery modes
* Product distribution
* Lead status
* Missing-value patterns
* Categorical distributions

The dataset contains **25 source categories, 12 sales agents, 17 locations, and 5 delivery modes**.

---

##  Data Preprocessing

The preprocessing workflow includes:

* Data quality checks
* Missing-value analysis
* Duplicate checks
* Feature selection
* Categorical variable encoding
* Target transformation
* Train-test splitting
* Class balancing

### Class Imbalance

The training data was imbalanced:

```text
Before SMOTE
Class 0 → 827
Class 1 → 695
```

SMOTE was applied to balance the training set:

```text
After SMOTE
Class 0 → 827
Class 1 → 827
```

## The notebook uses `SMOTE` to address the imbalance before model training.

##  Machine Learning Models

The project evaluates multiple classification algorithms, including:

* Logistic Regression
* K-Nearest Neighbors (KNN)
* Support Vector Machine (SVM)
* Decision Tree
* Random Forest
* Gradient Boosting
* XGBoost
* Artificial Neural Network (ANN)

---

##  Hyperparameter Tuning

Hyperparameter optimization was also explored using **GridSearchCV**.

For the Support Vector Machine model, GridSearchCV was used with different values of:

* `C`
* `gamma`
* `kernel`

The best estimator identified in the notebook was:

```text
SVC(C=100)
```

with accuracy used as the scoring metric.

---

##  Model Evaluation

The models were evaluated using classification metrics such as:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix
* Classification Report

The notebook's final model evaluation reports that:

| Model Group         | Performance   |
| ------------------- | ------------- |
| SVM                 | Performs well |
| Gradient Boosting   | Performs well |
| XGBoost             | Performs well |
| ANN                 | Average       |
| Logistic Regression | Average       |
| Decision Tree       | Average       |
| KNN                 | Poor          |
| Random Forest       | Poor          |

These performance groupings are stated in the notebook's final model evaluation report.

---

##  Key Business Value

The project demonstrates how machine learning can support sales teams by converting detailed lead-status information into a simpler **High Potential vs Low Potential** classification.

Potential applications include:

* Lead prioritization
* Sales-agent targeting
* Campaign optimization
* Improving conversion-focused efforts
* Identifying promising leads earlier

---

##  Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **Scikit-learn**
* **Imbalanced-learn**
* **SQLAlchemy**
* **PyMySQL**
* **Jupyter Notebook**


