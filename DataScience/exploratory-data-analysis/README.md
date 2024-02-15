# 🔍 Exploratory Data Analysis

_EDA is finding patterns and seeing what relationships there might be._

## <mark style="color:red;">Overview</mark>

***

### <mark style="color:yellow;">Purposes</mark>

\-Uncover the data structure\
\-Inspect the data by summarising and visualising it\
\-Detect outliers and missing data & address anomalies\
\-Get ideas for further analysis\
\-Prepare for model building

### <mark style="color:yellow;">Techniques</mark>

\-Data inspection\
\-Numerical summarisation\
\-Data visualisation

## <mark style="color:red;">Summary Statistics</mark>

***

<mark style="color:yellow;">Univariate analysis</mark> = analysis on one variable\
<mark style="color:yellow;">Bivariate analysis</mark> = summarise the relationship between two values\
<mark style="color:yellow;">Central tendancy</mark> = typical values

mean, median and mode\
trimmed mean is the mean excluding the top and bottom x %

Spread / distribution = the variability

Spread is affected by range, IQR, variance, standard deviation (square of deviation), mean absolute deviation (MAD)

IQR and MAD are good for data with extreme outliers

Categorical values are best summaried with counts\
Two quantitative values can use Pearsons correlation.\
Two categorical values can use a contingency table

### <mark style="color:yellow;">Types of Analysis</mark>

<mark style="color:yellow;">Univariate</mark> - Analysing one variable\
<mark style="color:yellow;">Bivariate</mark> - Analysing two variables together (such as age and height)\
<mark style="color:yellow;">Multivariant</mark> - Analysing more than two variables (such as age and height by county)

Multi variate analysis usually uses colours, shapes or sizes (visual cues)

![](https://images4.imagebam.com/f4/98/ee/MES1Q6R\_o.png)

![](https://images4.imagebam.com/4f/24/8e/MES1Q6Q\_o.png)

### <mark style="color:yellow;">Techniques</mark>

Binning = Clumping numerical data into categorical groups such as ages into age ranges

```python
bins = [ 10, 20, 30, 40 ]
df[ "new_col" ] = pd.cut( df[ "col" ], bins )
# returns bins cut by those values

df[ "new_col" ] = pd.cut( df[ "col" ], bins, labels = list_of_labels )
# If bins need a categorical name
```

Masking smaller values  = If some values are extremely under-represented in the dataset, then they can be combined into an "other" value.

```python
# Establish the value counts
counts = df.col.value_counts( )

# Create a mask of values based on logic
mask = df.isin( count[ count < number ].index )

# Assign the mask to the name "other"
df[ mask ] = "other"
```
