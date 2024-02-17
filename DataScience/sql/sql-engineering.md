# ✏ SQL Engineering

## <mark style="color:red;">**Indexes & Clusters**</mark>

***

### <mark style="color:yellow;">Create Index</mark>

```sql
CREATE INDEX table_column_idx 
ON table(column)

CREATE INDEX table_column_idx 
ON table(column1, column2)
```

Create an index on a table

### <mark style="color:yellow;">Drop Index</mark>

```sql
DROP INDEX index_name
```

Delete an index

### <mark style="color:yellow;">Cluster An Index</mark>

```sql
CLUSTER table ON index_name
```

Cluster the table by that index

Note: Mysql (innoDB) automatically clusters all tables by the primary key or the first unique column if no primary key is present.&#x20;

### <mark style="color:yellow;">Cluster a Table</mark>

```sql
CLUSTER table
```

Recluster the table if a cluster index exists

### <mark style="color:yellow;">Cluster all Tables</mark>

```sql
CLUSTER
```

Cluster all tables
