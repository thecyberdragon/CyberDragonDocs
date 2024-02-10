# 📊 Histogram

### Purpose

Show distributions

![](https://t20664121.p.clickup-attachments.com/t20664121/bae8ed3b-b65e-441b-b20d-c10844ba8c55/image.png)

####

### Seaborn Histogram

![](https://t20664121.p.clickup-attachments.com/t20664121/c79f4313-8c2b-4b05-870c-7a15eea77b45/Untitled.png)

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Create the plot
sns.distplot( x = "volumn", data = dataframe, kde = False )

# Show and clear the plot
plt.show( )
plt.clf( )
```

![](https://t20664121.p.clickup-attachments.com/t20664121/7ab00ba9-e4f8-493a-a7d2-513d80f95958/Untitled.png)

### Matplot Lib Histogram

```python
import matplotlib.pyplot as plt

# Create the plot
plt.hist(x = "column", data = df )

# Show and clear the plot
plt.show( )
plt.clf( )
```

####

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

_Axvline creates a vertical line on the graph_

Bins are how many bars are on the histogram

Range can be specified to only show a certain range of values

#### Matplotlib - Step-style probability density histogram

```python
import matplotlib.pyplot as plt

# Plot two histograms to be normalised
plt.hist( values_1, histtype = "step", density = True )
plt.hist( values_2, histtype = "step", density = True )

# Show and clear the plot
plt.show( )
plt.clf( )
```

Histtype step only shows the outline

Density normalises the distributions so they're comparable

#### Matplotlib - Overlapping alpha histograms (normed)

```python
import matplotlib.pyplot as plt

# Create plots
plt.hist( values_1 , color = "blue", label = "val_1", normed = True, alpha = 0.5 )
plt.hist( values_2 , color = "red", label = "val_2", normed = True, alpha = 0.5 )

# Show and clear the plot
plt.show( )
plt.clf( )
```

_Overlapping histogram. Normaled values normalises the proportions._

#### Numpy Histogram

```python
np.histogram( np_array, range = ( min, max ) bins = x )
```

_This returns two arrays, not an image._

Array 1 is the counts for each bin

Second array contains the value ranges for each bin
