## SQL
#### Week 1 Day 3

### Functions of the day
- **lead()** - takes value ahead
- **lag()** - takes value behind

## Objectives
- Explain the concepts of relational databases (RDBMS)
- Construct databases and tables in pSQL
- Construct SQL queries
- Use filters, conditionals, comparisons, and aggregation in SQL
- Use joins/unions to combine different tables

### SQL is important! Learn it!
- postgreSQL is an open source version of SQL, in industry they often use different ones

## Relational database

### schema
- skeleton tructure that represents the organization and relationships of data
- database is composed of tablees
- tables may be related to each other
- tables are composed of columns
  - There are different column types
      - `varchar` is often
      - integers / bigint (for large numbers)
      - date / timestamp (has hours:min:sec)
      - float



### from psql shell

```sql
CREATE DATABASE my_db;
DROP DATABASE IF EXISTS my_db;
```
- to create a sql database with two tables

```sql
CREATE TABLE my_table (
    user_id bigint PRIMARY KEY
    ,name varchar(30)
    ,age integer
    ,company_id bigint REFERENCES my_table_2 (company_id)
);
```

- or

```sql
CREATE TABLE abt as
    SELECT
        some_columns
    FROM
        some_table
    ;
```

### SQL Queries

- **SELECT** (required always) - What I want
- **FROM** - tables I want
- **WHERE** - filters I want
- **GROUP BY** - non-aggregated columns I want to aggregate
- **HAVING** - filters I want after aggregating
- **ORDER BY** - what I want to order by

### More specifically
- this is the order of operations that things when makeing a SQL command
#### FROM
- state the table names
- reference nested queries (ex. `SELECT FROM (SELECT FROM) AS...`)
- reference CTE (common table expression) aliases
- does the Joins
#### WHERE
- state conditions I want to meet
- pre-aggregation
#### GROUP BY
- aggregating columns
- not aggregated in the select statement
#### HAVING
- state conditions you want post aggregation
#### SELECT
- calls the columns we want from 'FROM'
- can use functions like `SUM(), MIN(), MAX(), AVG()`
- can use conditionals to change the data
    - `CASE when name = 'Bob' then 'cry-baby' else name END`
- cast types
    - `CAST(dat as varchar(10)`
    - shorthand `varname::type`
#### ORDER BY
- column_name DESC/ASC


## Joins

## Unions
- union vs. union All
- Unions - drop duplicates
- Union All - keeps everything

```sql
SELECT
    ID
    State
FROM
    Ltable
UNION ALL
SELECT
    ID
FROM
    Rtable

```
### Common Table Expressions
- When using a CTE, the temporary table must be defined above the final query
```sql
with my-tb as (


)
SELECT
FROM
....
```

- A **cross-join** takes all the combinations of things and returns the output, it's basically creating permutations

### window functions (OVER)
- Allows you to segment rows into sets so you can perform operations on them
- the function below runs a cumulative sum on doll_per
```sql
SELECT
    SUM(doll_per) OVER (partition by user_id # segments rows into sets
     ORDER BY date) as coll_sum
FROM
    table1
```
