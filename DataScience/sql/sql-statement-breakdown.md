# 🐬 SQL Statement Breakdown

## <mark style="color:red;">**Query Structure**</mark>

***

```sql
EXPLAIN ANALYZE
```

Check planning and execution time of the query

```sql
SELECT (columns or *)
```

What to select

```sql
OVER (PARTITION BY column ORDER BY)
```

Sub-group data for query calculation instead of group by

```sql
FROM table_name 
FROM (subquery) AS alias
```

From which table or subquery

```sql
WHERE condition1 IN/EXISTS/LIKE/=/(dataset/subquery/value)
```

Condition for query

```sql
GROUP BY 1,2,3
```

Group results by column(s)

```sql
HAVING AGGREGATION(col) = < > != value
```

Filter by a grouped value

```sql
ORDER BY 1,2,3 ASC/DESC
```

Order results by column(s), ascending by default

```sql
LIMIT number
```

Limit number of rows returned

