<!-- .slide: data-background="./Images/header.svg" data-background-repeat="none" data-background-size="40% 40%" data-background-position="center 10%" class="header" -->
# Lesson: Access Modifiers, Composition & Design

<!-- Put a link to the slides so that students can find them -->

**📝 &nbsp;Class Materials:** 
  <!-- Put a link to the slides -->
* [**Slides**](https://docs.google.com/presentation/d/1RkjEvVQsAh6j-r-z1nkuys9g0ejXGoCmGy2AeGIeqbg/edit?usp=sharing)

* **Repls:**
  * Coding Exercise 1: 
  
  <!-- [https://repl.it/@MakeSchool/accessmodifierspython#main.py](https://repl.it/@MakeSchool/accessmodifierspython#main.py) -->

```python
#In this example we will walk through how different access modifiers are indicated in Python
class Snake:
  def __init__(self, name, color, type):
    #public property
    self.name = name

    #protected
    self._color = color

    #private
    self.__type = type

  def example1(self):
    print("I eat rodents! (This is public)")

  def _example2(self):
    print("I like to slither in the sand (This is protected)")
    self.__example3()

  def __example3(self):
    print("I like to curl up on a hot rock! (This is private)")

# Make a snek caled albert
albert = Snake("Albert", "yellow", "Python")

# Look at each line below. Predict the output 
# by examining the class above. Then uncomment 
# the line and run the code: 

# albert.__example3()
# albert.example1()
# albert._example2()
# print(albert.name)
# print(albert._color)
# print(albert._Snake__type)
# print( dir(albert) )

```

  * Coding Exercise 2: 
  
  <!-- [https://repl.it/@MakeSchool/accessmodifierspractice#main.py](https://repl.it/@MakeSchool/accessmodifierspractice#main.py) -->

```python
# Make a class that creates an instance of yourself! 
# Your class will have some public, protected, and 
# private attributes. 

#TODO: Create a class that desribes you! Give your class three attributes

#TODO: Give your class one private, one protected, and one public attribute

#TODO: Give you class one private, one protected, and one public method

# TODO: Instantiate your class and try to modify each attribute

```

  * Coding Exercise 3: 
  
  <!-- [https://repl.it/@JessDahmen/gettersandsetters#main.py](https://repl.it/@JessDahmen/gettersandsetters#main.py) -->

```python
# In this example we will show how to create getters and setters for properties within a class

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
# Let's create a Player and then a Team class using composition!

class Player:
  def __init__(self, name, number):
    self.name = name
    self.number = number
    self.team = None
  
  def intro(self):
    print(f"Name: {self.name} number: {self.number} team: {self.team.name}")


class Team:
  def __init__(self, name, city, num_players):
    self.name = name
    self.city = city
    self.players = []
    self.num_players = num_players

  def add_player(self, player):
    player.team = self
    self.players.append(player)

  def roster(self):
    for player in self.players:
      print(player.name)


myTeam = Team("CS1.1", "San Francisco", 13)
andy = Player("Andy", 6)
myTeam.add_player(andy)

bob = Player("Bob", 7)
myTeam.add_player(bob)

myTeam.roster()

andy.intro() # andy says their name, number and team. 

# Both player and Team are classes. 
# Team has a list of players. 
# A Team is not a Player is not a Team!

# Note! Team owns a list of PLayers. Team can communicate 
# with Player in the the list. See the roster method. 

# On the other hand Player has no way to to communicate 
# with its Team. That is unless we provide that mechanism!

# Look at the Player's team attribute. Look at the the 
# Team's add_player method. Here, each time a player is 
# added to the team that players team attribute is set 
# to the team object. 
```

  <!-- * Coding Exercise 5: [https://repl.it/@MakeSchool/DeckCardsComposition#main.py](https://repl.it/@MakeSchool/DeckCardsComposition#main.py) -->

## Challenge!

You need to create two classes. One will represent a playing card. The other will represent a deck of cards. 

A deck of cards has 52 cards in four suits and two colors. Suits are: 

- ♠️ Spades
- ♣️ Clubs
- ♥️ Hearts
- ♦️ Diamonds

Values range from 1-13. 

Stretch challenge values range from Ace, 2-10, Jack, Jack, Queen, King. 

Color is either Red for Hearts and Diamonds, or black for Spades and Clubs. 

**Card** class will have attributes of:

- suit - The suit
- value - the value
- color - the color

Card will also have a `show()` method that prints the value and suit. 

**Deck** class will have attributes of: 

- `cards` - a list of Card instances 

Deck will have methods of: 

- `create_deck()` - populates the cards list with cards. You need 52 cards 1-13 in value for each of the four suits. 
- `shuffle()` - randomzies the list of cards. Note! You can use `random.shuffle()` from the built in python library. 

**Stretch Challenges**

- Add a `draw()` method to the `Deck` class. This method returns the first card in the cards list and returns it. 
- Add a `discard_pile` attribute to the `Deck` class. This property is a list that holds cards that were discarded. 
- Add a `discard()` method that takes a card and adds it to the discard list. 
- Every card should know what deck it belongs to. Add a `deck` attribute to the `Card` class. When a card is created set it's `deck` to the deck that created it. 
- Give `Card` a discard method. This method should add that card to it's deck's discard pile. A card can call discard on it's deck and pass it self as an argument!
- Create a `Hand` class. A had class is like a small deck. It stores a list of `cards` in an attribute. It also has a `deck` attribute that is the deck that the hand was drawn from.
- Add a `draw_hand()` method to the `Deck` class. This method should return a new instance of the `Hand` class and populate it with 7 cards. 
- The `Hand` class needs a draw method. This method calls `draw` on the deck the hand is working with and adds the returned card to the hand's cards list. 
- A `Hand` needs a `discard_random()` method. This method chooses a random card in the hand's cards list and passes it to it's deck's discard method. 
- Add a `discard()` method to the `Hand` class. This method takes the index of a card in the cards list and discards that card. 
 

