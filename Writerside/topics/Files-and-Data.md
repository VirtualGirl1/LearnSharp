# Files and Data

One of the most important features of software is being able to store data. Without this we would 
not be able to change settings, create notes, or even create programs. Most often we use files to
store data for our programs. In this part we'll go over some simple operations with storing data in text files with multiple 
formats.

## Reading Text Files

Let's start by creating a file to store data. Create a file and add a few lines to it. Now that 
we have this we can start coding.

First we need to create a `StreamReader` that will handle all the reading of our file.
```C#
StreamReader reader = File.OpenText("Path to your file");
```

Now that we have our reader lets print out the content of our file to the console.
```C#
string line;
while ( (line = reader.ReadLine()) != null)
{
    Console.WriteLine(line);
}
```
Here we use `ReadLine()` to get the next line in the text file. If we have reached the end of the
file then `ReadLine()` will return `null`.

## Writing Files

Now that we can read from the file let's write to a file. For this we can use `StreamWriter` to
write our data. We can also have the program create the file for us.
```C#
StreamWriter writer = File.CreateText("data.txt");

string? line;
while ( (line = Console.ReadLine()) != "quit")
{
    if (line != null)
    {
        writer.WriteLine(line);
    }
}
```
Here we will continue to get input from the user until they enter 'quit' and write it to the file.
However, we shouldn't write empty data to the file, so we need to check if the user entered a value
before we write it.
