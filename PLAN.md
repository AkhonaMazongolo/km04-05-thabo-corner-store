# Thabo's Corner Store - Project Plan

## Computational Thinking

## Project Overview

Thabo runs a small corner store and has been recording sales data in spreadsheets. Although the data contains useful information about products, sales trends, and stock levels, it is currently messy and difficult to analyse. The aim of this project is to build a Python-based system that cleans the raw data, stores it in an SQLite database, analyses sales performance, generates visual reports, and protects access to those reports with a simple password system. The final solution will help Thabo make better business decisions using reliable and organised data.

---

### 1. Decompose the Problem

To make the project manageable, I will divide it into five main tasks:

1. Clean the raw product and sales data.
2. Store the cleaned data in an SQLite database.
3. Analyse the data to generate useful business insights.
4. Create charts to visualise the results.
5. Add password protection to secure access to reports.

Breaking the project into smaller sections will make development and testing easier.

### 2. Identify Patterns

The data contains several recurring quality issues that need to be handled consistently.

**Products data:**

- Missing product names.
- Missing prices.
- Inconsistent category capitalisation.
- Duplicate product records.

**Sales data:**

- Dates recorded in multiple formats.
- Missing dates.
- Missing quantities.
- Missing payment methods.
- Product IDs that do not exist in the products dataset.
- Duplicate transactions.

Instead of fixing records one at a time, I will apply standard cleaning rules to all similar issues.

### 3. Abstraction

The most important information for this project is:

- Product details
- Quantities sold
- Sale dates
- Product prices
- Payment methods
- Customer types

Less important information will not be included in the analysis. The original CSV files will remain unchanged, and any assumptions or cleaning decisions will be documented. For example, I will clearly explain how ambiguous dates were standardised.

### 4. Algorithm Design

The project will follow these steps:

1. Load the `products.csv` and `sales.csv` files.
2. Clean and validate the products dataset.
3. Clean the sales dataset using the validated product data.
4. Create SQLite tables and define relationships between them.
5. Insert the cleaned data into the database.
6. Run SQL queries to generate business insights.
7. Calculate sales statistics and monthly trends.
8. Create charts to visualise the results.
9. Implement password protection for report access.
10. Test the complete system and document all decisions and findings in the README.

---

## Planned Module Order

### 1. `data_cleaning.py`

This module will be completed first because every other part of the system relies on accurate and consistent data.

### 2. `database.py`

After cleaning the data, it will be stored in SQLite tables using primary and foreign key relationships.

### 3. `analysis.py`

This module will calculate useful metrics such as:

- Total records processed
- Sales trends
- Stock alerts
- Transaction statistics
- Monthly sales summaries

### 4. `visualize.py`

The analysis results will be presented using charts, making trends and performance easier to understand.

### 5. `security.py`

This module will create a simple login system that uses hashed passwords to protect access to reports.

---

## Reason for the Module Order

The modules are arranged according to their dependencies. The data must be cleaned before it can be stored in a database. The database must exist before analysis can be performed, and analysis results are needed before charts can be created. Security is added last because it protects the completed reporting system.
