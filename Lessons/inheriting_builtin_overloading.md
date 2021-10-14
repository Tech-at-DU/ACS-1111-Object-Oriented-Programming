<!-- .slide: data-background="./Images/header.svg" data-background-repeat="none" data-background-size="40% 40%" data-background-position="center 10%" class="header" -->
# Lesson: Inheriting from Built In's and Overloading

<!-- Put a link to the slides so that students can find them -->

**📝 &nbsp;Class Materials:** 
  <!-- Put a link to the slides -->
* [**Slides**](https://docs.google.com/presentation/d/1rPcYDndeV2l5WiG9xPyF_KGwFzw_4CX07lyqJrcwqZA/edit?usp=sharing)

* **Repls:**
  * Coding Exercise 1: [https://repl.it/@MakeSchool/Init](https://repl.it/@MakeSchool/Init)

```python 
'''
To construct account objects from the Account class below I need a constructor which in Python is the __init__ magic method/dunder:
'''

class Account:
  # Magic method/dunder __init__
  def __init__(self, owner, amount): 
    self.owner = owner
    self.amount = amount
    self._transactions = []

    

'''
The constructor takes care of setting up the object. This allows us to create new accounts like this:
'''

joi_acc = Account('Joi Anderson', 1000)
print(joi_acc)
```

  * Coding Exercise 2: [https://repl.it/@MakeSchool/magicmethods](https://repl.it/@MakeSchool/magicmethods)

```python
# main.py
from Animal import Animal

otter = Animal("Octavious")
print(str(otter))
print(repr(otter))

another_otter = Animal("Marlene")

new_otter = otter + another_otter
del new_otter

print(Animal.animal_count)
#print(new_otter)
```

```python
class Animal:
  """This class represents an animal with a name"""
  animal_count = 0

  def __init__(self, name):
    """This method initializes the name property"""
    self._name = name
    Animal.animal_count += 1

  def __str__(self):
    """Override the str magic method to show the name"""
    return f"I'm an Animal and my name is {self._name}"
 
  def __repr__(self):
    """Override the repsr magic method to display a message to devs"""
    return f"Animal({self._name})"

  def __add__(self, other_animal):
    """Override the add magic method to create a new animal object and give it a merged name"""
    new_name = f"{self._name}  {other_animal._name}"
    return Animal(new_name)
    
  def __del__(self):
    Animal.animal_count -= 1
```

  * Coding Exercise 3: [https://repl.it/@MakeSchool/BuiltInsDocs](https://repl.it/@MakeSchool/BuiltInsDocs)

```python
# See source code for "str" object
# print(help(str))

# See source code for "int" object
#print(help(int))

# See source code for "float" object
#print(help(float))

# See source code for "list" object
#print(help(list))

# See source code for "dict" object
#print(help(dict))

# See source code for "tuple" object
#print(help(tuple))

# See source code for "set" object
#print(help(set))

```
  * Coding Exercise 4: [https://repl.it/@MakeSchool/stringonlylist](https://repl.it/@MakeSchool/stringonlylist)

```python
# main.py
from IntFloatList import IntFloatList

intfloat = IntFloatList([2,4,8])
print(intfloat)

intfloat.append(10)
print(intfloat)


intfloat.append("hello")
print(intfloat)

```

```python
# instructions.py
'''
Lets build a custom list class that will only accept integers and floats.

If we attempt to append, any other data-type, lets say for arguments sake a string, we will print an error message, to inform the user that this particular list can only accept integers and floats.
'''


# TODO: Create a IntFloatList.py and create a IntFloatList class that inherits from list

# TODO: import IntFloatList into main.py

# TODO: Create an object of type IntFloatList and call it intfloat_list.  What happens when it is printed?

# TODO: To add elements to our list, we pass a list of values. Pass a list of values.

# TODO: IntFloatList also inherited all of the methods from the list class. Lets try to test this using .append() to add a new element to our list of type string.

# TODO: Hm, we dont want to be able to append strings to our list. We only want to be able to append int and str. So lets override the append method 

```

```python
# IntFloatList.py
class IntFloatList(list):
  
  def append(self, new_element):
    if isinstance(new_element, (int, float)):
      super().append(new_element)
    else:
      print("You can only add ints or floats to this list")


```

<!-- > -->
