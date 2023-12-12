# Getters and Setters

In previous examples with classes you might have noticed the properties with { get; set; } and
wonder what it is for. These are methods to get and set the value of a property. In the case of 
{ get; set; } we don't need to define any code as the c# runtime does that for us. Where it 
becomes useful is when you want to restrict the values that it can be set to.

Here is an example for a rectangle where we don't want the sides to be negative:
```C#
private int _width;
public int Width
{
    get
    {
        return _width;
    }
    set
    {
        if (value <= 0)
        {
            throw new Exception("Width Cannot be negative");
        }
        _width = value;
    }
}
```
The first part of this is declaring a private field called `_width`. This is what we use to actually
store our width. In the get all we need to do is return `_width`. In the set however, we need to 
check the value. We don't want width to be 0 or less, so we check it and if it is, we throw an 
exception, otherwise we set `_width` to the value.

But properties don't need to store any data. We can have properties that only get data, like a 
property that returns the area of the rectangle.
```C#
public int Area
{
    get
    {
        return Width * Height;
    }
}
```

Lastly, sometimes we want a property to only be set by the class but still be accessible from outside.
In this case we can use the visibility modifiers to change where it can be accessed from. Here is an
example of a class that has a list that can only be manipulated by the class:
```C#
class ShoppingCart
{
    public List<ShoppingItem> Items { get; private set; }
}
```
Now only methods that are a part of `ShoppingCart` can set `Items`.
