# Creating a New Project

Now that we have everything installed and setup we can create our first project. In
the explorer tab you should see a button labeled "Create .NET Project". After a short
wait a dropdown list will appear with a list of project templates we can use, right now
we just need the 'Console App' template. Select this option and give it the name "HelloWorld".

For those more comfortable using the command line can use the following command.
```Shell
dotnet new console
```
Note that this will name the project to whatever folder you are in. So if you are in
your Documents folder your project will be Documents.

Your newly created project should look like this in vs code

![startProject.png](startProject.png)

All our code will be in `Program.cs` or any other `.cs` file we add. Open up `Program.cs` 
and you should see the follow line of code
```C#
// See https://aka.ms/new-console-template for more information
Console.WriteLine("Hello, World!");
```

Right now we have a runnable program so let's run it and see what happens. Go to run -> 
Run Without Debugging or press Ctrl + F5. After a few seconds you should see the following
in vs codes integrated terminal

![startPrint.png](startPrint.png)