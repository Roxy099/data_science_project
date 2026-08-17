# Credit Risk Project — Project Log

## Project Overview

**Project:** Credit Risk Prediction
**Dataset:** Home Credit Default Risk
**Primary Modeling Dataset:** `application_train`
**Database:** MySQL
**Analysis Environment:** Python / Jupyter Notebook

---

# Phase 1 — Project Foundation ✅

### Completed Activities

* Git & GitHub setup
* Project folder structure
* Business Understanding
* Project Log
* README

### Business Objective

The objective of this project is to develop a credit risk model that helps a lending institution identify applicants who are likely to experience payment difficulties.

The model should help the business:

* Reduce financial losses caused by high-risk applicants.
* Identify creditworthy applicants more consistently.
* Support faster and more data-driven credit decisions.
* Balance the identification of risky applicants with the approval of reliable customers.

### Project Approach

The project follows an enterprise-oriented Data Science workflow rather than treating the dataset as a purely Kaggle-based modeling exercise.

---

# Phase 2 — Database Setup ✅

### Completed Activities

* Created MySQL database.
* Imported the Home Credit CSV datasets into MySQL.
* Verified row counts.
* Verified the availability of the required datasets for future feature engineering.
* Documented the database schema.

### Dataset Information

| Table                   |       Rows | Columns |
| ----------------------- | ---------: | ------: |
| `application_train`     |    307,511 |     122 |
| `bureau`                |  1,716,428 |      17 |
| `bureau_balance`        | 27,299,925 |       3 |
| `previous_application`  |  1,670,214 |      37 |
| `POS_CASH_balance`      | 10,001,358 |       8 |
| `credit_card_balance`   |  3,840,312 |      23 |
| `installments_payments` | 13,605,401 |       8 |

### Data Preparation Principle

* **SQL** is used for database-level preparation, querying, validation, and data extraction.
* **Python** is used for data analysis, visualization, feature engineering, and machine learning.
* **Git** is used throughout the project for version control and tracking project changes.

---

# Phase 3 — Data Understanding ✅

## Objectives

* Explore data using SQL.
* Load data into Python from MySQL.
* Create a Data Dictionary.
* Assess data quality.
* Analyze the target variable.

---

## 1. Data Quality Assessment

The `application_train` dataset was initially assessed to understand its overall structure and data quality before proceeding with analysis and modeling.

### Dataset Structure

* Number of rows: **307,511**
* Number of columns: **122**

### Data Quality Checks

The following aspects were assessed:

* Dataset dimensions
* Missing values
* Unique values
* Variable characteristics
* Data types
* Target variable validity
* Different feature groups within the dataset

The purpose of this step was to identify potential data quality issues and understand the structure of the dataset before moving toward modeling.

---

## 2. Data Dictionary

A Data Dictionary was created to understand the business meaning and purpose of the variables in the `application_train` dataset.

The features were reviewed and grouped into meaningful categories, including:

* Demographic features
* Financial features
* Employment-related features
* Property and building-related features
* Contact-related features
* Document flag variables
* External source variables
* Amount-related variables

Special attention was given to understanding what each variable represents from a business perspective rather than treating the columns only as numerical or categorical values.

This understanding will help during EDA, feature selection, feature engineering, and model interpretation.

---

## 3. Target Variable Exploration

The target variable `TARGET` represents whether an applicant experienced payment difficulties:

* `TARGET = 0` → Applicant did not experience payment difficulties.
* `TARGET = 1` → Applicant experienced payment difficulties.

The target variable contains **307,511 observations**, with **2 unique values** and **no missing values**.

| TARGET |   Count | Percentage |
| :----: | ------: | ---------: |
|    0   | 282,686 |     91.93% |
|    1   |  24,825 |      8.07% |

The target variable is **highly imbalanced**, with only **8.07%** of applicants belonging to the positive class (`TARGET = 1`).

This class imbalance is important for the credit risk modeling process because a model that predicts most applicants as `TARGET = 0` could achieve high accuracy while failing to identify risky customers.

Therefore, accuracy alone will not be sufficient for evaluating our models. Metrics such as **recall, precision, ROC-AUC, and PR-AUC** will be considered during the modeling phase.

From a business perspective, correctly identifying applicants with payment difficulties is particularly important because failing to identify a risky applicant may result in financial losses for the lending institution.

---

## Phase 3 — Key Findings

* The primary modeling dataset `application_train` contains **307,511 applicants** and **122 features**.
* The dataset was assessed for data quality before modeling.
* A Data Dictionary was created to understand the business meaning of the available features.
* The target variable is binary with **2 unique values**.
* `TARGET` contains **no missing values**.
* `TARGET = 0` represents **91.93%** of applicants.
* `TARGET = 1` represents **8.07%** of applicants.
* The target variable is **highly imbalanced**.
* Accuracy alone will not be sufficient for evaluating the future credit risk models.
* Correctly identifying risky applicants is an important business objective because false negatives can result in financial losses.

### Phase 3 Status

**✅ COMPLETED**

---

# Phase 4 — Baseline Model ⏳

## Objectives

* Use the `application_train` table as the primary modeling dataset.
* Perform Exploratory Data Analysis (EDA).
* Clean the dataset.
* Handle missing values.
* Build a baseline machine learning model.
* Evaluate baseline model performance.

**Status:** Not Started

---

# Phase 5 — Feature Engineering ⏳

## Objectives

Engineer customer-level features from:

* `bureau`
* `bureau_balance`
* `previous_application`
* `installments_payments`
* `credit_card_balance`
* `POS_CASH_balance`

The engineered features will be merged into the master modeling dataset and the model will be retrained.

**Status:** Not Started

---

# Phase 6 — Final Model ⏳

## Objectives

* Hyperparameter tuning
* Model comparison
* Threshold optimization
* Business evaluation
* Model explainability

**Status:** Not Started

---

# Phase 7 — Deployment & Reporting ⏳

## Objectives

* Save the final model.
* Build the prediction pipeline.
* Develop an optional API.
* Build a Power BI dashboard.
* Complete final project documentation.

**Status:** Not Started

---

# Current Project Status

| Phase                            | Status        |
| -------------------------------- | ------------- |
| Phase 1 — Project Foundation     | ✅ Complete    |
| Phase 2 — Database Setup         | ✅ Complete    |
| Phase 3 — Data Understanding     | ✅ Complete    |
| Phase 4 — Baseline Model         | ⏳ Not Started |
| Phase 5 — Feature Engineering    | ⏳ Not Started |
| Phase 6 — Final Model            | ⏳ Not Started |
| Phase 7 — Deployment & Reporting | ⏳ Not Started |

## Current Position

**Phase 3 — Data Understanding: COMPLETED ✅**

**Next Phase:** Phase 4 — Baseline Model
