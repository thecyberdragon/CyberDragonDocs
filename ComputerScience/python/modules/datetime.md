# 🗃️ Datetime

### <mark style="color:yellow;">Datetime</mark>

```python
from datetime import datetime
```

#### <mark style="color:yellow;">Now</mark>

```python
now = datetime.now()
now = datetime.now().strftime("%H:%M:%S")
```

#### <mark style="color:yellow;">Datetime from numbers</mark>

```python
# year, month, day, hour, minute, second, milisecond
new_date = datetime(2024, 02, 01, 10, 30, 22, 123)
```

#### <mark style="color:yellow;">Reference a datetime value</mark>

```python
now = datetime.now()

# Week (0-6, mon-sun)
day_of_week = now.weekday()

# Date
year = now.year
month = now.month
day = now.day

# Time
hour = now.hour
minute = now.minute
second = now.second
microsecond = now.microsecond
```

#### <mark style="color:yellow;">Difference between dates</mark>

```python
difference = recent_datetime - earlier_datetime
# Returns datetime and timedelta
```

#### <mark style="color:yellow;">Parse a string as a date</mark>

```python
# the p in strptime = parse
new_datetime = datetime.strptime("01.02.2024", "%d.%m.%y")
```

#### <mark style="color:yellow;">Format a date as a string</mark>

```python
# the f in strftime = format
new_string = datetime.strftime(datetime_variable, "%d.%m.%y")
```

{% embed url="https://docs.python.org/3/library/datetime.html#strftime-and-strptime-format-codes" %}
