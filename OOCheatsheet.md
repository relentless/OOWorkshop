# C# Cheatsheet

Taken from https://github.com/jwill9999/C-Sharp-Cheatsheet/blob/master/README.md

# Index<br>

[Classes](#Classes)<br>
[Inheritance](#Inheritance)<br>
[Virtual and Override](#Virtual-and-Override)<br>
[Abstract Class](#Abstract-Class)<br>
[Abstract methods](#Abstract-methods)<br>
[Interfaces](#Interfaces)<br>


# Classes


A Class is a group of related methods and variables.  

You can create as many instances of your class as you want.  


```c#
using System;

namespace ConsoleApplication1
{
    class Program
    {
        static void Main(string[] args)
        {
            // Declare a variable of type Car
            Car car;

            // Creates an new instance
            car = new Car("Red");

            // New instance gives us method access
            Console.WriteLine(car.Describe());

            car = new Car("Green");
            Console.WriteLine(car.Describe());

            Console.ReadLine();

        }
    }

    class Car
    {
        private string color;

        public Car(string color)
        {
            this.color = color;
        }

        public string Describe()
        {
            return "This car is " + Color;
        }

        public string Color
        {
            get { return color; }
            set { color = value; }
        }
    }
}

```

* This code creates a new class called Car
* It defines a single variable, called color, which of course is used to tell the color of our car.
* Our Car class defines a constructor
* It takes a parameter which allows us to initialize Car objects with a color.
* The Describe() method allows us to get a nice message

<br>

# Inheritance

Inheritance is the ability to create classes which inherit data and functionality from a parent classe/classes. 

The entire .NET framework is built on this concept, with all classes inheriting (directly or indirectly) from System.Object

```c#

public class Animal
{
    public void Greet()
    {
        Console.WriteLine("Hello, I'm some sort of animal!");
    }
}

// Dog Inherits from Animal base classs
public class Dog : Animal
{

}

```

Then we can Create a new Animal and a new Dog. They will both have access to the Greet method though Inheritance.

```c#
Animal animal = new Animal();
animal.Greet();
Dog dog = new Dog();
dog.Greet();
```

<br>

# Virtual and Override 

Here we take the same principle as above however we override the Greet Method as defined in the Animal Base class. To allow this we have to add the keyword Virtual to the greet method. This then allows us to override that method in the child class dog.

```c#
public class Animal
{
    public virtual void Greet()
    {
        Console.WriteLine("Hello, I'm some sort of animal!");
    }
}

public class Dog : Animal
{
    public override void Greet()
    {
        Console.WriteLine("Hello, I'm a dog!");
    }
}

```


<br>


# Abstract Class

Abstract classes, marked by the keyword abstract in the class definition, are typically used to define a base class in the hierarchy
You ```can't``` create an instance of them.

```c#

// We can't new up an abstract class
abstract class FourLeggedAnimal
    {
        public virtual string Describe()
        {
            return "Not much is known about this four legged animal!";
        }
    }
 // We can inherit from it !
    class Dog : FourLeggedAnimal
    {

    }

```


<br>

# Abstract methods

Abstract methods are only allowed within abstract classes. 

We define them as abstract but without any code, then in our inherited class we override that method and include an implementation.

```c#
  abstract class FourLeggedAnimal
    {
        public abstract string Describe();
    }


    class Dog : FourLeggedAnimal
    {
        public override string Describe()
        {
            return "I'm a dog!";
        }
    }

```


<br>

# Interfaces

Interfaces are similar to Abstract Classes, with two main differnces:
 * You can't include any implementation in an Interface
 * You can implement multiple interfaces but only inherit from one class

You cannot crateate an instance of an Interface.

> NO METHODS ARE ALLOWED AT ALL

* All Interfaces are Public

> There are NO  access modifiers (public, private, protected etc.),<br> because they are not allowed.


```c#
    class Program
    {
        static void Main(string[] args)
        {
            List<Dog> dogs = new List<Dog>();
            dogs.Add(new Dog("Fido"));
            dogs.Add(new Dog("Bob"));
            dogs.Add(new Dog("Adam"));
            dogs.Sort();
            foreach(Dog dog in dogs)
                Console.WriteLine(dog.Describe());
            Console.ReadKey();
        }
    }
    
interface IAnimal
    {
        string Describe();

        string Name
        {
            get;
            set;
        }
    }

    class Dog : IAnimal, IComparable
    {
        private string name;

        public Dog(string name)
        {
            this.Name = name;
        }

        public string Describe()
        {
            return "Hello, I'm a dog and my name is " + this.Name;
        }
       

        // This method comes from the IComparable interface
        public int CompareTo(object obj)
        {
            if(obj is IAnimal)
                return this.Name.CompareTo((obj as IAnimal).Name);
            return 0;
        }

        public string Name
        {
            get { return name; }
            set { name = value; }
        }
    }

```

<br>
