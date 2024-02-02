# Loops and Conditionals


## Conditionals

Often times in code we need to do a specific action based on a condition. Here we use 
conditional statements for this. C# has 2 types of conditionals, the 'if/else' and 
'switch'. Let's start with the 'if/else'.

This example will check for 1 of 3 values entered, 'yes', 'no', 'maybe'
```C#
string answer = Console.ReadLine();

if (answer == "yes")
{
    Console.WriteLine("You answered 'yes'");
}
else if (answer == "no")
{
    Console.WriteLine("You answered 'no'");
}
else if (answer == "maybe")
{
    Console.WriteLine("You answered 'maybe'");
}
else 
{
    Console.WriteLine($"You answered '{answer}'");
}
```
Here we check the value and print out the respective message. But if the answer isn't one
of the expected values we use `else` to print out whatever the answered.

The other type of conditional is called the switch. It is much faster than 'if/else' but
only works for int or char values. 
```C#
char opt = Console.ReadLine()[0];

switch (opt)
{
    case 'a':
        Console.WriteLine("A is for apple");
        break;
    case 'b':
        Console.WriteLine("B is for Bees");
        break;
    case 'c':
        Console.WriteLine("C is for Coding");
        break;
    default:
        Console.WriteLine("I don't know that letter");
        break;
}   
```
Here we define what we want to happen based on the value of `opt` by using the `case`. When
we enter 'b' as the option the switch will jump straight to `case 'b':`. But we also have 
these break statements in each case. This is because if we don't have it our switch will
continue going through each case until it reaches a `break` or the end of the switch. This 
feature of the switch can be quite useful sometimes. Say we want 'q' and 'x' to mean quit,
we can create our program like this to get that result
```C#
char opt = Console.ReadLine()[0];

switch (opt)
{
    case 'x':
    case 'q':
        exit();
        break;
    default:
        Console.WriteLine($"You entered '{opt}'");
        break;
}
```


## Loops

Another important part of programming is loops. These are blocks of code that allow use 
to repeat code. We have access to a few different types of loops in C# each with its own
use cases.

Let's start with the most basic loop, the while loop. This will continue to run as long 
as the condition we give it is true. Here is an example of a while loop that reads an
option from the console until the user enters 'q' for quit.
```C#
char opt;
while ( (opt = Console.ReadLine()[0]) != 'q')
{
    // do stuff
}
```
Here we do 2 things in our loop. First we assign opt the character was entered, then we check
the value of `opt`. This kind of loop will not always run because if the first value we enter
is 'q' it will not enter the loop.

Here is another example using another kind of loop called a 'do' or 'do while'. This kind of
loop will always run at least 1 time.
```C#
int num = 0;
do 
{
    bool isValid = int.TryParse(Console.ReadLine());
} while (isValid);
```
This loop will continue to get input from the console and attempt to parse it into an int 
until the user enters a valid int.

Sometimes in our program we want to go through each item in a list. For this the best loop
to use is the 'foreach' loop. It has a very simple and easy to understand syntax. The 
example below will print out each fruit in the list to the console.
```C#
List<string> fruit = { "Apple", "Orange", "Banana", "Tomato", "Kiwi", "Grapefruit" };

foreach (string f in fruit)
{
    Console.WriteLine(f);
}
```

The 'foreach' is great for going through lists but has no way of keeping track of the index
of the item you are at or skipping over items. This example will loop through a list to find
the index of the largest number in the list.
```C#
List<int> list = { 4, 32, 1, 0, 18, 25 };
int max = 0,
    maxIndex;

for (int i = 0; i < list.Count; i++)
{
    if (list[i] > max)
    {
        max = list[i];
        maxIndex = i;
    }
}
Console.WriteLine($"The index of the largest number is {maxIndex}");
```
