# Enterprise Accounts Receivable Forecasting with Microsoft Fabric & Prophet

## Overview

Organizations depend on accurate cash flow forecasting to make informed financial decisions. While historical Accounts Receivable (AR) reports explain what has already happened, they provide little insight into future collections.

This project demonstrates how Microsoft Fabric and Facebook Prophet can be combined to build an enterprise-style forecasting solution that predicts future AR collections, evaluates forecast accuracy through cross-validation, and persists the forecast back into a Microsoft Fabric Lakehouse for downstream reporting and analytics.

The completed solution follows a modern data platform architecture using Microsoft Fabric Lakehouse, Delta tables, notebooks, and a semantic model designed for stakeholder reporting.

---

# Business Problem

Finance leaders frequently ask questions such as:

* How much cash should we expect to collect over the next 12 months?
* Are our collection trends improving or declining?
* Do seasonal collection patterns exist?
* How confident should we be in our forecast?
* How can forecasting improve budgeting, staffing, and cash flow planning?

Traditional reporting answers questions about the past.

Forecasting helps leadership prepare for the future.

---

# Solution Overview

This solution uses Microsoft Fabric to build an end-to-end forecasting workflow.

The process includes:

1. Loading historical Accounts Receivable collection data into a Microsoft Fabric Lakehouse.
2. Preparing the data for time-series forecasting.
3. Training a Prophet forecasting model.
4. Generating a 12-month collection forecast.
5. Performing cross-validation and grid search to identify the optimal forecasting parameters.
6. Rebuilding the final production model using the winning configuration.
7. Writing forecast results back to a Delta table within the Lakehouse.
8. Preparing the solution for downstream business intelligence consumption.

---

# Architecture

Historical AR Data

↓

Microsoft Fabric Lakehouse

↓

Microsoft Fabric Notebook

↓

Prophet Time-Series Forecasting

↓

Cross-Validation & Grid Search

↓

Final Tuned Production Model

↓

Delta Lake Forecast Table (`ar_forecast`)

↓

Semantic Model

↓

Power BI Dashboard (Stakeholder Consumption Layer)

---

# Technologies Used

* Microsoft Fabric
* Microsoft Fabric Lakehouse
* Microsoft Fabric Notebook
* Python
* Pandas
* Prophet
* Delta Lake
* Spark
* Semantic Model
* Power BI (planned stakeholder consumption layer)

---

# Forecasting Methodology

The forecasting workflow includes:

* Historical trend detection
* Seasonality analysis
* Automatic changepoint detection
* Confidence interval generation
* Time-series cross-validation
* Hyperparameter tuning
* Final production model retraining

The project compares multiple Prophet parameter combinations and selects the highest-performing configuration before generating the final production forecast.

---

# Business Value

This solution enables finance teams to move beyond historical reporting by providing:

* Forecasted Accounts Receivable collections
* Confidence intervals for planning
* Detection of seasonal collection behavior
* Improved cash flow visibility
* Support for budgeting and staffing decisions
* Better working capital planning

---

# Lessons Learned

Several enterprise architecture lessons emerged during development.

One of the most important was understanding the distinction between Microsoft Fabric Direct Lake semantic models and upstream data engineering.

Rather than relying on semantic model calculated columns, production-ready solutions should perform transformations upstream within the Lakehouse, notebooks, Dataflows, or SQL endpoints before exposing curated Delta tables to reporting tools.

This project also demonstrated the value of separating:

* Data Engineering
* Forecast Modeling
* Data Storage
* Business Intelligence

into clearly defined layers.

---

# Future Enhancements

Potential enhancements include:

* Invoice-level forecasting
* Customer payment segmentation
* Collections risk scoring
* DSO forecasting
* Scenario planning
* Automated model retraining
* Scheduled Fabric pipelines
* Executive Power BI dashboards

---

# Repository Contents

```
README.md
notebooks/
images/
docs/
```

---

# Author

**Devon Johnson**

This repository is part of my Microsoft Fabric and Data Engineering portfolio demonstrating enterprise analytics, forecasting, and modern data platform architecture.
