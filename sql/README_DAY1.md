Project: RavenStack SaaS Analytics
Date: 12/17/2025
Prepared by: Arslan


---------------------------------------------------- 1 Goal & Objective ---------------------------------------------------- 

Goal:
Ensure the RavenStack dataset is reliable, complete, and structured correctly before performing any advanced analysis or building dashboards.

Objectives:

Identify all tables and row counts.

Inspect columns and data types for correctness.

Validate primary keys for uniqueness.

Check foreign key integrity between tables.

Identify missing or NULL values in critical columns.

Document initial data quality issues and potential risks for future analysis.



----------------------------------------------------  2. Business Problem / Story ------------------------------------ 

“Before making decisions based on data, we must trust that it is accurate, complete, and structured correctly. Day 1 focuses on auditing the raw RavenStack SaaS dataset to establish a reliable foundation for revenue, churn, and product usage analytics.”

RavenStack operates a SaaS product with multiple tables: accounts, subscriptions, feature usage, support tickets, and churn events.

Decisions on churn, retention, and revenue require accurate data — identifying duplicates, missing values, and broken links is critical.




---------------------------------------------------- 3. Tasks Completed ---------------------------------------------------- 

Table Inventory

Listed all tables in the database.

Counted rows in each table.

Previewed first 10 rows for each table.


Column & Data Type Checks

Verified column names and data types.

Checked that date fields are stored as DATE/DATETIME.

Verified numeric fields for revenue are correctly typed.


Primary Key Validation

Checked uniqueness of account_id, subscription_id, usage_id, ticket_id, churn_event_id.


Foreign Key Integrity

Verified that all subscriptions link to valid accounts.

Verified that all feature usage entries link to valid subscriptions.

Verified that support tickets and churn events link to valid accounts.

Observations:

Most FKs are valid.

Minor orphaned records found in feature_usage and support_tickets (these need attention before dashboards/ML).


NULL & Missing Value Analysis

Counted NULLs per column.

Identified expected vs suspicious missing values:

subscriptions.end_date — NULL for active subscriptions (expected)

support_tickets.satisfaction_score — NULL if no response (expected)



----------------------------------------------------  4. Tools & Techniques Used ------------------------------------

MySQL Workbench for querying and table inspection.

SQL commands: SHOW TABLES, DESCRIBE, COUNT(*), LEFT JOIN, GROUP BY, HAVING.

CTEs used for organizing complex queries (optional in Day 1).



----------------------------------------------------  5. Key Findings / Observations -----------------------------------

Most tables are well-structured with correct primary keys.

Some NULL values found in:

subscriptions.end_date (expected for active subscriptions)

support_tickets.satisfaction_score (expected if user didn’t respond)

A few orphaned feature_usage records exist without matching subscriptions.

No duplicate primary keys detected.



----------------------------------------------------  6. Achievements / Portfolio Outcomes -----------------------------------
Data auditing skills: Confirmed dataset integrity before advanced analysis.

Foundation for analysis: Prepared reliable tables for revenue, churn, cohort, and product analytics.

Documentation habit: Established first professional report for GitHub portfolio.

SQL foundation: Practiced inspecting tables, checking data types, counting duplicates, and analyzing missing values.



----------------------------------------------------  7. Next Steps (Day 2 Preview) -------------------------
Analyze accounts and subscriptions performance:

Customer counts by plan tier

Trial vs paid conversions

Active vs churned subscriptions

Start building core SaaS KPIs and aggregation queries for portfolio showcase.




**************************************************** End of Day 1 Report ****************************************************



