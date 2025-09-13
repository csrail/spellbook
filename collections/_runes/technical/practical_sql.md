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

```sql
CREATE DATABASE [[database]];

-- where [[database]] is the name of the database
```

```sql
CREATE TABLE [[table]] (
    [dataType column | column <- [[columns]]]
);

-- where dataType is a legal data type that can be initialised
```

```sql
INSERT INTO [[table]] ([[columns]])
VALUES [value | value <- [[values]]];
```

<br>

The `postgres` is a default database to connect to to run operations; right-click Query-Tool -> write script -> execute script; refresh server.

```sql
CREATE DATABASE analysis;
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

### Chapter 3

Title: Understanding Data Types

Mettle: Managing data types for strings, numbers and dates in relation to size constraints and specificity.

Summary: 

Managing Strings
```sql
-- varchar holds up to n characters
varchar(n)

-- varchar holds n characters, positions not used are padded with whitespace
char(n)

-- text holds up to 1 GB of characters
-- 1 byte a character
-- 1KB 1000 characters
--- 1MB 1,000,000 characters
--- 1GB 1,000,000,000 characters
text
```

<br>

Managing Numbers:

- Integers
- Auto-incrementing Integers
- Decimal Numbers
  - Fixed-Point Numbers
  - Floating-Point Types

Integers:
```sql
smallint
-- defer to bigint unless constraints is applied

integer
-- defer to bigint unless constraint is applied

bigint
-- use as a default
```

Auto-incrementing Integers
```sql
smallserial

serial

bigserial
```

Decimal Numbers: Fixed-Point Numbers, exact math
```sql
numeric([[precision]], [[scale]])
-- where precision represents the total number of digits to store
-- where scale is the number of digits to the right of the decimal point to store

decimal([[precision]], [[scale]])
-- decimal is an alias for numeric
```

Decimal Numbers: Floating-Point, inexact math
```sql
-- precision varies based on input, choosing the smallest possible precision

real
-- 6 digit precision

double precision
-- 15 digit precision
```

<br>

Managing Dates and Times

```sql
date
-- YYYY-MM-DD

time with time zone
-- HH:MM:SS TZ

timestamp with time zone
-- YYYY-MM-DD HH:MM:SS TZ
-- now()
--
-- time zone options:
--   time zone e.g. EST
--   relative to UTC e.g. -8
--   location e.g. Australia/Melbourne

interval
-- 1 day, 1 week, 1 year, 1 century...
```

<br>

CAST: transforming values from one type to another

```sql
SELECT CAST([[column]] AS [[data_type]])
FROM [[table]]
```

Micellaneous Data Types:
- Boolean
- Geometric
- Network address
- UUID, Universally Unique Identifier
- Structured formats: XML, JSON

<br>

Exercise Q1

```sql
CREATE TABLE travel(
    id bigserial,
    mileage decimal(4,1)
);
```

Exercise Q2
```sql
CREATE TABLE driver(
    id bigserial,
    first_name varchar(100),
    last_name varchar(100)
);
-- separate first and last name so easy to query and order
```

<br>

Note: below timestamp is equivalent to 00:00 UTC.  The +13 indicates the offset, so 13:00 less 13 is 00:00 UTC

```
2018-12-31 13:00:00+13
```

<br>

### Chapter 4

Title: Importing and Exporting Data

Mettle: Importing and Exporting Data with temporary table management and copy subquery.

Summary:

Import data from specified path into an initialised table.
```sql
COPY [[table]]
FROM [[path]]
WITH (FORMAT CSV, HEADER);

-- where path is a single quote enclosed path to the csv file
```

```sql
COPY [[table]] ([[columns]])
FROM [[path]]
WITH (FORMAT CSV, HEADER);

-- where columns are columns in the csv file which are a subset of the columns in the table
```

<br>


Delete all records from a table.
```sql
DELETE FROM [[table]];
```

<br>

Use temporary tables to assist with data population of table while inserting default values.
```sql
CREATE TEMPORARY TABLE [[temp_table]] (LIKE [[table]]);

COPY [[temp_table]] ([[columns]])
FROM [[path]]
WITH (FORMAT CSV, HEADER);

INSERT INTO [[table]] ([[columns]])
SELECT [[col1]], [[value]], [[colN]]
FROM [[temp_table]];
-- where [[value]] is the default value to set for the corresponding column in a set of [[columns]]

