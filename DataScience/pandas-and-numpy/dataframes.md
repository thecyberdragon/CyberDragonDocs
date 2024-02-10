# 🐼 DataFrames

### DataFrames Overview

***

#### Show overview of a dataframe

```python
# Describe the frame
df.describe(include="all")

# Get info
df.info( )

# Get data types
df.dtypes

# Columns vs rows
df.shape
```

#### Accepted data types

float, int, bool, datetime, timedelta, category and object

####

#### Creating a dataframe from zipped lists

```python
data = list( zip( list_1, list_2, list_3 ) )
df = pd.DataFrame( date, columns = [ "name1", "name2", "name3" ] )
```

#### View Options

```python
pd.set_option("display.max_colwidth", None)
pd.set_option('display.float_format', '{:.2f}'.format)
```

_Displays the full content of a column_

#### **Select a column in a dataframe**

```python
df [ "column_name" ] or df.column_name
```

#### Making a copy of a DataFrame

```python
df2 = df1.copy()
```

#### **Getting data from existing data frame using a query**

```python
# Returns all columns with the matching column value
new_df = df [ df [ "column" ] == value ]

# Returns only the searched column
new_df = df.col[ df[ "col" ] == value ]
```

_If the column values for "column" == value, add the row to new\_df_

#### **Use multiple conditions in a data frame query.**

```python
new_df = df [ (df [ "column" ] == "value" ) | ( df [ "column" ] != "value" ) ]
```

_Using more than one query requires each query to be inside brackets and the logical operators used:_

_| for OR and & for AND_

#### **DataFrame Attributes**

df.index

df.columns - column names

df.axes

df.dtypes - data types of columns

df.size

df.shape

df.ndim

df.empty

df.values - values in the table

#### Add an entry to a dataframe

```python
df.loc[ len( df ) ] = { "key":"val", "key2":"val2" }
```

```python
df = df.append( { "key","val", "key2":"val2" }, ignore_index=True )
```

### DataFrames - Columns

***

#### **Creating a new column**

```python
# New column from values
df [ "new name" ] = values

# new colume from existing column
df[ "new name" ] = df[ "other name" ] ** 2
```

#### **Rename columns**

```python
# Manually rename all columns in order
df.columns = [ "new_col_1" , "new_col_2" ]

# Rename columns using a dictionary
df.rename ( columns = { "key" : "val" } , inplace = True )
```

_inplace = True_ _will replace the existing column names as opposed to making a new dataframe_

#### Remapping Column Case

```python
df.columns = map( str.lower, dp.columns )
```

Remap the columns case to lower as a string

#### Change a column data type

```cpp
df [ "col_to_change" ] = df [ "col_to_change" ] . astype ( "new_data_type" )
```

_Some types can't convert if there are any null values such as inf or nan from float to int_

_Pandas will make text an object, so needs converting to a string to use string operations on it_

#### Making a column a categorical type

```python
df [ "col" ] = pd.Categorical( df[ "col" ], [ "category_one", "category_two", "category_three", category_four" ], ordered = True )
```

_column order starts from the smallest first_

#### Category column code

```cpp
variable = df [ "categorical_column" ] . cat . codes
```

_Returns the value index and it's numerical categorisation_

#### Dummy columns with one-hot encoding

```python
df = pd.get_dummies( data = df, columns = [ "column" ] )
```

_Creates new binary columns for all values in the dataframe prefixed with the column name_

#### Dummy columns for regression models

```python
df = pd.get_dummies( data, columns = ["name"], drop_first = True )
```

_This drops the first indicator as per x-matrix in StatsModel_

#### New Dataframe from Columns

```python
df = df [[ "col1","col2","col3" ]]
```

#### Get column series using a search

```python
np_array = df.loc[ df[ "col" ] == "value" ][ "column_to_return" ]
```

#### Turning a series to a list

```python
new_list = df.col.tolist( )
```

#### Drop a column

```
df.drop("col_name", axis=1, inplace=True)
```

_axis=1 means column while axis=0 means row_

### DataFrames - Nulls

***

### Making a value null

```python
df [ "column" ] = df [ "column" ].replace( "char", np.NaN )
```

#### **Checking for and showing all null values**

```python
df [ "column_name" ].isnull ( ).values ( ).any ( )
```

#### Performing a sum for all null values in a column

```cpp
df [ "column_name" ].isnull ( ).sum ( )
```

####

#### Fill in NA & NAN fields in a column

```python
# Replace nulls with dictionary
df = df [ "column" ].fillna( value = { key:val, key:val }, inplace = True)

# Fill nulls with a value
df = df.fillna( "val" )

# Fill nulls in 1 column with a value
df = df.col.fillna( "val" )
```

_Can replace missing values with the data set mean_

#### Dropping Nulls

```python
# Drop all nulls
df = df.dropna( )

# Drop nulls from specific column
df = df.dropna( subset = [ "column" ] )
```

#### Finding count of null values

