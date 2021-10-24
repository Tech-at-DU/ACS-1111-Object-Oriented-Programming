<!-- .slide: data-background="./Images/header.svg" data-background-repeat="none" data-background-size="40% 40%" data-background-position="center 10%" class="header" -->
# Lesson: Attributes & Methods

<!-- Put a link to the slides so that students can find them -->

**📝 &nbsp;Class Materials:** 
  <!-- Put a link to the slides -->
* [**Slides**](https://docs.google.com/presentation/d/1wPzR-Cg65Heqb7dxnxB8312yjsMTfFSHUsc9C9vIN9U/edit?usp=sharing)

<!-- * **Repls:**
  * Coding Exercise 1: [https://repl.it/@MakeSchool/DogAttributeDemo](https://repl.it/@MakeSchool/DogAttributeDemo) -->

**Sample code**

```python
# Created the Dog class
class Dog:
  pass

# Instatiation
jess_dog = Dog()

# Create attributes for jess_dog object, using dot notation.

# Like variables, if attribute did not exist, it is created when you first assign it a value.

jess_dog.name = "Tara"
jess_dog.age = 1
jess_dog.color = "brown"
jess_dog.cuteness_level = 10

# Update attributes similar to how you would update a variable
jess_dog.age += 1
print(f"My age is {jess_dog.age}")

#  the name attribute 
#print(f"My name is {jess_dog.name}")

# Delete a property from an object with del

# del jess_dog.name
# print(f"My name is {jess_dog.age}")

# Rather than having to print all of the attributes one by one, we can use __dict__
print(jess_dog.__dict__)
```

  <!-- * Coding Exercise 2: [https://repl.it/@MakeSchool/AttributePractice](https://repl.it/@MakeSchool/AttributePractice) -->

**Challenge 1**

```python
# Dog class
class Dog:
  pass

# TODO: Instantiate 3 objects of type Dog
dog_1 = Dog()
dog_2 = Dog()
dog_3 = Dog()

# TODO: Each object should have the following attributes:
# name
# breed 
# fave_snack


# TODO: Using the object variable names, create a list of Dog objects called dogs.


# TODO: Using the loop print the names of the dogs


# TODO: Using a loop, delete breed attribute for all the dogs in the list dogs


# TODO: Using a loop, add an attribute 'species' and assign it the value 'canine'


# TODO: Use the __dict__ attribute to print each dog and check it's attributes and values 


```

  <!-- * Coding Exercise 3: [https://repl.it/@MakeSchool/WeatherAttributesPractice](https://repl.it/@MakeSchool/WeatherAttributesPractice) -->

**Challenge 2**

```python
# Location class
class Location:
  pass

# TODO: Instantiate three locations


# TODO: Each object have the following attributes:
# name - name of the city you picked
# country - the country the city is located in
# temperature - the city's temperature in F.
# latitude - city's latitude coordinate (look this up)
# longitude - city's longitude coordinate (look this up)


# TODO: Using the object variable names, create a list of Location objects called bucketlist.


# TODO: Using the loop print the name of the city of each location in bucketlist


# TODO: Using the loop, loop through the objects to find which location has the warmest weather


```

  <!-- * Coding Exercise 4: [https://repl.it/@MakeSchool/ClassAttributes](https://repl.it/@MakeSchool/ClassAttributes) -->

**Example 2**

```python
import math 

# Students Class
class Student:
  # class attributes are shared by all instances
  school = "Make School"
  location = "San Francisco"
  major = "Computer Science"


# Instantiate 2 object of type Student

jhene = Student()
kehlani = Student()

# Access class attributes using dot notation

print(f"Jhene studies {jhene.major} at {jhene.school} in {jhene.location}.")
print(f"Kehlani studies {kehlani.major} at {kehlani.school} in {kehlani.location}.")

# Print the  __dict__ attribute to for each object to see a dictionary of all the attributes defined for the object itself. 

print(jhene.__dict__)
print(kehlani.__dict__)

# Why is it blank?


# Let's say that Make School moves to San Diego
# We can update the class variable for all instances by:

# Student.location = "San Diego"


# Print the school for kehlani and jhene
# print(f"Jhene studies in {jhene.location}.")

# print(f"Kehlani studies in {kehlani.location}.")


# TODO: Kehlani transfered , update her school to UCLA.
# kehlani.school = "UCLA"

# print(jhene.school) 
# print(kehlani.school)

# Do you think that the name of the school will change for Jhene too? Test it.


# What happened?

# Print the __dict__ for kehlani

```

  * Coding Exercise 5: [https://repl.it/@MakeSchool/ConstructorDemo](https://repl.it/@MakeSchool/ConstructorDemo)

```python
class Student:
  def __init__(self):
    print("Welcome to Make School")

me = Student()
luna = Student()

# Instatiate an object of type Student

```

  * Coding Exercise 6: [https://repl.it/@MakeSchool/InstanceAttributes](https://repl.it/@MakeSchool/InstanceAttributes) 

```python
# Let's add instance attributes to the Students class:

class Student:

  # Class Variables
  school = 'Make School'
  location = 'San Francisco'
  major = 'Computer Science'
  num_students = 0

  def __init__(self, name, year, coach):
    self.name = name
    self.year = year
    self.coach = coach
    Student.num_students += 1


# TODO: Add three instances with attributes:
student_1 = Student("Jeffrey", 2021, "Lui") 
student_2 = Student("Hector", 2022, "Amanda") 
student_3 = Student("Consuela", 2023, "Paul") 
student_4 = Student("Consuela", 2023, "Paul") 


# Using __dict__, print the name space of each Student object
print(student_1.__dict__)
print(student_2.__dict__)
print(student_3.__dict__)

# TODO: Test accessing/modifying attributes
print(Student.num_students)

# TODO: Add a class attribute called num_students, which will keep count of the number of students created. Initialize it to 0


# TODO: In your __init__ method, increment the num_students class attribute by 1.

```

  * Coding Exercise 7: [https://repl.it/@MakeSchool/ClassMethods](https://repl.it/@MakeSchool/ClassMethods)

```python
# Let's add instance attributes to the Students class:

class Student:
  # Class Variables
  school = 'Make School'
  location = 'San Francisco'
  major = 'Computer Science'

  def __init__(self, name, year, coach):
    # Instance Variables
    self.name = name
    self.year = year
    self.coach = coach
    self.courses = []

  # TODO: Create a method called say_hello that returns a message with the students name and a greeting
  def say_hello(self):
    print(f'Hi, my name is {self.name}')

  def add_course(self, course_name):
    self.courses.append(course_name)

  def remove_course(self, course_name):
    self.courses.(course_name)


# TODO: Instatiate an object of type Student
jordan = Student("Jordan", 2020, "Braus")


# TODO: Invoke the say_hello method
jordan.say_hello()
jordan.add_course("SPD")
jordan.remove_course("SPD")
print(jordan.courses)



# TODO: Create a method called add_course that takes one parameter, the course name, and appends a course to the courses list

# TODO: Invoke the add_course method
jordan.add_course("CS1.1")




# TODO: Create a method called remove_course that takes one parameter, the class name, and removes it from a class from the class list

# TODO: Invoke the remove_course method
```

<!-- > -->
