<!-- .slide: data-background="./Images/header.svg" data-background-repeat="none" data-background-size="40% 40%" data-background-position="center 10%" class="header" -->
# Lesson: Scope

<!-- Put a link to the slides so that students can find them -->

**📝 &nbsp;Class Materials:** 
  <!-- Put a link to the slides -->
* [**Slides**](https://docs.google.com/presentation/d/1gkC9pYcR2eW2oTo4bndZmBiRoAIl4Uwv5j4W2SVgZGw/edit#slide=id.p1)

## Coding Exercise 1: Scope

```python
def cube(base):
    result = base ** 3
    print(f'The cube of {base} is: {result}')


cube(3)

# What are the local variables of cube()?
# result, base

# What will happen if we try to access result? Why?
# print(result)

# What happens and why?
# error, result is local to the func

# What will happen if we try to access base? Why?
# print(base)
```

## Coding Exercise 2:

```python
# global variables at the top of the file

name = "CS 1.1"

def welcome_class():
    # Is name a global var here?
    print(f'Welcome {name}!')

def dismiss_class():
    # Is name a global var here?
    print(f'Goodbye {name}!')

def print_name(name):
    # Is name a global var here? 
    print(f'Class Name: {name}')

def change_name():
    # Is name a global var here?
    name = 'CS 1.0' 
    return name
    # print(f'New Name: {name}')


# Try uncommenting each line below and running the script

# welcome_class()
# dismiss_class()
# print_name("WEB2.0") 
# print(name)
# name = change_name()

# What do you think will print?

# print(name)

# Examine the code here figure out the scope of name
# Will the below code work? Why/Why not?
def add_year(): 
    # Is name a global var here?
    name = name + ' 2021'
    print(f'New Name: {name}')

# add_year()
```

<!-- > -->

## Question: 

Do you think scope is causing problems or solving problems? 

What kinds of problems does scope create? 

What kind of problems does scope solve? 

## Example 2

What about scope in common blocks like for and if else? What happens when you define a variable inside one of these? 

**For Loop**

```python 
# Here i is defined and initialized by the for loop
for i in range(1,10):
    print(f"i: {i}")


print(i) # is i "visible" here?  
```

**If Else**

```python
import random


# Here a is defined and initialized inside the if and the else blocks
if random.random() < 0.5:
    a = 'Hello'
else:
    a = 'Goodbye'


print(a) # Is a visible outside of the if else block?
```

**Parameter**

```python
# n is a parameter variable that is defined when the count function is called
def count_to(n):
    for i in range(1, n):
        print(f"i: {i}")
        print(i)


count_to(5)


print(n) # is n "visible" here?
print(i) # what about i ?
```

**How do we get values out of a function?**

Some values will be calculated inside of a function. What do we do when we need those values outside of that function? 

```python
def list_to_str(list):
    # local vars: list, name, str
    str = "" 
    for name in list: 
        str = f"{str} {name}"
        print(str)
        return str # return values you need


str = list_to_str(['Andy', 'Bobby', 'Carl'])
print(str) # Which str is printed here? 
```

**Challenge Question:**

- How many variables are used here? 
- What is scope of each variable? 

```python
scores = [12, 32, 24, 21]


def average_scores(scores):
    total = 0
    for score in scores:
        total += score
	
    average = total / len(scores)
    return average


average = average_scores(scores)
print(average)
```

## Why Avoid Global Variables? 

Global variables lead to problems. The larger your program becomes the more variables it will use. 

Globals variables must be tracked carefully. The more variables you have the harder it is to remember what they all do and where they are used. 

Local variables on the other hand are limited in scope. It's easier to see the extend of their impact on your program. When you leave that scope you no longer need to think about those variables. 

## Using Arguments and Parameters

What could go wrong? Take a look at the code below. It's not working as intended. There are many global variables. Can you fix this? Can you remove all of the global variables and get the right answer? 

```python
radius = 10
price_per_sqr_inch = 0.05
area = 0
price = 0


def calculate_circle_area():
    area = 3.14 * radius * radius


def calculate_price():
    price = price_per_sqr_inch * area


def display_bill():
    print(f"Your bill is ${price} at ${price_per_sqr_inch} per sq. inch toal area {area}")


calculate_circle_area()
calculate_price()
display_bill()
```

## After Class

See the slides for homework! 
