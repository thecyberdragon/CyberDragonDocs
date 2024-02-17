# 🐬 SQL Statement Syntax

## <mark style="color:red;">Basic Syntax and features</mark>

***

### <mark style="color:yellow;">Selecting all data</mark>

```sql
SELECT *
FROM table
WHERE value = 'something'
LIMIT 10
```

### <mark style="color:yellow;">Selecting columns</mark>

```sql
SELECT
  col1,
  col2,
  col3 / col4 as 'new_col'
FROM table;
```

### <mark style="color:yellow;">Like Selection</mark>

```sql
SELECT *
FROM table
WHERE name LIKE 'tony%'
```

_% signs are wild cards indicating anything of any length. All like statements are processed in lower case._

### <mark style="color:yellow;">Where IN</mark>

```sql
SELECT *
FROM table
WHERE name IN (SELECT name FROM important_people)
```

### <mark style="color:yellow;">Basic Grouping</mark>

```sql
SELECT
  SUM(col2) AS 'all_values'
FROM table
```

### <mark style="color:yellow;">Grouping and ordering</mark>

```sql
SELECT
  name,
  MAX(col)
FROM table
GROUP BY 1
ORDER BY 2 DESC;
```

### <mark style="color:yellow;">Having</mark>

```sql
SELECT
    name,
    SUM(points) AS 'total_points'
FROM
    leaderboard
WHERE name IS NOT NULL
GROUP BY name
HAVING SUM(points) > 0
```

### <mark style="color:yellow;">Joining Tables</mark>

```sql
SELECT
  table_one.name,
  table_two.price
FROM table_one
INNER JOIN table_two ON table_two.id = table_one.id

#Joins: INNER, OUTER, LEFT, RIGHT, CROSS
```

_LEFT JOIN a table to itself to join rows where the id is the same and date = date +1 (tomorrows date) to see if there are reoccuring values by date. Mostly to use to calculate funnels & retention_

### <mark style="color:yellow;">Join Using</mark>

```sql
SELECT
  table_one.name,
  table_two.price
FROM table_one
INNER JOIN table_two USING (id)
```

_USING is for when both tables share identical join column names_

### <mark style="color:yellow;">Inserting</mark>

```sql
INSERT INTO table
(col1, col2, col3) VALUES ('value_1','value_2','value_3')
```

### <mark style="color:yellow;">Insert Selection</mark>

```sql
INSERT INTO 
table_two (col_1, col_2)
SELECT col_1, col_2
FROM table_one
WHERE col_3 > 0
```

### <mark style="color:yellow;">Updating</mark>

```sql
UPDATE table
SET col1 = 'name_change', col2 = 'value_change'
WHERE id = 15
```

### <mark style="color:yellow;">Delete</mark>

```sql
DELETE FROM table
WHERE id = 15
```

_If the delete or update method doesn't specify an index, SQL safe updates needs to be turned off in MySQL version 8 and above._&#x20;

_Always test a delete statement by first building a select statement and modifying after testing the results returned._

```sql
SET SAFE_SQL_UPDATES = 0
```

## <mark style="color:red;">Non-Basic Syntax</mark>

***

### <mark style="color:yellow;">Subqueries</mark>

```sql
SELECT
  first_name,
  last_name,
  (SELECT salary FROM salaries WHERE salaries.id = employees.id) AS salary
FROM 
  employees
```

### <mark style="color:yellow;">Table Alias</mark>

```sql
SELECT
    first_name,
    last_name,
    (SELECT partner FROM employees WHERE employees.id = employee_table.partner_id)
FROM
    employees AS 'employee_table'
```

### <mark style="color:yellow;">CTE Common Table Expression</mark>

```sql
WITH aggregation AS 
(
SELECT 
  player_id,
  full_name,
  team,
  SUM(points) AS points
GROUP BY 1
FROM scores_2023
)
SELECT 
  full_name,
  team,
  points
FROM aggregation
WHERE points > 300
  
```

### <mark style="color:yellow;">Case Statements</mark>

```sql
SELECT
    name,
    age,
    CASE 
    WHEN age < 18 THEN 'child'
    WHEN age >= 18 AND age < 25 THEN 'young'
    WHEN age >= 25 AND age < 40 THEN 'in_prime'
    WHEN age >= 40 AND age < 60 THEN 'aging'
    ELSE 'shouold_retire'
    END AS 'age_ranking'
FROM table
    
```

### <mark style="color:yellow;">Case As Logic</mark>

```sql
SELECT
    name,
    SUM(value)
FROM table
ORDER BY 
(SELECT CASE WHEN age < 25 THEN '01' ELSE '02')
```

## <mark style="color:red;">Table Union</mark>

***

### <mark style="color:yellow;">Basic Union</mark>

```sql
SELECT * FROM table_1
UNION
SELECT * FROM table_2
```

Combine datasets by unique values

### <mark style="color:yellow;">Full Union</mark>

```sql
SELECT * FROM table_1
UNION ALL
SELECT * FROM table_2
```

Combine datasets by all values whether unique or not

