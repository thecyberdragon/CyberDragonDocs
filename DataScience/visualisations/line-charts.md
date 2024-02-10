# 📊 Line Charts

### **Purpose**

Track changes over time

![](https://t20664121.p.clickup-attachments.com/t20664121/d68ded66-0d64-4ed6-862e-be7ed0a2e614/image.png)

_A point on a time series it call cross-sectional data._

#### Matplotlib Line Chart

![](https://t20664121.p.clickup-attachments.com/t20664121/8dabd87d-56fa-47a3-a140-7a67ae9c11bc/image.png)

```python
# Create plot
plt.plot( x_values, y_values, label = "this_label" )

# Select the graph area
plt.axis( [ x_min, x_max, y_min, y_max ] )

# Add a legend
plt.legend( )
```

#### Specify colours and line style

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

#### Manually set fill region

![](https://t20664121.p.clickup-attachments.com/t20664121/0c307737-564e-4ef2-b1f9-86a44e08ee00/image.png)

```python
# Specify fill region
plt.fill_between( x_values, y_lower, y_upper, alpha = 0.2 )

# Create plot
plt.plot( x_values, y_values )
```

_Line chart with error shade_
