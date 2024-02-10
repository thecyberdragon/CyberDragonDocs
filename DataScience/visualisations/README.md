# 📊 Visualisations

## Visualisations

####

#### Overview

***



**Terminology**

**Univariate** - show 1 variable - Usually a count or distribution

**Bivariate** - show 2 variables

**Multivariable** - show more than that

**Process of visualising**

Preparing

Visualising

Styling

Picking a chart to use

What is the question being asked?

What type of data is being worked with?

![](https://t20664121.p.clickup-attachments.com/t20664121/a2d12554-65b0-45ab-933c-5caba64758bb/image.png)

**Concepts**

**Aesthetics**

Size, Shape, Colour, Position, Pattern

**Information redundancy**

Showing the same info twice in two different ways

Helps for prioritising data visually

Helps key data points stand out

**Provide necessary details**

Include context for the audience

Avoid chart junk

**Accessibility (universal design)**

Hue + Value (colour blind)

Good colour comparisons use contrasting to show values

Make font large enough

Keep the reading level to high school level

Define unfamiliar terms

Pace and organise information to avoid overload

Data does not speak for itself

Own the viz as author

Providing context or a summary helps prevent misunderstanding or false conclusions

#### Misc Charts

***

**Map (geography) - Univariate**

![](https://t20664121.p.clickup-attachments.com/t20664121/7be7a48f-78a1-45ae-931b-6b44f6e90e0b/image.png)

**Lag Plots**

![](https://t20664121.p.clickup-attachments.com/t20664121/f9ca13bc-2e86-4cee-83bc-3e28fb5167ca/image.png)

Shows whether the lag (previous point) in a dataset correlates with the current data. Randomness suggests there is no relationship. A lag is the smallest increment back one step. Lag 2 is 2 steps back etc.

**Autocorrelation Plot**

![](https://t20664121.p.clickup-attachments.com/t20664121/0be7b170-d6b4-4b5a-99e3-08f286a20272/image.png)

Being close to 0 suggests a weak correlation. Being closer to 1 or -1 indicates a stronger correlation.

Positive correlations are + numbers while negative correlations as -

Oscillation like above indicates a seasonality or fluctuation.

Decreasing oscillation over time shows a lack of correlation over time

**Heatmaps**

![](https://t20664121.p.clickup-attachments.com/t20664121/37653b8a-5ebc-41d9-aa53-4036916bad22/image.png)

Shows the difference in values as colour temperature

**Stacked Charts**

Stacked charts aren't great for showing proportions, either in char charts of line charts.

[https://developers.google.com/chart/interactive/docs/gallery/barchart#stacked-bar-charts](https://developers.google.com/chart/interactive/docs/gallery/barchart#stacked-bar-charts)

#### **Design - Colour**

***

#### **Sequential**

Same hue at different intensities

![](https://t20664121.p.clickup-attachments.com/t20664121/2f07a164-b2ee-47ba-8072-e0dbf0ba0736/image.png)

**Divergent**

Two opposing colours to show two sides of a scale

![](https://t20664121.p.clickup-attachments.com/t20664121/720ffc1a-93a8-4193-b257-b88073cca9a8/image.png)

**Categorical**

A colour per category

![](https://t20664121.p.clickup-attachments.com/t20664121/82cb4648-7d06-4f01-bdeb-ea281e50270a/image.png)

We tend to see darker = more and lighter = less

**Colours**

Red & Green aren't super great colours for colourblind viewers.

[http://seaborn.pydata.org/tutorial/color\_palettes.html](http://seaborn.pydata.org/tutorial/color\_palettes.html)

#### Design - Title & Description

A title is one of the best immediate tools for making the graph explainable

Titles can be descriptive or questions

Annotations help show the reader what's going on

Annotations are great for highlighting key details or outliers

Avoid confusion & avoid deception

[https://datavizcatalogue.com/](https://datavizcatalogue.com/)

## Code to Wrangle

**Lag Plots**

```
from pandas.plotting import lag_plot
lag_plot( df )
plt.show( )
```

_Lag pot code with pandas_

**Autocorrelation plot**

```
from pandas.plotting import autocorrelation_plot
autocorrelation_plot( df )
```

_Shows if points in a time series are correlated or not_
