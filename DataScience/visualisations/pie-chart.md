# 📊 Pie Chart

![](https://t20664121.p.clickup-attachments.com/t20664121/d503c1a6-6e13-40cb-8e42-e5a03e626cbe/image.png)

### <mark style="color:yellow;">Using Value Counts</mark>

```python
df . col . value_counts ( ) . plot . pie()
```

### <mark style="color:yellow;">Manual Code</mark>

```cpp
plt.pie( [ list_of_values ], labels = [ list_of_labels ], autopct = "string_format", pctdistance = 1.30 )
plt.lenegd( [ list_of_labels ] )
plt.tight_layout( )
plt.axis( "equal" )
```

_<mark style="color:green;">Equal un-skews the view of the pie</mark>_

_Labels = puts the labels on the graph while legend shows the key in a table_\
string\_format can be

%0.2f = 2 decimal places\
%0.2f%% = 2 decimal places with a percent sign\
%d%% = int with a percent sign

Tight layout stops everything overlapping\
pctdistance sets the distance the percentages (if used) are from the center

### <mark style="color:yellow;">Visuals</mark>

```python
# Explode: Array must be the length of the number of pie slices
plt.pie( explode = (x, x, x, x))

# Shadow
plt.pie( shadow = True )
```

```python
# Rotating the pie/ Number is between 0 and 360. Rotating is to the left
plt.pie( startangle = number )

```

_<mark style="color:green;">x = explode number</mark>_

![](https://t20664121.p.clickup-attachments.com/t20664121/e1b6efed-753f-4164-8f52-cd0d8d33403e/image.png)
