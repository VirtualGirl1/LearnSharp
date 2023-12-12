# Error handling and Null

In the previous exercise we worked under the assumption that the user would enter
valid data, but this is almost never the case in the real world, people make typos
or write 'one thousand' instead of 1000. So let's add some checks to make sure our
program doesn't crash.

There's 2 ways of solving this problem. First we can let the program throw an exception
and catch it if an invalid number is entered. The other is to replace `double.Parse()`
with `double.TryParse()` and check the return value. `double.TryParse()` returns an 
optional value so if it fails to convert to the number it will return `null`.

With both methods we'll need to add a new bool variable called `isVaid`. Your variable
declarations should now look like this:
```C#
double left, right, result;
char operation;
bool isValid;
```
We need this because we will use a loop to continuously prompt for the number until a 
valid number is entered.

Now let's try the first method with exception handling.
```C#
// old code
// Console.Write("Enter left number: ");
// left = double.Parse(Console.ReadLine());
isValid = false;
while (!isValid)
{
    try 
    {
        Console.Write("Enter left number: ");
        left = double.Parse(Console.ReadLine());
        isValid = true;
    }
    catch (Exception err) 
    {
        Console.WriteLine("That's not a number, please try again");
    }
}
```
Let's start from the top. We create a while loop that will run as long as `isValid` is
not true, we then use the try/catch block. This block will try to run the code in 'try'
until an error occurs and an exception is thrown. If no exceptions are thrown it sets
`isValid` to true and skips over the 'catch' block. If the user enters an invalid number
that will result in an exception being thrown. It will go straight to the 'catch' block
and run the code in there. 


The second way of doing this is using `double.TryParse()`, which will return null if
it can't parse the string. In this case we will also need to update our variables.
```C#
double? left, right;
double result;
```
We use the `?` to make `left` and `right` nullable, or optional. Result doesn't need
to be optional, so we keep it as `double`. Now that we've updated our variables we 
can try method 2.
```C#
isValid = false;
while (!isValid) 
{
    left = double.TryParse(Console.ReadLine());
    if (left.HasValue)
    {
        isValid = true;
    }
}
```
This method is much simpler as you can see. All we need to do after parsing the string
is to check if it has a value with the `double?.HasValue` property and if it does set
`isValid` to true.
