# 🐍 Data Types

#### <mark style="color:yellow;">Casting</mark>

```python
# Int
new_int = int("0.1")

# String
new_string = str(0.1)

# Float
new_float = float("0.000220")
```

#### <mark style="color:yellow;">Check if a variable is a data type</mark>

```python
# Is it a string?
variable == str

# Is it an int?
variable == int

# Is it a float?
variable == float
```

## <mark style="color:red;">Data Types</mark>

***

### <mark style="color:yellow;">Tuples</mark>

Values within brackets -> (value, value, value)

Tuples are immutable, meaning once created they can't be changed.

Unpack a tuple into values:\
value1, value2, value3 = tuple

Tuple with 1 value

one\_value\_tuple = (value,) <- trailing comma

### <mark style="color:yellow;">Lists</mark>

A mutable data type meaning it can be changed once created.

Values within square brackets -> \[value, value, value]

List comprehension (creating a list using logic)

```python
new_list = [item for item in other_list if item = "something"]
```

