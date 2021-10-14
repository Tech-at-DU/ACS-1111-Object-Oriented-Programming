<!-- .slide: data-background="./Images/header.svg" data-background-repeat="none" data-background-size="40% 40%" data-background-position="center 10%" class="header" -->
# Lesson: Objects & Encapsulation

<!-- Put a link to the slides so that students can find them -->

**📝 &nbsp;Class Materials:** 
  <!-- Put a link to the slides -->
* [**Slides**](https://docs.google.com/presentation/d/1AdhOQDIZG1lgoK2DNeZXpXjPr7zpLD6S8hr7Bpi6ITk/edit?usp=sharing)

* **Repls:**
  * Coding Exercise 1: [https://repl.it/@MakeSchool/CoffeeOrderClassStarterCode](https://repl.it/@MakeSchool/CoffeeOrderClassStarterCode)


```python
# Classes are a blueprint
class CoffeeOrder:
  def __init__(self, name, coffeeType):
    self.name = name
    self.coffeetype = coffeeType


# Each are their own unique instances of the CoffeeOrder class:

adrianaOrder = CoffeeOrder("adriana", "latte")
marianaOrder = CoffeeOrder("mariana", "mocka")

# When we print them, we can see that they are both CoffeeOrder objects and saved into memory at different locations.

print(adrianaOrder.name)
print(marianaOrder.name)
```
  

<!-- > -->
