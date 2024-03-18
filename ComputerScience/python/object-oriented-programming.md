# ✏️ Object-Oriented Programming

### <mark style="color:yellow;">Overview</mark>

Class = a blueprint for something\
Object = the instance of that class

Objects are custom data types that can have their own variables and functions for more complex programming.

Example:\
Student = class\
person = Student()

## <mark style="color:red;">Classes</mark>

***

Class names should always be in CapWords case

{% embed url="https://peps.python.org/pep-0008/#class-names" %}

When defining variable inputs, default values must always be at the end

Classes can contain data types and functions.\
Attributes = variables like a string or bool\
Methods = functions within a class

Objects can contain objects from other classes

### <mark style="color:yellow;">Creating a class</mark>

```python
class Dog:
	def __init__(self, input_name, input_breed, input_age = 0, input_friendlyness = True):
			self.name = input_name
			self.breed = input_breed
			self.age = input_age
			self.friendly = input_friendly
```

\_\_init\_\_ is a constructor that defines the initial conditions of the object

#### <mark style="color:yellow;">Creating an object</mark>

```python
new_dog = Dog("big boi", "sausage", 12, True)
```

#### <mark style="color:yellow;">Define a new function in a class</mark>

```python
class Dog:
	def __init__(self, input_name):
		self.name = input_name
		self.is_happy = False
		
	def pet_the_dog(self):
		print("woof woof. *wags tail*")
		self.is_happy = True
```

Self refers to the instance or object of the class

A \_\_repr\_\_ function is used to print out all an object’s attributes (a custom message you define) when using print(object).

#### <mark style="color:yellow;">Type & Attributes</mark>

You can check if an object has an attribute.&#x20;

```python
# Returns true or false
hasattr(object, "attribute")

# hasattr(list, "count") will return True
```

Return the type of an object

```python
this_type = type(object)
```
