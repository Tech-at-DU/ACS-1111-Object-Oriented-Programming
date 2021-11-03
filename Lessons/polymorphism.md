<!-- .slide: data-background="./Images/header.svg" data-background-repeat="none" data-background-size="40% 40%" data-background-position="center 10%" class="header" -->
# Lesson: Polymorphism

<!-- Put a link to the slides so that students can find them -->

**📝 &nbsp;Class Materials:** 
  <!-- Put a link to the slides -->
* [**Slides**](https://docs.google.com/presentation/d/1gNvsR7IuPg-BuVHyak2vgBaSJA23RTVeJpiSEN9huMI/edit?usp=sharing)

* **Repls:**
  * Coding Exercise 1: 
  
  <!-- [https://repl.it/@MakeSchool/inheritanceoverridingpractice](https://repl.it/@MakeSchool/inheritanceoverridingpractice) -->

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

  def __init__(self, name, age, year, major):
    super().__init__(name,age)
    self._year = year
    self.major = major

  def get_courses(self): # adds a new method
    print(f"{self._name} is majoring in {self.major}") 

  def introduce_self(self): # overrides an inherited method
    print(f"My name is {self._name} and I'm a Student")


# create a Student and have them introduce themselves

student_example = Student("Danika", "28", "2022")
student_example.introduce_self()
student_example.get_courses()

#print(help(Student))
```

  * Coding Exercise 2: 
  
  <!-- [https://repl.it/@MakeSchool/Polymorphic-Classes](https://repl.it/@MakeSchool/Polymorphic-Classes) -->

```python
'''
In the code below, we created a Shark class and a Clownfish class, each of which will define methods for swim(), swim_backwards(), and skeleton().

They share three methods in common with the same name. However, each of the functionalities of these methods differ for each class.
'''

class Shark():
  def swim(self):
      print("The shark is swimming.")

  def swim_backwards(self):
      print("The shark cannot swim backwards, but can sink backwards.")

  def skeleton(self):
      print("The shark's skeleton is made of cartilage.")

class Clownfish():
  def swim(self):
      print("The clownfish is swimming.")

  def swim_backwards(self):
      print("The clownfish can swim backwards.")

  def skeleton(self):
      print("The clownfish's skeleton is made of bone.")


jaws = Shark()
nemo = Clownfish()
marlin = Clownfish()
marlin_jr = Clownfish()

# Now that we have two objects that make use of a common interface, we can use the two objects in the same way regardless of their individual types.

school_of_fish = [jaws, nemo, marlin, marlin_jr]

for fish in school_of_fish:
  fish.swim()
  fish.swim_backwards()
  fish.skeleton()

# Example from Digital Ocean 🐠
```

  * Coding Exercise 3: 
  
  <!-- [https://repl.it/@MakeSchool/Person](https://repl.it/@MakeSchool/Person) -->

```python
class Person:
  def __init__(self, my_name):
    self.name = my_name
  
  def say_hello(self):
    print(f'Hello my name is: {self.name}')


class Student(Person):
  def say_hello(self):
    print(f'What\'s up my name is {self.name}')


class Teacher(Person):
  def say_hello(self):
    print(f'Hi, I am {self.name}. I teach CS.')


michelle = Person("Michelle")
mike = Student("Mike")
joi = Teacher("Joi")

## have them all say hello
array_people = [michelle, mike, joi]
for person in array_people:
  person.say_hello()

```

  * Coding Exercise 4: 
  
  <!-- [https://repl.it/@MakeSchool/animalpolymorphismexample](https://repl.it/@MakeSchool/animalpolymorphismexample) -->

Create a separate file for each of the code snippets below. Make sure they are all in the same folder together. 

```python
# main.py
from Animal import Animal
from Dog import Dog

lemar = Animal("Zoboomafoo")
#print(lemar.speak())

dog = Dog("Wuffles")
dog.speak()
```

```python
# Animal.py
class Animal:
  """ This is the animal super class"""

  def __init__(self, name):
    """Initializes the animal class with a name protected property"""
    self._name = name

  def speak(self):
    """returns a string greeting with the animal name"""
    print(f"My name is {self._name}")
```

```python
# Dog.py
from Animal import Animal

class Dog(Animal):
  """Dog inherits from the animal class"""

  def speak(self):
    """Overrides Animal's speak method"""
    super().speak() #why is this super call not exeuting on the base class?
    print("Bork bork you are doing me a frighten")

```

```python
# Monkey.py
from Animal import Animal

class Monkey(Animal):

  def eat(self):
    return "Yummy bananas!"

  # Overriding the speak() method
  def speak(self):
    return "Ooo oo ahh ahh!"

```

  * Coding Exercise 5: 
  
  <!-- [https://repl.it/@MakeSchool/animalpolymorphismexample](https://repl.it/@MakeSchool/animalpolymorphismexample) -->

```python
# main.py
from Animal import Animal
from Dog import Dog

lemar = Animal("Zoboomafoo")
#print(lemar.speak())

dog = Dog("Wuffles")
dog.speak()

```

```python
# Animal.py
class Animal:
  """ This is the animal super class"""

  def __init__(self, name):
    """Initializes the animal class with a name protected property"""
    self._name = name

  def speak(self):
    """returns a string greeting with the animal name"""
    print(f"My name is {self._name}")

```

```python
# Dog.py
from Animal import Animal

class Dog(Animal):
  """Dog inherits from the animal class"""

  def speak(self):
    """Overrides Animal's speak method"""
    super().speak() #why is this super call not exeuting on the base class?
    print("Bork bork you are doing me a frighten")
```

```python
# Monkey.py
from Animal import Animal

class Monkey(Animal):

  def eat(self):
    return "Yummy bananas!"

  # Overriding the speak() method
  def speak(self):
    return "Ooo oo ahh ahh!"
```

  * Coding Exercise 6: 
  
  <!-- [https://repl.it/@JoiAnderson2/TrueMistyroseDigits](https://repl.it/@JoiAnderson2/TrueMistyroseDigits)   -->

```python
class Duck:

  def quack(self):
      print('Quack, quack')

  def fly(self):
      print('Flap, Flap!')


class Person:

  def quack(self):
      print("I'm can quack like a duck!")

  def fly(self):
      print("I'm flapping my arms in the air!")

class Butterfly:
  def fly(self):
    print("Flying towards a flower ttyl")

# -----------------------------------
# This is a function. It is not in a class.
# def quack_and_fly(thing):
  
#   # Not Duck-Typed. Why? In duck typing, we do not care if the object is an instance of Duck. We only care if it behaves like a duck when we ask it to do so.

#   # Person class has quack and fly methods, so there is not reason for it not to work. So we should remove the checks.

#   if isinstance(thing, Duck):
#       thing.quack()
#       thing.fly()
#   else:
#       print('This has to be a Duck!')

# # Works
# daffy = Duck()
# quack_and_fly(daffy)
# print(isinstance(daffy, Duck))

# # Does not work the way we needed it to
# peter = Person()
# quack_and_fly(peter)
# print(isinstance(peter, Duck))



# def quack_and_fly(thing):

#     # Person class has quack and fly class, so there is not reason for it not to work. So we should remove the checks.

#   thing.quack()
#   thing.fly()

# # Works
# d = Duck()
# quack_and_fly(d)


# p = Person()
# quack_and_fly(p)

# b = Butterfly() 
# quack_and_fly(b)


# # # You might be thinking... well, Joi. Wouldnt this cause error? Is this dangerous? Well, yes. 

# # Instead of lets have checks that methods exist
# # Look before you leap.

# def quack_and_fly(thing):  
#   if hasattr(thing, 'quack'):
#       if callable(thing.quack):
#           thing.quack()

#   if hasattr(thing, 'fly'):
#       if callable(thing.fly):
#           thing.fly()

# # Works
# d = Duck()
# quack_and_fly(d)

# # Works
# p = Person()
# quack_and_fly(p)


# EAFP: “it’s easier to ask for forgiveness than permission

def quack_and_fly(thing):
  try:
      thing.quack()
      thing.fly()
      thing.bark()
  except AttributeError as e:
      print(f"ooooo this is baddd {e}")


# Works
d = Duck()
quack_and_fly(d)

# Does not work the way we needed it to
# p = Person() 
# quack_and_fly(p)


```

<!-- > -->
