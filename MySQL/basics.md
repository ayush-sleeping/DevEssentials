# 📘 MySQL + Laravel Interview Prep Guide

---

## ✅ Goal: Become Interview-Ready in MySQL

### 🔥 What You Need:

* Clear understanding of **what's going on behind phpMyAdmin**
* Know how to **write SQL queries manually**
* Understand **relations**, **constraints**, and **indexes**
* Be able to talk about **MySQL + Laravel integration**

---



## 📝 Short Summary: MySQL in Laravel

Laravel makes working with MySQL seamless by using:

* **Environment variables** in `.env` to store DB credentials
* **Migrations** to create and modify tables using PHP
* **Eloquent ORM** to interact with MySQL tables like objects
* **Query Builder** for fluent SQL-like syntax in PHP
* **Seeders and Factories** to populate test data easily
* **Eager loading and relationships** to optimize joins and queries

All this helps you avoid writing raw SQL unless needed, while still giving full power and flexibility of MySQL.

---

## ✅ Step-by-Step Roadmap for MySQL Interview Prep

### 🔹 1. **Understand What MySQL Is**

> *MySQL is a relational database management system (RDBMS) that stores data in tables made of rows and columns.*

* Structured using **tables**
* Tables have **columns** (fields) and **rows** (data)
* Uses **SQL (Structured Query Language)**

✅ In Laravel, you interact with MySQL using:

* **`.env`** file (to connect)
* **Migrations** (to define schema in code)
* **Eloquent/Query Builder** (to write queries in PHP)

---

### 🔹 2. **Must-Know SQL Commands**

| Task                  | Query Example                                                            |
| --------------------- | ------------------------------------------------------------------------ |
| Create a table        | `CREATE TABLE users (id INT PRIMARY KEY, name VARCHAR(50));`             |
| Insert data           | `INSERT INTO users (id, name) VALUES (1, 'Ayush');`                      |
| Select data           | `SELECT * FROM users;`                                                   |
| Select with condition | `SELECT * FROM users WHERE name = 'Ayush';`                              |
| Update data           | `UPDATE users SET name = 'Ayu' WHERE id = 1;`                            |
| Delete data           | `DELETE FROM users WHERE id = 1;`                                        |
| Join two tables       | `SELECT u.name, o.total FROM users u JOIN orders o ON u.id = o.user_id;` |

💡 *Practice these queries inside phpMyAdmin's SQL tab.*

---

### 🔹 3. **Understand MySQL Concepts Used in Laravel**

#### ✅ Primary Key

* Unique ID per row
* Usually `id INT AUTO_INCREMENT PRIMARY KEY`

#### ✅ Foreign Key

* Used for relationships
* Example: orders table has `user_id` linked to `users.id`

#### ✅ Data Types

* `INT`, `VARCHAR`, `TEXT`, `DATE`, `BOOLEAN`, etc.

#### ✅ Indexes

* Speed up queries
* Laravel automatically creates index on primary & foreign keys

#### ✅ Joins

Used when fetching related data:

* `INNER JOIN`, `LEFT JOIN`, etc.

In Laravel, this is abstracted by Eloquent relationships:

```php
User::with('orders')->get();
```

is internally a JOIN.

---

### 🔹 4. **Laravel + MySQL Integration Concepts**

| Concept       | Laravel Example                | MySQL Behind the Scenes                  |
| ------------- | ------------------------------ | ---------------------------------------- |
| `.env` config | `DB_HOST`, `DB_DATABASE`       | Laravel connects to MySQL                |
| Migration     | `Schema::create('users', ...)` | Translates to `CREATE TABLE users`       |
| Seeder        | `User::factory(10)->create()`  | `INSERT INTO users ...`                  |
| Eloquent      | `User::where('name', 'Ayush')` | `SELECT * FROM users WHERE name='Ayush'` |

---

## 📘 Common Interview Questions with Sample Answers

### ✅ Q1: How does Laravel connect to a MySQL database?

**Answer:**

> Laravel connects to MySQL using configuration settings in the `.env` file. I set DB\_HOST, DB\_DATABASE, DB\_USERNAME, and DB\_PASSWORD to match my MySQL setup. Laravel uses PDO under the hood for this connection.

### ✅ Q2: What is a foreign key? Have you used it?

**Answer:**

> Yes, I use foreign keys to define relationships between tables, like linking an `orders` table to `users`. In Laravel, I define these relationships in migrations using `foreignId('user_id')->constrained()`.

### ✅ Q3: How do you perform a JOIN in Laravel?

**Answer:**

