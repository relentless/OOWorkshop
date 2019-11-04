# Exercises

These exercises are designed to help you learn and practice OO concepts in C#.  Don't worry if you don't finish them, especially if these things are new to you.

## Part 1: How to do OO in C#

In these exercises we will learn the C# syntax and rules for object orientation in C# by building up an object model for products in a web store similar to Amazon.

Create a console application to create your classes in.  You will use this to try out your classes and objects, although you won't be writing an application as such.

### 1.1: Classes & Objects

Create a Product class which has some properties:
 * Id
 * Name
 * Price
 
It should also have a method 'Describe()' which returns a string including all of the details in a readable format.

Create a couple of instances of your classes and use Describe() to output them to the console.

### 1.2: Inheritance

#### 1.2.1: Simple Hierarchy

Use your Product class as the parent for two derived classes, Book and CD, with the folowing properties:

**Book**  

 * Title
 * Author
 * Number of Pages
 
**CD**

* Artist
* Track List
* Total Length

Ensure the Describe() method works appropriately for these new classes.

Again, try them out in the app with a couple of examples.

#### 1.2.2: Extending the Hierarchy

Extend your object hierarchy with another class representing an audio book.  This will require you to refine your class model by having a generic Book class which is the parent of the more specific AudioBook and TextualBook classes.  AudioBook should have the following properties:

**AudioBook**

 * Title
 * Author
 * Narrator
 * Total Length
 
 You should use the class hierarchy to share as many of these as possible in the Book class.

The class hierarchy should look as follows:

```
            Product
             /   \  
            CD  Book
               /     \
              /       \
       TextualBook  AudioBook
```

Make as many of the classes and methods as you can Abstract.  (The Product class for example can be abstract as it doesn't make sense to have an instance of a non-specific product).

### 1.3: Interfaces

Create an interface IShippable which will be used for things which will be physically delivered.  This should include relevant properties such as Weight.

Make all of the appropriate classes implement the IShippable interface.

### 1.4: Polymorphism

Create a ShoppingBasket class which contains a collection of objects representing the items somebody is ordering.  Include a method which adds a product to the basket.

Write a method which returns the total cost of the order, and one which returns the total weight of shippable items.


## Part 2: Object Model Design with OO

In this section you will put your knowledge of OO syntax into practice by designing and implementing an object hierarchy in C#.

This is a more open-ended section which has no right or wrong answers but requires you to weigh up different design options and consider how well they would work as part of a larger system.

### 2.1: Class Hierarchy Design

Design and implement a class hierarchy representing a simple banking system which allows money to be stored, spent and transferred in different ways.

Consider the different forms money can take, for example cash, credit cards and vouchers, and the different properties of those.

Think about different currencies and how the ability to store and/or pay in different ones affects the model.

The result of this exercise should be an object model implemented in C# which uses inheritance and other OO features as approproate, which could be used by banking services.  If you have time, demonstrate the use of your classes as well, for example with a console application or unit tests.
