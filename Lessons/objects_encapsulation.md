<!-- .slide: data-background="./Images/header.svg" data-background-repeat="none" data-background-size="40% 40%" data-background-position="center 10%" class="header" -->
# Lesson: Objects & Encapsulation

<!-- Put a link to the slides so that students can find them -->

**📝 &nbsp;Class Materials:** 
  <!-- Put a link to the slides -->
* [**Slides**](https://docs.google.com/presentation/d/1AdhOQDIZG1lgoK2DNeZXpXjPr7zpLD6S8hr7Bpi6ITk/edit?usp=sharing)

```python
# Classes are a blueprint
class CoffeeOrder:
  def __init__(self, name, coffee_type):
    self.name = name
    self.type = coffee_type


# Each are their own unique instances of the CoffeeOrder class:

adrianaOrder = CoffeeOrder("adriana", "latte")
marianaOrder = CoffeeOrder("mariana", "mocha")

# When we print them, we can see that they are both CoffeeOrder objects and saved into memory at different locations.

print(adrianaOrder.name)
print(marianaOrder.name)

# TODO: Order yourself a coffee by making a new instance of the CoffeeOrder class. 
# - Define a new variable and initialize an instance of CoffeeOrder
# - when initializing your instance include your name and coffee type


# TODO: Some people like to have milk with their coffee. Add a new attribute to 
# the CoffeeOrder class: has_milk. This should store a bool. 
# Add a parameter that will allow you to initialize has_milk in the __init__
# Include the new third argument with each of the three coffee orders. 


# TODO: Let's test that. Print a messsage for each order that has the order's
# name, coffee_type, and has_milk. Make it read something like: 
# Name: <name> type: <coffee_type> Has Milk: <has_milk>


# If you though about making a function to solve that last TODO you are 
# doing this right! With classes we can go a step further by making the function
# part of the class itself! 

# TODO: Add a new method to the CoffeeOrder class. This method will return a 
# string describing the order. Often class will implement a "to_string" method
# that returns a human readable string describing the class instance. 
# - add a new function inside the class but NOT in the __init__ watch the indentation!
# - this new method should return a string: "Name: <name> type: <coffee_type> Has Milk: <has_milk>"
# - To access attributes of your class use the keyword self! For example: self.name


```
  
<!-- > -->

## After Class

Start working on the [Bank Account](bank_account.md) challenge.



