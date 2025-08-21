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

🔹 Concept
- **RDBMS (Relational Database Management System)**: Stores data in tables with rows and columns; supports relationships, transactions, and constraints.
- **MySQL vs Other Databases**:
	- MySQL: Open-source, widely used, great for web apps, strong community.
	- PostgreSQL: Advanced features (CTEs, window functions), strict standards.
	- SQLite: Lightweight, file-based, good for prototyping.
	- MongoDB: NoSQL, document-based, flexible schema.
- **When to Use MySQL**:
	- Structured data, ACID compliance, joins, transactions, scalability.
	- Most PHP/Laravel apps, WordPress, e-commerce, analytics.

💻 Example (Connect to MySQL):
```sql
-- Connect using CLI
mysql -u root -p
```

💻 Example (Basic Table Creation):
```sql
CREATE TABLE users (
	id INT AUTO_INCREMENT PRIMARY KEY,
	name VARCHAR(100),
	email VARCHAR(100) UNIQUE
);
```

💻 Example (Laravel Eloquent Model):
```php
// app/Models/User.php
class User extends Model {}
```


<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Database Design Principles

🔹 Concept
- **Normalization**: Organize data to reduce redundancy and improve integrity (1NF, 2NF, 3NF).
- **Denormalization**: Add redundancy for performance (faster reads, fewer joins).
- **Entity Relationships**:
	- One-to-One: Each row in Table A relates to one in Table B.
	- One-to-Many: One row in Table A relates to many in Table B.
	- Many-to-Many: Rows in Table A relate to many in Table B via a pivot table.
- **Best Practices**:
	- Use primary keys and foreign keys
	- Avoid storing duplicate data
	- Index columns used in joins/searches

💻 Example (Normalization):
```sql
-- Split user and address into separate tables
CREATE TABLE users (
	id INT PRIMARY KEY,
	name VARCHAR(100)
);
CREATE TABLE addresses (
	id INT PRIMARY KEY,
	user_id INT,
	address VARCHAR(255),
	FOREIGN KEY (user_id) REFERENCES users(id)
);
```

💻 Example (Many-to-Many Relationship):
```sql
CREATE TABLE user_roles (
	user_id INT,
	role_id INT,
	PRIMARY KEY (user_id, role_id)
);
```

💻 Example (Laravel Migration for Relationship):
```php
Schema::create('addresses', function (Blueprint $table) {
	$table->id();
	$table->unsignedBigInteger('user_id');
	$table->string('address');
	$table->foreign('user_id')->references('id')->on('users');
});
```


<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### MySQL Data Types

🔹 Concept
- **Numeric Types**:
	- INT, BIGINT: Whole numbers
	- DECIMAL, FLOAT, DOUBLE: Decimal numbers
- **String Types**:
	- VARCHAR(n): Variable-length string (up to n chars)
	- CHAR(n): Fixed-length string
	- TEXT, MEDIUMTEXT, LONGTEXT: Large text
- **Date & Time Types**:
	- DATE, DATETIME, TIMESTAMP, TIME, YEAR
- **Other Types**:
	- BOOLEAN (TINYINT(1)), ENUM, SET
	- BLOB: Binary data (images, files)
- **Choosing Data Types**:
	- Use smallest type that fits your data
	- Use VARCHAR for emails, TEXT for descriptions
	- Use INT for IDs, DECIMAL for money

💻 Example (Table with Various Data Types):
```sql
CREATE TABLE products (
	id INT PRIMARY KEY,
	name VARCHAR(100),
	price DECIMAL(10,2),
	in_stock BOOLEAN,
	created_at DATETIME
);
```

💻 Example (Laravel Migration):
```php
Schema::create('products', function (Blueprint $table) {
	$table->id();
	$table->string('name', 100);
	$table->decimal('price', 10, 2);
	$table->boolean('in_stock');
	$table->dateTime('created_at');
});
```


<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Laravel Database Configuration

🔹 Concept
- **.env Setup**: Store DB credentials in `.env` file for security.
- **Database Connections**:
	- Configure in `config/database.php`
	- Supports MySQL, SQLite, PostgreSQL, SQL Server
- **Multiple Databases**:
	- Define multiple connections in config
	- Use `DB::connection('mysql2')->select(...)`
- **Best Practices**:
	- Never commit `.env` with secrets
	- Use environment variables for credentials
	- Test connection with `php artisan migrate`

💻 Example (.env file):
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=myapp
DB_USERNAME=root
DB_PASSWORD=secret
```

💻 Example (config/database.php):
```php
'connections' => [
	'mysql' => [
		'driver' => 'mysql',
		'host' => env('DB_HOST', '127.0.0.1'),
		'database' => env('DB_DATABASE', 'forge'),
		'username' => env('DB_USERNAME', 'forge'),
		'password' => env('DB_PASSWORD', ''),
		// ...other options
	],
	'mysql2' => [
		'driver' => 'mysql',
		'host' => env('DB_HOST2', '127.0.0.1'),
		'database' => env('DB_DATABASE2', 'forge'),
		'username' => env('DB_USERNAME2', 'forge'),
		'password' => env('DB_PASSWORD2', ''),
		// ...other options
	],
]
```

💻 Example (Switching Connections):
```php
$users = DB::connection('mysql2')->table('users')->get();
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Creating Databases and Tables

🔹 Concept
- **DDL (Data Definition Language)**: SQL commands to define and modify database structure.
- **Common Operations**:
	- CREATE DATABASE, CREATE TABLE
	- ALTER TABLE (add/drop columns, change types)
	- DROP TABLE, DROP DATABASE
- **Laravel Migrations**: Version-controlled schema changes using PHP code.

💻 Example (Create Database):
```sql
CREATE DATABASE myapp;
```

💻 Example (Create Table):
```sql
CREATE TABLE users (
	id INT AUTO_INCREMENT PRIMARY KEY,
	name VARCHAR(100),
	email VARCHAR(100) UNIQUE
);
```

💻 Example (Alter Table):
```sql
ALTER TABLE users ADD COLUMN age INT;
```

💻 Example (Drop Table):
```sql
DROP TABLE users;
```

💻 Example (Laravel Migration):
```php
Schema::create('users', function (Blueprint $table) {
	$table->id();
	$table->string('name');
	$table->string('email')->unique();
});
```

💻 Example (Laravel Migration - Add Column):
```php
Schema::table('users', function (Blueprint $table) {
	$table->integer('age')->nullable();
});
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Data Insertion

🔹 Concept
- **INSERT Statement**: Add new rows to a table.
- **Bulk Insert**: Insert multiple rows at once.
- **Laravel Query Builder/Eloquent**: Insert data using PHP methods.

💻 Example (SQL Insert):
```sql
INSERT INTO users (name, email) VALUES ('Ayush', 'ayush@example.com');
```

💻 Example (Bulk Insert):
```sql
INSERT INTO users (name, email) VALUES
	('Sam', 'sam@example.com'),
	('Alex', 'alex@example.com');
```

💻 Example (Laravel Eloquent):
```php
User::create(['name' => 'Ayush', 'email' => 'ayush@example.com']);
```

💻 Example (Laravel Query Builder):
```php
DB::table('users')->insert([
	['name' => 'Sam', 'email' => 'sam@example.com'],
	['name' => 'Alex', 'email' => 'alex@example.com'],
]);
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Data Selection Basics

🔹 Concept
- **SELECT Statement**: Retrieve data from tables.
- **WHERE Clause**: Filter results based on conditions.
- **Laravel Eloquent/Query Builder**: Fetch data using PHP methods.

