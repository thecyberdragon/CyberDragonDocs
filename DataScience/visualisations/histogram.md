# 📊 Histogram

## <mark style="color:red;">Purpose</mark>

***

Show distributions

![](https://images4.imagebam.com/dc/11/e7/MES1OSM\_o.png)

## <mark style="color:red;">Python Code</mark>

***

![](https://images4.imagebam.com/68/0f/a7/MES1OSN\_o.png)

### <mark style="color:yellow;">Seaborn Histogram</mark>

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Create the plot
sns.distplot( x = "volumn", data = dataframe, kde = False )

# Show and clear the plot
plt.show( )
plt.clf( )
```

![](https://images4.imagebam.com/36/4e/3f/MES1OSO\_o.png)

### <mark style="color:yellow;">Matplot Lib Histogram</mark>

```python
import matplotlib.pyplot as plt

# Create the plot
plt.hist(x = "column", data = df )

# Show and clear the plot
plt.show( )
plt.clf( )
```

#### Matplotlib - AX Line, bins, range

```python
import matplotlib.pyplot as plt

# Create plot limiting by a range and setting number of bins
plt.hist( values, range = (  first_value, last_value ), bins = num )

# Set a vertical line at a set location
plt.axvline( number, color = "color", linestyle = "dashed" )

# Show and clear the plot
plt.show( )
plt.clf( )
```

_Axvline creates a vertical line on the graph_\
Bins are how many bars are on the histogram\
Range can be specified to only show a certain range of values

### <mark style="color:yellow;">Matplotlib - Step-style probability density histogram</mark>

```python
import matplotlib.pyplot as plt

# Plot two histograms to be normalised
plt.hist( values_1, histtype = "step", density = True )
plt.hist( values_2, histtype = "step", density = True )

# Show and clear the plot
plt.show( )
plt.clf( )
```

Histtype step only shows the outline\
Density normalises the distributions so they're comparable

### <mark style="color:yellow;">Matplotlib - Overlapping alpha histograms (normed)</mark>

```python
import matplotlib.pyplot as plt

# Create plots
plt.hist( values_1 , color = "blue", label = "val_1", normed = True, alpha = 0.5 )
plt.hist( values_2 , color = "red", label = "val_2", normed = True, alpha = 0.5 )

# Show and clear the plot
plt.show( )
plt.clf( )
```

_<mark style="color:green;">Overlapping histogram. Normaled values normalises the proportions.</mark>_

### <mark style="color:yellow;">Numpy Histogram</mark>

```python
np.histogram( np_array, range = ( min, max ) bins = x )
```

_<mark style="color:green;">This returns two arrays, not an image.</mark>_

Array 1 is the counts for each bin\
Second array contains the value ranges for each bin
