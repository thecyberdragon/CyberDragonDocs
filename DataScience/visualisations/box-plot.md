# 📊 Box Plot

## <mark style="color:red;">Diagram</mark>

***

![](https://images4.imagebam.com/fa/42/2e/MES1OSI\_o.png)

## <mark style="color:red;">Python Code</mark>

***

### <mark style="color:yellow;">Seaborn</mark>

![](https://images4.imagebam.com/9d/6e/d4/MES1OSK\_o.png)

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Create the box plot
sns.boxplot( x = "column", data = dataframe )

# Show and clear the plot
plt.show( )
plt.clf( )
```

#### Multiple Boxes

![](https://images4.imagebam.com/f0/31/78/MES1OSL\_o.png)

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Create the plot
sns.boxplot ( x = "variables", y = "values", data = df )

# Show and clear the plot
plt.show( )
plt.clf( )
```

### <mark style="color:yellow;">MatplotLib</mark>

```python
plt.boxplot( dataset )
plt.boxplot( [ dataset, dataset2 ], labels = [ "label one", "label two" ] )

plt.show( )
```
