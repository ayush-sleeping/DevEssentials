## MySQL Notes for Laravel Backend Developers

#### 📌 Learning Goals
- Write complex SQL queries manually when Eloquent isn't enough
- Understand what happens behind Laravel's Query Builder
- Optimize database performance in Laravel applications
- Know when to use raw SQL vs Eloquent vs Query Builder

<div id="top"></div>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->

### 📋 Table of Contents

| Section | Topic | Description | Priority |
|---------|-------|-------------|----------|
| **FOUNDATIONS** | | | |
| 1 | [MySQL Fundamentals](#mysql-fundamentals) | RDBMS concepts, MySQL vs other databases, when to use MySQL |  Critical |
| 2 | [Database Design Principles](#database-design-principles) | Normalization, denormalization, entity relationships |  Critical |
| 3 | [MySQL Data Types](#mysql-data-types) | Understanding all MySQL data types and when to use them |  Critical |
| 4 | [Laravel Database Configuration](#laravel-database-configuration) | .env setup, database connections, multiple databases |  Critical |
| **BASIC SQL OPERATIONS** | | | |
| 5 | [Creating Databases & Tables](#creating-databases--tables) | DDL commands: CREATE, ALTER, DROP + Laravel migrations |  Critical |
| 6 | [Data Insertion](#data-insertion) | INSERT statements + Laravel Query Builder insert methods |  Critical |
| 7 | [Data Selection Basics](#data-selection-basics) | SELECT statements, WHERE clauses + Laravel where() methods |  Critical |
| 8 | [Data Updates & Deletion](#data-updates--deletion) | UPDATE, DELETE statements + Laravel update/delete methods |  Critical |
| **INTERMEDIATE QUERIES** | | | |
| 9 | [Sorting & Limiting](#sorting--limiting) | ORDER BY, LIMIT, OFFSET + Laravel orderBy(), take(), skip() |  High Priority |
| 10 | [Filtering & Conditions](#filtering--conditions) | Complex WHERE conditions, IN, BETWEEN, LIKE + Laravel equivalents |  High Priority |
| 11 | [Grouping & Aggregation](#grouping--aggregation) | GROUP BY, HAVING, COUNT, SUM, AVG + Laravel groupBy(), aggregate functions |  High Priority |
| 12 | [Working with NULL Values](#working-with-null-values) | IS NULL, IFNULL, COALESCE + Laravel whereNull(), orWhereNull() |  High Priority |
| **ADVANCED QUERIES** | | | |
| 13 | [Subqueries](#subqueries) | Nested SELECT statements + Laravel subquery methods |  High Priority |
| 14 | [Common Table Expressions (CTEs)](#common-table-expressions-ctes) | WITH clauses for complex queries + Laravel CTE implementation |  Advanced |
| 15 | [Window Functions](#window-functions) | ROW_NUMBER, RANK, LAG, LEAD + Laravel raw expressions |  Advanced |
| 16 | [Case Statements](#case-statements) | Conditional logic in SQL + Laravel selectRaw with CASE |  High Priority |
| **RELATIONSHIPS & JOINS** | | | |
| 17 | [Understanding Relationships](#understanding-relationships) | One-to-One, One-to-Many, Many-to-Many concepts |  Critical |
| 18 | [INNER JOIN](#inner-join) | Basic joins + Laravel join() method |  Critical |
| 19 | [LEFT & RIGHT JOIN](#left--right-join) | Outer joins + Laravel leftJoin(), rightJoin() |  Critical |
| 20 | [FULL OUTER JOIN](#full-outer-join) | Complete outer joins + Laravel implementation |  High Priority |
| 21 | [SELF JOIN](#self-join) | Joining table with itself + Laravel self-referential relationships |  High Priority |
| 22 | [CROSS JOIN](#cross-join) | Cartesian products + Laravel crossJoin() |  Advanced |
| 23 | [Complex Multi-table Joins](#complex-multi-table-joins) | Joining 3+ tables + Laravel complex join scenarios |  High Priority |
| **CONSTRAINTS & INTEGRITY** | | | |
| 24 | [Primary Keys](#primary-keys) | AUTO_INCREMENT, composite keys + Laravel primary key definitions |  Critical |
| 25 | [Foreign Keys](#foreign-keys) | Referential integrity, CASCADE options + Laravel foreign key constraints |  Critical |
| 26 | [Unique Constraints](#unique-constraints) | UNIQUE keyword + Laravel unique validation and constraints |  High Priority |
| 27 | [Check Constraints](#check-constraints) | Data validation at DB level + Laravel custom constraints |  High Priority |
| 28 | [NOT NULL Constraints](#not-null-constraints) | Preventing null values + Laravel nullable() vs required fields |  High Priority |
| **INDEXES & PERFORMANCE** | | | |
| 29 | [Index Fundamentals](#index-fundamentals) | How indexes work, when to use them |  Critical |
| 30 | [Creating Indexes](#creating-indexes) | Single column, composite indexes + Laravel index() method |  High Priority |
| 31 | [Query Optimization](#query-optimization) | EXPLAIN plans, query analysis + Laravel query optimization |  High Priority |
| 32 | [Index Strategy](#index-strategy) | Choosing right indexes, avoiding over-indexing |  Advanced |
| **STORED PROCEDURES & FUNCTIONS** | | | |
| 33 | [Stored Procedures](#stored-procedures) | Creating and calling procedures + Laravel stored procedure calls |  Advanced |
| 34 | [User-Defined Functions](#user-defined-functions) | Custom MySQL functions + Laravel function calls |  Advanced |
| 35 | [Triggers](#triggers) | Database-level automation + Laravel event alternatives |  Advanced |
| **VIEWS & VIRTUAL TABLES** | | | |
| 36 | [Creating Views](#creating-views) | Virtual tables for complex queries + Laravel view usage |  High Priority |
| 37 | [Updatable Views](#updatable-views) | Modifying data through views + Laravel considerations |  Advanced |
| **TRANSACTIONS & CONCURRENCY** | | | |
| 38 | [Transaction Basics](#transaction-basics) | BEGIN, COMMIT, ROLLBACK + Laravel DB::transaction() |  Critical |
| 39 | [ACID Properties](#acid-properties) | Atomicity, Consistency, Isolation, Durability |  High Priority |
| 40 | [Isolation Levels](#isolation-levels) | READ COMMITTED, SERIALIZABLE + Laravel transaction isolation |  Advanced |
| 41 | [Deadlock Handling](#deadlock-handling) | Preventing and resolving deadlocks + Laravel retry mechanisms |  Advanced |
| **LARAVEL SPECIFIC INTEGRATION** | | | |
| 42 | [Raw SQL in Laravel](#raw-sql-in-laravel) | DB::select(), DB::statement() - when and how to use |  Critical |
| 43 | [Query Builder vs Eloquent](#query-builder-vs-eloquent) | When to use each approach, performance considerations |  Critical |
| 44 | [Complex Laravel Queries](#complex-laravel-queries) | Combining raw SQL with Query Builder, selectRaw(), whereRaw() |  High Priority |
| 45 | [Laravel Query Scopes](#laravel-query-scopes) | Local and global scopes for reusable query logic |  High Priority |
| 46 | [Database Migrations Advanced](#database-migrations-advanced) | Complex migrations, data migrations, schema changes |  High Priority |
| **PERFORMANCE & OPTIMIZATION** | | | |
| 47 | [Query Performance Analysis](#query-performance-analysis) | Using EXPLAIN, slow query log + Laravel Debugbar, Telescope |  High Priority |
| 48 | [Laravel Query Optimization](#laravel-query-optimization) | N+1 problems, eager loading, lazy loading strategies |  Critical |
| 49 | [Database Connection Optimization](#database-connection-optimization) | Connection pooling, persistent connections + Laravel configuration |  Advanced |
| 50 | [Caching Strategies](#caching-strategies) | Query result caching, Redis integration + Laravel cache |  High Priority |
| **ADVANCED MYSQL FEATURES** | | | |
| 51 | [Full-Text Search](#full-text-search) | MATCH AGAINST + Laravel Scout integration |  High Priority |
| 52 | [JSON Data Types](#json-data-types) | Working with JSON columns + Laravel JSON operations |  High Priority |
| 53 | [Partitioning](#partitioning) | Table partitioning strategies + Laravel considerations |  Advanced |
| 54 | [Replication](#replication) | Master-slave setup + Laravel read/write connections |  Advanced |
| **SECURITY & BEST PRACTICES** | | | |
| 55 | [SQL Injection Prevention](#sql-injection-prevention) | Prepared statements + Laravel parameter binding |  Critical |
| 56 | [User Management](#user-management) | MySQL users, privileges + Laravel database security |  High Priority |
| 57 | [Data Backup & Recovery](#data-backup--recovery) | mysqldump, restoration + Laravel backup packages |  High Priority |
| **TESTING & DEBUGGING** | | | |
| 58 | [Database Testing](#database-testing) | Test databases, transactions in tests + Laravel testing |  High Priority |
| 59 | [Query Debugging](#query-debugging) | MySQL logs, Laravel query logging, debugging techniques |  High Priority |
| **REAL-WORLD SCENARIOS** | | | |
| 60 | [Complex Reporting Queries](#complex-reporting-queries) | Analytics queries, dashboard data + Laravel reporting |  Advanced |
| 61 | [Data Migration & ETL](#data-migration--etl) | Moving data between systems + Laravel data processing |  High Priority |
| 62 | [Multi-tenant Applications](#multi-tenant-applications) | Database strategies for multi-tenancy + Laravel implementation |  Advanced |




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### MySQL Fundamentals
