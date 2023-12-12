# Parsing

In the previous section we showed how to read data from the console. but we
only read it into a string. What do we do when we want to read other types like numbers

Each data type in C# has 2 methods for this, `Parse()` and `TryParse()`. These will
read a string and convert it into the desired data type. However, the main difference
between them is that if `Parse()` cannot read it, it will throw an exception. `TryParse()`
will return null if it can't read it.

```C#
var i = int.Parse("1");
var d = double.Parse("1.5");
var b = bool.Parse("true");
```

When you create your own classes you can also implement these methods to parse custom 
data types.