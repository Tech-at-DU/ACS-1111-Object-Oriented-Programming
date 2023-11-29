<!-- .slide: data-background="./Images/header.svg" data-background-repeat="none" data-background-size="40% 40%" data-background-position="center 10%" class="header" -->
# Lesson: Multiple Inheritance & Mix-ins

<!-- Put a link to the slides so that students can find them -->

**📝 &nbsp;Class Materials:** 
  <!-- Put a link to the slides -->
* [**Slides**](https://docs.google.com/presentation/d/1XNlnRFBA6fJeifNT3ecG1LSHr_xR7ll5lgLXi-OXsdE/edit?usp=sharing)

<!-- * **Repls:**
  * Coding Exercise 1: [https://repl.it/@MakeSchool/inheritanceoverridingpractice](https://repl.it/@MakeSchool/inheritanceoverridingpractice) -->

```python
# Superclass - Parent
class Person:

  def __init__(self, name, age):
    self._name = name
    self._age = age

  def introduce_self(self):
    print(f"My name is {self._name} and my age is {self._age}.")


# create a Person and have them introduce themselves
person_example = Person("Adriana", "28")
person_example.introduce_self()
# create Student class
class Student(Person):

  def __init__(self, name, age, year):
    super().__init__(name,age)
    self._year = year
    self.courses = [] 

  def get_courses(self):
    print(f"{self._name} is taking CS 1.1") 

  def introduce_self(self):
    print(f"My name is {self._name} and I'm a Student")


# create a Student and have them introduce themselves

student_example = Student("Danika", "28", "2022")
student_example.introduce_self()
student_example.get_courses()

#print(help(Student))
```

  * Coding Exercise 2: [https://repl.it/@MakeSchool/MultipleInheritanceSyntax#main.py](https://repl.it/@MakeSchool/MultipleInheritanceSyntax#main.py)

```python
class Mammal:
    pass

class WingedAnimal:
    pass

class Bat(Mammal, WingedAnimal):
    pass



battie = Bat()
print(isinstance(battie, Bat))
print(isinstance(battie, Mammal))
print(isinstance(battie, WingedAnimal))


# TODO: Use issubclass to check if Bat is a subclass of Mammal and WingedAnimal

# Syntax: issubclass(subclass, superclass)

```

  * Coding Exercise 3: [https://repl.it/@MakeSchool/MultipleInheritance#main.py](https://repl.it/@MakeSchool/MultipleInheritance#main.py)

```python
# main.py

from Bat import Bat

battie = Bat(True)
battie.display()
print(Bat.mro())
print(help(Bat))

# TODO: create initializers in all classes

# TODO: Add a display() method to WingedAnimal, and Mammal. Which display will be called first?


# TODO: Add a display() method to Bat. Which method will be invoked this time when we use .display()?


# TODO: Update the display() method in Bat to call the display methods in Mammal and WingedAnimal


# TODO: Create an init method in WingedAnimal and Mammal. Which init method will be used when we create a Bat object?

# TODO: How can we fix this?

```

```python
# Bat.py

from Mammal import Mammal
from WingedAnimal import WingedAnimal

class Bat(WingedAnimal, Mammal):
  
  def __init__(self, is_vampire):
    self.is_vampire = is_vampire
    Mammal.__init__(self, False)
    WingedAnimal.__init__(self, True)

```

```python
# Mammal.py

class Mammal:

  produce_milk = True

  def __init__(self, lays_eggs):
    self.lays_eggs = lays_eggs

  def display(self):
    if self.lays_eggs:
      print("I'm a mammal that can lay eggs")
    else:
      print("I'm a mammal")

```

```python
# WingedAnimal.py

class WingedAnimal:

  def __init__(self, can_fly):
    self.can_fly = can_fly

  def display(self):
    if self.can_fly:
      print("I'm a winged animal and can fly")
    else:
      print("I'm a winged animal")

```

  * Coding Exercise 4: [https://repl.it/@JessDahmen/multipleinheritancepractice](https://repl.it/@JessDahmen/multipleinheritancepractice)

```python
#TODO: make you own example of multiple inheritance
```

  * Coding Exercise 5: [https://www.residentmar.io/2019/07/07/python-mixins.html](https://www.residentmar.io/2019/07/07/python-mixins.html)

```python

```

<!-- > -->
