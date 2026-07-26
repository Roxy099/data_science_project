# Credit Risk Project Master Roadmap

> This roadmap is the single source of truth for the project. We will
> follow it unless we both explicitly decide to change it.

## Phase 1 -- Project Foundation ✅

-   Git & GitHub setup
-   Project folder structure
-   Business Understanding
-   Project Log
-   README

## Phase 2 -- Database Setup

-   Create MySQL database
-   Import Home Credit CSV files into MySQL
-   Verify row counts and relationships
-   Document schema

## Phase 3 -- Data Understanding

-   Explore data using SQL
-   Load data into Python from MySQL
-   Create Data Dictionary
-   Assess data quality
-   Analyze target variable

## Phase 4 -- Baseline Model

-   Use the application_train table as the primary modeling dataset
-   Perform EDA
-   Clean data
-   Handle missing values
-   Build baseline ML model
-   Evaluate performance

## Phase 5 -- Feature Engineering

Engineer customer-level features from: - bureau - bureau_balance -
previous_application - installments_payments - credit_card_balance -
POS_CASH_balance

Merge engineered features into the master modeling dataset and retrain
the model.

## Phase 6 -- Final Model

-   Hyperparameter tuning
-   Model comparison
-   Threshold optimization
-   Business evaluation
-   Model explainability

## Phase 7 -- Deployment & Reporting

-   Save model
-   Build prediction pipeline
-   Optional API
-   Power BI dashboard
-   Final documentation

## Ground Rules

1.  SQL prepares data.
2.  Python performs analysis, visualization, feature engineering and ML.
3.  Git is used throughout.
4.  We update PROJECT_LOG.md after every session.
5.  We do not change this roadmap unless we both agree.

## Session Reminder Prompt

At the beginning of each session, use:

    Continue the Credit Risk Project using the Master Roadmap.
    Current phase:
    Completed in last session:
    Today's objective:
