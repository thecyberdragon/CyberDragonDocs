# 🎲 Categorical Summary Stats

### <mark style="color:yellow;">Ordered categorical data</mark>

Convert to categorical then use [cat.codes](http://cat.codes)

```python
df[ "col" ] = pd.Categorical( df[ "col" ], [ "list" , "of" , "categories ], ordered = True )

# Can use this to find the median
df[ "col" ].cat.codes
```

The mean is not appropriate for ordinal categorical values as it assumes equal spacing between categories.

### <mark style="color:yellow;">Returning a category</mark>

```python
# Specify the order
order = [ "one","two","three" ]

# Find the index of the category you're looking for
category_index = np.percentile( df.col.cat.codes, 0.25 )

# Use the index to query the order list
print( order[ int( category_index ) ] )
```

### <mark style="color:yellow;">Getting proportions from value counts</mark>

```python
# Manual way (takes into consideration missing data)
df.col.value_counts( ) / len( df.col )

# Elegant way (doesn't count missing data)
df.col.value_counts( normalize = True )

# Allow value_counts to count missing data
df.col.value_counts( dropna = False )
```

### <mark style="color:yellow;">Getting the sum of a binary column</mark>

```python
count = np.sum( df.col == "condition" )
proportion = count / len( df )
```
