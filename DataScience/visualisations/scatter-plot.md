# 📊 Scatter Plot

## <mark style="color:red;">Structure</mark>

***

Data by x and y axis (numeric values)

![](https://images4.imagebam.com/ae/ab/4f/MES1OSY\_o.png)

## <mark style="color:red;">Python Code</mark>

***

![](https://images4.imagebam.com/23/19/f6/MES1OSZ\_o.png)

### <mark style="color:yellow;">Seaborn scatter plot</mark>

```python
# Create lmplot and setting the colour
sns.lmplot( x = "col_1", y = "col_2", data = df, hue = "col" )

# Create lmplot and specify the line appearence
sns.lmplot( x = "col_1", y = "col_2", data = df, line_kws = { "color":"black" }, lowess = True )
```

_<mark style="color:green;">Seaborn scatter plot with auto regression lines and hue</mark>_

Lowess = locally weighted scatterplot smoothing

#### Scatter with the jitters

![](https://images4.imagebam.com/8c/3b/bf/MES1OT1\_o.png)

```python
sns.lmplot( x = "col_1", y = "col_2", data = df, x_jitter = 0.15, y_jitter = 0.15, fit_reg = False )
```

### <mark style="color:yellow;">Matplotlib Scatter Graph</mark>

![](https://images4.imagebam.com/ce/37/a5/MES1OT2\_o.png)

```python
# Standard basic syntax
plt.scatter( x = df.col1, y = df.col2 )
plt.xlabel("label")
plt.ylabel("label")

# For multi variate charts
plt.scatter( x = df.col1, y = df.col2, style = "style", s = size_of_points, alpha = number )
```

### <mark style="color:yellow;">Plotting a line of best fit</mark>

```python
# Create scatter plot
plt.scatter( x = data.value, y = data.other_value )

# Not sure if this is needed or not
plt.plot( [0, 1], [val1, val2] )

# Plot the line of best fit
plt.plot( data.x_value, results.predict( data.x_value ) )
```

_results comes from the statsmodel OLS function -->_ [statsmodels.api.md](statsmodels.api.md "mention")