### <mark style="color:yellow;">Intersect Union</mark>

```sql
SELECT * FROM table_1
INTERSECT
SELECT * FROM table_2
```

Return rows from the top dataset where they exist in the second

### <mark style="color:yellow;">Except</mark>

```sql
SELECT * FROM table_1
EXCEPT
SELECT * FROM table_2
```

Return rows on the top dataset if they don't appear in the second

## <mark style="color:red;">Window Functions</mark>

***

### <mark style="color:yellow;">Window Function Examples</mark>

```sql
SELECT
  col1,
  FIRST_VALUE OVER ( PARTITION BY col2 ORDER BY col3 ) as non_agg_window
FROM table
```

```sql
SELECT
  col1,
  ROW_NUMBER() OVER ( PARTITION BY id ) as row
FROM table;
```

### <mark style="color:yellow;">Window Function List</mark>

| **Name**                                                                                                             | **Description**                                                 |
| -------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| [`CUME_DIST()`](https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function\_cume-dist)       | Cumulative distribution value                                   |
| [`DENSE_RANK()`](https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function\_dense-rank)     | Rank of current row within its partition, without gaps          |
| [`FIRST_VALUE()`](https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function\_first-value)   | Value of argument from first row of window frame                |
| [`LAG()`](https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function\_lag)                   | Value of argument from row lagging current row within partition |
| [`LAST_VALUE()`](https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function\_last-value)     | Value of argument from last row of window frame                 |
| [`LEAD()`](https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function\_lead)                 | Value of argument from row leading current row within partition |
| [`NTH_VALUE()`](https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function\_nth-value)       | Value of argument from N-th row of window frame                 |
| [`NTILE()`](https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function\_ntile)               | Bucket number of current row within its partition.              |
| [`PERCENT_RANK()`](https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function\_percent-rank) | Percentage rank value                                           |
| [`RANK()`](https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function\_rank)                 | Rank of current row within its partition, with gaps             |
| [`ROW_NUMBER()`](https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function\_row-number)     | Number of current row within its partition                      |

## <mark style="color:red;">Logic in SQL</mark>

***

### <mark style="color:yellow;">IF ELSE Logic</mark>

```sql
SELECT
  name,
  IF(age > 30, 'Aging', 'Youngen') AS 'age_rank'
FROM people
```

### <mark style="color:yellow;">CASE statements</mark>

```sql
SELECT
  CASE
  WHEN age < 18 THEN 'super small'
  WHEN age >= 18 AND age < 30 THEN 'getting there'
  WHEN age >= 30 AND age < 45 THEN 'hol up'
  WHEN age >= 45 AND age < 60 THEN 'oh no'
  ELSE 'you old'
  END AS 'age_ranking'
FROM people
```

### <mark style="color:yellow;">OR and NOT</mark>

```sql
SELECT *
FROM Table
WHERE (name LIKE '% richardson' OR name LIKE '% richardsons')
NOT name = 'dave %'
```

### <mark style="color:yellow;">Between</mark>

```sql
SELECT name
FROM table
WHERE age BETWEEN 10 AND 20
```

## <mark style="color:red;">SQL Aggregation Function List</mark>

***

| **Name**                                                                                                        | **Description**                                  |
| --------------------------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| [`AVG()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function\_avg)                       | Return the average value of the argument         |
| [`BIT_AND()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function\_bit-and)               | Return bitwise AND                               |
| [`BIT_OR()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function\_bit-or)                 | Return bitwise OR                                |
| [`BIT_XOR()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function\_bit-xor)               | Return bitwise XOR                               |
| [`COUNT()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function\_count)                   | Return a count of the number of rows returned    |
| [`COUNT(DISTINCT)`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function\_count-distinct)  | Return the count of a number of different values |
| [`GROUP_CONCAT()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function\_group-concat)     | Return a concatenated string                     |
| [`JSON_ARRAYAGG()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function\_json-arrayagg)   | Return result set as a single JSON array         |
| [`JSON_OBJECTAGG()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function\_json-objectagg) | Return result set as a single JSON object        |
| [`MAX()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function\_max)                       | Return the maximum value                         |
| [`MIN()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function\_min)                       | Return the minimum value                         |
| [`STD()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function\_std)                       | Return the population standard deviation         |
| [`STDDEV()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function\_stddev)                 | Return the population standard deviation         |
| [`STDDEV_POP()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function\_stddev-pop)         | Return the population standard deviation         |
| [`STDDEV_SAMP()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function\_stddev-samp)       | Return the sample standard deviation             |
| [`SUM()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function\_sum)                       | Return the sum                                   |
| [`VAR_POP()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function\_var-pop)               | Return the population standard variance          |
| [`VAR_SAMP()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function\_var-samp)             | Return the sample variance                       |
| [`VARIANCE()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function\_variance)             | Return the population standard variance          |

## <mark style="color:red;">Documentation</mark>

***

[https://dev.mysql.com/doc/refman/8.0/en/programs.html](https://dev.mysql.com/doc/refman/8.0/en/programs.html)