💻 Example (SQL Select All):
```sql
SELECT * FROM users;
```

💻 Example (SQL Select with Condition):
```sql
SELECT * FROM users WHERE email = 'ayush@example.com';
```

💻 Example (Laravel Eloquent):
```php
$users = User::all();
$user = User::where('email', 'ayush@example.com')->first();
```

💻 Example (Laravel Query Builder):
```php
$users = DB::table('users')->get();
$user = DB::table('users')->where('email', 'ayush@example.com')->first();
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Data Updates and Deletion

🔹 Concept
- **UPDATE Statement**: Modify existing rows.
- **DELETE Statement**: Remove rows from a table.
- **Laravel Eloquent/Query Builder**: Update/delete using PHP methods.

💻 Example (SQL Update):
```sql
UPDATE users SET name = 'Ayush Mishra' WHERE email = 'ayush@example.com';
```

💻 Example (SQL Delete):
```sql
DELETE FROM users WHERE email = 'alex@example.com';
```

💻 Example (Laravel Eloquent Update):
```php
$user = User::where('email', 'ayush@example.com')->first();
$user->name = 'Ayush Mishra';
$user->save();
```

💻 Example (Laravel Eloquent Delete):
```php
$user = User::where('email', 'alex@example.com')->first();
$user->delete();
```

💻 Example (Laravel Query Builder Update/Delete):
```php
DB::table('users')->where('email', 'ayush@example.com')->update(['name' => 'Ayush Mishra']);
DB::table('users')->where('email', 'alex@example.com')->delete();
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Sorting and Limiting

🔹 Concept
- **ORDER BY**: Sort results by one or more columns.
- **LIMIT/OFFSET**: Restrict number of rows returned, paginate results.
- **Laravel Eloquent/Query Builder**: Use `orderBy()`, `limit()`, `offset()`, `take()`, `skip()`.

💻 Example (SQL Sort & Limit):
```sql
SELECT * FROM users ORDER BY name ASC LIMIT 5 OFFSET 10;
```

💻 Example (Laravel Eloquent):
```php
$users = User::orderBy('name', 'asc')->skip(10)->take(5)->get();
```

💻 Example (Laravel Query Builder):
```php
$users = DB::table('users')->orderBy('name')->offset(10)->limit(5)->get();
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Filtering and Conditions

🔹 Concept
- **WHERE**: Filter rows based on conditions.
- **IN, BETWEEN, LIKE**: Advanced filtering operators.
- **Laravel Eloquent/Query Builder**: Use `where()`, `whereIn()`, `whereBetween()`, `whereLike()`.

💻 Example (SQL IN):
```sql
SELECT * FROM users WHERE id IN (1, 2, 3);
```

💻 Example (SQL BETWEEN):
```sql
SELECT * FROM products WHERE price BETWEEN 100 AND 500;
```

💻 Example (SQL LIKE):
```sql
SELECT * FROM users WHERE name LIKE 'Ayu%';
```

💻 Example (Laravel Eloquent):
```php
$users = User::whereIn('id', [1,2,3])->get();
$products = Product::whereBetween('price', [100, 500])->get();
$usersLike = User::where('name', 'like', 'Ayu%')->get();
```

💻 Example (Laravel Query Builder):
```php
$users = DB::table('users')->whereIn('id', [1,2,3])->get();
$products = DB::table('products')->whereBetween('price', [100, 500])->get();
$usersLike = DB::table('users')->where('name', 'like', 'Ayu%')->get();
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Grouping and Aggregation

🔹 Concept
- **GROUP BY**: Group rows by column values.
- **HAVING**: Filter groups based on aggregate conditions.
- **Aggregate Functions**: COUNT, SUM, AVG, MIN, MAX.
- **Laravel Eloquent/Query Builder**: Use `groupBy()`, aggregate methods.

💻 Example (SQL Group & Count):
```sql
SELECT role, COUNT(*) as total FROM users GROUP BY role;
```

💻 Example (SQL HAVING):
```sql
SELECT role, COUNT(*) as total FROM users GROUP BY role HAVING total > 5;
```

💻 Example (SQL SUM/AVG):
```sql
SELECT AVG(price) FROM products;
SELECT SUM(price) FROM products;
```

💻 Example (Laravel Eloquent):
```php
$roleCounts = User::select('role', DB::raw('count(*) as total'))->groupBy('role')->get();
$rolesHaving = User::select('role', DB::raw('count(*) as total'))
	->groupBy('role')->having('total', '>', 5)->get();
$avgPrice = Product::avg('price');
$sumPrice = Product::sum('price');
```

💻 Example (Laravel Query Builder):
```php
$roleCounts = DB::table('users')->select('role', DB::raw('count(*) as total'))->groupBy('role')->get();
$rolesHaving = DB::table('users')->select('role', DB::raw('count(*) as total'))
	->groupBy('role')->having('total', '>', 5)->get();
$avgPrice = DB::table('products')->avg('price');
$sumPrice = DB::table('products')->sum('price');
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Working with NULL Values

🔹 Concept
- **IS NULL/IS NOT NULL**: Check for missing values.
- **IFNULL, COALESCE**: Replace NULLs with default values.
- **Laravel Eloquent/Query Builder**: Use `whereNull()`, `whereNotNull()`, `selectRaw()`.

💻 Example (SQL IS NULL):
```sql
SELECT * FROM users WHERE age IS NULL;
```

💻 Example (SQL COALESCE):
```sql
SELECT name, COALESCE(age, 0) as age FROM users;
```

💻 Example (Laravel Eloquent):
```php
$usersNull = User::whereNull('age')->get();
$usersNotNull = User::whereNotNull('age')->get();
$usersWithDefaultAge = User::select('name', DB::raw('COALESCE(age, 0) as age'))->get();
```

💻 Example (Laravel Query Builder):
```php
$usersNull = DB::table('users')->whereNull('age')->get();
$usersNotNull = DB::table('users')->whereNotNull('age')->get();
$usersWithDefaultAge = DB::table('users')->select('name', DB::raw('COALESCE(age, 0) as age'))->get();
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Subqueries

🔹 Concept
- **Subquery**: A query nested inside another query (SELECT, WHERE, FROM, etc.).
- **Use Cases**: Filtering, aggregation, complex conditions.
- **Laravel Eloquent/Query Builder**: Use closures, selectSub(), whereIn(), or raw SQL.

💻 Example (SQL Subquery in WHERE):
```sql
SELECT * FROM products WHERE price > (SELECT AVG(price) FROM products);
```

💻 Example (SQL Subquery in SELECT):
```sql
SELECT name, (SELECT COUNT(*) FROM orders WHERE orders.user_id = users.id) as order_count FROM users;
```

💻 Example (Laravel Eloquent - whereIn with subquery):
```php
$avgPrice = Product::avg('price');
$products = Product::where('price', '>', $avgPrice)->get();
```

💻 Example (Laravel Query Builder - selectSub):
```php
$users = DB::table('users')
	->select('name')
	->selectSub(function($query) {
		$query->from('orders')->selectRaw('COUNT(*)')->whereColumn('orders.user_id', 'users.id');
	}, 'order_count')
	->get();
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Common Table Expressions

🔹 Concept
- **CTE (Common Table Expression)**: Temporary named result set using WITH clause for complex queries.
- **Use Cases**: Recursive queries, breaking down complex logic.
- **Laravel**: Use DB::statement() for raw CTEs, or selectRaw().

💻 Example (SQL CTE):
```sql
WITH high_value_orders AS (
	SELECT * FROM orders WHERE amount > 1000
)
SELECT * FROM high_value_orders WHERE status = 'completed';
```

💻 Example (Recursive CTE):
```sql
WITH RECURSIVE category_tree AS (
	SELECT id, name, parent_id FROM categories WHERE parent_id IS NULL
	UNION ALL
	SELECT c.id, c.name, c.parent_id FROM categories c
	INNER JOIN category_tree ct ON c.parent_id = ct.id
)
SELECT * FROM category_tree;
```

💻 Example (Laravel Raw CTE):
```php
$orders = DB::select('WITH high_value_orders AS (SELECT * FROM orders WHERE amount > 1000) SELECT * FROM high_value_orders WHERE status = "completed"');
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Window Functions

