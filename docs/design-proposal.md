## Title

**Design and Implementation of an End-to-End Sales Data Warehouse**

---

## Background

A retail company generates daily transactional sales data from multiple sources. The analytics team requires a centralized data warehouse that supports historical analysis, trend reporting, and reliable data access. You are assigned as the Data Engineer responsible for designing, building, and operating this data platform.

---

## Objective

Design and implement a **production-grade batch data pipeline** that ingests raw sales data, processes it reliably, and exposes analytics-ready datasets following dimensional modeling best practices.

---

## Technology Constraints

* Development environment must be **macOS-compatible**
* Use **open-source tools**
* Pipeline must be **orchestrated**
* Data warehouse must support **historical tracking**

---

## Source Data

### 1. Sales Transactions (CSV – Daily Batch)

| Column      | Description             |
| ----------- | ----------------------- |
| order_id    | Unique order identifier |
| order_date  | Date of order           |
| customer_id | Customer identifier     |
| product_id  | Product identifier      |
| quantity    | Quantity sold           |
| unit_price  | Price per unit          |
| country     | Country of sale         |

Data quality issues may exist, including:

* Missing values
* Duplicate records
* Late-arriving data
* Schema inconsistencies

---

### 2. Reference Data

* Customer master data
* Product master data
* Country reference data

Reference data may change over time.

---

## Functional Requirements

### FR1 – Data Ingestion

* Ingest raw data into a staging layer
* Preserve raw data without transformation
* Support incremental data loads
* Capture metadata such as load timestamp and record counts

---

### FR2 – Data Cleaning and Standardization

* Handle missing and invalid values
* Remove duplicate records
* Standardize categorical fields
* Ensure data consistency across sources

---

### FR3 – Data Modeling

* Design a **dimensional data model**
* Clearly define the grain of the fact table
* Implement surrogate keys
* Support historical changes in dimensional attributes

---

### FR4 – Historical Data Management

* Track changes in customer attributes over time
* Preserve historical records
* Ensure accurate point-in-time reporting

---

### FR5 – Fact Table Construction

* Populate fact tables using conformed dimensions
* Calculate derived metrics (e.g., revenue)
* Enforce referential integrity

---

### FR6 – Orchestration

* Orchestrate the pipeline using a workflow scheduler
* Define task dependencies
* Implement retry and failure-handling mechanisms
* Support backfills and reprocessing

---

### FR7 – Data Quality and Validation

* Define data quality rules
* Validate row counts, null constraints, and key relationships
* Prevent publishing of invalid data

---

### FR8 – Analytics Enablement

* Provide analytics-ready tables
* Support queries for:

  * Revenue trends over time
  * Top products and customers
  * Country-level sales analysis

---

### FR9 – Observability and Reliability

* Log pipeline execution details
* Track data freshness
* Provide failure visibility

---

### FR10 – Scalability Considerations

* Discuss how the solution would scale with increased data volume
* Identify potential bottlenecks and mitigation strategies

---

## Non-Functional Requirements

* Solution must be **reproducible**
* Code must follow **clean engineering practices**
* System must be **idempotent**
* Data processing must be **deterministic**
* Documentation must be clear and complete

---

## Deliverables

1. Source code repository
2. Database schema definitions
3. Orchestration workflow(s)
4. Data quality validation artifacts
5. Sample analytical queries
6. Technical documentation
