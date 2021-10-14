<!-- .slide: data-background="./Images/header.svg" data-background-repeat="none" data-background-size="40% 40%" data-background-position="center 10%" class="header" -->
# Lesson: Inheritance & Overriding

<!-- Put a link to the slides so that students can find them -->

**📝 &nbsp;Class Materials:** 
  <!-- Put a link to the slides -->
* [**Slides**](https://docs.google.com/presentation/d/1DkCcA-xcWPfv217vKFYvWkCpQwHQjssOXR7wep_roO8/edit?usp=sharing)
* **Repls:**
  * Coding Exercise 1: [https://repl.it/@MakeSchool/inheritanceoverridingpractice#main.py](https://repl.it/@MakeSchool/inheritanceoverridingpractice#main.py)

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

  * Coding Exercise 2: [https://repl.it/@MakeSchool/createmusiciansubclass#main.py](https://repl.it/@MakeSchool/inheritanceoverridingpractice#main.py)
  
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

<!-- > -->
