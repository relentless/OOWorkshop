# Exercises

These exercises are designed to help you learn and practice OO concepts in C#.  Don't worry if you don't finish them, especially if these things are new to you.

## Part 1: How to do OO in C#

In these exercises we will learn the C# syntax and rules for object orientation in C# by building up an object model for products in a web store similar to Amazon.

Create a console application to create your classes in.  You will use this to try out your classes and objects, although you won't be writing an application as such.

### 1.1: Classes & Objects

Create a Product class which has some properties:
 * Id
 * DisplayName
 * Price
 
It should also have a method 'Describe()' which returns a string including all of the details in a readable format.

Create a couple of instances of your classes and use Describe() to output them to the console.

### 1.2: Inheritance

#### 1.2.1: Simple Hierarchy

Use your Product class as the parent for two derived classes, Book and CD, with the folowing properties:

**Book**  

 * Title
 * Author
 * NumberOfPages
 
**CD**

* Title
* Artist
* TrackList
* TotalLength

Ensure the Describe() method works appropriately for these new classes (you will need to override the one in the base class).

For Book, the DisplayName should be taken from the Title and Author properties in the format '{Title} by {Author}', and for CD it should be '{Artist} - {Title}'.

Again, try them out in the app with a couple of examples.

#### 1.2.2: Extending the Hierarchy

Extend your object hierarchy with another class representing an audio book.  This will require you to refine your class model by having a generic Book class which is the parent of the more specific AudioBook and TextualBook classes.  AudioBook should have the following properties:

**AudioBook**

 * Title
 * Author
 * Narrator
 * TotalLength
 
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

#### 1.2.3: Getting Abstract

Make as many of the classes and methods as you can Abstract.  (The Product class for example can be abstract as it doesn't make sense to have an instance of a non-specific product.  Only the final nodes of the hierarchy reresent real things in this example).

### 1.3: Interfaces

#### 1.3.1: Ship It

Create an interface IShippable which will be used for things which will be physically delivered.  It only has a single property, Weight.

Make all of the appropriate classes implement the IShippable interface.

### 1.3.2: Audible

Create another interface called IPlayable for audio products.  It should have a TotalLength property and a PlaySample() method.  Make the CD and AudioBook implement this interface.  (We're not actually going to play any audio in this exercise, so when the method is called simply write 'Playing [x]' to the console, where x is the DisplayName.)


### 1.4: Polymorphism

Create a ShoppingBasket class which contains a collection of objects representing the items somebody is ordering.  Include a method which adds a product to the basket.

Write a method which returns the total cost of the order, and one which returns the total weight of shippable items.


## Part 2: An Exercise in Object Model Design

In this section you will practice your OO syntax and stretch your design muscles by extending the object hierarchy to include a variety of other things.

This is a more open-ended section which has no right or wrong answers but requires you to weigh up different design options and consider how well they would work as part of a larger system.

### 2.1: Extend the Model

Extend the class hierarchy you created, and add supporting classes and interfaces, in whatever way you think most appropriate for use in an online web store.

Here are some suggestions you could try:

 * Extend the existing model for example with eBooks and/or digital music.
 * Add samples to the TextualBooks.
 * Add other kinds of products such as headphones, pens, and toasters.
 * For composite items (e.g. CDs composed of tracks), calculate the aggregated info (e.g. TotalLength) from the individual items.
 

