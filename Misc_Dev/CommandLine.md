# Using the Command Line / Terminals
**Read this article for a more in-depth understanding: [Command Line Introduction](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line#welcome_to_the_terminal)**

Very often, you'll see programmers using the command line to run programs and/or execute different actions on their computers. One common use of the command line is to navigate the files and folders of a computer without the use of the graphical user interface.
- Graphical User Interface (GUI) - a way to interact with the computer by physically seeing the files and folders (i.e. image of a folder)
  
With the command line, we don't exactly get to see images of the files and folders. The only thing we get is text.

## Command Line vs. Terminal
You will likely hear folks refer to a "terminal" in addition to the command line. The article provided above has a pretty good explanation of the differences between the two (just search for 'Side Note: what's the difference between a command line and a terminal?' and it should lead you to that section) — but the terminal is essentially the window that the command line sits inside of.

## Terminals in Different Operating Systems
See [this](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line#how_do_you_access_the_terminal) section of the article for more information on how to open up terminals in different systems. Linux/Unix and MacOS systems tend to be easier to work with, but it is possible to get things up and running on Windows machines.

## Commands
When in a terminal, we are able to execute commands. Commands are used to execute a specific action, whether it be for navigating, creating, deleting, or seeing what's in a folder.
  
Before we get into commands, you have to understand one simple thing: the location of a file or folder can be typed by using the folder names and '/'. For instance, here is the path to get to a file *example.txt* that is within a folder *examples*
```
examples/example.txt
```

Now, here are some common commands:
  
`cd <file route>` 
- This allows us to change folder location in the terminal.
- cd stands for *change directory*. Directory is another word we use for a folder.
- The route passed in depends on your current location in the folders.
- `cd ~` brings you back to the home directory.
- `cd ..` moves you 1 directory up. It's how you go backwards.

`ls`
- This allows you to see what files and folders are within a folder.
- It is useful when you need to get into a folder, but you forgot it's name or something similar.
  
`touch <file name>`
- This allows us to create a file along with it's extension (i.e. .js, .rb, .jpeg).
- This file will be created based on your location in the folders.

`mkdir <folder name>`
- This allows us to create a folder/directory.
- mkdir stands for *make directory*.
  
`rm <file or folder name>`
- This deletes a file or folder.
- Be careful when using this command.
  
There are many more commands: [Click here](https://www.git-tower.com/blog/command-line-cheat-sheet/) if you want to see a cheat sheet of them.
