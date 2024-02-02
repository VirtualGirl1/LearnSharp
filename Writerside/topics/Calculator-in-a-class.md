# Calculator in a Class

Now that we know what a class is let's try and use one. We'll use the calculator app that we 
built in the last section. In your project folder create a new file called `Calculator.cs` 
and add the following code.
```C#
class Calculator 
{
    
    public Calculator() 
    {
    }
};
```
Now we have an empty class that we can use for our calculator app. To keep the code clean let's 
create a new method to get our left and right numbers.
```C#
public static double GetNumber()
{
    bool isValid = false;
    double number;
    
    while (!isValid)
    {
        Console.Write("Please enter a number: ");
        isValid = double.TryParse(Console.ReadLine(), number);
    }
    
    return number.Value;
}
```
This method is pretty close to what we have in the previous example. The main difference is the return
part. This lets us pass the number back to the area that called it. We could just return `number` because
we have already made sure that it is not null, but we can add this as an extra check. If number is somehow
still null it will fail to read `number.Value` and not be able to return.

Now let's add the code for the operator.
```C#
public static char GetOperation()
{
    bool isValid = false;
    string validOperations = "+-*/";
    char operation = '\0';
    
    while (!isValid) 
    {
        Console.Write("Please enter an operation: ");
        operation = Console.ReadLine()[0];
        if (validOperations.Contains(operation))
        {
            isValid = true;
        }
    }
    
    return operation;
}
```
Here we also add a little validation. Because we have a set amount of operation we need some way to 
check. Here we can use a string to hold a list of valid operation chars, we then check if it 
contains the entered operation and set `isValid` to true if it does.

See how both of the methods above are marked as static. This means we don't need an instance of the
class to use these methods. We can directly call them like `Calculator.GetNumber();`.

Now that we have these let's put it all together. We'll create a new method that will run until we 
close the program with Ctrl+C. Let's call this method `Run()`.
```C#
public void Run()
{
    double left, right, result;
    char operation;
    
    while(true) 
    {
        left = Calculator.GetNumber();
        right = Calculator.GetNumber();
        operation = Calculator.GetOperation();
        
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
    }
}
```
Now with the working calculator class all we need to do is call it in our `Program.cs`.
```C#
Calculator calc = new Calculator();
calc.Run();
```
The first line here creates a new instance of the class that we can use. The second line calls
the `Run()` method to start the calculator.


## Bonus Challenge

Now that you have your working calculator try adding methods for each of the operations that will perform 
that operation and return the result.
