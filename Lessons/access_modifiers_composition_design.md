<!-- .slide: data-background="./Images/header.svg" data-background-repeat="none" data-background-size="40% 40%" data-background-position="center 10%" class="header" -->
# Lesson: Access Modifiers, Composition & Design

<!-- Put a link to the slides so that students can find them -->

**📝 &nbsp;Class Materials:** 
  <!-- Put a link to the slides -->
* [**Slides**](https://docs.google.com/presentation/d/1RkjEvVQsAh6j-r-z1nkuys9g0ejXGoCmGy2AeGIeqbg/edit?usp=sharing)

* **Repls:**
  * Coding Exercise 1: [https://repl.it/@MakeSchool/accessmodifierspython#main.py](https://repl.it/@MakeSchool/accessmodifierspython#main.py)

```python
#In this example we will walk through how different access modifiers are indicated in Python
class Python:

  def __init__(self, name, color, age):
    #public property
    self.name = name

    #protected
    self._color = color

    #private
    self.__age = age

  def example1(self):
    print("This is public")
  
  def _example2(self):
    print("This is protected")

  def __example3(self):
    print("This is private")

albert = Python("Albert", "yellow", 2) 
#albert.__example3()

#print(albert.name)
#print(albert._color)
#print(albert._Python__age)

# print( dir(albert))

```

  * Coding Exercise 2: [https://repl.it/@MakeSchool/accessmodifierspractice#main.py](https://repl.it/@MakeSchool/accessmodifierspractice#main.py)

```python
#TODO: create a class with a name of your choice

#TODO: give you class one private, one protected, and one public attribute

#TODO: give you class one private, one protected, and one public method

#Instantiate your class and try to modify each attribute

```

  * Coding Exercise 3: [https://repl.it/@JessDahmen/gettersandsetters#main.py](https://repl.it/@JessDahmen/gettersandsetters#main.py)

```python
#In this example we will show how to create getters and setters for properties within a class

class Person:
  """This class represents a person with a name, and age"""

  def __init__(self, name, age):
    """Initializes the Person class"""
    self.__name = name
    self.__age = age

  def get_name(self):
    """This method returns the name plus the prefix text"""
    return "The person's name is: " + self.__name

  def set_name(self, new_name):
    self.__name = new_name

  def set_age(self, new_age):
    if new_age > 0:
      self.__age = new_age
    else:
      print("error")

  def get_age(self):
    return self.__age


jess = Person("Jess", 29)
name = jess.get_name()
print(name)
name = "Bob"

print(jess.get_name())
jess.set_name("Bob")
print(jess.get_name())

jess.set_age(40)
print(jess.get_age())
jess.set_age(-1)
print(jess.get_age())
```
  * Coding Exercise 4: [https://repl.it/@MakeSchool/composition#main.py](https://repl.it/@MakeSchool/composition#main.py)

```python
#Let's create a Player and then a Team class using composition!

class Player:
  def __init__(self, name, number):
    self.name = name
    self.number = number


class Team:
  def __init__(self, name, city, num_players):
    self.name = name
    self.city = city
    self.players = []
    self.num_players = num_players

    for player in range(num_players):
      new_player = Player("Adriana", 8)
      self.players.append(new_player)

  def addPlayer(self, player):
    self.players.append(player)

myTeam = Team("CS1.1", "San Francisco", 13)
nacho = Player("Nacho", 6)
myTeam.addPlayer(nacho)

eden = Player("Eden Hazard", 7)
myTeam.addPlayer(eden)


for player in myTeam.players:
  print(player.__dict__)
```
  * Coding Exercise 5: [https://repl.it/@MakeSchool/DeckCardsComposition#main.py](https://repl.it/@MakeSchool/DeckCardsComposition#main.py)

```python
import random

class Card:
  def __init__(self, suit, value):
    self.suit = suit
    self.value = value
  
  def show(self):
    print(f"{self.value} of {self.suit}")



#myCard = Card("Hearts", 3)
#myCard.show()

class Deck:
  def __init__(self):
    self.cards = []
    self.build_deck()

  def build_deck(self):

    suits = ["Hearts", "Spades", "Diamonds", "Clubs"]

    for suit in suits:
      for value in range(1,14):
        new_card = Card(suit, value)
        self.cards.append(new_card)

  def shuffleDeck(self):
    random.shuffle(self.cards)

  def draw(self):
    hand = random.sample(self.cards, 10)
    for card in hand:
      card.show()

example_deck = Deck()
example_deck.shuffleDeck()
#print(example_deck.cards)

#for card in example_deck.cards:
  #card.show()

example_deck.draw()

```

<!-- > -->
