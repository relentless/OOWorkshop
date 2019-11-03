# Exercises

## Part 1: How to do OO in C#

In these exercises we will learn the C# syntax and rules for object orientation in C# by building up an application.

If you are not very familiar with OO, you may not finish this section.

### 1.1: Classes & Objects

Create a Product class which has some properties:
 * Id
 * Name
 * Price
 
It should also have a method 'Describe()' which returns a string including all of the details in a readable format.

### 1.2: Inheritance

Use your Product class as the parent for two derived classes, Book and CD.  They should have properties particular to those kinds of things, for example Book might have Author, Title and number of pages, CD might have a list of tracks and a length in time.

Extend your object hierarchy with another class representing an audio book.  You will want a general class such as Book which inherits from Product, which is then the parent class for AudioBook and PhysicalBook.

Ensure the Describe() method works appropriately for these new classes.

Make as many of the classes and methods as you can Abstract.  (The Product class for example can be abstract as it doesn't make sense to have an instance of a non-specific product).

### 1.3: Interfaces

Create an interface IShippable which will be used for things which will be physically delivered.  This should include relevant properties such as Weight.

Make all of the appropriate classes implement the IShippable interface.

### 1.4: Polymorphism



## Part 2: Object Model Design with OO

In this section you will put your knowledge of OO syntax into practice by designing and implementing an object hierarchy in C#.

This is a more open-ended section which has no right or wrong answers but requires you to weigh up different design options and consider how well they would work as part of a larger system.

### 2.1: Class Hierarchy Design

Design and implement a class hierarchy representing a simple banking system which allows money to be stored, spent and transferred in different ways.

Consider the different forms money can take, for example cash, credit cards and vouchers, and the different properties of those.

Think about different currencies and how the ability to store and/or pay in different ones affects the model.

The result of this exercise should be an object model implemented in C# which uses inheritance and other OO features as approproate, which could be used by banking services.  If you have time, demonstrate the use of your classes as well, for example with a console application or unit tests.
