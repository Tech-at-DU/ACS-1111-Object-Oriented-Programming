<!-- .slide: data-background="./Images/header.svg" data-background-repeat="none" data-background-size="40% 40%" data-background-position="center 10%" class="header" -->
# Lesson: Function Arguments and Overloading

<!-- Put a link to the slides so that students can find them -->

**📝 &nbsp;Class Materials:** 
  <!-- Put a link to the slides -->
* [**Slides**](https://docs.google.com/presentation/d/19KGxaVHIJUXlig9PACenEGdB4zcub4QlgkaMf_GlE44)
* **Repls:**
  * Coding Exercise 1: [https://repl.it/@MakeSchool/DefaultArguments](https://repl.it/@MakeSchool/DefaultArguments)

```python
'''
This function greets to a person with a provided message.

If the message is not provided, it defaults to "How are you?"
'''

def greet(name="Luna", msg="Hey this is the default message"):
  print(f"Hello, {name}. {msg}")

greet("my own message")



#def greet(name, msg="How are you?"):
  #print(f"Hello, {name}. {msg}")

#greet('Joi') 
#greet('Dee')

#greet('Joi', 'Good Morning!')
#greet('Joi', 'Good Night!')




# TODO: What should we do to make `name` a default argument?


```

  * Coding Exercise 2: [https://repl.it/@MakeSchool/DefaultArgumentSplitBill](https://repl.it/@MakeSchool/DefaultArgumentSplitBill)

```python
'''
Imagine that you and a friend go to lunch together and regularly spend $10 on each of your
meals.

To make calculating the amount each of you need to pay if you split the bill evenly,
you made a function called `split_bill()`.

'''

#TODO: Create a function called split_bill()
# Parameters: price1 and price2
# Function body: Add two prices and divide by two, to determine how much each person should pay.
# Print a message "You each need to pay $X.XX"


#TODO: You lunch order came to $13.95 and your friend's bill came to $15.20. Use split_bill to see how much each of you need to pay to cover the bill. 



#TODO: Update the parameters, price1 and price2, in your split_bill functions to be default parameters. price1 and price2 should be 10 by default

# TODO: call split_bill() with out passing arguments to see if it is working
```

  * Coding Exercise 3: [https://repl.it/@MakeSchool/KeywordArguments](https://repl.it/@MakeSchool/KeywordArguments)

```python
def area(width, height):
  return width * height


# Positional Arguments
#print(area(10, 20))


# Keyword Arguments (in order)
##print(area(width=10, height=20))

# Keyword Arguments (out of order)
#print(area(height = 20, width = 10))


# 1 Positional, 1 keyword
print(area(10, height = 20))

print(area(10, height = 20))


#Is the function call below permitted?
# area(height = 20, 10)

# Spoiler Alert: No, keyword arguments must follow positional arguments
```

  * Coding Exercise 4: [https://repl.it/@MakeSchool/KeywordArgumentExample](https://repl.it/@MakeSchool/KeywordArgumentExample)

```python
# main.py
'''

The following function will print a Make School student's Term 2 classes. 

'''
#TODO:
# Make class1 cs1.1 by default
# Make class2 web1.1 by default
# Make class3 spd1.2 by default

# TODO: Let's say that you decided to be a Front End concentration. This term, you might be taking FEW1.2 instead of WEB1.1. Using positional arguments, update the class schedule such that class 2 is few1.2


def term_2(name, class1="cs1.1", class2="web1.1", class3="spd1.2"):
  print(f"{name}'s Term 2 schedule:")
  print(f"Class 1: {class1}")
  print(f"Class 2: {class2}")
  print(f"Class 3: {class3}")

term_2("Adriana")

# I.e. their schedule cs1.1, web1.1, mob1.1
#term_2("Adriana", class3="mob1.1")

```

```python
# instructions.py


#TODO: Create a function called term_2(), it take 5 params: name, class1, class2, class3
#TODO:
# Make class1 cs1.1 by default
# Make class2 web1.1 by default
# Make class3 spd1.2 by default


#Run: term2() without positional arguments other than name





#Using keyword arguments, update the class schedule such that class 2 is few1.1


# Another student decided to take mob1.1 for  class 3. 
# I.e. their schedule cs1.1, web1.1, mob1.1, s&l


# TODO: How should with do this using positional arguments


#That was a lot of work. What if we used keyword arguments?

```

  * Coding Exercise 5: [https://repl.it/@MakeSchool/UsingArgs](https://repl.it/@MakeSchool/UsingArgs)

```python
def greet(*names):
  print(names)
  print(len(names))
  for name in names: 
    print(f"Hey, {name}")

greet("Brenda", "LaTisha", "Linda", "Felicia","Brenda", "LaTisha", "Linda", "Felicia", "Brenda", "LaTisha", "Linda", "Felicia")


# Other things to try:
# Comment function body and return names and see what happens when you print names
# Wondering how many arguments were passed in? Just take the length of names.


```

  * Coding Exercise 6: [https://repl.it/@MakeSchool/SplitBillsUsingArgs](https://repl.it/@MakeSchool/SplitBillsUsingArgs)

```python
# main.py
'''
While you primarily only eat lunch with one friend, you welcome any of your other friends to
join you for lunch. 

The number of additional guest varies each day and it would be inefficient
to update the `splitBill()` function definiton with additional parameters every time you went out for lunch.

To be able to use your `splitBill()` function to calculate the amount each attendee needs to
pay, you add a *args to the function definiton to store the prices of the meals of the additional attendees.

See instructions.py
'''

def split_bill(price1=10, price2=10, *prices):
  bill_total = price1 + price2 + sum(prices)
  num_guest = 2 + len(prices)
  split_cost = bill_total / num_guest
  print(f"There are {num_guest} guests in your party.")
  print(f"Each should pay ${split_cost}")

#split_bill()
split_bill(10,30,40,76,2)

```

```python
# instructions.py
# TODO: update the function defintion to allow for arbritrary arguments. Use *prices. 

# Call the function again, but use more than two arguments
# You will see that it will not fail. If you remove it, it will


# Let's see what *prices is storing for the above function call. At the end of the function, print out prices. What do we see and why?

# Let's update our function:

# TODO: We need to include the prices in *prices to the bill total. we can use sum() to sum the values in a list/tuple

# TODO: We need to increase the number of party guest. To get the number of additional guest, we need to know how many additional arguments were passed.


# TODO: Call the function in 3 different ways
# split_bill()
# split_bill(price2=40)
# split_bill(50, 60 ,40 ,60)
```

  * Coding Exercise 7: [https://repl.it/@MakeSchool/kwargs](https://repl.it/@MakeSchool/kwargs)

```python
# Using *args
def intro(*data): 
  print(f"This is what data looks like:{data}")
  for data_item in data:
    print(data_item)

#intro("Joi", 25, "NYC", "Software Engineer")

# Using **kwargs
def intro(**data):   
  print(f"This is what data looks like:{dict(data.items())}")

  for key, value in data.items():
      print(f"{key} is {value}")

intro(name="Joi", age=25, city="NYC", job="Software Engineer", salary="100000")

```

<!-- > -->
