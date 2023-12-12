# Calculator Project

Now that we have our project template we can start coding. We don't need the code 
generated for us, so you can go ahead and delete everything in the `Program.cs` file.

We'll learn some basic concepts of programming by creating a simple calculator that
takes in 2 numbers and asks which operation to perform and print the result. 

We can start by declaring 4 variables.
```C#
double left, right, result;
char operation;
```
First we define 3 variable of the type double. Doubles are a floating point type, meaning
they can have a decimal point. Will use these for the left and right of the operation and 
the result that we want to print. Then we define a char that will represent the operation 
we want to perform (+, -, *, /).


Now that we have our variables defined we can ask the user for their values.
```C#
Console.Write("Enter left number: ");
left = double.Parse(Console.ReadLine());

Console.Write("Enter right number: ");
right = double.Parse(Console.ReadLine());

Console.Write("Enter the operation you want to perform: ");
operation = Console.ReadLine[0];
```
That's a lot more code than before so let's go through it. The first line writes out to
prompt the user to enter something. Notice how we use `Console.Write()` instead of 
`Console.WriteLine()` like in the template. The difference here is that `Console.WriteLine` 
will create a new line after it prints out while `Console.Write()` won't.

Next is a bit more complicated so lets break it down. `Console.ReadLine()` will wait for the 
user to press the `Enter` key and read whatever was written. For this example we'll assume 
that the use has entered a valid number. `double.Parse()` will read the string returned by 
`Console.ReadLine()` and convert it to a double type. Again we'll assume the user has entered 
a valid number otherwise the program will crash. Last is `left = double.Parse(Console.ReadLine())`.
Here we take the number that `double.Parse()` returns and assign it to the variable `left`.
We then do the same thing for `right`.

Lastly is getting the operation. Here we use `Console.ReadLine()` but we don't do any parsing.
This is because all a string is, is a list of characters. Because of this all we need to do is
read the first letter that was entered. We can do this using `[i]` where `i` is the index of the
character you want to get. Remember that lists in computing always starts at 0.


Now that we have our variables we can perform our operations. We can use an if/else block to
do this but since operation is a char we can use a different statement called a `switch`. 
```C#
switch (operation) 
{
    case '+':
        result = left + right;
        break;
    case '-':
        result = left - right;
        break;
    case '*':
        result = left * right;
        break;
    case '/':
        result = left / right;
        break;
    default:
        result = 0;
}
```
The `switch` takes an integer value as its argument. We can use char as the argument because
char is just a single byte int. Then based on the value of `operation` switch will send the 
program to the matching `case`. We use the `default` just in case one of the cases was not run.
Lastly is the `break` in each `case`. We need this to exit out of the switch statement, otherwise
the program will run through each case regardless of the value of `operation`.

The last bit of code for this example is to print the `result`.
```C#
Console.WriteLine($"Result is {result}");
```
Pretty simple, but you might notice something different about this print statement, the '$' 
before the quotation marks. We use this to create a string literal. This allows us
to reference variables in '{}'.

In the end we are left with the following code.
```C#
double left, right, result;
char operation;

Console.Write("Enter left number: ");
left = double.Parse(Console.ReadLine());

Console.Write("Enter right number: ");
right = double.Parse(Console.ReadLine());

Console.Write("Enter the operation you want to perform: ");
operation = Console.ReadLine[0];

switch (operation)
{
    case '+':
        result = left + right;
        break;
    case '-':
        result = left - right;
        break;
    case '*':
        result = left * right;
        break;
    case '/':
        result = left / right;
        break;
    default:
        result = 0;
}

Console.WriteLine($"Result is {result}");
```