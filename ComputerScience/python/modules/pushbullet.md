# 🗃️ Pushbullet

### <mark style="color:yellow;">Overview</mark>

Purpose: Notifications to phone

### <mark style="color:yellow;">Installing</mark>

```
pip install pushbullet.py
```

### <mark style="color:yellow;">Importing the library</mark>

```python
from pushbullet import Pushbullet
```

### <mark style="color:yellow;">Features</mark>

#### <mark style="color:yellow;">Sending a notification</mark>

```python
API_TOKEN = "xxxxxxxxxxxxxxxxxxxx"
push = Pushbullet(API_TOKEN)
send = push.push_note("Header","Notification Message")
```

#### <mark style="color:yellow;">Sending an image</mark>

```python
API_TOKEN = "xxxxxxxxxxxxxxxxxxxx"
push = Pushbullet(API_TOKEN)
image = "path\\to\\image\\this.jpg"

with open(image, "rb") as pic: 
    file_data = push.upload_file(pic, "image_name.jpg")
    image_push = push.push_file(**file_data)
```

### <mark style="color:yellow;">Documentation</mark>

{% embed url="https://pypi.org/project/pushbullet.py/0.9.1/" %}
