<!-- .slide: data-background="./Images/header.svg" data-background-repeat="none" data-background-size="40% 40%" data-background-position="center 10%" class="header" -->
# Lesson: Scope

<!-- Put a link to the slides so that students can find them -->

**📝 &nbsp;Class Materials:** 
  <!-- Put a link to the slides -->
* [**Slides**](https://docs.google.com/presentation/d/1gkC9pYcR2eW2oTo4bndZmBiRoAIl4Uwv5j4W2SVgZGw/edit#slide=id.p1)
* **Repls:**
  * Coding Exercise 1: [https://repl.it/@MakeSchool/LocalVariables](https://repl.it/@MakeSchool/LocalVariables)

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
## print(base)
```



  * Coding Exercise 2: [https://repl.it/@MakeSchool/GlobalVariables](https://repl.it/@MakeSchool/GlobalVariables)

```python
# global variables at the top of the file

name = "CS 1.1"

def welcome_class():
  # Is name a global var here?
  # yes
  print(f'Welcome {name}!')

def dismiss_class():
  # Is name a global var here?
  # yes
  print(f'Goodbye {name}!')

def print_name(name):
  # Is name a global var here? 
  # no, it's local
  print(f'Class Name: {name}')

def change_name():
  # Is name a global var here?
  # local
  name = 'CS 1.0' 
  return name
  #print(f'New Name: {name}')


#welcome_class()
# dismiss_class()
#print_name("WEB2.0") 
#print(name)
# name = change_name()

# What do you think will print?
# print(name)

# Will the below code work? Why/Why not?
def add_year(): 
  # Is name a global var here?
  name = name + ' 2021'
  print(f'New Name: {name}')

add_year()
```


  * Kahoot: [https://create.kahoot.it/share/scoping/969373e2-3457-4264-9061-d2f7ec5dc356](https://create.kahoot.it/share/scoping/969373e2-3457-4264-9061-d2f7ec5dc356)
  

<!-- > -->
