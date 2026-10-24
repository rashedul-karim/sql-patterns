# SQL Patterns

One problem, four dialects: PostgreSQL, SQL Server (T-SQL), Oracle and Spark SQL.

Each pattern solves the same problem in all four, then compares the execution plans:
where the optimizers agree, where they differ, and what that means when moving a
workload from an on-premises database to a lakehouse.

> **Status:** planned. Patterns are added after the current lakehouse project.

## Planned patterns
| # | Pattern | What the comparison shows |
|---|---|---|
| 1 | Top-N per group | Window functions vs LATERAL / CROSS APPLY, and how Spark handles both |
| 2 | Upsert | ON CONFLICT vs MERGE in three engines vs Delta Lake MERGE |
| 3 | Slowly changing dimension type 2 | The same history load in an OLTP database and in Delta |
| 4 | Running totals over time | RANGE frames by engine, and the Spark equivalent |
| 5 | Deduplication | ROW_NUMBER vs QUALIFY vs DISTINCT ON |

## How each pattern is laid out
pattern-name/
  README.md        Problem, sample data, results and plan comparison
  postgres.sql
  sqlserver.sql
  oracle.sql
  spark.sql        Run on Databricks
