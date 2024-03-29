# 📊 Bar Chart

## <mark style="color:red;">**Overview**</mark>

***

Show different variables or values

![](https://images4.imagebam.com/ae/dd/37/MES1OTJ\_o.png)

## <mark style="color:red;">Python Code</mark>

***

![](https://images4.imagebam.com/e0/21/aa/MES1OTK\_o.png)

### <mark style="color:yellow;">Seaborn Bar Chart</mark>

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Seaborn bar chart
sns.barplot( x = df.col1, y = df.col2 )

# Show then clear the plot
plt.show( )
plt.clf( )
```

### <mark style="color:yellow;">Cat Plot</mark>

![](https://images4.imagebam.com/cf/4d/a9/MES1OTL\_o.png)

```python
# no plt required
sns.catplot( data=df, kind="bar", x="field", y="field", height = 6, aspect = 2 )

# Create a chart per category
sns.catplot( x = "x_col", col = "col_per_chart", data = df, kind = "count", height = 6, aspect = 2 )
```

### <mark style="color:yellow;">Count Plots</mark>

![](https://images4.imagebam.com/4b/5c/d7/MES1OTN\_o.png)

```python
# Method 1: From column in dataframe
sns.countplot( x = "column", data = df, palette = "seaborn_palette" )

# Method 2: From column in dataframe and spceify values
sns.countplot( data[ "column" ], order = [ "list", "of", "values" ] )

# Method 3: From column in a dataframe and order by all unique values
sns.countplot( data[ "column" ], order = data[ "column" ].value_counts( ).index )
```

### <mark style="color:yellow;">Pyplot Bar Chart</mark>

```python
import matplotlib.pyplot as plt

# Pyplot Bar Chart
plt.bar( x_values, y_values )

# Show then clear the plot
plt.show( )
plt.clf( )
```

### <mark style="color:yellow;">Side-By-Side Bar Chart</mark>

```python
# Variables to use
number_of_set = 2
number_of_bars = 4
width = 0.8

# Values of first bar locations
x_values1 = [ 1 * element + width * number_of_set for element in range( number_of_bars ) ]

#value_1 = 1 * 0 + 0.8 * 2 = 1.6
#value_2 = 1 * 1 + 0.8 * 2 = 2.6

# Values of second bar locations
x_values2 = [ 2 * element + width * number_of_set for element in range( number_of_bars ) ]

# Plot the values and their locations
plt.bar( x_values1, x_numbers1 )
plt.bar( x_values2, x_numbers2 )

# Mid point of bars
middle_x = [ ( a + b ) / 2.0 for a, b in zip( x_values1, x_values2 ) ]


```

_To get side by side bars using pyplot_

### <mark style="color:yellow;">Stacking Bars</mark>

![](https://images4.imagebam.com/ca/3d/89/MES1OTO\_o.png)

```python
import matplotlib.pyplot as plt

# Plot the first and second values
plt.bar( xvals_1, x_nums1 )
plt.bar( xvals_2, x_nums2, bottom = xvals_1 )

# Find the height of bottom for more than 2 types
bottom_3 = np.add( val_a, val_b )

# Show then clear the plot
plt.show( )
plt.clf( )
```

### <mark style="color:yellow;">Error Bars</mark>

![](https://images4.imagebam.com/44/75/aa/MES1OSH\_o.png)

```python
import matplotlib.pyplot as plt

# Plot the Bar Chart
plt.bar( x_values, x_numbers, yerr = number, capsize = 10 )
```

_The top and bottom of the lines are 'caps'_\
yerr is the error range\
capsize is the width of the cap on the graph\
yerr can also equal a list to have different sizes
