# 🗃️ PIL

### <mark style="color:yellow;">Overview</mark>

Purpose: Image metadata extraction

### <mark style="color:yellow;">Installing</mark>

```python
pip install pillow
```

### <mark style="color:yellow;">Importing the library</mark>

```python
from PIL import Image
```

### <mark style="color:yellow;">Features</mark>

#### <mark style="color:yellow;">Extracting parameters</mark>

```python
image = Image.open(png)
image.load()
params = image.info["parameters"]
```

### <mark style="color:yellow;">Documentation</mark>

{% embed url="https://pillow.readthedocs.io/en/latest/handbook/tutorial.html" %}
