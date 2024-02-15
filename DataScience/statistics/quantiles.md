# 🎲 Quantiles

### <mark style="color:yellow;">Quartiles</mark>

Quartiles split the data into four equal chunks\
Q1, Q2 and Q3

Q2 is the median

Find the median (Q2)\
Sort the dataset and find the middle value\
Odd datasets = 1 explicit value as the median\
Even datasets = mean of the two middle values

Find Q1 and Q3\
Q1 is the median of every value below Q2\
Q3 is the median of every value after Q2

Some methods don't exclude Q2 from Q1 and Q3 calculations which might yield different results.

Odd datasets = include the middle value\
Even datasets = the same as method 1 (don't include the implicit median)

```python
# Number is between 0 and 1
np.quantile(  np_array, number )
np.quantile( np_array, [ q1, q2, q3, q4 ... ] )
```

_The number is the quantile point. 0.5 = Q2, 0.75 = Q3_

### <mark style="color:yellow;">Five-Number Summary</mark>

Q1, Q2, Q3, Minimum and Maximum\
Interquartile range is the range between Q1 and Q3

```python
from numpy.stats import iqr

interquartile_range = iqr( np_array )
```

### <mark style="color:yellow;">Box Plots</mark>

Whiskers are the lines extending out from the IQR before the ends of the plot\
Outliers are last the whiskers and are represented as dots

Whiskers can be:

* The minimum and maximum values
* 1.5 \* the IQR in each direction (usually to the nearest point in the direction towards the IQR)

![](https://images4.imagebam.com/12/ff/8c/MES1OPJ\_o.png)
