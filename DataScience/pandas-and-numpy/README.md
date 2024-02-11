# 🐼 Pandas & Numpy

## <mark style="color:red;">Importing pandas</mark>

***

```python
import pandas as pd
```

## <mark style="color:red;">NumPy & Scipy</mark>

***

### <mark style="color:yellow;">Numpy creating array</mark>

```python
array = np.array( list )
array = df.col.values
```

### <mark style="color:yellow;">Convert pandas series to log</mark>

```python
log_series = np.log( df )
```

### <mark style="color:yellow;">Trimmed mean with scipy.stats</mark>

```python
from scipy.stats import trim_mean
trim_mean(df.col, proportiontocut=0.1)
```

_<mark style="color:green;">0.1 trims the 10% extreme values</mark>_

### <mark style="color:yellow;">NumPy min and max</mark>

```python
np.amin( np_array )
np.amax( np_array )
```

### <mark style="color:yellow;">NumPy count elements in array</mark>

```python
np.count_nonzero( x == 5 )
```

## <mark style="color:red;">CSV Operation</mark>

***

### <mark style="color:yellow;">**Read a CSV**</mark>

```python
df.read_csv ( "filename.csv" )
```

### <mark style="color:yellow;">**Write to CSV**</mark>

```python
df.to_csv ( "filename.csv" )
```

## <mark style="color:red;">Pandas Series</mark>

***

### <mark style="color:yellow;">Value Counts</mark>

```python
df [ "column" ].value_counts ( sort = True, ascending = False, normalize = True )
```

normalize=True will normalise the data to a decimal proportion of the total values, otherwise it will return the actual counts

### <mark style="color:yellow;">Pandas documentation</mark>

***

#### 10 Minutes to Pandas

[https://pandas.pydata.org/docs/user\_guide/10min.html](https://pandas.pydata.org/docs/user\_guide/10min.html)

#### Pandas Merge

[https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.merge.html](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.merge.html)

###
