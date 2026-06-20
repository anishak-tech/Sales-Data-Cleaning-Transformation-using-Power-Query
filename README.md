# Sales Data Cleaning & Transformation using Power Query

**Author:** Anisha K
**Role:** Data Analyst | BI Analyst
**Tool Used:** Microsoft Power BI (Power Query Editor)

---

# Project Overview

This project demonstrates a complete data cleaning and transformation workflow using Power Query in Power BI. The objective was to convert a raw sales dataset containing inconsistencies, duplicate records, missing values, and formatting issues into a clean, structured, and analysis-ready dataset.

The project follows industry-standard ETL (Extract, Transform, Load) practices commonly used in Business Intelligence and Data Analytics projects.

---

# Business Problem

The raw sales data contained several data quality issues that could negatively impact reporting accuracy and business decision-making. Before analysis, the dataset required extensive cleaning and standardization.

Key challenges included:

* Duplicate records
* Missing values
* Inconsistent text formatting
* Invalid characters
* Mixed product information
* Non-standardized customer information

The goal was to improve data quality and prepare the dataset for reporting and dashboard development.

---

# Dataset Information

### Raw Dataset Columns

| Column Name  |
| ------------ |
| OrderID      |
| Product_Info |
| First_Name   |
| Last_Name    |
| Email        |

---

# Data Quality Issues Identified

## 1. Duplicate Records

Duplicate Order IDs existed within the dataset.

Example:

| OrderID |
| ------- |
| 1001    |
| 1001    |

---

## 2. Missing Values

Several records contained blank values in key fields.

Examples:

* Missing Product Information
* Missing Customer Names
* Missing Emails

---

## 3. Invalid Characters

Customer names contained unnecessary special characters.

Examples:

| Before  |
| ------- |
| #Anna   |
| #Jean   |
| #Claire |
| #Paul   |

---

## 4. Inconsistent Capitalization

Examples:

| Before                                    |
| ----------------------------------------- |
| MARTIN                                    |
| schmidt                                   |
| DIAZ                                      |
| [SOFIA@email.com](mailto:SOFIA@email.com) |

---

## 5. Combined Product Information

Product Name and Product Category were stored in a single column.

Examples:

| Product_Info        |
| ------------------- |
| Laptop Pro | ELEC   |
| Gaming Mouse | ACC  |
| Office Chair | FURN |

---

# Power Query Transformation Process

## Step 1: Promoted Headers

Converted the first row into column headers to establish proper field names.

---

## Step 2: Removed Unnecessary Columns

Deleted irrelevant columns that were not required for analysis.

---

## Step 3: Removed Blank Rows

Removed empty records to improve data quality.

---

## Step 4: Filtered Invalid Records

Excluded records containing unusable or incomplete information.

---

## Step 5: Removed Duplicate Records

Eliminated duplicate Order IDs and repeated entries.

---

## Step 6: Trimmed Text Values

Removed leading and trailing spaces from text columns.

Applied to:

* Product_Info
* First_Name
* Last_Name
* Email

---

## Step 7: Standardized Text Formatting

### Names

Applied "Capitalize Each Word" transformation.

Examples:

| Before  | After   |
| ------- | ------- |
| CARLOS  | Carlos  |
| MARTIN  | Martin  |
| schmidt | Schmidt |

### Emails

Converted all email addresses to lowercase.

Examples:

| Before                                    | After                                     |
| ----------------------------------------- | ----------------------------------------- |
| [ANNA@email.com](mailto:ANNA@email.com)   | [anna@email.com](mailto:anna@email.com)   |
| [SOFIA@email.com](mailto:SOFIA@email.com) | [sofia@email.com](mailto:sofia@email.com) |

---

## Step 8: Replaced Invalid Characters

Removed special characters from customer names.

Examples:

| Before  | After  |
| ------- | ------ |
| #Anna   | Anna   |
| #Jean   | Jean   |
| #Claire | Claire |
| #Paul   | Paul   |

