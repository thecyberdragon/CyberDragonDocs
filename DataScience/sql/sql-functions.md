# 🐬 SQL Functions

### <mark style="color:yellow;">Casting</mark>

```sql
SELECT 
    name,
    CAST(age AS CHAR)
FROM table 
```

### <mark style="color:yellow;">Replacing</mark>

```sql
SELECT
    name,
    last_name,
    REPLACE(country, 'UK', 'United Kingdom') AS 'country'
FROM people
```

### <mark style="color:yellow;">Trim</mark>

```sql
SELECT
    TRIM(first_name) AS 'first',
    TRIM(last_name) AS 'last
FROM csv_import

# LTRIM = left
# RTRIM = right
# TRIM = both
```

### <mark style="color:yellow;">Instr</mark>

```sql
SELECT
    INSTR('this is in here', 'here') AS 'here'
FROM table

# Return = index
```

### <mark style="color:yellow;">String to Date</mark>

```sql
SELECT
    name,
    STR_TO_DATE(date_string, 'd%.m%.y%') AS 'dob'
FROM table

# Input string dd.mm.yyyy
```

### <mark style="color:yellow;">Adding or Subtracting dates</mark>

```sql
SELECT
    event,
    DATE_ADD(origina_date, INTERVAL 1 DAY) AS 'tomorrow',
    DATE_SUB(origina_date, INTERVAL 1 DAY) AS 'yesterday'
FROM table
```

### <mark style="color:yellow;">Get current date</mark>

```sql
SELECT CURDATE()
```

