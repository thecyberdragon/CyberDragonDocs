# 🐼 Pandas & Numpy

#### Importing pandas

```python
import pandas as pd
```

### NumPy & Scipy

***

#### Numpy creating array

```python
array = np.array( list )
array = df.col.values
```

#### Convert pandas series to log

```python
log_series = np.log( df )
```

#### Trimmed mean with scipy.stats

```python
from scipy.stats import trim_mean
trim_mean(df.col, proportiontocut=0.1)
```

_0.1 trims the 10% extreme values_

#### NumPy min and max

```python
np.amin( np_array )
np.amax( np_array )
```

#### NumPy count elements in array

```python
np.count_nonzero( x == 5 )
```

### CSV Operation

***

####

#### **Read a CSV**

```python
df.read_csv ( "filename.csv" )
```

#### **Write to CSV**

```python
df.to_csv ( "filename.csv" )
```

### Pandas Series

***

#### Value Counts

```python
df [ "column" ].value_counts ( sort = True, ascending = False, normalize = True )
```

normalize=True will normalise the data to a decimal proportion of the total values, otherwise it will return the actual counts

Pandas documentation

***

### 10 Minutes to Pandas

[https://pandas.pydata.org/docs/user\_guide/10min.html](https://pandas.pydata.org/docs/user\_guide/10min.html)

### Pandas Merge

[https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.merge.html](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.merge.html)

###
