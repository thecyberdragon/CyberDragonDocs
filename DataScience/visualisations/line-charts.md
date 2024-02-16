# 📊 Line Charts

## <mark style="color:red;">**Purpose**</mark>

***

Track changes over time

![](https://images4.imagebam.com/03/81/d8/MES1OSQ\_o.png)

_A point on a time series it call cross-sectional data._

### <mark style="color:yellow;">Matplotlib Line Chart</mark>

![](https://images4.imagebam.com/b0/06/e4/MES1OSR\_o.png)

```python
# Create plot
plt.plot( x_values, y_values, label = "this_label" )

# Select the graph area
plt.axis( [ x_min, x_max, y_min, y_max ] )

# Add a legend
plt.legend( )
```

### <mark style="color:yellow;">Specify colours and line style</mark>

```python
# Plot 1 as blue
plt.plot( x_values, y_values, color="blue", linestyle = "--" )

# Plot 2 as red
plt.plot( x_values, y_values_2, color="red", linestyle = ":" )

# Add legend and specify the location
plt.legend( [ label_1, label_2 ], loc = 1-9 )
#1 - 9 sets the legend location
```

_marker = "o" / "s" / "\*" (circle, square, star) <- The points on the line chart_

### <mark style="color:yellow;">Manually set fill region</mark>

![](https://images4.imagebam.com/15/1b/b3/MES1OSS\_o.png)

```python
# Specify fill region
plt.fill_between( x_values, y_lower, y_upper, alpha = 0.2 )

# Create plot
plt.plot( x_values, y_values )
```

_Line chart with error shade_