🔹 Concept
- **Window Functions**: Perform calculations across rows related to the current row (ROW_NUMBER, RANK, LAG, LEAD, etc.).
- **Use Cases**: Ranking, running totals, comparisons.
- **Laravel**: Use selectRaw() for window functions.

💻 Example (SQL ROW_NUMBER):
```sql
SELECT id, name, ROW_NUMBER() OVER (ORDER BY created_at) as row_num FROM users;
```

💻 Example (SQL RANK):
```sql
SELECT id, name, RANK() OVER (ORDER BY score DESC) as rank FROM users;
```

💻 Example (SQL LAG/LEAD):
```sql
SELECT id, name, LAG(score) OVER (ORDER BY id) as prev_score, LEAD(score) OVER (ORDER BY id) as next_score FROM users;
```

💻 Example (Laravel selectRaw):
```php
$users = User::select('id', 'name', DB::raw('ROW_NUMBER() OVER (ORDER BY created_at) as row_num'))->get();
$usersRank = User::select('id', 'name', DB::raw('RANK() OVER (ORDER BY score DESC) as rank'))->get();
$usersLagLead = User::select('id', 'name', DB::raw('LAG(score) OVER (ORDER BY id) as prev_score, LEAD(score) OVER (ORDER BY id) as next_score'))->get();
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Case Statements

🔹 Concept
- **CASE Statement**: Conditional logic in SQL queries (if/else for columns).
- **Use Cases**: Custom labels, computed columns, conditional aggregation.
- **Laravel**: Use selectRaw() for CASE logic.

💻 Example (SQL CASE in SELECT):
```sql
SELECT name, CASE WHEN age >= 18 THEN 'Adult' ELSE 'Minor' END as age_group FROM users;
```

💻 Example (SQL CASE in Aggregation):
```sql
SELECT COUNT(CASE WHEN status = 'active' THEN 1 END) as active_count FROM users;
```

💻 Example (Laravel selectRaw CASE):
```php
$users = User::select('name', DB::raw("CASE WHEN age >= 18 THEN 'Adult' ELSE 'Minor' END as age_group"))->get();
$activeCount = User::select(DB::raw("COUNT(CASE WHEN status = 'active' THEN 1 END) as active_count"))->first();
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Understanding Relationships

🔹 Concept
- **One-to-One**: Each row in Table A relates to one in Table B.
- **One-to-Many**: One row in Table A relates to many in Table B.
- **Many-to-Many**: Rows in Table A relate to many in Table B via a pivot table.
- **Laravel Eloquent**: Define relationships in models using `hasOne`, `hasMany`, `belongsTo`, `belongsToMany`.

💻 Example (SQL One-to-One):
```sql
-- users and profiles (one profile per user)
CREATE TABLE users (
	id INT PRIMARY KEY,
	name VARCHAR(100)
);
CREATE TABLE profiles (
	id INT PRIMARY KEY,
	user_id INT UNIQUE,
	bio TEXT,
	FOREIGN KEY (user_id) REFERENCES users(id)
);
```

💻 Example (Laravel Eloquent One-to-One):
```php
// User.php
public function profile() {
	return $this->hasOne(Profile::class);
}

// Profile.php
public function user() {
	return $this->belongsTo(User::class);
}
```

💻 Example (SQL One-to-Many):
```sql
-- users and posts (one user, many posts)
CREATE TABLE posts (
	id INT PRIMARY KEY,
	user_id INT,
	title VARCHAR(255),
	FOREIGN KEY (user_id) REFERENCES users(id)
);
```

💻 Example (Laravel Eloquent One-to-Many):
```php
// User.php
public function posts() {
	return $this->hasMany(Post::class);
}

// Post.php
public function user() {
	return $this->belongsTo(User::class);
}
```

💻 Example (SQL Many-to-Many):
```sql
-- users and roles (pivot table user_roles)
CREATE TABLE roles (
	id INT PRIMARY KEY,
	name VARCHAR(50)
);
CREATE TABLE user_roles (
	user_id INT,
	role_id INT,
	PRIMARY KEY (user_id, role_id),
	FOREIGN KEY (user_id) REFERENCES users(id),
	FOREIGN KEY (role_id) REFERENCES roles(id)
);
```

💻 Example (Laravel Eloquent Many-to-Many):
```php
// User.php
public function roles() {
	return $this->belongsToMany(Role::class);
}

// Role.php
public function users() {
	return $this->belongsToMany(User::class);
}
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### INNER JOIN

🔹 Concept
- **INNER JOIN**: Returns rows with matching values in both tables.
- **Use Cases**: Combine related data from multiple tables.
- **Laravel**: Use `join()` in Query Builder, or Eloquent relationships.

💻 Example (SQL INNER JOIN):
```sql
SELECT users.name, posts.title
FROM users
INNER JOIN posts ON users.id = posts.user_id;
```

💻 Example (Laravel Query Builder INNER JOIN):
```php
$results = DB::table('users')
	->join('posts', 'users.id', '=', 'posts.user_id')
	->select('users.name', 'posts.title')
	->get();
```

💻 Example (Laravel Eloquent Relationship):
```php
// Get all posts with user info
$posts = Post::with('user')->get();
foreach ($posts as $post) {
	echo $post->user->name . ': ' . $post->title;
}
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### LEFT and RIGHT JOIN

🔹 Concept
- **LEFT JOIN**: Returns all rows from the left table, and matched rows from the right table.
- **RIGHT JOIN**: Returns all rows from the right table, and matched rows from the left table.
- **Use Cases**: Find unmatched records, include all from one side.
- **Laravel**: Use `leftJoin()`, `rightJoin()` in Query Builder.

💻 Example (SQL LEFT JOIN):
```sql
SELECT users.name, posts.title
FROM users
LEFT JOIN posts ON users.id = posts.user_id;
```

💻 Example (SQL RIGHT JOIN):
```sql
SELECT users.name, posts.title
FROM users
RIGHT JOIN posts ON users.id = posts.user_id;
```

💻 Example (Laravel Query Builder LEFT JOIN):
```php
$results = DB::table('users')
	->leftJoin('posts', 'users.id', '=', 'posts.user_id')
	->select('users.name', 'posts.title')
	->get();
```

