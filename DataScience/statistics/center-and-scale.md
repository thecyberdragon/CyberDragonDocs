# 🎲 Center and Scale

### <mark style="color:yellow;">Data centering</mark>

Subtract the mean from each data point. The new centered mean = 0.

![](https://t20664121.p.clickup-attachments.com/t20664121/09979bbf-fb98-441f-8568-81255be54d14/image.png)

u = the mean

When one set of values is outweighted by a disproportionate scale compared to the other (age vs income for example).

### <mark style="color:yellow;">Min-Max normalisation</mark>

Min is scaled to 0\
Max is scaled to 1

Everything else is between 0 and 1

![](https://t20664121.p.clickup-attachments.com/t20664121/ee2ea9be-e4fc-4d85-872b-19b57e4eea3f/image.png)

### <mark style="color:yellow;">Using sklearn to min max scale</mark>

```python
from sklearn.preprocessing import MinMaxScaler

scaler = MinMaxScaler( )
normalised_data = scaler.fit_transform( df )
```

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler( )
satdnardised_data = scaler.fit_transform( df )
```

### <mark style="color:yellow;">Log Transformation</mark>

Normalises skewed data to make it more usable.

Larger numbers are closer together and lower numbers are given more room.

![](https://t20664121.p.clickup-attachments.com/t20664121/7b59cc52-98cf-4cad-b3d1-8decd7071566/image.png)

```python
log_data = np.log( np.array )
```

```python
from sklearn.preprocessing import PowerTransformer

log_transformed = PowerTransformer()
log_transformed.fit( np_array )
```

### <mark style="color:yellow;">Getting the skew of a distribution</mark>

```python
skew = df.col.skew( )
```

_Skew above 1 or under -1 means the data is highly skewed_\
Some other methods of normalising distributions

(Right Skew) Cube root transformation - x becomes x^(1/3) - Works with negative numbers\
(left Skew) Square transformation - x becomes x^2
