# Data Types

A large part of any program is variables. This is data that is stored
and can be changed by the program. In C# there are 5 simple data types:
 - int - any whole number
 - double - any number with a decimal point
 - string - text
 - char - a single character 
 - bool - a true or false


## Arrays

There are also arrays which allow programmers to store multiple variables of a type 
in one variable. They are defined by adding `[]` to the end of the variable name. 
Here is an example of an int array: `int arr[]`. You can read from the array by 
`arr[3]`. This will read the 4th value from the array.

## Nullables

The last simple data type is the optional or nullable type this means the variable 
can have a value, or it can be null. To make a variable null simply add a '?' to the 
end of the type name like so `int?`. This can be added to any type, including classes
and enums

Programmers can also define their own data types in multiple different ways.

## Enumerations

Enumerations allow us to give names to specific int values. 

Say we have a function that sets our background color, this function takes one argument, 
a number relating to the color. 0 for clear, 1 for black, 2 for white, 3 for red and so on.
It is difficult to remember what number each color relates to, so we use an enum.

```C#
enum Color 
{
    clear,
    black,
    white, 
    red,
    ...
}
```
Note that we don't write any numbers here. C# defines the options starting at 0, going up with 
each new option in the enum.

But what if our function takes the RGBA value as an int. In that case we can define our enum like this:
```C#
enum Color 
{
    clear = 0,
    black = 4294967295,
    white = 255,
    red = 4278190335,
    ...
}
```


## Classes

Classes allow us to define more complex data structures as well as 'methods' to act on them. A class 
can be thought of as a blueprint to describe the layout of something. When we create an instance of a
class in our program we call that an object.


