<!-- .slide: data-background="./Images/header.svg" data-background-repeat="none" data-background-size="40% 40%" data-background-position="center 10%" class="header" -->
# Lesson: Abstract Classes & Static/Class Methods

<!-- Put a link to the slides so that students can find them -->

**📝 &nbsp;Class Materials:** 
  <!-- Put a link to the slides -->
* [**Slides**](https://docs.google.com/presentation/d/1UDoctLTBnG0p0x1QIqFrWZUNE0GIrLXXco6e0WuQURg/edit?usp=sharing)

* **Repls:**
  * Coding Exercise 1: [https://repl.it/@MakeSchool/InstanceMethodsExample#main.py](https://repl.it/@MakeSchool/InstanceMethodsExample#main.py)

```python
class Student:
  # Class Variables
  location = 'San Francisco'
  major = 'Computer Science'
  school = 'Make School'

  def __init__(self, name, year, coach):
    # Instance Variables
    self.name = name
    self.year = year
    self.coach = coach
    self.courses = []

  # Instance Methods
  def say_hello(self):
    print(f'Hi, my name is {self.name}')      

  def add_course(self, course):
    self.courses.append(course)

  def remove_course(self, course):
    self.courses.remove(course)


# Examples: 

alberto = Student("Alberto", 2020, "Joi")
alberto.say_hello()

jay = Student("Jay", 2020, "Joi") 
jay.say_hello()


jay.add_course("Physics")
print(jay.courses)
print(jay.__dict__)
```

  * Coding Exercise 2: [https://repl.it/@MakeSchool/ClassMethodExample#main.py](https://repl.it/@MakeSchool/ClassMethodExample#main.py)

```python
class Student:
  # Class Attributes
  school = 'Make School'
  location = 'San Francisco'
  major = 'Computer Science'
  tuition = 35000

  def __init__(self, name, year, coach):
    # Instance Attributes
    self.name = name
    self.year = year
    self.coach = coach
    self.courses = []

  # Instance Methods
  def say_hello(self):
    print(f'Hi, my name is {self.name}')

  def add_course(self, course):
    self.courses.append(course)

  def remove_course(self, course):
    self.courses.remove(course)

  # Class Methods
  @classmethod
  def lower_tuition(cls, amount):
    cls.tuition -= amount

  # TODO: Create a class method to raise tution
  @classmethod
  def raise_tuition(cls, amount):
    cls.tuition += amount


# Tests:
tristan = Student("Tristan", 2020, "Adriana")
jenna = Student("Jenna", 2020, "Adriana")

print(jenna.tuition)
print(tristan.tuition)

Student.lower_tuition(15000)

print(jenna.tuition)
print(tristan.tuition)


# Raise tuition by $10

```

  * Coding Exercise 3: [https://repl.it/@MakeSchool/FactoryMethod#main.py](https://repl.it/@MakeSchool/FactoryMethod#main.py)

```python
class Movie:
  # Class Attribute
  platform = 'Netflix'

  # Instance Attributes
  def __init__(self, title, genre, year, rating):
    self.title = title
    self.genre = genre
    self.year = year
    self.rating = rating

  # Instance Method / regular method
  def show_rating(self):
    print(f"{self.title} was rated {self.rating} stars.")

  # Class Method - Use 1: Updating Class Attributes
  @classmethod
  def change_platform(cls, new_platform):
    cls.platform = new_platform 
    
  
  # Class Method - Use 2: Creating another constructor
  @classmethod
  def fromString(cls, movie_data):
    movie_title, movie_genre, movie_year, movie_rating = movie_data.split('-')
    return cls(movie_title, movie_genre, movie_year, movie_rating)

  
soul = Movie("Soul", "Animated", 2020, 9)
soul.show_rating()

Movie.change_platform("Disney Plus")
print(soul.platform)

moana = Movie.fromString("Moana-Childrens-2016-9")
print(moana.__dict__)

# TODO: Engineers want to be able to create a Movie object using a string: Moana-Childrens-2016-9
# Add a class method that serves as a new constructor

```

  * Coding Exercise 4: [https://repl.it/@MakeSchool/StaticMethodStudentExample#main.py](https://repl.it/@MakeSchool/StaticMethodStudentExample#main.py)

```python
class Student:
  # Class Attribute
  school = 'Make School'
  location = 'San Francisco'
  major = 'Computer Science'
  tuition = 35000

  def __init__(self, name, year, coach):
    # Instance attribute
    self.name = name
    self.year = year
    self.coach = coach
    self.courses = []

  # Instance Methods
  def say_hello(self):
    print(f'Hi, my name is {self.name}')

  def add_course(self, course):
    self.courses.append(course)

  def remove_course(self, course):
    self.courses.remove(course)

  # Class Methods
  @classmethod
  def lower_tuition(cls, amount):
    cls.tuition -= amount

  # Static Method
  @staticmethod
  def is_classday(day):
    if day in ['Satuday', 'Sunday']:
      return False
    return True


jackie = Student("Jackie", 2020, "Joi")

print( Student.is_classday('Monday') )
print( Student.is_classday('Sunday') )
```

  * Coding Exercise 5: [https://repl.it/@MakeSchool/staticvsinstancemethods#main.py](https://repl.it/@MakeSchool/staticvsinstancemethods#main.py)

```python
# main.py
from CalculatorInstance import CalculatorInstance
from CalculatorStatic import CalculatorStatic
#with non-static methods
#we have to create an object instance in memory
#then we can call the method


my_calculator = CalculatorInstance()
print(my_calculator.div(5,6))

#with static methods we do not have to create an object, ee just use the class name
#static methods only work on the data provided to the arguments

CalculatorStatic.add(5,6)

print(CalculatorStatic.add(5,6))
```

```python
# CalculatorInstance.py
class CalculatorInstance:

#Instance methods
  def add(self, num1, num2):
    return num1 + num2

  def subtract(self, num1, num2):
    return num1 - num2

  def multiply(self, num1, num2):
    return num1 * num2

  def divide(self, num1, num2):
    return num1 / num2

```

```python
# CalculatorStatic.py
class CalculatorStatic:

  @staticmethod
  def add(num1, num2):
    return num1 + num2

  @staticmethod
  def subtract(num1, num2):
    return num1 - num2

  @staticmethod
  def multiply(num1, num2):
    return num1 * num2
    
  @staticmethod
  def divide(num1, num2):
    return num1 / num2
  
```

  * Coding Exercise 6: [https://repl.it/@MakeSchool/abstractclass#main.py](https://repl.it/@MakeSchool/abstractclass#main.py)

```python
# main.py
from Monkey import Monkey
from Snake import Snake
from Tiger import Tiger

monkey = Monkey("George", 4)
monkey.eat()
monkey.sleep()


pythony = Snake("Sssid", 5)
pythony.eat()
pythony.sleep()

#tigger = Tiger("Sam", 1)
```

```python
# Animal.py

# Step 1: Import ABC and abstractmethod from abc
from abc import ABC, abstractmethod

# Step 2: Create Animal class, which inherits from ABC
class Animal(ABC):

  # Step 3: Implement methods with full functioinality that all instances should inherit.

  def __init__(self, name, age):
    self.name = name
    self.age = age

  def say_name(self):
    print(f"My name is {self.name}")
    
  # Step 4: Define methods that all class should have, but each have different functionatily. Label these with the abstractmethod decorator and put pass in the method body.

  @abstractmethod
  def sleep(self):
    pass

  @abstractmethod
  def eat(self):
    pass

  # Example:  Not an abstract method bc it doesnt have the abstract method decorator

```

```python
# Monkey.py

from Animal import Animal

class Monkey(Animal):
  
  def eat(self):
    print("I like to eat bananas! 🍌")
  
  def sleep(self): 
    print("Zzzz... see ya in 15 hours")

```

```python
# Snake.py

from Animal import Animal

class Snake(Animal):
  
  def eat(self):
    print("Mmmmm mouse")

  def sleep(self):
    print("Zzz.. see you in 16 hr 🐍")
```

```python
# Tiger.py

from Animal import Animal

class Tiger(Animal):
  pass

```

  * Coding Exercise 7: [https://repl.it/@MakeSchool/abstractclasspractice#main.py](https://repl.it/@MakeSchool/abstractclasspractice#main.py)

```python

```

<!-- > -->
