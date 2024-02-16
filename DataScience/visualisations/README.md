# 📊 Visualisations

## <mark style="color:red;">Overview & Process</mark>

***

### <mark style="color:yellow;">**Terminology**</mark>

**Univariate** - show 1 variable - Usually a count or distribution\
**Bivariate** - show 2 variables\
**Multivariable** - show more than that

### <mark style="color:yellow;">**Process of visualising**</mark>

Preparing\
Visualising\
Styling

Picking a chart to use\
What is the question being asked?\
What type of data is being worked with?

![](https://images4.imagebam.com/b5/f0/4d/MES1OT8\_o.png)

## <mark style="color:red;">**Concepts**</mark>

***

### <mark style="color:yellow;">**Aesthetics**</mark>

Size, Shape, Colour, Position, Pattern

### <mark style="color:yellow;">**Information redundancy**</mark>

Showing the same info twice in two different ways\
Helps for prioritising data visually\
Helps key data points stand out

### <mark style="color:yellow;">**Provide necessary details**</mark>

Include context for the audience\
Avoid chart junk

### <mark style="color:yellow;">**Accessibility (universal design)**</mark>

Hue + Value (colour blind)\
Good colour comparisons use contrasting to show values\
Make font large enough\
Keep the reading level to high school level\
Define unfamiliar terms\
Pace and organise information to avoid overload\
Data does not speak for itself\
Own the viz as author\
Providing context or a summary helps prevent misunderstanding or false conclusions

## <mark style="color:red;">Misc Charts</mark>

***

### <mark style="color:yellow;">**Map (geography) - Univariate**</mark>

![](https://images4.imagebam.com/78/2c/e4/MES1OT9\_o.png)

### <mark style="color:yellow;">**Lag Plots**</mark>

![](https://images4.imagebam.com/01/25/dc/MES1OTB\_o.png)

Shows whether the lag (previous point) in a dataset correlates with the current data. Randomness suggests there is no relationship. A lag is the smallest increment back one step. Lag 2 is 2 steps back etc.

```python
from pandas.plotting import lag_plot
lag_plot( df )
plt.show( )
```

_<mark style="color:green;">Lag pot code with pandas</mark>_

### <mark style="color:yellow;">**Autocorrelation Plot**</mark>

![](https://images4.imagebam.com/5b/23/fe/MES1OTC\_o.png)

Being close to 0 suggests a weak correlation. Being closer to 1 or -1 indicates a stronger correlation.\
Positive correlations are + numbers while negative correlations as -\
Oscillation like above indicates a seasonality or fluctuation.\
Decreasing oscillation over time shows a lack of correlation over time

```python
from pandas.plotting import autocorrelation_plot
autocorrelation_plot( df )
```

_<mark style="color:green;">Shows if points in a time series are correlated or not</mark>_

### <mark style="color:yellow;">**Heatmaps**</mark>

![](https://images4.imagebam.com/69/3b/84/MES1OTD\_o.png)

Shows the difference in values as colour temperature

### <mark style="color:yellow;">**Stacked Charts**</mark>

Stacked charts aren't great for showing proportions, either in char charts of line charts.

[https://developers.google.com/chart/interactive/docs/gallery/barchart#stacked-bar-charts](https://developers.google.com/chart/interactive/docs/gallery/barchart#stacked-bar-charts)

## <mark style="color:red;">**Design - Colour**</mark>

***

### <mark style="color:yellow;">**Sequential**</mark>

Same hue at different intensities

![](https://images4.imagebam.com/68/72/78/MES1OTF\_o.png)

### <mark style="color:yellow;">**Divergent**</mark>

Two opposing colours to show two sides of a scale

![](https://images4.imagebam.com/be/e6/49/MES1OTH\_o.png)

### <mark style="color:yellow;">**Categorical**</mark>

A colour per category

![](https://images4.imagebam.com/26/2e/1f/MES1OTI\_o.png)

We tend to see darker = more and lighter = less

### <mark style="color:yellow;">**Colours**</mark>

Red & Green aren't super great colours for colourblind viewers.

[http://seaborn.pydata.org/tutorial/color\_palettes.html](http://seaborn.pydata.org/tutorial/color\_palettes.html)

## <mark style="color:red;">Design - Title & Description</mark>

***

A title is one of the best immediate tools for making the graph explainable\
Titles can be descriptive or questions\
Annotations help show the reader what's going on\
Annotations are great for highlighting key details or outliers\
Avoid confusion & avoid deception

[https://datavizcatalogue.com/](https://datavizcatalogue.com/)

```
```
