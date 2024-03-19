# 🐍 Python

#### <mark style="color:yellow;">Updating print outputs</mark>

```python
total = len(big_list)
i = 1
for item in big_list:
    print(str.format("\rProcessing file {0} of {1}", i, total), end="")
```

The /r command puts the cursor at the beginning of the line, and , end="" stops print adding a new line at the end, resulting in an updating print statement

#### <mark style="color:yellow;">Handling errors</mark>

```python
try:
    print(something)
except Exception as e:
    print(e.message)
```

This is assuming that the exception has a message attribute

```python
except Exception as e:
    if hasattr(e, "message"):
        print(e.message)
```
