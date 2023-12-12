# Enumeration

Enumerations are a way of giving names to specific number. 

Say we have a function that sets our background color. This function takes a number representing
the color, 0 for clear, 1 for black, 2 for white, 3 for red and so on. It's hard to memorize these
relationships when you are working on large projects, so we use enumerations. Here is a Color enum:
```C#
enum Color
{
    Clear,
    Black,
    White,
    Red
};
```
Notice how we don't assign any numbers. That's because enums will do that for us, starting with the
first option as 0 and increase with each option. If you need to you can define specific values for
each option in an enum.


