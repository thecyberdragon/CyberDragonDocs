# ✏ SQL Engineering

* [ ] Triggers
* [ ] Stored Procedures
* [ ] Events

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

## Tables

***

### <mark style="color:yellow;">Create Table</mark>

```sql
CREATE TABLE table_name(
    id INT PRIMARY KEY AUTO_INCREMENT,
    department_id INT UNIQUE,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    dob DATE NOT NULL,
    alive BOOL NOT NULL,
    net_worth DOUBLE(9,2),
    last_login DATETIME,
    CHECK(UNIQUE(CONCAT(first_name, '-', last_name)))  
    FOREIGN KEY(id) REFERENCES people(id)      
)
```

### <mark style="color:yellow;">Delete Table</mark>

```sql
DROP TABLE table_name
```

### <mark style="color:yellow;">Alter Column</mark>

```sql
ALTER TABLE table_name
MODIFY COLUMN alive BOOL
```

### <mark style="color:yellow;">Remove Column</mark>

```sql
ALTER TABLE table_name
DROP COLUMN net_worth
```

### <mark style="color:yellow;">Add Column</mark>

```sql
ALTER TABLE table_name
ADD COLUMN sex VARCHAR(6) AFTER dob
```

## <mark style="color:red;">Engineering</mark>

***

### <mark style="color:yellow;">Create Stored Procedure</mark>

```
x
```

### <mark style="color:yellow;">Create Trigger</mark>

```sql
x
```

### <mark style="color:yellow;">Create Event</mark>

```
x
```
