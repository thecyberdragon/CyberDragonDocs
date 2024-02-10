# 🐬 SQL

### Todo

* [ ] date time functions
* [x] joining
* [x] subquery
* [x] with statements
* [x] if else and cases

### Basic Syntax and features

***

#### Searching

```sql
SELECT *
FROM table
WHERE value = 'something';
```

#### Selecting columns

```sql
SELECT
  col1,
  col2,
  col3 / col4 as new_col
FROM table;


```

### Grouping

***

#### Basic Grouping and ordering

```sql
SELECT
  name,
  SUM(col2)
FROM table
GROUP BY 1
ORDER BY 2 DESC;
```

#### Aggregation

```sql
SELECT
  MAX(col)
FROM table
```

#### Joining Tables

```sql
SELECT
  table_one.name,
  table_two.price
FROM table_one
INNER JOIN table_two ON table_two.id = table_one.id

#Joins: INNER, OUTER, LEFT, RIGHT, CROSS
```

#### Subqueries

```sql
SELECT
  first_name,
  last_name,
  (SELECT salary FROM salaries WHERE salaries.id = employees.id) AS salary
FROM 
  employees
```

#### CTE Common Table Expression

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

#### IF ELSE Logic

```sql
SELECT
  name,
  IF(age > 30, 'Aging', 'Youngen') AS 'age_rank'
FROM people
```

#### CASE statements

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

#### SQL Function List

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

### Window Functions

***

#### Window Function Examples

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

#### Function List

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

### Documentation

***

[https://dev.mysql.com/doc/refman/8.0/en/programs.html](https://dev.mysql.com/doc/refman/8.0/en/programs.html)