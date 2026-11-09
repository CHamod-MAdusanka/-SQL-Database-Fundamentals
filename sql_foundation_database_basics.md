# 📘 SQL & Database Fundamentals (Part 01)

This study guide covers the core foundational concepts of SQL and Relational Database Management Systems (RDBMS) for backend development and database security.

## 1. Core Concepts

* **Database:** Functions like a main directory or storage folder that securely organizes related data tables.

* **Table:** Functions like an individual file inside a database where data is structured into **Rows** (records) and **Columns** (attributes).

* **File System Path:** On Linux systems (Debian/Kali), MySQL/MariaDB stores data files by default at `/var/lib/mysql/`.

---

## 2. Common Data Types

| Data Type | Purpose | Example | 
| ----- | ----- | ----- | 
| `INT` | Whole numbers / Integers | `1`, `100`, `5025` | 
| `VARCHAR(length)` | Variable-length strings, text, and characters | `'Chamod'`, `'Class 10-A'` | 

> **Note:** In SQL, string data (text) must always be enclosed within **single quotes (`' '`)**.

---

## 3. Essential SQL Commands

### 3.1 Managing Databases

* **Create a new database:**
  ```sql
  CREATE DATABASE database_name;
  ```
  *Example:* `CREATE DATABASE school;`

* **Select a database to use:**
  ```sql
  USE database_name;
  ```
  *Example:* `USE school;`

* **List all existing databases:**
  ```sql
  SHOW DATABASES;
  ```

### 3.2 Managing and Inspecting Tables

* **Create a new table:**
  ```sql
  CREATE TABLE table_name (
      column1_name DATA_TYPE,
      column2_name DATA_TYPE,
      column3_name DATA_TYPE
  );
  ```
  *Example:*
  ```sql
  CREATE TABLE Student (
      Name VARCHAR(50),
      id INT,
      Class VARCHAR(10)
  );
  ```

* **List all tables in the active database:**
  ```sql
  SHOW TABLES;
  ```

* **Inspect table structure (Columns, Types, Null status):**
  ```sql
  DESCRIBE table_name;
  ```
  *Shorthand:*
  ```sql
  DESC table_name;
  ```

### 3.3 Data Manipulation (Inserting & Retrieving Data)

* **Insert data into a table (`INSERT INTO`):**
  ```sql
  INSERT INTO table_name (column1, column2, column3) VALUES (value1, value2, value3);
  ```
  *Example:*
  ```sql
  INSERT INTO Student (Name, id, Class) VALUES ('Chamod', 1, '10A');
  ```
  *(Text values require single quotes `' '`; numeric values do not).*

* **Retrieve and view data (`SELECT`):**
  ```sql
  SELECT * FROM table_name;
  ```
  *Example:*
  ```sql
  SELECT * FROM Student;
  ```
  *(The asterisk `*` represents "all columns").*

---

## 4. Understanding `DESCRIBE` Command Output

| Field Header | Description | 
| ----- | ----- | 
| **Field** | Column name (e.g., `Name`, `id`, `Class`) | 
| **Type** | Data type and allocated size (e.g., `varchar(50)`, `int(11)`) | 
| **Null** | `YES` allows the column to remain empty (`NULL`). `NO` requires a value. | 
| **Key** | Indicates indexing or key constraints (`PRIMARY KEY`, `FOREIGN KEY`). | 
| **Default** | Default value assigned automatically if no value is explicitly provided. | 

---

## 5. Common Syntax Errors to Avoid

1. **Missing Semicolon (`;`):**
   Every SQL statement must end with a semicolon `;` to signal the end of the query execution.

2. **Spelling Mistakes:**
   * `CREAT` ❌ $\rightarrow$ `CREATE` ✅
   * `varcher` ❌ $\rightarrow$ `VARCHAR` ✅

3. **Data Type Parameters:**
   Always specify the maximum string length inside parentheses for `VARCHAR` (e.g., `VARCHAR(50)`).

---
*Note created for study purposes & Backend Development / SQLi learning path.*