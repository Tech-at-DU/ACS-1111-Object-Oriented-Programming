<!-- .slide: data-background="./Images/header.svg" data-background-repeat="none" data-background-size="40% 40%" data-background-position="center 10%" class="header" -->
# Lesson: Inheritance & Overriding

<!-- Put a link to the slides so that students can find them -->

**📝 &nbsp;Class Materials:** 
  <!-- Put a link to the slides -->
* [**Slides**](https://docs.google.com/presentation/d/1DkCcA-xcWPfv217vKFYvWkCpQwHQjssOXR7wep_roO8/edit?usp=sharing)

<!-- * **Repls:**
  * Coding Exercise 1: [https://repl.it/@MakeSchool/inheritanceoverridingpractice#main.py](https://repl.it/@MakeSchool/inheritanceoverridingpractice#main.py) -->

```python
# Superclass - Parent
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age

  def introduce_self(self):
    print(f"My name is {self.name} and my age is {self.age}.")


# create two people and have them introduce themselves
person_1 = Person("Adriana", "28")
person_1.introduce_self()

person_2 = Person("Braus", "32")
person_2.introduce_self()

# create Student class

class Student(Person):
  def __init__(self, name, age, major):
    super().__init__(name, age)
    self.major = major
  
  def study(self):
    print(f"{self.name} studies {self.major}")

  def introduce_self(self):
    super(Student, self).introduce_self()
    print(f"I major in {self.major}")
    
# create a Student and have them introduce themselves

student_1 = Student("Danika", "28", "Computer Science")
student_1.introduce_self()
```

## Challenges 

- Create a a Musician class that extends Person
- Muscians should have a favorite song. Musician class should have a favorite_song attribute that is initialized when an instance is created. 
- A muscian should have a method called hum_tune. When this method is called you should print: "{name} hums {favorite_sing}" 
- When a musician introduces themself they say: "My name is {name} and my age is {age}." and "my favorite song is {favorite_sing}".

**Stretch goals**
- Define an instrument class. An Instrument has attributes: name and sound
  - Initialize an instrument with a sound
  - Instruments make a sound: "Toot", "Hmmm", "Plink", "Bom", etc. Initialize an instrument with a sound. 
- All musicians learn one or more instruments in school! Give the Muscian class an instruments attribute. This is an array.
  - Add a method add_instrument. This method takes an Instrument as an argument and adds that instrument to that muscian's instruments array. 
  - Musicians can play their instrument. Give the Musican a play method. A musician will always play the first instrument in their instruments list by print the sound of the instrument a number of times: "Toot Toot", "Hmmm Hmmm Hmmm", "Plink Plink Plink" etc. Songs are in 4/4 or 3/4 or 7/4 so this method takes a second parameter that says how many times to play the sound. For example: dave.play(4) -> "Bom Bom Bom Bom"
- Make a Band class. A band has a name, genre, and a list of members. Members is a list of musicians! 
  - Give Band an add_musician method. This method takes a Musician as an argument and adds that musician to the members list. 
  - Give band an interview method. When there's an interview all band members introduce themselves. 
  - Give band a play_show method. This method plays a song. A song has a time signature so it takes a number as an argument. When a band plays a song Every band member plays their instrument and the process repeats for the time signature. For example: Band of Mick (Doo) and Kieth (Plink) plays a song in 4
    - "Doo Plink Doo Plink Doo Plink Doo Plink"