> I typically use Eloquent relationships like `hasMany` or `belongsTo`, and then use `with()` to eager load related data. This performs an internal SQL JOIN.

### ✅ Q4: Have you written raw SQL queries?

**Answer:**

> Yes, while I mostly use Eloquent or Query Builder, I’ve written raw SQL in Laravel using `DB::select()` when needed for complex or optimized queries.

---

## ✅ 25 Advanced MySQL Interview Questions for Laravel Developers

### 🔸 1. What is MySQL?

A relational database management system (RDBMS) used to store structured data in rows and columns.

### 🔸 2. Differences between CHAR and VARCHAR?

* CHAR: Fixed length. Always takes up defined space.
* VARCHAR: Variable length. Saves space.

### 🔸 3. What are MySQL storage engines? Which is default?

* InnoDB (default): supports transactions, foreign keys.
* MyISAM: faster but no FK support.

### 🔸 4. How to define a primary key in Laravel migration?

```php
$table->id(); // AUTO_INCREMENT PRIMARY KEY
```

### 🔸 5. What is a foreign key? How to define it in Laravel?

```php
$table->foreignId('user_id')->constrained();
```

### 🔸 6. What is normalization?

Organizing data to reduce redundancy. Common forms: 1NF, 2NF, 3NF.

### 🔸 7. What’s the difference between DELETE and TRUNCATE?

* DELETE: row-by-row deletion (can rollback).
* TRUNCATE: fast, irreversible deletion (resets auto-increment).

### 🔸 8. What is indexing?

It improves performance on search queries.

```sql
CREATE INDEX idx_name ON users(name);
```

### 🔸 9. Difference between UNION and UNION ALL?

* UNION: removes duplicates.
* UNION ALL: keeps duplicates.

### 🔸 10. What is a view in MySQL?

A virtual table based on a query.

```sql
CREATE VIEW active_users AS SELECT * FROM users WHERE active=1;
```

### 🔸 11. How to find duplicate rows?

```sql
SELECT name, COUNT(*) FROM users GROUP BY name HAVING COUNT(*) > 1;
```

### 🔸 12. What is a trigger?

A set of SQL commands that run automatically on insert/update/delete.

### 🔸 13. What are ENUM and SET?

* ENUM: single value from predefined list
* SET: multiple values from a list

### 🔸 14. What is ACID?

Set of properties that ensure database reliability:

* Atomicity, Consistency, Isolation, Durability

### 🔸 15. How do you define relationships in Laravel models?

```php
// In User.php
public function posts() {
  return $this->hasMany(Post::class);
}
```

### 🔸 16. How does Laravel define a one-to-many relation?

With `hasMany()` and `belongsTo()` methods in models.

### 🔸 17. How do you eager load in Laravel?

```php
User::with('posts')->get();
```

### 🔸 18. How to run raw SQL in Laravel?

```php
DB::select('SELECT * FROM users');
```

### 🔸 19. What is Query Builder?

Laravel’s fluent interface to build SQL queries.

```php
DB::table('users')->where('active', 1)->get();
```

### 🔸 20. How to debug slow MySQL queries?

* Use `EXPLAIN SELECT...`
* Check indexes
* Use Laravel Debugbar

### 🔸 21. What’s the role of `.env` in MySQL connection?

Holds credentials for `DB_HOST`, `DB_DATABASE`, etc.

### 🔸 22. How to rollback a migration in Laravel?

```bash
php artisan migrate:rollback
```

### 🔸 23. What’s a pivot table in Laravel?

Used in many-to-many relationships.

### 🔸 24. What is soft delete?

It uses a `deleted_at` timestamp to mark records as deleted.

```php
use SoftDeletes;
```

### 🔸 25. How to seed data into a MySQL table via Laravel?

```bash
php artisan db:seed
```

Seeder Example:

```php
User::factory()->count(10)->create();
```

---

## ✅ Your Action Plan (1–2 Days Before Interview)

| Task                        | How to Do It                                      |
| --------------------------- | ------------------------------------------------- |
| Review 20 SQL queries       | Practice in phpMyAdmin SQL tab                    |
| Learn schema concepts       | Revise primary key, foreign key, constraints      |
| Create a simple DB manually | Try building a user-order schema                  |
| Try a JOIN                  | Write a join manually, then write same in Laravel |
| Understand Laravel + MySQL  | Map `.env`, migrations, Eloquent to SQL           |

---

## 🧠 Bonus Tip

Install **TablePlus** or **MySQL Workbench** if you want a cleaner GUI than phpMyAdmin to visualize your tables and relationships.

---


