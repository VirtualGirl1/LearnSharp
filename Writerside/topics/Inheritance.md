# Inheritance

One common problem may developers face is constantly rewriting code. With OOP we don't 
have to worry about this with classes. When you define a class that class can be 
extended with other classes using inheritance. This gives the child class access to all
the parent classes public or protected fields and methods.

Say we want a class that describes a teacher. We can create a teacher class that inherits
from `Person`.
```C#
public class Teacher : Person
{
    public string Subject { get; set; }
    public int YearsTeaching { get; set; }
    
    public Teacher(string firstName, string LastName,
            string subject, int yearsExp)
    {
        FirstName = firstName;
        LastName = lastName; 
        Subject = subject;
        YearsTeaching = yearsExp;
    }
};
```
Notice above how we're able to use the properties from Person. However, we can't access any 
fields we set as private, such as `_height`. This also means that we can't actually set `Height`
because we set its setter to private. We can fix this using the `protected` keyword.

By defining the setter as protected instead of clear any class that inherits from`Person` can 
access the setter, but it still cannot be accessed from outside the class.