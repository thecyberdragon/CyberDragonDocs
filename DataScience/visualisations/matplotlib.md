# ⚙ Matplotlib

### Importing

***

```python
import matplotlib.pyplot as plt
```

### Labels & Axis

***

```python
plt.xlabel( "name of x label" )
plt.ylabel( "name of y label" )
plt.title( "name of title", pad=num )
plt.xlim( val_1, val_2 )
```

_pad will increase the space between the title and the chart_

#### Axis Limit

```python
plt.ylim(0, 1e12)
```

_This is to set the y limit. The number is the digit limit. 12 being 1 followed by 12 0's._

### Clearing the plot

***

```python
plt.show ( ) 

# To close the plot
plt.close ( )

# To close and clear the plot
plt.clf ( )
```

### Subplots

***

![](https://t20664121.p.clickup-attachments.com/t20664121/8a6e2765-694e-4461-8224-c006b50d733a/image.png)

```python
plt.subplot( row_numbers, col_numbers, plot_number )
```

_The sum of subplots is called the figure_

**Alternatively**

```
fig = plt.figure( )
ax1 = fig.add_subplot( rows, cols, 1 )
ax2 = fig.add_subplot( rows, cols, 2 )
ax3 = fig.add_subplot( rows, cols, 3 )

ax1.scatter( x, y )
ax2.bar( x, y )
ax3.pie( array, labels - [ "list", "of", "labels ] )
```

_This allows you to call each subplot instead of relying on the code order_

#### Configure Subplots

```python
plt.subplot( 1, 2, 1 )
plt.plot( x, y )
plt.title( "chart_one" )

plt.subplot( 1, 2, 2 )
plt.plot( x2, y2 )
plt.title( "chart_two" )
```

#### Adjust Subplots

```python
plt.subplots_adjust ( parameter_margin = number )
# left / right / bottom / top
# wspace (horizontal) / hspace (vertical)
plt.tight_layout( )
# Should auto the margins
```

### Making 3D plots

```
fig = plt.figure( )
ax1 = fig.add_subplot( 1,1,1,projection="3d )
ax1.scatter( x, y, z )
```

#### X and Y Ticks

```python
ax = plt.subplot ( 1, 1, 1 )
plt.plot( x, y )
plt.plot (x2, y2 )
ax.set_xticks( [ x1, x2, x3 ] )
ax.set_yticks( [ y1, y2, y3 ] )

ax.set_yticklabels( "y1%", "y2%", "y3%" )
ax.set_xticklabels( [ label1, label2, label3 ], rotation = 30 )
```

_Ticks are the graph value labels on the_

_Tick labels are for reformatting the axis_

#### Rotate and Align

```python
plt.xticks(rotation=30, ha='right')
```

_ha = horizontal alignment_

#### Flip Axis

```python
ax = plt.subplot( 1, 1, 1 )
ax.invert_yaxis( )
```

#### Close all subplots

```python
plt.close("all")
```

### Figures

***

```python
fig = plt.figure( figsize = ( x, y ) )
fig.suptitle( "title of figure" )
plt.plot( x, y )
plt.savefig( "file_name.png" )
```

```python
plt.figure(1)
```

###

### Colours

![](https://t20664121.p.clickup-attachments.com/t20664121/ff8bf454-86bd-42cc-a109-d948218fbb5b/image.png)

### Documentation

[https://matplotlib.org/](https://matplotlib.org/)
