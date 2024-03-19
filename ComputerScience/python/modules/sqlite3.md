# 🗃️ SQLite3

#### <mark style="color:yellow;">Importing</mark>

```python
import sqlite3
```

<mark style="color:yellow;">Connecting to a database</mark>

```python
conn = sqlite3.connect(file_path_string)
cursor = conn.cursor()

# Return one result
cursor.execute(sql_query_string).fetchone()

# Return all results
cursor.execute(sql_query_string).fetchall()
```

#### <mark style="color:yellow;">Insert / update using paramaterised queries</mark>

```python
# Example where value = "cat" and col2 WHERE = "fluffy"
data = ("cat","fluffy")
cursor.execute("INSERT INTO table (col1) VALUES (?) WHERE col2 = ?", data)
conn.comit()
```

The input data must be a tuple

