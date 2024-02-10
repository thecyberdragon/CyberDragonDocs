# 🔍 Exploratory Data Analysis

_EDA is finding patterns and seeing what relationships there might be._

### Overview

***

#### Purposes

\-Uncover the data structure

\-Inspect the data by summarising and visualising it

\-Detect outliars and missing data & address anomilies

\-Get ideas for further analysis

\-Prepare for model building

#### Techniques

\-Data inspection

\-Numerical summarisation

\-Data visualisation

### Summary Statistics

***

Univariate analysis = analysis on one variable

Bivariate analysis = summarise the relationship between two values

Central tendancy = typical values

mean, median and mode

trimmed mean is the mean exlucing the top and bottom x %

Spread / distribution = the variability

Spread is affected by range, IQR, variance, standard deviation (square of deviation), mean absolute deviation (MAD)

IQR and MAD are good for data with extreme outliars

Categorical values are best summaried with counts

Two quantitative values can use Pearsons correlation.

Two categorical values can use a contingency table

####

### Types of Analysis

***

Univariate - Analysing one variable

Bivariate - Analysing two variables together (such as age and height)

Multivariant - Analysing more than two variables (such as age and height by county)

Multi variate analysis usually uses colours, shapes or sizes (visual cues)

![](https://t20664121.p.clickup-attachments.com/t20664121/c748a927-0dcd-4413-93ac-563906ca5046/image.png)

![](https://t20664121.p.clickup-attachments.com/t20664121/52195ac7-2dc7-4978-ab69-8b60960c8924/image.png)

#### Binning

Clumping numerical data into categorical groups such as ages into age ranges

```python
bins = [ 10, 20, 30, 40 ]
df[ "new_col" ] = pd.cut( df[ "col" ], bins )
# returns bins cut by those values

df[ "new_col" ] = pd.cut( df[ "col" ], bins, labels = list_of_labels )
# If bins need a categorical name
```

#### Masking smaller values

If some values are extremely under-represented in the dataset, then they can be combined into an "other" value.

```python
# Establish the value counts
counts = df.col.value_counts( )

# Create a mask of values based on logic
mask = df.isin( count[ count < number ].index )

# Assign the mask to the name "other"
df[ mask ] = "other"
```
