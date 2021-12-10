# OOP Final Challenge

Your goal is to show your knowledge of OOP and Python. This is an assessment of your abilities and should show roughly where your CS skills are at.

The goal is to use OOP to create a coffee bar with customers who place orders. You'll define a person class to represent people that place orders, you'll define an order class that will represent an order that is placed at the coffee bar. You'll also define a CoffeeBar class that can take orders and process those orders. Last, the coffee bar will have a barista which is a sub-class of person. 

-------------

## Challenge 1 

Define a class that will represent a Person. 

A person has a `name` and a `favorite_drink`.

A person has a `my_order` method that returns an Order of their favorite drink. You'll make the `Order` class next challenge and finish this method in challenge 3. 

**Result:** you have defined a Person class and you should be able to initialize it. It has some attributes and a method (which is finished yet...)

-------------

## Challenge 2

Define an `Order` class. This class represents an order for a drink. 

An order has a `type` and a `person` who made the order. 

An order also has a `to_string` method that returns a string with the name of the person and the type of drink they ordered. The order string might look like this: "{customer name} orders: {drink type}"

**Result:** You have defined the Order class. It has some attributes and a method. You can initialize it with a Person and a type. 

-------------

## Challenge 3 

Finish the Person class. The `my_order` method should make an instance of Order which includes the person and their favorite drink.

**Result:** Calling a Person's my_order method should now return an Order instance for that person's favorite drink. 

-------------

## Challenge 4

Create three instances of the Person class. Give each a different name and favorite drink.

- Amy - Coffee
- Bob - Tea
- Cat - Milk

**Result:** You have defined three person instances. Each has a unique name and a different favorite drink. Calling the `my_order` method on any Person instance should return an instance of an order. 

-------------

## Challenge 3 

`CoffeeBar` is a class that has a name and a list of orders. 

It has a `place_order` method which takes an `Order` instance which it appends to its `orders_list`. 

`CoffeeBar` also has a `process_orders` method which loops through all of the orders in the list and prints each order. Use each order's `to_string` method to print the name of the person that ordered and type of the order. 

**Result:** You have defined the CoffeeBar class. It has a `name` and methods `place_order` and `process_orders`. 

-------------

## Challenge 4 

Create an instance of `CoffeeBar`. Give your `CoffeeBar` a name.

**Result:** You have created an instance of the `Coffeebar` class.

-------------

## Challenge 5 

Have each of your three customers (Amy, Bob, Cat) place an order with your coffee bar.

You should be calling the person's `my_order` method to get the order and passing this to the coffee bar's `place_order` method. 

**Result:** Your coffee bar has taken some orders.

-------------

## Challenge 6 

Process all of the orders at your `Coffeebar` instance.

Call the `process_orders` method on your coffee bar instance. 

**Result:** You should see each of the three orders you placed printed to the terminal.

-------------

## Challenge 7 

Make a `Barista` class. This class extends the `Person` class and adds a `greeting` attribute. 

**Result:** You have defined `Barista` as a sub-class of `Person`. 

-------------

## Challenge 8 

Make an instance of a barista named Kevin. Kevin's greeting is "Hey dude!"

**Results:** You have defined an instance of a barista with a greeting. 

-------------

## Challenge 9 

Add a new barista attribute to the CoffeeBar class. 

**Results:** Coffeebar now has a Barista. 

-------------

## Challenge 10 

Assign your Barista, Kevin to your CoffeeBar instance. 

**Results:** Your coffee bar has a Barista. 

-------------

## Challenge 11 

Modify the `process_order` method of the Coffeebar class so that it prints the barista's greeting before it prints the order string. For example, if Kevin is the barista processing an order should read something like: "Hey dude! Amy orders: Coffee"

**Results:** Your coffee bar should now process orders using the barista's greeting. 

-------------

## Challenge 12 (stretch) 

The following problems are all stretch goals. These are all optional problems to solve. 

We need to track money spent. Give each Person a wallet property that holds a float. Imagine this is the amount of money that person has.

Initialize each person with an amount in their wallet. 

Each order should have a price. Which is how much that order will cost. The Coffeebar can decide on the price based on the type.

A person should be charged for the order when the order is processed by the coffee bar. 

A Coffeebar has a register property that holds the money taken in by the coffee bar. When processing an order subtract the cost of the order from the person's wallet and add that amount to the CoffeeBar's register. 

Add a cash-out method to CoffeeBar that prints the amount of money in the register. 

Track the receipts. Every time an order is placed we need to track the order. Give the CoffeeBar a receipts property. This should be a list. Each time an order is processed remove the order from the orders list and add it to the receipts list. 

Kevin needs some tips! Give each person a tip amount. This is the amount that they tip. 

Assign each person instance a different tip amount: 

- Amy - 20%
- Bob - 18%
- Cat - 15%

Give each order a tip amount. A person sets the tip amount when a person places an order they add the amount they tip to the order. 

When calculating the cost of the order subtract the cost of the order plus the tip from each person's wallet. Add the order amount to the register. 

Add a tip_jar attribute to the CoffeeBar class. When an order is processed add the tip amount to the tip jar. 

After processing all orders add the tip jar to Kevin's wallet. 

