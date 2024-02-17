# ✏ SQL CheatSheet

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

###

### **Table data manipulation**

***

UNION

Combine datasets by unique values

UNION ALL

Combine datasets by all values

INTERSECT

Return rows from the top dataset where they exist in the second

EXCEPT

Return rows on the top dataset if they don't appear in the second

### **Indexs**

***

CREATE INDEX table\_column\_idx ON table(column(s))

Create an index on a table

DROP INDEX index\_name

Delete an index

CLUSTER table ON index\_name

Cluster the table by that index

CLUSTER table

Recluster the table if a cluster index exists

CLUSTER

Cluster all tables

ADD

CASE

SUM & COUNT(CASE conditions END) AS alias

DATE

TIME

DATETIME

REPLACE

CAST

CREATE TABLE

ALTER TABLE

LAG

LEAD

INSTR

DATE

JOIN table USING(common\_value)

LEFT JOIN a table to itself to join rows where the id is the same and date= date -1 (tomorrows date) to see if reoccuring values by date