DROP TABLE [[temp_table]];
```

<br>

Export data from table to specified path.
```sql
COPY [[table]]
TO [[path]]
WITH (FORMAT CSV, HEADER, DELIMITER [[delimiter]]);

-- where [[delimiter]] is a single quote enclosed character.
```

```sql
COPY [[table]] ([[columns]])
TO [[path]]
WITH (FORMAT CSV, HEADER, DELIMITER [[delimiter]]);

-- where [[columns]] specifies the subset of columns to export from the table.
```

```sql
COPY ([[select]])
TO [[path]]
WITH (FORMAT CSV, HEADER, DELIMITER [[delimiter]]);

-- where [[select]] is a table produced by a SELECT query with qualifiers
```

<br>

Exercise Q1

```sql
COPY credit (id, movie, actor)
FROM 'path/to/import_file.csv'
WITH (FORMAT CSV, HEADER, DELIMITER ':', QUOTE '#');

-- the argument to QUOTE tells the database to include the value enclosed in that surrounding character
```

Exercise Q2

```sql
COPY (
    SELECT geo_name, state_us_abbreviation, housing_unit_count_100_percent
    FROM us_counties_2010
    ORDER BY housing_unit_count_100_percent DESC
    LIMIT 20
  )
TO 'path/to/export_file.txt'
WITH (FORMAT CSV, HEADER, DELIMITER ',');
```

Exercise Q3

No, data type `numeric(3,8)` has the precision and scale set up the wrong way round.  It is not sensible for the scale to be larger than the precision.

<br>

### Chapter 5

Title: Basic Math and Stats with SQL

Mettle: Basic Math functions and WITHIN GROUP semantic.

Summary: 

Human readable column names and using them for ordering:
```sql
SELECT [[column]] AS [[label]]
FROM [[table]]
ORDER BY [[label]] [[ASC|DESC]];
```

<br>

Rounding:
```sql
SELECT round(([[expression]]), [[scale]]) AS [[label]];

-- where expression is a sequence of arithmetic operations applied to columns
-- where scale determines the number of places to round to
```

<br>

Aggregate Functions: Sum
```sql
SELECT sum([[column]]) AS [[label]]
FROM [[table]];
```

Aggregate Functions: Average
```sql
SELECT round(avg([[column]]), [[scale]]) AS [[label]]
FROM [[table]];
```

<br>

Percentile Function: Median, continuous
```sql
SELECT
    percentile_cont(.5)
    WITHIN GROUP (ORDER BY [[column]])
FROM [[table]];

-- where percentile_cont(.5) will report the median value when the total count is even
```

Percentile Function: Median, discrete
```sql
SELECT
    percentile_disc(.5)
    WITHIN GROUP (ORDER BY [[column]])
FROM [[table]];

-- where percentile_disc(.5) will report the last value in the first 50 percent of the numbers
```

<br>

Percentile Function: Lower Quartile, Median, Upper Quartile
```sql
SELECT percentile_cont(array[.25,.5.75])
       WITHIN GROUP (ORDER BY [[column]]) AS [[label]]
FROM [[table]];

-- where [[label]] should naturally be "quartiles"
```

Percentile Function: Lower Quartile, Median, Upper Quartile in separate rows
```sql
SELECT unnest(
             percentile_cont(array[.25,.5.75])
             WITHIN GROUP (ORDER BY [[column]])
             ) AS [[label]]
FROM [[table]];
```

<br>

Exercise Q1

```sql
SELECT PI() * 5^2
```

Exercise Q2
```sql
SELECT geo_name,
       round((CAST (p0010005 AS numeric(8,1)) / p0010001) * 100,2) AS "pct_American_Indian/Alaska Native"
FROM us_counties_2010
WHERE state_us_abbreviation = 'NY'
ORDER BY "pct_American_Indian/Alaska Native" DESC;
```

Ahkwesáhsne is a reserved place for the Mohawk tribe.  It is a territory that borders modern day USA and Canada.  This reservation allows the people of the Mohawk tribe to move freely between the USA and Canada borders.

Exercise Q3
```sql
SELECT percentile_cont(.5)
WITHIN GROUP (ORDER BY p0010001) AS "50th Percentile"
FROM us_counties_2010
WHERE state_us_abbreviation = 'CA'
UNION ALL
SELECT percentile_cont(.5)
WITHIN GROUP (ORDER BY p0010001) AS "50th Percentile"
FROM us_counties_2010
WHERE state_us_abbreviation = 'NY'
```

The 2010 median county population was higher in California compared to New York, 179140.5 to 91301 respectively.