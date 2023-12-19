# OOP Intro

OOP refers to on of the [Paradigms of Programming](https://en.wikipedia.org/wiki/Programming_paradigm).
It stands for Object-Oriented Programming where programmers use classes to represent parts of a 
program or system. Let's look at an example to see how it works

Here we create a class called `Person` that will describe an individual person.
```C#
class Person
{
    public string Name { get; set; }
    public int Age { get; set; }
    public string HairColor { get; set; }
    
    public Person() 
    {
        Name = "John Smith";
        Age = 40;
        HairColor = "Brown";
    }
    
    public Person(string name, string hair, int age)
    {
        Name = name;
        Age = age;
        HairColor = hair;
    }
    
    public void Talk(string msg) 
    {
        Console.WriteLine(msg);
    }
};
```
Now we have a full person class but what does it all mean? Let's go through it.

```C#
public string Name { get; set; }
public int Age { get; set; }
public string HairColor { get; set; }
```
Here we define a few properties that describe parts of the object. 

```C#
public Person() 
{
    Name = "John Smith";
    Age = 40;
    HairColor = "Brown";
}
```
Next we define a 'default constructor'. This is called whenever we create a new instance of our class
like `var person = new Person();`. This will set `Name` to 'John Smith', `Age` to 40 and `HairColor` to 
'Brown'. But what if we want to set these to different values

```C#
public Person(string name, string hair, int age)
{
    Name = name;
    Age = age;
    HairColor = hair;
}
```
This part declares a constructor that takes in 3 arguments, the name, hair color and age. Because it takes
in arguments unlike the default constructor we call this a 'greedy constructor'.

```C#
public void Talk(string msg) 
{
    Console.WriteLine(msg);
}
```
Lastly a method called `Talk`. This method takes 1 argument, the message to print, and writes it to
the console.
