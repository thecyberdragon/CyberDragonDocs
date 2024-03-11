# 🗃️ Openpyxl

### <mark style="color:yellow;">Overview</mark>

Purpose: Create workbooks

### <mark style="color:yellow;">Installing</mark>

```
pip install openpyxl
```

### <mark style="color:yellow;">Importing the library</mark>

```python
from openpyxl import Workbook
from openpyxl.drawing.image import Image
```

### <mark style="color:yellow;">Features</mark>

#### <mark style="color:yellow;">Create new workbook</mark>

```python
# Create worksheet
book = Workbook()
book.save("C:\\path\\worksheet.xls")

# Make worksheet's sheet active
Worksheet = book.active
```
