# 📊 Box Plot

### Diagram

![](https://t20664121.p.clickup-attachments.com/t20664121/c7e35c2f-968b-4a8a-8fba-1d678cb03146/image.png)

####

### Seaborn

![](https://t20664121.p.clickup-attachments.com/t20664121/6b1f62be-b969-4ed6-a564-43704a644050/Untitled-1.png)

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

![](https://t20664121.p.clickup-attachments.com/t20664121/c8961a76-e837-4830-919d-82160c797a66/Untitled.png)

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Create the plot
sns.boxplot ( x = "variables", y = "values", data = df )

# Show and clear the plot
plt.show( )
plt.clf( )
```

#### MatplotLib

```python
plt.boxplot( dataset )
plt.boxplot( [ dataset, dataset2 ], labels = [ "label one", "label two" ] )

plt.show( )
```
