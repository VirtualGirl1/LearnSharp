# C# Basics

The simplest thing you can do with any language is take arguments and write to the console

Here is an example of a simple program that asks for your name and greets you

```C#
Console.Write("Enter your name please: ");
string name = Console.ReadLine();
Console.WriteLine($"Hello {name}}");
```

Line 1 prompts the user for their name and the user can write their name on the same line.

Line 2 will wait for the user to press 'Enter' and read whatever the user wrote in the name variable

line 3 has the most going on. First we see that the function to write is different. Instead of using 
`Console.Write()` we've used `Console.WriteLine()`. The difference between these 2 functions is that
`Console.WriteLine()` will always print a newline character `\n` at the end so that any text written 
after will be on a separate line.

Second our string is started with the `$` symbol. This symbol declares a string a literal meaning we can
use variables in it. Without this line 3 would write "hello {name}" and not the name you gave it. The last
part is the use of `{}`, this allows us to name variables in our string.