💻 Example (Laravel Query Builder RIGHT JOIN):
```php
$results = DB::table('users')
	->rightJoin('posts', 'users.id', '=', 'posts.user_id')
	->select('users.name', 'posts.title')
	->get();
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### FULL OUTER JOIN

🔹 Concept
- **FULL OUTER JOIN**: Returns all rows when there is a match in either table.
- **Note**: MySQL does not support FULL OUTER JOIN directly; use UNION of LEFT and RIGHT JOINs.
- **Laravel**: Use raw SQL with `DB::select()`.

💻 Example (SQL FULL OUTER JOIN workaround):
```sql
SELECT users.name, posts.title
FROM users
LEFT JOIN posts ON users.id = posts.user_id
UNION
SELECT users.name, posts.title
FROM users
RIGHT JOIN posts ON users.id = posts.user_id;
```

💻 Example (Laravel Raw SQL FULL OUTER JOIN):
```php
$results = DB::select("
	SELECT users.name, posts.title
	FROM users
	LEFT JOIN posts ON users.id = posts.user_id
	UNION
	SELECT users.name, posts.title
	FROM users
	RIGHT JOIN posts ON users.id = posts.user_id
");
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->



### SELF JOIN

🔹 Concept
- **SELF JOIN**: Join a table with itself to compare rows within the same table.
- **Use Cases**: Hierarchies, parent-child relationships, finding related records.
- **Laravel**: Use Query Builder with aliases; Eloquent for self-referential relationships.

💻 Example (SQL SELF JOIN):
```sql
SELECT e1.id, e1.name AS employee, e2.name AS manager
FROM employees e1
LEFT JOIN employees e2 ON e1.manager_id = e2.id;
```

💻 Example (Laravel Eloquent Self-Referential):
```php
// Employee.php
public function manager() {
	return $this->belongsTo(Employee::class, 'manager_id');
}
public function subordinates() {
	return $this->hasMany(Employee::class, 'manager_id');
}
```

💻 Example (Laravel Query Builder SELF JOIN):
```php
$results = DB::table('employees as e1')
	->leftJoin('employees as e2', 'e1.manager_id', '=', 'e2.id')
	->select('e1.id', 'e1.name as employee', 'e2.name as manager')
	->get();
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->



### CROSS JOIN

🔹 Concept
- **CROSS JOIN**: Returns the Cartesian product of two tables (all possible combinations).
- **Use Cases**: Combinatorial queries, pairing every row from two tables.
- **Laravel**: Use `crossJoin()` in Query Builder.

💻 Example (SQL CROSS JOIN):
```sql
SELECT a.name, b.name
FROM table_a a
CROSS JOIN table_b b;
```

💻 Example (Laravel Query Builder CROSS JOIN):
```php
$results = DB::table('table_a')
	->crossJoin('table_b')
	->select('table_a.name', 'table_b.name')
	->get();
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->



### Complex Multi table Joins

🔹 Concept
- **Multi-table Joins**: Join three or more tables to fetch related data.
- **Use Cases**: Reporting, analytics, combining data from multiple sources.
- **Laravel**: Chain multiple `join()`/`leftJoin()` calls in Query Builder; Eloquent with nested relationships.

💻 Example (SQL Multi-table JOIN):
```sql
SELECT users.name, posts.title, comments.body
FROM users
INNER JOIN posts ON users.id = posts.user_id
INNER JOIN comments ON posts.id = comments.post_id;
```

💻 Example (Laravel Query Builder Multi-table JOIN):
```php
$results = DB::table('users')
	->join('posts', 'users.id', '=', 'posts.user_id')
	->join('comments', 'posts.id', '=', 'comments.post_id')
	->select('users.name', 'posts.title', 'comments.body')
	->get();
```

💻 Example (Laravel Eloquent Nested Relationships):
```php
// User.php
public function posts() {
	return $this->hasMany(Post::class);
}
// Post.php
public function comments() {
	return $this->hasMany(Comment::class);
}
// Usage
$users = User::with('posts.comments')->get();
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Primary Keys

🔹 Concept
- **Primary Key**: Uniquely identifies each row in a table.
- **AUTO_INCREMENT**: Automatically generates unique values.
- **Composite Key**: Combination of two or more columns as a primary key.
- **Laravel**: `$table->id()`, `$table->primary()`, `$table->increments()`

💻 Example (SQL Primary Key):
```sql
CREATE TABLE users (
	id INT AUTO_INCREMENT PRIMARY KEY,
	name VARCHAR(100)
);
```

💻 Example (SQL Composite Primary Key):
```sql
CREATE TABLE user_roles (
	user_id INT,
	role_id INT,
	PRIMARY KEY (user_id, role_id)
);
```

💻 Example (Laravel Migration Primary Key):
```php
Schema::create('users', function (Blueprint $table) {
	$table->id();
	$table->string('name');
});
```

💻 Example (Laravel Migration Composite Key):
```php
Schema::create('user_roles', function (Blueprint $table) {
	$table->unsignedBigInteger('user_id');
	$table->unsignedBigInteger('role_id');
	$table->primary(['user_id', 'role_id']);
});
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Foreign Keys

🔹 Concept
- **Foreign Key**: Enforces referential integrity between tables.
- **CASCADE**: Automatically updates/deletes related rows.
- **Laravel**: `$table->foreign()`, `onDelete('cascade')`, `onUpdate('cascade')`

💻 Example (SQL Foreign Key with CASCADE):
```sql
CREATE TABLE posts (
	id INT PRIMARY KEY,
	user_id INT,
	FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE ON UPDATE CASCADE
);
```

💻 Example (Laravel Migration Foreign Key):
```php
Schema::create('posts', function (Blueprint $table) {
	$table->id();
	$table->unsignedBigInteger('user_id');
	$table->foreign('user_id')
		->references('id')->on('users')
		->onDelete('cascade')
		->onUpdate('cascade');
});
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Unique Constraints

🔹 Concept
- **UNIQUE Constraint**: Ensures all values in a column (or group of columns) are unique.
- **Laravel**: `$table->unique()`, validation rules.

💻 Example (SQL UNIQUE Constraint):
```sql
CREATE TABLE users (
	id INT PRIMARY KEY,
	email VARCHAR(100) UNIQUE
);
```

💻 Example (SQL Multi-column UNIQUE Constraint):
```sql
CREATE TABLE products (
	id INT PRIMARY KEY,
	name VARCHAR(100),
	sku VARCHAR(50),
	UNIQUE (name, sku)
);
```

💻 Example (Laravel Migration UNIQUE Constraint):
```php
Schema::create('users', function (Blueprint $table) {
	$table->id();
	$table->string('email')->unique();
});
```

💻 Example (Laravel Migration Multi-column UNIQUE):
```php
Schema::create('products', function (Blueprint $table) {
	$table->id();
	$table->string('name');
	$table->string('sku');
	$table->unique(['name', 'sku']);
});
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Check Constraints

🔹 Concept
- **CHECK Constraint**: Validates data based on a condition.
- **Laravel**: `$table->check()` (Laravel 8+), or raw SQL.

💻 Example (SQL CHECK Constraint):
```sql
CREATE TABLE employees (
	id INT PRIMARY KEY,
	age INT,
	CHECK (age >= 18)
);
```

💻 Example (Laravel Migration CHECK Constraint):
```php
Schema::create('employees', function (Blueprint $table) {
	$table->id();
	$table->integer('age');
	$table->check('age >= 18');
});
```

💻 Example (Laravel Migration Raw CHECK):
```php
DB::statement('ALTER TABLE employees ADD CONSTRAINT chk_age CHECK (age >= 18)');
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### NOT NULL Constraints

🔹 Concept
- **NOT NULL**: Prevents columns from having NULL values.
- **Laravel**: Default is NOT NULL unless `nullable()` is used.

💻 Example (SQL NOT NULL Constraint):
```sql
CREATE TABLE products (
	id INT PRIMARY KEY,
	name VARCHAR(100) NOT NULL,
	price DECIMAL(10,2) NOT NULL
);
```

💻 Example (Laravel Migration NOT NULL):
```php
Schema::create('products', function (Blueprint $table) {
	$table->id();
	$table->string('name'); // NOT NULL by default
	$table->decimal('price', 10, 2); // NOT NULL by default
});
```

💻 Example (Laravel Migration Nullable):
```php
Schema::table('products', function (Blueprint $table) {
	$table->string('description')->nullable();
});
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Index Fundamentals

🔹 Concept
- **Index**: Data structure that speeds up searches and queries on a table.
- **Types**: Primary, unique, composite, full-text, spatial.
- **How Indexes Work**: B-tree, hash, etc. Indexes allow fast lookup but slow down writes.
- **When to Use**: On columns used in WHERE, JOIN, ORDER BY, and frequently searched.

💻 Example (SQL Index Info):
```sql
SHOW INDEX FROM users;
```

💻 Example (SQL Create Index):
```sql
CREATE INDEX idx_email ON users(email);
```

💻 Example (Laravel Migration Index):
```php
Schema::table('users', function (Blueprint $table) {
	$table->index('email');
});
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Creating Indexes

🔹 Concept
- **Single Column Index**: Index on one column.
- **Composite Index**: Index on multiple columns.
- **Unique Index**: Ensures values are unique.
- **Laravel**: `$table->index()`, `$table->unique()`, `$table->primary()`

💻 Example (SQL Single Column Index):
```sql
CREATE INDEX idx_name ON products(name);
```

💻 Example (SQL Composite Index):
```sql
CREATE INDEX idx_name_price ON products(name, price);
```

💻 Example (SQL Unique Index):
```sql
CREATE UNIQUE INDEX idx_email ON users(email);
```

💻 Example (Laravel Migration Single/Composite/Unique Index):
```php
Schema::table('products', function (Blueprint $table) {
	$table->index('name');
	$table->index(['name', 'price']);
});
Schema::table('users', function (Blueprint $table) {
	$table->unique('email');
});
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Query Optimization

🔹 Concept
- **Query Optimization**: Improving query speed and efficiency.
- **EXPLAIN**: Shows how MySQL executes a query.
- **Analyze Queries**: Look for full table scans, missing indexes, slow queries.
- **Laravel**: Use `DB::select('EXPLAIN ...')`, Laravel Debugbar, Telescope.

💻 Example (SQL EXPLAIN):
```sql
EXPLAIN SELECT * FROM users WHERE email = 'ayush@example.com';
```

💻 Example (SQL Analyze Table):
```sql
ANALYZE TABLE users;
```

💻 Example (Laravel Query Optimization):
```php
// Get query plan
$plan = DB::select('EXPLAIN SELECT * FROM users WHERE email = ?', ['ayush@example.com']);

// Use Laravel Debugbar/Telescope for query analysis
// Debugbar: barryvdh/laravel-debugbar
// Telescope: laravel/telescope
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->



### Index Strategy

🔹 Concept
- **Best Practices**: Index columns used in WHERE, JOIN, ORDER BY.
- **Avoid Over-indexing**: Too many indexes slow down INSERT/UPDATE/DELETE.
- **Drop Unused Indexes**: Remove indexes not used by queries.
- **Composite Index Order**: Place most selective column first.
- **Monitor Performance**: Use slow query log, EXPLAIN, and query profiling.

💻 Example (SQL Drop Index):
```sql
DROP INDEX idx_email ON users;
```

💻 Example (SQL Find Unused Indexes):
```sql
SELECT * FROM information_schema.statistics WHERE table_schema = 'myapp' AND table_name = 'users';
```

💻 Example (Laravel Migration Drop Index):
```php
Schema::table('users', function (Blueprint $table) {
	$table->dropIndex(['email']);
});
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Stored Procedures

🔹 Concept
- **Stored Procedure**: Predefined set of SQL statements stored in the database, can be called with parameters.
- **Use Cases**: Encapsulate business logic, reusable operations, batch processing.
- **Laravel**: Use `DB::select()`, `DB::statement()` to call procedures.

💻 Example (SQL Create Procedure):
```sql
DELIMITER //
CREATE PROCEDURE GetUserByEmail(IN user_email VARCHAR(100))
BEGIN
	SELECT * FROM users WHERE email = user_email;
END //
DELIMITER ;
```

💻 Example (SQL Call Procedure):
```sql
CALL GetUserByEmail('ayush@example.com');
```

💻 Example (Laravel Call Procedure):
```php
$users = DB::select('CALL GetUserByEmail(?)', ['ayush@example.com']);
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### User Defined Functions

🔹 Concept
- **User Defined Function (UDF)**: Custom function that returns a value, can be used in SQL statements.
- **Use Cases**: Reusable calculations, custom logic in queries.
- **Laravel**: Use raw SQL in queries to call functions.

💻 Example (SQL Create Function):
```sql
DELIMITER //
CREATE FUNCTION GetFullName(first_name VARCHAR(50), last_name VARCHAR(50))
RETURNS VARCHAR(101)
DETERMINISTIC
BEGIN
	RETURN CONCAT(first_name, ' ', last_name);
END //
DELIMITER ;
```

💻 Example (SQL Use Function):
```sql
SELECT GetFullName('Ayush', 'Mishra') AS full_name;
```

💻 Example (Laravel Use Function in Query):
```php
$fullName = DB::select('SELECT GetFullName(?, ?) AS full_name', ['Ayush', 'Mishra']);
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->



### Triggers

🔹 Concept
- **Trigger**: Database event that runs automatically before/after INSERT, UPDATE, DELETE.
- **Use Cases**: Audit logs, automatic updates, enforcing business rules.
- **Laravel**: Use raw SQL for triggers; for app-level events, use Eloquent model events (`creating`, `updating`, etc.).

💻 Example (SQL Create Trigger):
```sql
CREATE TRIGGER before_user_insert
BEFORE INSERT ON users
FOR EACH ROW
SET NEW.created_at = NOW();
```

💻 Example (SQL Audit Trigger):
```sql
CREATE TRIGGER after_order_update
AFTER UPDATE ON orders
FOR EACH ROW
INSERT INTO order_audit(order_id, status, changed_at)
VALUES (NEW.id, NEW.status, NOW());
```

💻 Example (Laravel Eloquent Event Alternative):
```php
// In User model
protected static function boot() {
	parent::boot();
	static::creating(function ($user) {
		$user->created_at = now();
	});
	static::updating(function ($order) {
		// Log audit info, etc.
	});
}
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Creating Views

🔹 Concept
- **View**: A virtual table based on the result of a SQL query. Simplifies complex queries, improves security, and enables reuse.
- **Use Cases**: Reporting, analytics, hiding complexity, restricting access.
- **Laravel**: Use raw SQL for view creation; query views like tables.

💻 Example (SQL Create View):
```sql
CREATE VIEW active_users AS
SELECT id, name, email FROM users WHERE status = 'active';
```

💻 Example (SQL Query View):
```sql
SELECT * FROM active_users;
```

💻 Example (Laravel Query View):
```php
$activeUsers = DB::table('active_users')->get();
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Updatable Views

🔹 Concept
- **Updatable View**: A view that allows INSERT, UPDATE, DELETE operations if it meets certain criteria (single table, no aggregates, etc.).
- **Limitations**: Not all views are updatable (e.g., those with JOINs, GROUP BY, aggregates).
- **Laravel**: Treat updatable views as tables in Query Builder/Eloquent (if DB supports it).

💻 Example (SQL Updatable View):
```sql
CREATE VIEW user_emails AS
SELECT id, email FROM users;
```

💻 Example (SQL Update via View):
```sql
UPDATE user_emails SET email = 'new@example.com' WHERE id = 1;
```

💻 Example (Laravel Update via View):
```php
DB::table('user_emails')->where('id', 1)->update(['email' => 'new@example.com']);
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Transaction Basics

🔹 Concept
- **Transaction**: A sequence of SQL operations executed as a single unit. Ensures data integrity.
- **Commands**: `BEGIN`, `COMMIT`, `ROLLBACK`.
- **Laravel**: Use `DB::transaction()` for atomic operations.

💻 Example (SQL Transaction):
```sql
START TRANSACTION;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;
COMMIT;
```

💻 Example (SQL Rollback):
```sql
START TRANSACTION;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
-- Something goes wrong
ROLLBACK;
```

💻 Example (Laravel Transaction):
```php
DB::transaction(function () {
	Account::where('id', 1)->decrement('balance', 100);
	Account::where('id', 2)->increment('balance', 100);
});
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### ACID Properties

🔹 Concept
- **Atomicity**: All operations in a transaction succeed or none do.
- **Consistency**: Transactions bring the database from one valid state to another.
- **Isolation**: Concurrent transactions do not interfere with each other.
- **Durability**: Once committed, changes persist even after failures.
- **Laravel**: Transactions are ACID-compliant when using `DB::transaction()`.

💻 Example (SQL ACID Transaction):
```sql
START TRANSACTION;
-- Atomic: All or nothing
UPDATE inventory SET stock = stock - 1 WHERE product_id = 10;
UPDATE sales SET sold = sold + 1 WHERE product_id = 10;
COMMIT;
```

💻 Example (Laravel ACID Transaction):
```php
DB::transaction(function () {
	Inventory::where('product_id', 10)->decrement('stock');
	Sale::where('product_id', 10)->increment('sold');
});
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Isolation Levels

🔹 Concept
- **Isolation Level**: Controls how/when changes made by one transaction are visible to others.
- **Levels**:
	- READ UNCOMMITTED: See uncommitted changes (dirty reads)
	- READ COMMITTED: Only see committed changes
	- REPEATABLE READ: Same data for duration of transaction
	- SERIALIZABLE: Highest isolation, transactions fully isolated
- **Laravel**: Set isolation level with raw SQL before transaction.

💻 Example (SQL Set Isolation Level):
```sql
SET TRANSACTION ISOLATION LEVEL SERIALIZABLE;
START TRANSACTION;
-- ...queries...
COMMIT;
```

💻 Example (Laravel Set Isolation Level):
```php
DB::statement('SET TRANSACTION ISOLATION LEVEL SERIALIZABLE');
DB::transaction(function () {
	// ...queries...
});
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Deadlock Handling

🔹 Concept
- **Deadlock**: Two or more transactions block each other, waiting for resources.
- **Prevention**: Keep transactions short, access tables in same order, avoid user input inside transactions.
- **Resolution**: MySQL rolls back one transaction; app should retry.
- **Laravel**: Use retry logic for deadlocks.

💻 Example (SQL Deadlock Situation):
```sql
-- Transaction 1
START TRANSACTION;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
-- Transaction 2
START TRANSACTION;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;
-- Both try to update each other's rows, causing deadlock
```

💻 Example (Laravel Deadlock Retry):
```php
use Illuminate\Support\Facades\DB;
use Illuminate\Database\QueryException;

$maxAttempts = 3;
$attempt = 0;
do {
	try {
		DB::transaction(function () {
			// ...queries...
		});
		break;
	} catch (QueryException $e) {
		if (str_contains($e->getMessage(), 'Deadlock')) {
			$attempt++;
			if ($attempt >= $maxAttempts) throw $e;
			sleep(1); // Wait before retry
		} else {
			throw $e;
		}
	}
} while ($attempt < $maxAttempts);
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Raw SQL in Laravel
🔹 Concept

- **Raw SQL**: Directly execute SQL queries using Laravel's DB facade. Useful for complex queries, performance, or unsupported features.
- **When to Use**: Complex joins, CTEs, window functions, bulk operations, vendor-specific SQL.
- **Security**: Always use parameter binding to prevent SQL injection.

💻 Example (DB::select):

```php
$users = DB::select('SELECT * FROM users WHERE status = ?', ['active']);
```

💻 Example (DB::statement):

```php
DB::statement('UPDATE users SET status = ? WHERE id = ?', ['inactive', 5]);
```

💻 Example (Raw Insert):

```php
DB::insert('INSERT INTO users (name, email) VALUES (?, ?)', ['Sam', 'sam@example.com']);
```

💻 Example (Raw SQL with CTE):

```php
$orders = DB::select('WITH high_value_orders AS (SELECT * FROM orders WHERE amount > 1000) SELECT * FROM high_value_orders WHERE status = "completed"');
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Query Builder vs Eloquent
🔹 Concept

- **Query Builder**: Fluent interface for building SQL queries. Returns arrays/objects, not models. Fast, flexible, good for joins and aggregates.
- **Eloquent ORM**: ActiveRecord implementation. Returns model instances, supports relationships, events, scopes, mutators.
- **When to Use**:
	- Query Builder: Complex queries, joins, aggregates, performance-critical code.
	- Eloquent: CRUD, relationships, business logic, model events.
- **Performance**: Query Builder is faster for large, complex queries; Eloquent is more expressive for model logic.

💻 Example (Query Builder):

```php
$users = DB::table('users')->where('status', 'active')->get();
```

💻 Example (Eloquent):

```php
$users = User::where('status', 'active')->get();
```

💻 Example (Query Builder Join):

```php
$results = DB::table('users')
	->join('posts', 'users.id', '=', 'posts.user_id')
	->select('users.name', 'posts.title')
	->get();
```

💻 Example (Eloquent Relationship):

```php
$posts = Post::with('user')->get();
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Complex Laravel Queries
🔹 Concept

- **Complex Queries**: Use raw SQL, selectRaw(), whereRaw(), subqueries, unions, CTEs, window functions, JSON operations.
- **Combining Query Builder & Raw SQL**: Use selectRaw(), whereRaw(), or DB::select for advanced logic.

💻 Example (selectRaw):

```php
$users = User::select('name', DB::raw('CASE WHEN age >= 18 THEN "Adult" ELSE "Minor" END as age_group'))->get();
```

💻 Example (whereRaw):

```php
$users = User::whereRaw('YEAR(created_at) = ?', [2025])->get();
```

💻 Example (Subquery in Query Builder):

```php
$avgPrice = Product::avg('price');
$products = Product::where('price', '>', $avgPrice)->get();
```

💻 Example (Union):

```php
$query1 = DB::table('users')->where('status', 'active');
$query2 = DB::table('users')->where('status', 'pending');
$users = $query1->union($query2)->get();
```

💻 Example (Window Function):

```php
$users = User::select('id', 'name', DB::raw('ROW_NUMBER() OVER (ORDER BY created_at) as row_num'))->get();
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Laravel Query Scopes
🔹 Concept

- **Query Scope**: Reusable query logic in Eloquent models. Local scopes for specific queries, global scopes for all queries on a model.
- **Benefits**: DRY code, improved readability, reusable filters.

💻 Example (Local Scope):

```php
// In User.php model
public function scopeActive($query) {
	return $query->where('status', 'active');
}

// Usage
$activeUsers = User::active()->get();
```

💻 Example (Global Scope):

```php
// In User.php model
protected static function booted() {
	static::addGlobalScope('active', function ($query) {
		$query->where('status', 'active');
	});
}

// Usage
$users = User::all(); // Only active users returned
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Database Migrations Advanced
🔹 Concept

- **Advanced Migrations**: Schema changes, data migrations, renaming tables/columns, adding indexes, foreign keys, constraints, custom SQL.
- **Data Migration**: Move/transform data during schema changes.
- **Best Practices**: Use transactions, backup data, test migrations.

💻 Example (Rename Table):

```php
Schema::rename('old_table', 'new_table');
```

💻 Example (Rename Column):

```php
Schema::table('users', function (Blueprint $table) {
	$table->renameColumn('username', 'login');
});
```

💻 Example (Add Index):

```php
Schema::table('users', function (Blueprint $table) {
	$table->index('email');
});
```

💻 Example (Add Foreign Key):

```php
Schema::table('posts', function (Blueprint $table) {
	$table->unsignedBigInteger('user_id');
	$table->foreign('user_id')->references('id')->on('users');
});
```

💻 Example (Data Migration):

```php
DB::table('users')->whereNull('email')->update(['email' => 'unknown@example.com']);
```

💻 Example (Custom SQL in Migration):

```php
DB::statement('ALTER TABLE users ADD COLUMN is_active BOOLEAN DEFAULT 1');
```


<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Query Performance Analysis
🔹 Concept

- **Performance Analysis**: Identify slow queries, bottlenecks, and optimize database operations.
- **Tools**: EXPLAIN, slow query log, query profiling, Laravel Debugbar, Telescope.

💻 Example (SQL EXPLAIN):

```sql
EXPLAIN SELECT * FROM users WHERE email = 'ayush@example.com';
```

💻 Example (SQL Slow Query Log):

```sql
SET GLOBAL slow_query_log = 'ON';
SET GLOBAL long_query_time = 2; -- Log queries longer than 2 seconds
```

💻 Example (SQL Query Profiling):

```sql
SHOW PROFILE FOR QUERY 1;
```

💻 Example (Laravel Debugbar):

```php
// Install: composer require barryvdh/laravel-debugbar --dev
// Usage: Shows queries, execution time, and more in browser
```

💻 Example (Laravel Telescope):

```php
// Install: composer require laravel/telescope --dev
// Usage: Monitor queries, requests, jobs, exceptions
```

💻 Example (Laravel EXPLAIN):

```php
$plan = DB::select('EXPLAIN SELECT * FROM users WHERE email = ?', ['ayush@example.com']);
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Laravel Query Optimization
🔹 Concept

- **Query Optimization**: Improve query speed and reduce resource usage.
- **N+1 Problem**: Multiple queries for related data; solved by eager loading.
- **Eager Loading**: Load related models with one query (`with()`).
- **Lazy Loading**: Load related models when accessed; can cause N+1.
- **Best Practices**: Use indexes, select only needed columns, avoid unnecessary queries.

💻 Example (N+1 Problem):

```php
$posts = Post::all();
foreach ($posts as $post) {
	echo $post->user->name; // Triggers a query for each post
}
```

💻 Example (Eager Loading):

```php
$posts = Post::with('user')->get();
foreach ($posts as $post) {
	echo $post->user->name; // No extra queries
}
```

💻 Example (Select Only Needed Columns):

```php
$users = User::select('id', 'name')->get();
```

💻 Example (Query Builder Optimization):

```php
$users = DB::table('users')->where('status', 'active')->limit(10)->get();
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Database Connection Optimization
🔹 Concept

- **Connection Optimization**: Reduce overhead, improve scalability, and handle high traffic.
- **Connection Pooling**: Reuse connections to reduce latency.
- **Persistent Connections**: Keep connections open for reuse.
- **Laravel**: Configure in `config/database.php` and `.env`.

💻 Example (MySQL Persistent Connection):

```env
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=myapp
DB_USERNAME=root
DB_PASSWORD=secret
DB_PERSISTENT=true
```

💻 Example (Laravel Database Config):

```php
'mysql' => [
	'driver' => 'mysql',
	'host' => env('DB_HOST', '127.0.0.1'),
	'database' => env('DB_DATABASE', 'forge'),
	'username' => env('DB_USERNAME', 'forge'),
	'password' => env('DB_PASSWORD', ''),
	'options' => [
		PDO::ATTR_PERSISTENT => true,
	],
],
```

💻 Example (Multiple Connections):

```php
$users = DB::connection('mysql2')->table('users')->get();
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Caching Strategies
🔹 Concept

- **Caching**: Store query results to reduce database load and improve speed.
- **Types**: Query caching, object caching, Redis integration.
- **Laravel**: Use Cache facade, Redis, or third-party packages.

💻 Example (MySQL Query Cache):

```sql
SHOW VARIABLES LIKE 'query_cache%';
SET GLOBAL query_cache_size = 1048576; -- 1MB
```

💻 Example (Laravel Cache Query Result):

```php
$users = Cache::remember('active_users', 60, function () {
	return User::where('status', 'active')->get();
});
```

💻 Example (Laravel Redis Cache):

```php
// .env
REDIS_HOST=127.0.0.1
REDIS_PORT=6379

// Usage
Cache::store('redis')->put('key', 'value', 600);
$value = Cache::store('redis')->get('key');
```

💻 Example (Clear Cache):

```php
Cache::forget('active_users');
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Full Text Search
🔹 Concept

- **Full-Text Search**: Efficiently search text data using indexes and natural language queries.
- **MATCH AGAINST**: MySQL syntax for full-text search.
- **Laravel**: Use Laravel Scout for full-text search integration.

💻 Example (SQL Full-Text Index):

```sql
ALTER TABLE posts ADD FULLTEXT(title, body);
```

💻 Example (SQL Full-Text Search):

```sql
SELECT * FROM posts WHERE MATCH(title, body) AGAINST('laravel tips');
```

💻 Example (Laravel Scout Search):

```php
// In Post model: use Searchable trait
use Laravel\Scout\Searchable;
class Post extends Model {
	use Searchable;
}

$results = Post::search('laravel tips')->get();
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### JSON Data Types
🔹 Concept

- **JSON Data Type**: Store and query structured data in a single column.
- **MySQL**: Use JSON type, functions like JSON_EXTRACT, JSON_SET.
- **Laravel**: Query JSON columns with whereJsonContains, whereJsonLength, etc.

💻 Example (SQL Create Table with JSON):

```sql
CREATE TABLE products (
	id INT PRIMARY KEY,
	name VARCHAR(100),
	attributes JSON
);
```

💻 Example (SQL Query JSON):

```sql
SELECT * FROM products WHERE JSON_EXTRACT(attributes, '$.color') = 'red';
```

💻 Example (Laravel Query JSON):

```php
$products = Product::whereJsonContains('attributes->color', 'red')->get();
$productsWithSize = Product::whereJsonContains('attributes->size', 'L')->get();
```

💻 Example (Laravel Update JSON):

```php
Product::where('id', 1)->update([
	'attributes->color' => 'blue'
]);
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Partitioning
🔹 Concept

- **Partitioning**: Split large tables into smaller, manageable pieces for performance and maintenance.
- **Types**: RANGE, LIST, HASH, KEY.
- **MySQL**: Use PARTITION BY clause.
- **Laravel**: No direct support; use raw SQL in migrations.

💻 Example (SQL Partition Table):

```sql
CREATE TABLE sales (
	id INT PRIMARY KEY,
	sale_date DATE
)
PARTITION BY RANGE (YEAR(sale_date)) (
	PARTITION p2024 VALUES LESS THAN (2025),
	PARTITION p2025 VALUES LESS THAN (2026)
);
```

💻 Example (Laravel Migration Raw SQL):

```php
DB::statement('CREATE TABLE ... PARTITION BY RANGE (YEAR(sale_date)) (...)');
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Replication
🔹 Concept

- **Replication**: Copy data from one MySQL server (master) to others (slaves) for redundancy and scaling.
- **Types**: Master-slave, master-master.
- **Laravel**: Configure read/write connections in `config/database.php`.

💻 Example (MySQL Replication Setup):

```sql
-- On master
CHANGE MASTER TO MASTER_HOST='slave_host', MASTER_USER='replica', MASTER_PASSWORD='password';
START SLAVE;
```

💻 Example (Laravel Read/Write Connections):

```php
'mysql' => [
	'read' => [
		'host' => ['192.168.1.2', '192.168.1.3'],
	],
	'write' => [
		'host' => ['192.168.1.1'],
	],
	'driver' => 'mysql',
	'database' => 'myapp',
	'username' => 'root',
	'password' => '',
],
```

💻 Example (Laravel Use Read Connection):

```php
$users = DB::connection('mysql')->table('users')->get();
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### SQL Injection Prevention
🔹 Concept

- **SQL Injection**: Malicious input that alters SQL queries and compromises security.
- **Prevention**: Use prepared statements, parameter binding, ORM methods.
- **Laravel**: Query Builder and Eloquent use parameter binding by default.

💻 Example (Vulnerable SQL):

```php
$email = $_GET['email'];
$user = DB::select("SELECT * FROM users WHERE email = '$email'"); // Vulnerable
```

💻 Example (Safe SQL with Binding):

```php
$email = $_GET['email'];
$user = DB::select('SELECT * FROM users WHERE email = ?', [$email]); // Safe
```

💻 Example (Eloquent Safe Query):

```php
$user = User::where('email', $email)->first();
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### User Management
🔹 Concept

- **User Management**: Create, update, delete users and manage privileges.
- **MySQL**: Use CREATE USER, GRANT, REVOKE, DROP USER.
- **Laravel**: Use migrations, seeders, and policies for user management and security.

💻 Example (SQL Create User):

```sql
CREATE USER 'ayush'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON myapp.* TO 'ayush'@'localhost';
```

💻 Example (SQL Revoke Privileges):

```sql
REVOKE ALL PRIVILEGES, GRANT OPTION FROM 'ayush'@'localhost';
```

💻 Example (Laravel Seeder for User):

```php
User::create([
	'name' => 'Ayush',
	'email' => 'ayush@example.com',
	'password' => bcrypt('password'),
]);
```

💻 Example (Laravel Policy):

```php
// In UserPolicy.php
public function update(User $user, User $model) {
	return $user->id === $model->id;
}
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Data Backup and Recovery
🔹 Concept

- **Backup**: Save database state for disaster recovery.
- **Recovery**: Restore data from backup.
- **MySQL**: Use mysqldump, restore with mysql CLI.
- **Laravel**: Use backup packages (spatie/laravel-backup).

💻 Example (MySQL Backup):

```sh
mysqldump -u root -p myapp > backup.sql
```

💻 Example (MySQL Restore):

```sh
mysql -u root -p myapp < backup.sql
```

💻 Example (Laravel Backup Package):

```php
// Install: composer require spatie/laravel-backup
// Usage: php artisan backup:run
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Database Testing

🔹 Concept

- **Database Testing**: Validate data integrity, business logic, and query correctness.
- **Test Databases**: Use separate DB for tests; rollback changes after each test.
- **Transactions in Tests**: Use transactions to isolate tests and auto-rollback.
- **Laravel**: Use PHPUnit, Laravel's testing helpers, and RefreshDatabase trait.

💻 Example (SQL Test Transaction):

```sql
START TRANSACTION;
INSERT INTO users (name, email) VALUES ('Test', 'test@example.com');
ROLLBACK;
```

💻 Example (Laravel Test with Transaction):

```php
use Illuminate\Foundation\Testing\RefreshDatabase;

class UserTest extends TestCase {
	use RefreshDatabase;

	public function testUserCreation() {
		User::create(['name' => 'Test', 'email' => 'test@example.com']);
		$this->assertDatabaseHas('users', ['email' => 'test@example.com']);
	}
}
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Query Debugging

🔹 Concept

- **Query Debugging**: Find and fix issues in SQL queries and database interactions.
- **MySQL Logs**: Enable general/slow query logs for analysis.
- **Laravel**: Use query logging, Debugbar, Telescope.

💻 Example (Enable MySQL General Log):

```sql
SET GLOBAL general_log = 'ON';
```

💻 Example (View MySQL Log File):

```sh
tail -f /var/log/mysql/mysql.log
```

💻 Example (Laravel Query Log):

```php
DB::listen(function ($query) {
	logger($query->sql, $query->bindings);
});
```

💻 Example (Laravel Debugbar):

```php
// Shows all queries, execution time, and more in browser
```

💻 Example (Laravel Telescope):

```php
// Monitor queries, requests, jobs, exceptions
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Complex Reporting Queries

🔹 Concept

- **Reporting Queries**: Aggregate, filter, and join data for analytics and dashboards.
- **SQL**: Use GROUP BY, HAVING, JOIN, window functions, subqueries.
- **Laravel**: Use Query Builder, Eloquent, selectRaw, and reporting packages.

💻 Example (SQL Reporting Query):

```sql
SELECT users.name, COUNT(orders.id) AS total_orders, SUM(orders.amount) AS total_spent
FROM users
LEFT JOIN orders ON users.id = orders.user_id
GROUP BY users.id
HAVING total_spent > 1000;
```

💻 Example (Laravel Reporting Query):

```php
$report = DB::table('users')
	->leftJoin('orders', 'users.id', '=', 'orders.user_id')
	->select('users.name', DB::raw('COUNT(orders.id) as total_orders'), DB::raw('SUM(orders.amount) as total_spent'))
	->groupBy('users.id')
	->having('total_spent', '>', 1000)
	->get();
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Data Migration & ETL

🔹 Concept

- **Data Migration**: Move data between databases or systems.
- **ETL (Extract, Transform, Load)**: Extract data, transform/clean, load into target.
- **MySQL**: Use INSERT INTO ... SELECT, export/import tools.
- **Laravel**: Use migrations, seeders, custom scripts.

💻 Example (SQL Data Migration):

```sql
INSERT INTO new_users (id, name, email)
SELECT id, name, email FROM old_users;
```

💻 Example (Laravel Data Migration):

```php
// Seeder or custom command
$oldUsers = DB::table('old_users')->get();
foreach ($oldUsers as $user) {
	DB::table('new_users')->insert([
		'id' => $user->id,
		'name' => $user->name,
		'email' => $user->email,
	]);
}
```

💻 Example (Laravel ETL with Collection):

```php
$data = DB::table('source')->get()->map(function ($row) {
	return [
		'name' => strtoupper($row->name),
		'email' => strtolower($row->email),
	];
});
DB::table('target')->insert($data->toArray());
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Multi-tenant Applications

🔹 Concept

- **Multi-tenancy**: Support multiple clients (tenants) in a single app/database.
- **Strategies**: Shared DB with tenant_id, separate DBs, separate schemas.
- **MySQL**: Use tenant_id column, row-level security, or separate databases.
- **Laravel**: Use packages (tenancy/tenancy), global scopes, middleware.

💻 Example (SQL Multi-tenant Table):

```sql
CREATE TABLE invoices (
	id INT PRIMARY KEY,
	tenant_id INT,
	amount DECIMAL(10,2)
);
SELECT * FROM invoices WHERE tenant_id = 1;
```

💻 Example (Laravel Global Scope for Tenant):

```php
// In Invoice.php model
protected static function booted() {
	static::addGlobalScope('tenant', function ($query) {
		$query->where('tenant_id', auth()->user()->tenant_id);
	});
}
```

💻 Example (Laravel Multi-tenancy Package):

```php
// Use stancl/tenancy or similar package for advanced multi-tenancy
```


<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->
