---
layout: spell
date: 09-09-2025
---

### Chapter 0

Title: Introduction

Mettle: SQL informs the structure of data and the relationships between entities.  Quickfire setup for SQL environment.

Summary: Install PostgreSQL environment with Postgres.app (Database Server UI)and PGAdmin (Database Management System)

```
-- Config in Postgres.app

Name: Postgres [V]
Host: localhost
Port: 5432
User: [System Username]

where [V] is the version number of the server
where [System Username] is the username of the machine
```

<br>

### Chapter 1

Title: Creating Your First Database and Table

Mettle: Populating a simple database: create table and insert rows.

Summary:

The `postgres` is a default database to connect to to run operations; right-click Query-Tool -> write script -> execute script; refresh server.

```sql
CREATE DATABSE analysis;
```

Engage the database: `analysis/[username]@Postgres 17`

```sql
CREATE TABLE teachers (
    -- bigserial auto-increments by 1 every time a new row is added to the table
    id bigserial,
    first_name varchar(25),
    last_name varchar(50),
    school varchar(50),
    hire_date date,
    salary numeric
);
```

Inpsect :: PostgreSQL 17 -> Databases -> analysis -> Schemas -> Tables -> teachers

```sql
-- INSERT INTO :: teachers table with the columns to be filled
-- VALUES :: rows with values assigned to each column
-- Note the id is not listed but is auto-incremented
INSERT INTO teachers(first_name, last_name, school, hire_date, salary)
VALUES ('Janet', 'Smith', 'F.D. Roosevelt HS', '2011-10-30', 36200),
       ('Lee', 'Reynolds', 'F.D. Roosevelt HS', '1993-05-22', 65000),
       ('Samuel', 'Cole', 'Myers Middle School', '2005-08-01', 43500),
       ('Samantha', 'Bush', 'Myers Middle School', '2011-10-30', 36200),
       ('Betty', 'Diaz', 'Myers Middle School', '2005-08-30', 43500),
       ('Kathleen', 'Roush', 'F.D. Roosevelt HS', '2010-10-22', 38500);
```

<br>

### Chapter 2

Title: Beginning Data Exploration With Select

Mettle: Data Exploration with selection, ordering (ranking) and filters (subsetting).

Summary: Interview the data: assess whether what is described is supported by the data.

Select to return records and their attributes.
```sql
SELECT [[columns]]
FROM [[table]];
```

<br>

Return unique values for a column.  Can help to identify incorrect data entries.
```sql
SELECT DISTINCT [[column]]
FROM [[table]];
```

```sql
-- distinct on multiple columns lists all unique combinations
SELECT DISTINCT [[columns]]
FROM [[table]];
```

<br>

Order returned rows by column value to observe rankings and trends.
```sql
SELECT [[columns]]
FROM [[table]]
ORDER BY [[column]] DESC; -- list from highest to lowest
```

```sql
-- order by multiple columns in specified sequence
SELECT [[columns]]
FROM [[table]]
ORDER BY [column [ASC|DESC] | column <- [[columns]]];
```

<br>


Filter records to return a subset of the original set returned.
```sql
SELECT [[columns]]
FROM [[table]]
WHERE [[column]] [[operator]] [[value]];

-- where [[operator]] implements the Eq or Ord class
```

```sql
SELECT [[columns]]
FROM [[table]]
WHERE [[column]] BETWEEEN [[value1]] AND [[value2]];
```

```sql
SELECT [[columns]]
FROM [[table]]
WHERE [[column]] ILIKE [[value]];

-- where [[value]] contains pattern matching symbols for Strings:
-- % wildcard maches one or more characters
-- _ wildcard exactly one character
```

```sql
SELECT [[columns]]
FROM [[table]]
WHERE [[filter1]]
[AND|OR] [[filter2]];

-- with logical AND, logical OR to chain filters
```

<br>

Everything together:
```sql
SELECT [[columns]]
FROM [[table]]
WHERE [[filtering_predicate]]
ORDER BY [[ordering_predicate]]
```

<br>

Exercise Q1

```sql
SELECT *
FROM teachers
ORDER BY school ASC, last_name ASC
```

Exercise Q2
```sql
SELECT *
FROM teachers
WHERE first_name ILIKE 's%'
  AND salary > 40000
```

Exercise Q3
```sql
SELECT *
FROM teachers
WHERE hire_date > '2010-01-01'
ORDER BY salary DESC;
```

<br>

