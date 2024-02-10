# 🐍 Python Features

### Strings

***

#### Splitting by a delimiter

```python
array = string . split ( 'delimiter' )

# Recall from split string array
first = array.str.get( 0 )
second = array.str.get( 1 )


```

#### Slicing a string

```python
string [ start_index : end_index ]
```

_Minus number can be used as indexes as well as empty space_

#### Stripping Strings

```python
new_str = str.lstrip( 'to_remove_from_left' )
```

###

### Probability

***

#### A or B not A and B probability

```python
prob_a = len(a) / len(all_values)
prob_b = len(b) / len(all_values)
intersection = a.intersection(b)
inter_prob = len(intersection) / len(all_values)
```

_a\_or\_b = prob\_a + prob\_b - inter\_prob_

### FIle operations

***

#### Glob

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
