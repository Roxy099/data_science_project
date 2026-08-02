\# Database Schema



\## Project Information



\- \*\*Project:\*\* Credit Risk Prediction using Home Credit Default Risk Dataset

\- \*\*Database:\*\* MySQL

\- \*\*Database Name:\*\* `credit\_risk`

\- \*\*Data Source:\*\* Home Credit Default Risk (Kaggle)



\---

---

## POS_CASH_balance

**Purpose**

Contains the monthly repayment history of previous Point-of-Sale (POS) and Cash loans.

Each row represents one month's status of one previous POS/Cash loan.

**Primary Key Candidate**

* Composite Key: (`SK_ID_PREV`, `MONTHS_BALANCE`)

**Foreign Keys**

* `SK_ID_PREV`
* `SK_ID_CURR`

**Important Columns**

* `MONTHS_BALANCE`
* `CNT_INSTALMENT`
* `CNT_INSTALMENT_FUTURE`
* `SK_DPD`
* `SK_DPD_DEF`
* `NAME_CONTRACT_STATUS`

---

## credit_card_balance

**Purpose**

Contains monthly snapshots of customers' previous credit card accounts.

Each row represents one month's activity for one credit card account.

**Primary Key Candidate**

* Composite Key: (`SK_ID_PREV`, `MONTHS_BALANCE`)

**Foreign Keys**

* `SK_ID_PREV`
* `SK_ID_CURR`

**Important Columns**

* `MONTHS_BALANCE`
* `AMT_BALANCE`
* `AMT_CREDIT_LIMIT_ACTUAL`
* `AMT_DRAWINGS_CURRENT`
* `AMT_PAYMENT_CURRENT`
* `AMT_TOTAL_RECEIVABLE`
* `SK_DPD`
* `SK_DPD_DEF`

---

## installments_payments

**Purpose**

Contains repayment history for installment loans.

Each row represents one installment payment made (or expected) by a customer.

**Primary Key Candidate**

* Composite Key: (`SK_ID_PREV`, `NUM_INSTALMENT_NUMBER`)

**Foreign Keys**

* `SK_ID_PREV`
* `SK_ID_CURR`

**Important Columns**

* `NUM_INSTALMENT_VERSION`
* `NUM_INSTALMENT_NUMBER`
* `DAYS_INSTALMENT`
* `DAYS_ENTRY_PAYMENT`
* `AMT_INSTALMENT`
* `AMT_PAYMENT`

---

## Updated Notes

* SQL is used for data storage, querying, and preparation.
* Python will be used for data exploration, visualization, feature engineering, and machine learning.
* `application_train` is the primary modeling dataset.
* All remaining tables contain historical customer information and will be aggregated to the customer level before being merged with `application_train` during the Feature Engineering phase.
* Data type corrections and data quality assessment will be performed in Python after loading the data from MySQL.


\# Table Summary



| Table Name | Grain (One Row Represents) | Primary Key Candidate | Foreign Key | Rows | Columns | Status |

|------------|----------------------------|-----------------------|-------------|------:|--------:|--------|

| application\_train | One current loan application | SK\_ID\_CURR | - | 307511 | 122 | Imported |

| bureau | One previous credit account from another financial institution | SK\_ID\_BUREAU | SK\_ID\_CURR | 1716428 | 17 | Imported |

| bureau\_balance | One monthly record for a bureau credit account | (SK\_ID\_BUREAU, MONTHS\_BALANCE) | SK\_ID\_BUREAU | 27299925 | 3 | Imported |

| previous\_application | One previous Home Credit loan application | SK\_ID\_PREV | SK\_ID\_CURR | 1670214 | 37 | Imported |

| POS_CASH_balance | One monthly record for a previous POS/Cash loan | (SK_ID_PREV, MONTHS_BALANCE) | SK_ID_PREV, SK_ID_CURR | 10001358 | 8 | Imported |

| credit_card_balance | One monthly record for a previous credit card account | (SK_ID_PREV, MONTHS_BALANCE) | SK_ID_PREV, SK_ID_CURR | 3840312 | 23 | Imported |

| installments_payments | One installment payment record | (SK_ID_PREV, NUM_INSTALMENT_NUMBER) | SK_ID_PREV, SK_ID_CURR | 13605401 | 8 | Imported |

\---



\# Database Relationships



```text

application\_train

\-----------------

PK : SK\_ID\_CURR

&#x20;       |

&#x20;       | 1 -----> Many

&#x20;       |

&#x20;       v

bureau

\-----------------

PK : SK\_ID\_BUREAU

FK : SK\_ID\_CURR

&#x20;       |

&#x20;       | 1 -----> Many

&#x20;       |

&#x20;       v

bureau\_balance

\-----------------

FK : SK\_ID\_BUREAU





application\_train

\-----------------

PK : SK\_ID\_CURR

&#x20;       |

&#x20;       | 1 -----> Many

&#x20;       |

&#x20;       v

previous\_application

\-----------------

PK : SK\_ID\_PREV

FK : SK\_ID\_CURR

```



\---



\# Table Descriptions



\## application\_train



\*\*Purpose\*\*



Main modeling table.



Each row represents one current loan application submitted by a customer.



\*\*Primary Key Candidate\*\*



\- `SK\_ID\_CURR`



\*\*Target Variable\*\*



\- `TARGET`

&#x20; - `0` = Loan Repaid

&#x20; - `1` = Loan Default



\---



\## bureau



\*\*Purpose\*\*



Contains previous credit history obtained from other financial institutions.



Each row represents one previous credit account.



\*\*Primary Key Candidate\*\*



\- `SK\_ID\_BUREAU`



\*\*Foreign Key\*\*



\- `SK\_ID\_CURR`



\---



\## bureau\_balance



\*\*Purpose\*\*



Contains the monthly history of every credit account in the `bureau` table.



Each row represents one month of history for one bureau account.



\*\*Important Columns\*\*



\- `SK\_ID\_BUREAU`

\- `MONTHS\_BALANCE`

\- `STATUS`



\---



\## previous\_application



\*\*Purpose\*\*



Contains all previous loan applications submitted to Home Credit before the current application.



Each row represents one previous loan application.



\*\*Primary Key Candidate\*\*



\- `SK\_ID\_PREV`



\*\*Foreign Key\*\*



\- `SK\_ID\_CURR`



\---



\# Notes



\- SQL is used for data storage, querying, and preparation.

\- Python will be used for data exploration, visualization, feature engineering, and machine learning.

\- This document will be updated as additional tables are imported.

