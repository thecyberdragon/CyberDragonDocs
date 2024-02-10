# 📊 Scatter Plot

### Structure

Data by x and y axis (numeric values)

![](https://t20664121.p.clickup-attachments.com/t20664121/70897440-4321-4049-bcde-4dee14765a1c/image.png)

### Seaborn scatter plot

![](https://t20664121.p.clickup-attachments.com/t20664121/f3121835-ef99-40fc-8527-a5d53079dac2/image.png)

```python
# Create lmplot and setting the colour
sns.lmplot( x = "col_1", y = "col_2", data = df, hue = "col" )

# Create lmplot and specify the line appearence
sns.lmplot( x = "col_1", y = "col_2", data = df, line_kws = { "color":"black" }, lowess = True )
```

_Seaborn scatter plot with auto regression lines and hue_

Lowess = locally weighted scatterplot smoothing

#### Scatter with the jitters

![](https://t20664121.p.clickup-attachments.com/t20664121/0abe15e9-3b99-4c3b-bc5e-bef4158671f5/image.png)

```python
sns.lmplot( x = "col_1", y = "col_2", data = df, x_jitter = 0.15, y_jitter = 0.15, fit_reg = False )
```

#### Matplotlib Scatter Graph

![](https://t20664121.p.clickup-attachments.com/t20664121/ec1faff2-169c-4315-ae71-21960542883e/Untitled.png)

```python
# Standard basic syntax
plt.scatter( x = df.col1, y = df.col2 )
plt.xlabel("label")
plt.ylabel("label")

# For multi variate charts
plt.scatter( x = df.col1, y = df.col2, style = "style", s = size_of_points, alpha = number )
```

#### Plotting a line of best fit

```python
# Create scatter plot
plt.scatter( x = data.value, y = data.other_value )

# Not sure if this is needed or not
plt.plot( [0, 1], [val1, val2] )

# Plot the line of best fit
plt.plot( data.x_value, results.predict( data.x_value ) )
```

_results comes from the statsmodel OLS function -->_ Private ([https://app.clickup.com/20664121/docs/kpktt-588/kpktt-1748](https://app.clickup.com/20664121/docs/kpktt-588/kpktt-1748))
