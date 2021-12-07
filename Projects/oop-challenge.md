# OOP Final Challenge

Your goal is to show your knowledge of OOP and Python. 

The goal is to use OOP to create a coffee bar with customers who place orders. 

-----------

## Challenge 1 

Define a class that will represent a Person. 

A person has a name and a favorite drink. 

A person has a my_order method that returns an Order of their favorite drink. You'll make the order class next challenge and finish this method in challenge 3. 

**Result:** you have defined a Person class. 

-------------

## Challenge 2

Define an Order class. This class represents an order for a drink. 

An order has a type and a person who made the order. 

An order also has a to_string method that returns a string with the name of the person and the type of drink they ordered. The order string might look like this: "{customer name} orders: {drink type}"

**Result:** You have defined the Order class.

-------------

## Challenge 3 

Finish the Person class. The my_order method should make an instance of Order which includes the person and their favorite drink.

**Result:** Calling a Person's my_order method should now return an an Order instance for that person's favorite drink. 

-------------

## Challenge 4

Create three instances of the Person class. Give each a different name and favorite drink.

- Amy - Coffee
- Bob - Tea
- Cat - Milk

**Result:** You have defined three person instances. Each has a unique name and a different favorite drink. 

-------------

## Challenge 3 

CoffeeBar is a class that has a name and a list of orders. 

It has a place_order method which takes an Order instance which it appends to it's orders list. 

CoffeeBar also has a process_orders method which loops through all of the orders in the list and prints each order. Use each order's to_string method to print the name of the person that ordered and type of the order. 

**Result:** You have defined the CoffeeBar class. 

--------------

## Challenge 4 

Create an instance of CoffeeBar. Give your CoffeeBar a name.

**Result:** You have created an instance of the Coffeebar class.

--------------

## Challenge 5 

Have each of your three customers place an order with your coffee bar.

You should be calling the person's my_order method to get the order and passing this to the coffebar's place_order method. 

**Result:** Your coffee bar has taken some orders.

---------------

## Challenge 6 

Process all of the orders at your Coffeebar instance.

Call the process_orders method on your coffee bar instance. 

**Result:** You should see each of the three orders you placed printed to the terminal. 

-------------

## Challenge 7 

Make a Barista class. This class extends the person class and adds a greeting attribute. 

**Result:** You have defined the Barista a sub class of person. 

------------

## Challenge 8 

Make instance of barista named kevin. Kevin's greeting is "Hey dude!"

**Results:** You have defined an instance of barista with a greeting. 

------------

## Challenge 9 

Add a new barista attribute to the CoffeeBar class. 

-------------

## Challenge 10 

Assign your Barista, Kevin to your CoffeeBar instance. 

**Results:** Your coffee bar has a Barista. 

-------------

## Challenge 11 

Modify the process order method of the Coffeebar class so that it prints the barista's greeting before it prints the order string. For example, if Kevin is the barista processing an order should read something like: "Hey dude! Amy orders: Coffee"

**Results:** Your coffee bar should now process orders using the barista's greeting. 

-------------

## Challenge 12 (stretch) 

The following problems are all stretch goals. These are all optional problems to solve. 

We need to track money spent. Give each Person a wallet property that holds a float. Imagine this is the amount of money that person has.

Initialize each person with an amount in their wallet. 

Each order should have a price. Which is how much that order will cost.

A person should be charged for the order when order is processed by the coffee bar. 

A Coffeebar has a register property that holds the money taken in by the coffee bar. When processing an order subtract the cost of the order from the person's wallet and add that amount to the CoffeeBar's register. 

Add a add a cash out method to CoffeeBar that prints the amount of money in the register. 

Track the receipts. Every time an order is placed we need to track the order. Give the CoffeeBar a receipts property. This should be a list. Each time an order is processed remove the order from the orders list and add it to the receipts list. 

Kevin needs some tips! Give each person a tip amount. This is amount that they tip. 

Assign each person instance a different tip amount: 

- Amy - 20%
- Bob - 18%
- Cat - 15%

Give each order a tip amount. A person sets the tip amount when a person places an order they add the amount they tip to the order. 

When calculating the cost of the order subtract the cost of the order plus the tip from each person's wallet. Add the order amount to the register. 

Add a tip_jar attribute to the CoffeeBar class. When an order is processed add the tip amount to the tip jar. 

After processing all orders add the tip jar to Kevins wallet. 

