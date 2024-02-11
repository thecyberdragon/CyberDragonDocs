---
description: Features in python for data science not from the main data science libraries
---

# 🐍 Python Features

## <mark style="color:red;">Strings</mark>

***

### <mark style="color:yellow;">Splitting by a delimiter</mark>

```python
array = string . split ( 'delimiter' )

# Recall from split string array
first = array.str.get( 0 )
second = array.str.get( 1 )


```

### <mark style="color:yellow;">Slicing a string</mark>

```python
string [ start_index : end_index ]
```

_Minus number can be used as indexes as well as empty space_

### <mark style="color:yellow;">Stripping Strings</mark>

```python
new_str = str.lstrip( 'to_remove_from_left' )
```

## <mark style="color:red;">Probability</mark>

***

### <mark style="color:yellow;">A or B not A and B probability</mark>

```python
prob_a = len(a) / len(all_values)
prob_b = len(b) / len(all_values)
intersection = a.intersection(b)
inter_prob = len(intersection) / len(all_values)
```

_<mark style="color:green;">a\_or\_b = prob\_a + prob\_b - inter\_prob</mark>_

## <mark style="color:red;">File Operations</mark>

***

### <mark style="color:yellow;">Glob</mark>

```python
import glob
import pandas as pd

dataframes = []
files = glob.glob("file_pattern")
for filename in files:
  data = pd.read_csv(filename)
  dataframes.append(data)

pd.concat(dataframes)
```