```python
df.isna( ).sum( )
```

#### Replacing values with nulls

```python
df.column = df.column.where( df.column == "logic", np.nan )
```

### DataFrames - Modifying and sorting

***

#### **After modifying a data frame**

```python
df.reset_index ( drop=True , inplace=True )
```

_reset\_index_ _will reset the index back to 0,1,2,3,4 and_ _drop = True_ _will delete the old indexes which will carry over._ _inplace = True_ _will alter the dataframe as opposed to making a new dataframe._

#### **Locating row by index or string**

```python
# Using an index
row_with_index = df.iloc( int )

# Using logic (True = new value if found)
df.loc[ df [ "col" ].str.contains( "string" ), "new_column"] = True
```

#### Updating a row based on the index

```python
for index, row in df.iterrows():
  df.at[ index, "col_to_update" ] = "new_value"
```

#### **ySorting a dataframe**

```python
sorted = data.sort_values ( by=column_name, ascending=False )
```

#### Returning the top x of a column

```python
top_10 = df.nlargest( 10, "column_name" )
```

#### Sorting by a categorical column

```python
sort_order = [ "list", "of", "categories" ]
df[ "col" ] = pd.Categorical( df[ "col" ], categories = sort_order, ordered = True )
df = df.sort_values( by = "col" )
```

#### Find Duplicates

```python
pd.duplicated()
```

#### Drop Duplicates

```python
# Drop all duplicates
df = df.drop_duplicates()

# Drop all duplicates by checking 1 column
df = df.drop_duplicates(subset = ["item"])
```

#### CrossTab Function

```python
pd.crosstab(
  df.col, 
  df.col2.isna( ),
  rownames = ['row_name'],
  colnames = ['col2 is na']
)
```

#### Adding column names to rows

```python
df = pd.melt(frame=df,
  id_vars = ["col_to_preserve"],
  value_vars = ["old_columns"]
  var_name = "new_col_for_old_col_names",
  value_name = "new_col_name_for_old_variables"
)
```

#### Creating bins from data

```python
quantile = pd.cut(df[ "col" ], q = 5  ) 
```

### DataFrames - Applying Logic

***

#### **Applying logic to a dataframe**

```python
df [ "altered" ] = df [ "column" ].apply ( something )
```

#### Applying logic to a dataframe using a lambda function

```python
# Apply logic using lambda with an if else statement
df [ "new_column" ] = df [ "column" ].apply ( lambda x: "True" if x == "something" else "False" )

# Apply logic using a lambda
new_df = df [ df [ "column" ].apply ( lambda x: x == "something" ) ]
```

```python
df [ "new_col" ] = df.apply( lambda x: x.col + x.col2 )
```

#### List comprehension inside a lambda function

```python
# New data frame where any records match any list items
new_df = df [ df [ "column" ].apply ( lambda x: any( item in row for item in list_items ) ) ]

# New dataframe where all records match all list items
new_df = df [ df [ "column" ].apply ( lambda x: all( item in row for item in list_items ) ) ]
```

_Using lambda to make a new dataframe using list comprehension and any ( ) or all ( )_

axis=1 must be passed at the end of an apply if a single column isn't specified and allows the input of an entire row.

#### Random subset from data frame

```python
sub_df = df.sample( n = int( df.shape[0] * percentage ) )
```

#### Replacing values with RegEx

```python
df.col = df["col"].replace( "regex", "replace_with", regex = True )
```

#### Converting Col to numbers

```cpp
df.col = pd.to_numeric( df.col )
```

###

#### Replacing characters with regex

```python
df.col = df["col"].replace( "char", "replace_with", regex=True )
```

_Do not use inplace=True_

#### Returning values if present in another data frame

```
new_df = df.col.isin( df2[ df2.col ] )
```

###

### DataFrames - Merging

***

#### **Merging**

```python
pd.merge ( df1 , df2 )
```

_Automatically performs an inner join on two data frames where there is a matching column name_

#### **Merging by renaming a column**

```python
new_df = pd.merge ( df_table_1 , df_table_2.rename ( columns = { "id" : "product_id" } ) )
```

_This passes a dictionary to a rename clause which forces the columns to match to allow for a merge_

#### Merging on specific columns

```python
# Merge on specific column
pd.merge( df_table_1 , df_table_2 , left_on = "left_col" , right_on = "right_col" )

# Suffic column names if they contain duplicate column names (auto _x _y)
pd.merge( df_table_1 , df_table_2 , left_on = "left_col" , right_on = "right_col" ,suffixes = [ "_table" , "_table" ] )
```

_Uses pandas to merge two tables (data frames) specifying which columns to match up when their names don't match._

_Suffixes is used to force a suffix on duplicate column names. If this isn't done, it will automatically rename them to \_x and \_y_

#### **Inner Merge**

```python
df.merge( df_table_1, df_table_2 ) 
```

Default merge is an inner join in SQL

#### Outer Merge

