# 🚿 Data Cleaning & Wrangling

## <mark style="color:red;">Starting off</mark>

***

How many non-null observations are there?\
How manyuinique columns and features do we have?\
Which columns contain missing data?\
What is the data type of each column?\
Keep a record of cleaning / changes incase that might be needed later

## <mark style="color:red;">**Missing Data**</mark>

***

Handling missing data helps increase accuracy of observations and gives us more statistical power.

### <mark style="color:yellow;">**Missing data terms**</mark>

Missing completely at random - Random missing data\
Missing at random - Missing data by some sort of pattern\
Structurally missing - optional or contextual data points

### <mark style="color:yellow;">Reasons data might be missing</mark>

#### Systemic - Data not originally provided.

1- Check data was uploaded correctly in the first place. Handle missing data by preventing it.\
2- Take a look at small chunks of data\
3- Look at statistics for the dataset

### <mark style="color:yellow;">Types of missing data</mark>

<mark style="color:yellow;">Structurally missing</mark> - Logical reasons for data to be missing\
<mark style="color:yellow;">Missing completely at random</mark> - All data has an equal chance of being missing\
<mark style="color:yellow;">Missing at random</mark> - Likelihood different for different groups but equal within that group (sub group)\
<mark style="color:yellow;">Missing not at random</mark> - There is some non-structural reason for the missing data

### <mark style="color:yellow;">Methods to handle missing data</mark>

<mark style="color:yellow;">Impute</mark> - Taking the average to fill missing values\
<mark style="color:yellow;">Interpolate</mark> - Generating values based on the distribution\
<mark style="color:yellow;">Delete</mark> - Remove the observation

### <mark style="color:yellow;">Metadata of the data</mark>

Who compiled it, date, time, how etc.

### <mark style="color:yellow;">Deletion</mark>

Introduces the risk of bias.

Deleting too much data might misrepresent the dataset.

\-It's safe if the data is missing at random or missing completely at random.

Deleting too much may reduce the sample size too much.

\-It's safe to remove data with low correlation to other features.

**Listwise deletion** - Complete case analysis - remove entire observation

This can be used with missing variables will directly impact analysis. Be cautious not to delete too much. 5% is a good "too much data to remove" standard.

```python
# Using a pandas dataframe as df
df.dropna( inplace=True )
```

**Pairwise deletion** - Based on context. Only remove rows when missing data is part of the analysis.

This method retains as much information as possible.

```python
# Using a pandas data frame as df
df.dropna( subset=[ "col1","col2" ], inplace=True, how="any" )
```

If a column is missing enough data, we may drop it entirely. This is only a last resort. More data is better than less. Generally, if the column is missing over 60% of the data.

### <mark style="color:yellow;">Single imputation</mark>

Filling in a single missing field.\
Possible to introduce bias in the analysis.\
Useful quick fix, but not sophisticated.

#### LOCF - last observation carried forward. Good for when data is close together and consistent.

```python
# Pandas data frame
df.col.ffill( axis=0, inplace=True )

# Numpy array
impyute.imputations.ts.locf( data, axis=0 )
```

#### NOCB - Next observation carried backwards. If future data is consistent.

```python
# Pandas data frame
df.col.bfil( axis=0, inplace=True )

# Numpy array
impyute.imputation.ts.nocb( date, axis=0 )
```

#### BOCF - Baseline observation carried forward. First value in data set

```python
# Pandas data frame
baseline = df.col[0]
df.col.fillna( value=baseline, inplace=True )
```

#### WOCF - Worst observation carried forward. Worst value in data set

```python
# If low = worse
worst = df.col.min()
df.col.fillna( value=worst, inplace=True )
```

### <mark style="color:yellow;">Multiple Imputation</mark>

Filling in multiple missing data multiple times.

\-Assign placeholder value\
\-Remove missing data for one variable\
\-Predict values based on other variables\
\-Replace values in variable --> _Remove missing data for one variable_\
\-Integrate predicted values into dataset

For missing at random categorical datasets.\
After each iteration, the variables should become more accurate.

The goal is to fill in the missing data so that it can find a model to best fit the dataset, typically either a normal or chi-square model.

Best used for missing at random data. There is an assumption that there is an underlying reason for the missing data and we have a good understanding of why. You can't use random data to fill as the missingness isn't totally at random.

This method doesn't introduce bias. The model we get at the end will ensure the added values will be a close approximation to the actual values.

```python
# Import libraries
from sklearn.experimental import enable_iterative_imputer
from sklean.impute import IterativeImputer

# Create a model to predict values
imp = IterativeImputer(max_iter=10, random_state=0)

# df_test is a DataFrame for the model, can be a subset of the main dataset
# df is the data set to fill
# This can return a proportion of the dataset for the df_test
traindf, testdf = train_test_split( imputedf, train_size=0.1 )

# Fit values in the data frame
imp.fit( df_test )
df_complete = pd.DataFrame( imp.transform( df ), columns=["col1", "col2", "col3"] )


```

```python
from sklearn.experimental import enable_iterative_imputer
from sklearn.impute import IterativeImputer
from sklearn.model_selection import train_test_split

imputedf = df[ [ "col_1", "col_2"  ] ]
traindf, testdf = train_test_split( imputedf, train_size=0.1 )

imp = IterativeImputer(max_iter=20, randomstate=0)

imp.fit( imputedf )
```

<mark style="color:red;">What is the df\_test for????</mark>

#### Checking percentage of missing data per column

```python
# Get the total row count
maxrows = df.id.count( )

# Return per row the percentage of missing data
print((1 - df.count( ) / maxrows) * 100)
```





