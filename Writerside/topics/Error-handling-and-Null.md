# Error handling and Null

In the previous exercise we worked under the assumption that the user would enter
valid data, but this is almost never the case in the real world, people make typos
or write 'one thousand' instead of 1000. So let's add some checks to make sure our
program doesn't crash.

There's 2 ways of solving this problem. First we can let the program throw an exception
and catch it if an invalid number is entered. The other is to replace `double.Parse()`
with `double.TryParse()` and check the return value. `double.TryParse()` returns an 
optional value so if it fails to convert to the number it will return `null`.

Here is using the First method:
```C#

```