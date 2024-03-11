# 🗃️ Glob

### <mark style="color:yellow;">Overview</mark>

Purpose: get files & folders

### <mark style="color:yellow;">Installing</mark>

```
pip install glob2
```

### <mark style="color:yellow;">Importing the library</mark>

```python
import glob
```

### <mark style="color:yellow;">Features</mark>

#### <mark style="color:yellow;">Get files by extension</mark>

```python
directory = "c:\\path"
png_files = glob.glob(directory + "\\*.png)
```

#### <mark style="color:yellow;">Get files in subfolders</mark>

```python
directory = "C:\\path"
sub_files = glob.glob(directory + "\\**\*.jpg", recursive=True)
```

### <mark style="color:yellow;">Documentation</mark>

{% embed url="https://docs.python.org/3/library/glob.html" %}
