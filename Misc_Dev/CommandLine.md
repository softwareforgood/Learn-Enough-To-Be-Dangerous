# Command Line
* Read this article for a more in-depth understanding: [Command Line Introduction](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line#basic_built-in_terminal_commands)
  
One of the main purposes of the command line is to navigate the files and folders of a computer without the use of the graphical user interface.
- Graphical User Interface (GUI) - a way to interact with the computer by physically seeing the files and folders (i.e. image of a folder)
  
With the command line, we don't physically see images of the files and folders. The only thing we get is text.

## Terminal
Another name for the command line is the terminal. Depending on your operating system, the terminals that are available differs. Each have their pros and cons, and you should research more into them to better understand each one.

## Commands
When in a terminal/command line, we are able to execute commands. Commands are used to execute a specific action, whether it be for navigating, creating, deleting, or seeing what's in a folder.
  
Before we get into commands, you have to understand one simple thing: the location of a file or folder can be typed by using the folder names and '/'. For instance, here is the route to get to a file *example.txt* that is within a folder *examples*
```
examples/example.txt
```

Now, here are some common commands:
  
`cd <file route>` 
- this allows us to change folder location in the terminal.
- cd stands for *change directory*. Directory is another word we use for a folder.
- The route passed in depends on your current location in the folders.
- `cd ~` brings you back to the home directory
- `cd ..` moves you 1 directory up. It's how you go backwards.

`ls`
- this allows you to see what files and folders are within a folder.
- it is useful when you need to get into a folder, but you forgot it's name or something similar.
  
`touch <file name>`
- this allows us to create a file along with it's extension (i.e. .js, .rb, .jpeg)
- this file will be created based on your location in the folders

`mkdir <folder name>`
- this allows us to create a folder/directory
- mkdir stands for *make directory*
  
`rm <file or folder name>`
- this deletes a file or folder
- be careful when using this command
  
There are many more commands: [Click here](https://www.git-tower.com/blog/command-line-cheat-sheet/) if you want to see a cheat sheet of them.

# Terminals Types
There are various terminals and they go by so many names. Here are some names that the terminal can be called:
- terminal
- command line
- command line interface
- shell
- prompt
- console
  
## Terminals for Mac, Linux, and PC (Windows)
### Mac
- macOS

### Linux
- Ubuntu

### PC
- Powershell
- Command Prompt