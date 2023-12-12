# Object Oriented Programming

Object-Oriented Programming, usually shortened to OOP, is a method of programming
where the programmer uses class to define objects that can represent different parts
of a program or system.

Below is a class representing a person
```C#
public class Person
{
    private int _height;
    public int Height 
    { 
        get 
        {
            return _height;
        }
        private set
        {
            if (value < 50)
            {
                throw new Exception("That is too short");
            }
            _height = value;
        }
    }
    
    public string FirstName { get; set; };
    public string LastName { get; set; };
    public string Name 
    {
        get 
        {
            return FirstName + LastName;
        }
    }
    
    public Person(string firstName, string lastName, int height)
    {
        FirstName = firstName;
        LastName = lastName;
        Height = height;
    }

    public void Talk(string words)
    {
        Console.WriteLine(words);
    }
    
    public static string Species() 
    {
        return "Homo Sapien";
    }
};
```

Let's go through each of the parts in this class

```C#  
private int _height
```

This line defines 1 field called _height. The private keyword here means that it can
only be accessed from inside the class.

```C#
public int Height
{
    get
    {
        return _height;
    }
    private set
    {
        if (value < 50)
        {
            throw new Exception("That is too short");
        }
        _height = value;
    }
}
```
Here create a property. This is similar to a field with the added benefit of being
able to define methods to check for that the value is valid.

The first part of it is getter which only returns the _height field. While the setter
checks if the value we gave is less than 50 and if it is, throws an exception. Otherwise,
the `_height` field is assigned value. Note also that `set` is private. this means 
that it can only be written to from inside the class

```C#
public string FirstName { get; set; };
public string LastName { get; set; };
```
In these lines we define 2 properties called first name and last name. We do not need a
backing field like we did with `Height` because the dotnet will do this for us. 

```C#
public string Name
{
    get
    {
        return FirstName + LastName;
    }
}
```
Here is the last property defined in the class. This property does not actually store
any data, instead it gives you the first and last names put together.

```C#
public Person(string firstName, string lastName, int height)
{
    FirstName = firstName;
    LastName = lastName;
    Height = height;
}
```
The above method is what is called a `Constructor`. This method is what is used to 
initialize the class with the provided values. You can define multiple of these that
take in different arguments or none at all.

If the constructor takes no arguments it is called a default constructor. When it
does take arguments we call it a greedy constructor

```C#
public void Talk(string words)
{
    Console.WriteLine(words);
}
```
Here we define a method called 'Talk' which takes a single argument 'words'. When we
call this method it will write `words` to the console.

```C#
public static string Species()
{
    return "HomoSapien";
}
```
Lastly we have a method that returns Species. Because all people are the same species
we can mark this method as static. This means that we don't need to create an instance
of `Person` in order to access this method. 
