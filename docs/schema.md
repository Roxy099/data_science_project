\# Database Schema



\## Project Information



\- \*\*Project:\*\* Credit Risk Prediction using Home Credit Default Risk Dataset

\- \*\*Database:\*\* MySQL

\- \*\*Database Name:\*\* `credit\_risk`

\- \*\*Data Source:\*\* Home Credit Default Risk (Kaggle)



\---



\# Table Summary



| Table Name | Grain (One Row Represents) | Primary Key Candidate | Foreign Key | Rows | Columns | Status |

|------------|----------------------------|-----------------------|-------------|------:|--------:|--------|

| application\_train | One current loan application | SK\_ID\_CURR | - | 307511 | 122 | Imported |

| bureau | One previous credit account from another financial institution | SK\_ID\_BUREAU | SK\_ID\_CURR | 1716428 | 17 | Imported |

| bureau\_balance | One monthly record for a bureau credit account | (SK\_ID\_BUREAU, MONTHS\_BALANCE) | SK\_ID\_BUREAU | 27299925 | 3 | Imported |

| previous\_application | One previous Home Credit loan application | SK\_ID\_PREV | SK\_ID\_CURR | 1670214 | 37 | Imported |



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

