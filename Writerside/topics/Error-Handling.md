# Error Handling

Error handling is a very important part of any programmer experience. 
Here we will quickly cover the basics before going into more depth 
later on.

The fundamentals of error handling in C# is the try catch block
```C#
try
{
    // do something that could cause an error
}
catch(Exception err)
{
    // handle the error
}
```
First the program will 'try' to do whatever is in the try block. If
it all runs it will move on to code after the catch, but if an error 
occurs it will send the program to the start of the catch block.
here you set behaviour that might run code to fix what ever went 
wrong or simply exit the program.

Errors are not always something that will cause a program to crash,
however. Say that we have a function that calculates the area of a rectangle
```C#
int Area(int width, int height) 
{
    if (width < 0 || height < 0)
    {
        throw new Exception("Sides cannot be negative");
    }
    
    return width * height;
}
```

