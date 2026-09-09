
[Data Governance](./Images/dg.jpg)

![Static Badge](https://img.shields.io/badge/%D9%90DataGovernance-blue?style=flat)
# Data Governance Implementation on Station Table

## Part of the Weather Data Pipeline project
Applied  data governance practices on real weather pipline
( station-level data) using OpenMetadata, covering schema definition,
data quality, and access control planning .


# Challenges & Solution

### 1. Inconsistent ID format across regions
**problem:** Inconsistant ID format across differnt regions (hypothetical example: (Austia AT-0989)(Germany  123454)
**Solution:** Defined as CHAR (fixed-length) with regext pattern[x]
**Status:** Documented/Implemented in pipline

### 2. Invalid lattitude/longitude ranges
**Problem:** No validation existed for coordinate bounds (hypothetical example: lan: 100 , long 290)
**Solution:** added openMetaData  Data Qulaity tests
(columnValuesTobetween: lat -90/90 , long -180/ 180)
**Status:** Implementd and tested

### 3. Data Classification
**Finding:** NO PII present
**Action:** Tgged  as nonsensitive

### 4. Access control (country-level)
**Requirement:** Each region's team should only view their own data
**Design:** Row-Level Security via BigQuery Row Access Policy +
mapping table (scalable to N teams without policy duplication)
**Status:** Designed, not yet implemented in this exercise

## Screenshots
— [Glossary definitions for station columns](./Images/glossary.png)
— [Column-level metadata (owner, tags, glossary links)](./Images/DG.png)
— [Data Quality test cases and results](./Images/tests.png)
- [Team structure (Data engineer Team / Austria Team)](./Images/TEAM .png)
— [User role assignment (steward role)](./Images/user.png)
- [prfiler Data](./Images/profiler .png)