```python
df.merge( df_table1 , df_table_2 , how= "outer" )
```

_This is an outer merge - all rows from both data frame tables_

#### Left and Right Merge

```python
df.merge( df_table1 , df_table_2 , how= "left" )
df.merge( df_table1 , df_table_2 , how= "right" )
```

_This is finally how to do a left or a right join on two data frame tables_

**Combine data frames**

```python
pd.concat ( [ df1 , df2 , df3 , df4 ] )
```

_This combines all data frames into one big table. All columns must be the same_

### DataFrames - Grouping

***

#### **Grouping**

```python
# Group by one column
df.groupby( "column1" ).column2.measurement( ).reset_index( )

# Group by more than one column
df.groupby ( [ "col1" , "col2" ] ).col3.measurement( ).reset_index( )
```

_This groups the data by column 1 and calculates the aggregate using column2's command._

_Follow groupby statement with a .reset\_inex( ). Groupby outputs a pandas series and reset\_index() turns it back into a dataframe._

#### Counting the occurrence of a string in a column

```cpp
df = df.groupby( "group_col" )[ "apply_using" ].apply ( lambda x: x.str.count( "keyword" ).sum ( ) )
```

_Groups a dataframe by a group\_col then applys a lambda to the apply\_using column._

_x.str.count("keyword).sum( ) finds all instances of that keyword and returns the count per group\_col_

#### Counting the number of rows in each group

```python
df_grouped = df.groupby( ["col1", "col2"]).size( ).reset_index( name="Count" )
```

_Groups the data by these two columns, calculates the number of occurrences per group and calls the new column "Count"_

#### **Data Frame column methods**

| Method                                                                                                                                                                      | Description                                                        |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| [`any()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.any.html#pandas.core.groupby.DataFrameGroupBy.any)                | Compute whether any of the values in the groups are truthy         |
| [`all()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.all.html#pandas.core.groupby.DataFrameGroupBy.all)                | Compute whether all of the values in the groups are truthy         |
| [`count()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.count.html#pandas.core.groupby.DataFrameGroupBy.count)          | Compute the number of non-NA values in the groups                  |
| [`cov()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.cov.html#pandas.core.groupby.DataFrameGroupBy.cov) \*             | Compute the covariance of the groups                               |
| [`first()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.first.html#pandas.core.groupby.DataFrameGroupBy.first)          | Compute the first occurring value in each group                    |
| [`idxmax()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.idxmax.html#pandas.core.groupby.DataFrameGroupBy.idxmax) \*    | Compute the index of the maximum value in each group               |
| [`idxmin()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.idxmin.html#pandas.core.groupby.DataFrameGroupBy.idxmin) \*    | Compute the index of the minimum value in each group               |
| [`last()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.last.html#pandas.core.groupby.DataFrameGroupBy.last)             | Compute the last occurring value in each group                     |
| [`max()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.max.html#pandas.core.groupby.DataFrameGroupBy.max)                | Compute the maximum value in each group                            |
| [`mean()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.mean.html#pandas.core.groupby.DataFrameGroupBy.mean)             | Compute the mean of each group                                     |
| [`median()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.median.html#pandas.core.groupby.DataFrameGroupBy.median)       | Compute the median of each group                                   |
| [`min()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.min.html#pandas.core.groupby.DataFrameGroupBy.min)                | Compute the minimum value in each group                            |
| [`nunique()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.nunique.html#pandas.core.groupby.DataFrameGroupBy.nunique)    | Compute the number of unique values in each group                  |
| [`prod()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.prod.html#pandas.core.groupby.DataFrameGroupBy.prod)             | Compute the product of the values in each group                    |
| [`quantile()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.quantile.html#pandas.core.groupby.DataFrameGroupBy.quantile) | Compute a given quantile of the values in each group               |
| [`sem()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.sem.html#pandas.core.groupby.DataFrameGroupBy.sem)                | Compute the standard error of the mean of the values in each group |
| [`size()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.size.html#pandas.core.groupby.DataFrameGroupBy.size)             | Compute the number of values in each group                         |
| [`skew()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.skew.html#pandas.core.groupby.DataFrameGroupBy.skew) \*          | Compute the skew of the values in each group                       |
| [`std()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.std.html#pandas.core.groupby.DataFrameGroupBy.std)                | Compute the standard deviation of the values in each group         |
| [`sum()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.sum.html#pandas.core.groupby.DataFrameGroupBy.sum)                | Compute the sum of the values in each group                        |
| [`unique()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.sum.html#pandas.core.groupby.DataFrameGroupBy.sum)             | List of unique values in column                                    |
| [`var()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.var.html#pandas.core.groupby.DataFrameGroupBy.var)                | Compute the variance of the values in each group                   |

### Pivot Tables

***

#### **Creating a pivot table**

```python
pivot = data_frame.pivot ( columns = " column_field " ,
index = " column_to_be_rows " ,
values = " values "
).reset_index( )
```

_This makes the table more readable and allows for further calculations_