---

## Step 9: Corrected Data Types

Assigned appropriate data types to ensure consistency and compatibility for future analysis.

Examples:

* OrderID → Whole Number
* Text Fields → Text

---

## Step 10: Split Product Information

Separated Product Name and Category using the "|" delimiter.

Example:

| Before            |
| ----------------- |
| Laptop Pro | ELEC |

Result:

| Product_Name | Category |
| ------------ | -------- |
| Laptop Pro   | ELEC     |

---

## Step 11: Renamed Columns

Renamed generated columns to meaningful business names.

Examples:

| Old Name  | New Name     |
| --------- | ------------ |
| Column2.1 | Product_Name |
| Column2.2 | Category     |

---

## Step 12: Merged Customer Names

Combined First_Name and Last_Name into a single Customer_Name column.

Example:

| First_Name | Last_Name | Customer_Name |
| ---------- | --------- | ------------- |
| Anna       | Schmidt   | Anna Schmidt  |
| Jean       | Martin    | Jean Martin   |

---

## Step 13: Duplicated Customer ID

Created a duplicate Customer ID column for additional transformations without affecting the original field.

---

## Step 14: Reordered Columns

Arranged columns into a logical business-friendly structure.

---

## Step 15: Extracted Country Codes

Derived country information from Customer IDs.

Examples:

| Customer_ID |
| ----------- |
| C-1001-DE   |
| C-1002-FR   |
| C-1003-IT   |

Result:

| Country_Code |
| ------------ |
| DE           |
| FR           |
| IT           |

---

# Power Query Workflow

```text
Raw Dataset
     ↓
Promote Headers
     ↓
Remove Blank Rows
     ↓
Filter Invalid Records
     ↓
Remove Duplicates
     ↓
Trim Text Values
     ↓
Standardize Text Formatting
     ↓
Replace Invalid Characters
     ↓
Split Product Information
     ↓
Rename Columns
     ↓
Merge Customer Names
     ↓
Extract Country Codes
     ↓
Reorder Columns
     ↓
Cleaned Dataset
```

# Before vs After Transformation

| Issue               | Before                                  | After                                   |
| ------------------- | --------------------------------------- | --------------------------------------- |
| Email Formatting    | [ANNA@email.com](mailto:ANNA@email.com) | [anna@email.com](mailto:anna@email.com) |
| Name Formatting     | MARTIN                                  | Martin                                  |
| Invalid Characters  | #Anna                                   | Anna                                    |
| Product Information | Laptop Pro | ELEC                       | Product + Category Split                |
| Duplicate Records   | Present                                 | Removed                                 |

---

# Final Dataset Structure

| Column Name   |
| ------------- |
| OrderID       |
| Email         |
| Customer_ID   |
| Amount        |
| Price         |
| Order_Date    |
| Product_Name  |
| Category      |
| Customer_Name |
| Country_Code  |

---

# Project Outcomes

* Improved overall data quality
* Eliminated duplicate records
* Standardized customer information
* Standardized email formatting
* Removed invalid characters
* Separated product and category information
* Generated customer full names
* Extracted country-level information
* Created an analysis-ready dataset

---

# Skills Demonstrated

### Power BI

* Data Preparation
* ETL Workflow Design
* Data Modeling Preparation

### Power Query

* Data Cleaning
* Data Transformation
* Text Standardization
* Column Splitting
* Column Merging
* Duplicate Removal
* Missing Value Handling

### Data Analysis

* Data Quality Assessment
* Data Validation
* Data Structuring
* Business Data Preparation

---

# Tools Used

* Microsoft Power BI
* Power Query Editor

---

# Conclusion

This project showcases a complete end-to-end data cleaning and transformation process using Power Query. By applying multiple transformation techniques, the raw sales dataset was converted into a clean, consistent, and business-ready dataset suitable for reporting, dashboard creation, and advanced analytics.


