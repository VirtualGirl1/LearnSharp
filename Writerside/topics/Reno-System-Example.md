# Reno System Example

Now that we know about enums and classes, it's time for something more complex. You're going to 
create a simple app to design rooms. The user can create a room and add walls and openings. You
don't need to display the layout, but you should display information about the room. You will
also need to validate so that the walls follow the rules laid out below.

A note about `ToString()` methods: We haven't gone over it yet but there is a special way of 
declaring this method: `public override string ToString()`.

## Setup 

0q1
This project is a little different as you'll use 2 projects, a class library and a console app.
First you need to create a dotnet Solution, this is a collection of projects that work together.
This command will create a new solution called 'RenoSystem'.
```Shell
dotnet new sln --name RenoSystem
```

Now that you have your solution file, you can create your projects. These commands will create a
console app project called 'RenoSystem' that will be the main part of your app and the second will
create a class library project called 'RenoLib' that will hold all your classes for the system.
```Shell
dotnet new console --name RenoSystem
dotnet new classlib --name RenoLib
```
Finally, you need to link the 2 projects so that you can access your classes in `RenoLib` from 
`RenoSystem`. This next command will add a reference in `RenoSystem` to `RenoLib`.
```Shell
dotnet add RenoSystem/RenoSystem.csproj reference RenoLib/RenoLib.csproj
```

## Project

Now that your solution has successfully been set up, you can start coding. Your project must have the 
following enums:
 - OpeningType
 - FlooringType
 - Color

The `RenoLib` project must also have the following classes

![](RenoSys.png)

## Here's some rules for the system for when you create the classes:

Opening:
 - Width and Height must be positive and greater than 50cm
 - Edging can be 0 but must be positive
 - Edging is included in the Area
 - `ToString()` should be formatted: "Height, Width, Edging, OpeningType"

Wall:
 - Width and Height must be positive and greater than 50cm
 - A walls opening cannot be greater than 80% of the walls area
 - `ToString()` should be formatted: "Height, Width, Color, Opening"

Room:
 - Must have at least 3 walls
 - Adding walls must use the `AddWall()` method
 - `ToString()` should be formatted: "Name, Flooring, Walls"

Feel free to add any other methods for utility.
