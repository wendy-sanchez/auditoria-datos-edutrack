# EduTrack — SQL Database Audit & Data Analysis

A practical SQL database auditing project focused on data quality, record management, and business insights for an online learning platform.

[English](README.md) | [Español](README.es.md)

## Overview

EduTrack is a fictional online learning platform used as the context for a database auditing exercise.

The platform had been operating for two years, collecting enrollment records through multiple channels without a formal data quality review.

The objective of this project was to audit its enrollment database, identify inconsistencies, correct incomplete records, remove test accounts, and extract meaningful insights to support operational reporting.

The project uses SQL queries executed in Supabase and documents the actual results in a dedicated analysis report.

## Project Objectives

- Identify students with low course completion rates and potential dropout cases.
- Detect enrollment records with missing instructor information.
- Insert a missing enrollment record.
- Remove test accounts and their associated enrollments.
- Analyze enrollment distribution across course categories.
- Calculate average course completion rates.
- Identify courses with higher enrollment volumes.
- Aggregate payment amounts by course category.
- Document query results and findings in a readable report.

## Key Features

### Data Retrieval & Filtering

- Retrieve enrollment records by course.
- Identify students with completion rates below 10%.
- Find records with missing instructor assignments.
- Rank students by completion progress among those who have not passed.
- Filter enrollment records by date.

### Data Modification & Cleaning

- Insert a missing enrollment record using `INSERT`.
- Update records with missing instructor information using `UPDATE`.
- Remove test account enrollments using `DELETE`.
- Verify records before and after data modifications.

### Data Aggregation & Analysis

- Count enrollments by course category using `COUNT()` and `GROUP BY`.
- Calculate average completion rates using `AVG()`.
- Filter grouped results using `HAVING`.
- Calculate total payment amounts by category using `SUM()`.
- Sort aggregated results to facilitate comparisons.

## Tech Stack

| Technology | Purpose |
|---|---|
| SQL | Database querying, auditing, and data manipulation |
| PostgreSQL | Relational database engine |
| Supabase | Database hosting and SQL query execution |
| Markdown | Technical documentation and analysis reporting |
| GitHub | Version control and project documentation |

## Repository Structure

```text
aie-pt-3--auditoria-datos-edutrack/
│
├── README.md
├── README.es.md
├── queries.sql
├── analysis_report.md
│
├── Comprobación courses.png
├── Comprobación inicial.png
├── Comprobación students.png
└── Ejecución exitosa de base de datos de Edutrack.png
```

## SQL Queries

The `queries.sql` file contains 12 main exercises covering different database operations:

| # | Operation | SQL Concepts |
|---|---|---|
| 01 | Retrieve enrollments for a specific course | `SELECT`, `WHERE` |
| 02 | Identify potential dropouts | Filtering |
| 03 | Find enrollments without instructors | `IS NULL` |
| 04 | Rank students who have not passed | `ORDER BY`, `LIMIT` |
| 05 | Retrieve enrollments from the last year | Date filtering, subqueries |
| 06 | Insert a missing enrollment | `INSERT INTO` |
| 07 | Assign a default value to missing instructors | `UPDATE` |
| 08 | Remove test account enrollments | `DELETE`, `LIKE` |
| 09 | Count enrollments by category | `COUNT()`, `GROUP BY` |
| 10 | Calculate average completion by course | `AVG()`, `GROUP BY` |
| 11 | Identify courses with more than three enrollments | `HAVING` |
| 12 | Calculate payment totals by category | `SUM()`, `GROUP BY` |

**Note:** The date analysis includes an alternative query that uses the most recent enrollment date in the dataset as its reference point. This was necessary because the original query based on the current date returned no records with the available historical data.

## Analysis Report

The `analysis_report.md` file documents the actual query results, including:

- Students with low course completion rates.
- Enrollment records requiring instructor assignments.
- Records successfully inserted, updated, and deleted.
- Enrollment distribution across categories.
- Average completion percentages by course.
- Courses with more than three enrollments.
- Payment totals grouped by category.

The report makes the findings accessible without requiring readers to execute the SQL queries themselves.

## Database Execution & Validation

The SQL queries were executed using the Supabase SQL Editor.

Initial database checks were performed to verify the availability and structure of the `enrollments`, `students`, and `courses` tables.

Screenshots documenting the initial checks and successful database execution are included in the repository.

## Getting Started

This repository contains the SQL queries and analysis documentation. It does not include the original database creation script or a complete dataset.

To reproduce the analysis:

1. Create or access a Supabase project.
2. Set up the EduTrack database with the required tables and source records.
3. Open the Supabase SQL Editor.
4. Review and execute the queries in `queries.sql` against the prepared database.
5. Compare the results with the documented findings in `analysis_report.md`.

**Important:** The `INSERT`, `UPDATE`, and `DELETE` statements modify database records. Execute them against a suitable test database and review the affected records before running them.

## Project Scope

This project focuses on practical SQL skills and relational database auditing rather than application development.

It demonstrates the use of SQL to investigate data quality issues, perform controlled data modifications, generate aggregated results, and communicate findings through technical documentation.

---

**Developer Wendy Sanchez**
