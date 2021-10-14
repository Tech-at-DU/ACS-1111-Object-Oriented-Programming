<!-- .slide: data-background="./Images/header.svg" data-background-repeat="none" data-background-size="40% 40%" data-background-position="center 10%" class="header" -->
# Lesson: Decorators

<!-- Put a link to the slides so that students can find them -->

**📝 &nbsp;Class Materials:** 
  <!-- Put a link to the slides -->
* [**Slides**](https://docs.google.com/presentation/d/1n7isJtK6Zbwd_ib9LuxvT4q2SxcfhNSQOVR3jhtyDKo/edit?usp=sharing)

* **Repls:**
  * Coding Exercise 1: [https://repl.it/@MakeSchool/FunctionsAsVariables#main.py](https://repl.it/@MakeSchool/FunctionsAsVariables#main.py)

```python
def greet(name):
  return f"Hello, {name}"

say_hello = greet
print(say_hello("Adriana"))
```

  * Coding Exercise 2: [https://repl.it/@MakeSchool/FunctionsInList#main.py](https://repl.it/@MakeSchool/FunctionsInList#main.py)

```python
#used summ instead of sum, bc sum is reseved.
def summ(num1, num2):
  return num1 + num2

def diff(num1, num2):
  return num1 - num2

def mult(num1, num2):
  return num1 * num2

funcs = [summ, diff, mult]

for func in funcs:
  print(func(10,8))


# print( funcs[0](10, 10) ) # sum
# print( funcs[1](10, 10) ) # diff
# print( funcs[2](10, 10) ) # mult

```

  * Coding Exercise 3: [https://repl.it/@MakeSchool/HigherOrderFunctions#main.py](https://repl.it/@MakeSchool/HigherOrderFunctions#main.py)

```python
# Two math functions
def summ(num1, num2):
  return num1 + num2

def diff(num1, num2):
  return num1 - num2

# Calculate is a Higher Order Function
def calculate(math_func):
  answer = math_func(8, 2)
  return answer

ages = [5, 12, 17, 18, 24, 32]

def myFunc(x):
  if x < 18:
    return False
  else:
    return True

adults = filter(myFunc, ages)

for x in adults:
  print(x)
```

  * Coding Exercise 4: [https://repl.it/@MakeSchool/NestedFunctions#main.py](https://repl.it/@MakeSchool/NestedFunctions#main.py)

```python
# def print_msg(msg):
#     # This is the outer enclosing function
#     def printer(txt):
#         # This is the nested function
#         print(txt)
#     printer(msg)

# print_msg("Hello")



# #The code below will throw an error. Read the error.
# # printer("Hello")


def weather(location, temperature):

  def todays_temp(t):
    print(f"Today's temp is: {t}")

  def your_location(l):
    print(f"Your location is: {l}")

  your_location(location)
  todays_temp(temperature)


weather("washington", 27)
todays_temp(35)

```

  * Coding Exercise 5: [https://repl.it/@MakeSchool/FunctionsReturingFunctions#main.py](https://repl.it/@MakeSchool/FunctionsReturingFunctions#main.py)

```python
def print_msg(msg):
    # This is the outer enclosing function
    def printer():
        # This is the nested function
        print(f"Message example: {msg}")
    return printer  # returns the nested function

say_hello = print_msg("Hello")

```

  * Coding Exercise 6: [https://repl.it/@MakeSchool/FunctionsReturningFunctions2#main.py](https://repl.it/@MakeSchool/FunctionsReturningFunctions2#main.py)

```python
def get_speak_func(volume):

    def whisper(text):
        return text.lower() 

    def yell(text):
        return text.upper()

    if volume > 0.5:
        return yell
    else:
        return whisper


speak_func = get_speak_func(0.9)
print(speak_func())

```

  * Coding Exercise 7: [https://repl.it/@MakeSchool/uglydecorator](https://repl.it/@MakeSchool/uglydecorator)

```python
# main.py
'''
Components of a Decorator:

1. Take in a function as a parameter
2. Inside that function, define a wrapper function (i.e. a nested function) that uses the passed function and adds stuff to it.
3.Return the wrapper function

#TODO: Write your own ugly decorator that will extend a simpler function by adding "Entering Function" before the function is called and "Exiting Function" after it is called.

Entering Function
Hello World
Exiting Function
'''
# TODO: Create ugly_decorator (you can call it whatever you want btw).
def ugly_decorator(func):
  def wrapper():
    print("About to execute a function")
    func()
    print("Finished executing a function")
  return wrapper

# Note: create our decorator functions before the functions that use it, not after. 

# Our simple function
def fetch_user():
    print("Fetching user data")

decorated_fetch_user = ugly_decorator(fetch_user)
decorated_fetch_user()

#TO DO: After creating your ugly decorator, reassign the original function to the decorated one.
```

```python
# copy.py
'''
Components of a Decorator:

1. Take in a function as a parameter

2. Inside that function, define a wrapper function (i.e. a nested function) that uses the passed function and adds stuff to it.

3.Return the wrapper function



#TODO: Write your own ugly decorator that will extend a simpler function by adding "Entering Function" before the function is called and "Exiting Function" after it is called.

Entering Function
Hello World
Exiting Function
'''


# TODO: Create ugly_decorator (you can call it whatever you want btw).

# Note: create our decorator functions before the functions that use it, not after. 


# Our simple function
def hello_world():
    print("Hello World")

#TO DO: After creating your ugly decorator, reassign the original function to the decorated one.


```

  * Coding Exercise 8: [https://repl.it/@MakeSchool/decorators#main.py](https://repl.it/@MakeSchool/decorators#main.py)

```python
# main.py

# # Our ugly decorator 
#  def ugly_decorator(func):

#   def wrapper():  
#     print("Entering Function")
#     func()
#     print("Exiting Function")

#   return wrapper


# # Our simple function
# def hello_world():
#     print("Hello World")



# # The ugly way to decorate
# hello_world = ugly_decorator(hello_world)
# hello_world()


# The clean way to decorate: 
def logging_decorator(func):
  def wrapper(): 
    print("Entering Function")
    func()
    print("Exiting Function")
  return wrapper

# Use the @ symbol and the name of the function name of the decorator
@logging_decorator
def hello_world():
    print("Hello World")

@logging_decorator
def say_goodbye():
  print("See ya!")

# #Now every time we call our decorated function Python knows to also call the extended code in the decorator
hello_world()

```

```python
# copy.py 

# Our ugly decorator 
def ugly_decorator(func):

  def wrapper(): 
    print("Entering Function")
    func()
    print("Exiting Function")

  return wrapper


# Our simple function
def hello_world():
    print("Hello World")



# The ugly way to decorate
hello_world = ugly_decorator(hello_world)
hello_world()



# # ✋🏽️ Comment the above code. Uncomment code below.


# # The clean way to decorate: 


# def ugly_decorator(func):

#   def wrapper(): 
#     print("Entering Function")
#     func()
#     print("Exiting Function")

#   return wrapper

# # Use the @ symbol and the name of the function name of the decorator
# @ugly_decorator
# def hello_world():
#     print("Hello World")



# #Now every time we call our decorated function Python knows to also call the extended code in the decorator

# hello_world()
```

  * Coding Exercise 9: [https://repl.it/@MakeSchool/DecoratorWithParams#main.py](https://repl.it/@MakeSchool/DecoratorWithParams#main.py)
  
```python
'''
Currently our Enter and Exit messages are hardcoded as "Entering Function" and "Exiting Function".

Let's make our decorator even more dynamic by allowing the user to pass in what enter and exit message they would like

'''

# Step one, create a function with the name you want for your decorator (@enter_exit_logging -> enter_exit_logging) and give it parameters, enter_msg and exit_msg

# Step 2: Inside enter_exit_logging create a wrapper function, it takes one parameter, func (which will be the function you decorate)

# Step 3: Inside your wrapper, write the logic for your decorator

# Step 4: Outside wrapper, but inside enter_exit_logging return the wrapper function

#Step 5: Let's test.

# Use the @ symbol and the name of the function name of the decorator


def logging_messages(enter_msg, exit_msg):
  def wrapper_function(function):
    def wrapper():
      print(enter_msg)
      function()
      print(exit_msg)
    return wrapper
  return wrapper_function

@logging_messages("Starting user data fetch","User data successfully fetched")
def fetch_user_data():
  print("Fetching user data from web server")

fetch_user_data()
```

<!-- > -->
