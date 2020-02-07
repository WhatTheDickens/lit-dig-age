[Next &gt;&gt;](journal-script.md)

# Your first shell script

The terminal window that you've been using to talk directly to your computer's operating system is sometimes called a *shell*.

In this class, we're using a particular shell known as the *Bourne Again Shell*, or *Bash* for short.

A *shell script* is bit of code that can run in this shell. Instead of typing the code at the command line every time you want to use it, though, you can save this bit of code in a file. Once you've saved it in a file, one way you can make it run in the shell is to simply double-click it in your GUI, just as you would a file that you want to open. Clicking on a shell-script file doesn't simply open it, though; it runs the script, carrying out a task.

## Set-up

Before we write our shell script, let's create a new folder inside `/Users/yourusername` and call it `scripts`. It's nice to have a dedicated folder for any scripts you write. 

Open a terminal window, and at the prompt (`$`) type this:

`mkdir scripts`

Hit `Enter` (or `return`). This should land you back at the prompt. Now type

`code scripts`

Again, hit `Enter/return`. This should open up VS Code if it isn't already open, and show your new folder in the "Explorer" in the left navigation pane of your window.

Use `File > New File` from the VS Code menu or the `New File` icon that appears when you mouse over the folder name to create a new file inside your `scripts` folder. Name the file `hello.sh`.

You'll recall that the `.md` extension tells VS Code to interpret your plain text file as markdown, and that the `.html` extension tells it to interpret your plain text as html markup intended for display in a browser. The `.sh` extension lets VS Code (and your computer's operating system) know that you're writing a shell script.

Type the following into `hello.sh` *exactly* as you see it here, then save the file. We really do mean *exactly*. If you get anything wrong, your script won't run. (Sure, you could just copy-paste, but it's really worthwhile to give typing it a try. It will help you pay closer attention to what's in the file.)

```
#!/bin/bash

mkdir ~/hello
cd hello
echo "Hello World!" > hello_world.txt
code hello_world.txt
```

Save the file.

## Deep breath

Let's take a second to understand what we're doing here.

The first line, `#!/bin/bash`, is like a hand-wave to your operating system, saying "Hey, look at me, I'm a bash script!"

The next line, `mkdir ~/hello` tells your computer to create a directory (i.e., folder) named `hello` in your home folder. (`~/` is just useful shorthand for `/Users/yourusername` where `yourusername` is your actual username.)

The line after that says, "Switch to the folder `hello`."

The one after that says, "Print the text string 'Hello World!' and write it to a new file inside the current directory, naming that file `hello_world.txt`"

The final line says, "Open the file `hello_world.txt` in VS Code."

Each of these lines is its own command. When the script runs, the commands will be executed in sequence: (1) Make a new directory (2) Move into the new directory, (3) Print a string of text and write it to a new file, (4) Open the new file in VS Code.

We're almost ready to run this script. Just a few more steps.

## Make your script executable

If you're a Windows user, you should now be able to go to `/Users/yourusername/scripts` (aka `~/scripts`) in your GUI and double-click `hello.sh` to make the code run. If it runs successfully, you'll see your new file, `hello_world.txt` open up in VS Code. The contents of the file should read `Hello World!`

If you're a Mac user, you may have to take a couple of additional steps.

### Mac user step one

You may need to tell your Mac to treat your `.sh` file as executable code rather than a file you want to open and read. To do that, click once on `hello.sh`, go to File > Get Info (or simply type `command-I`), and use the dropdown near the bottom of the Info box to select `Terminal.app` as the application that should be used to open the file.

![Get Info](../images/get_info.png)

### Mac user step two

You may need to alter the file's permissions in order to run it. To do this, go back to your terminal window and make sure you're in your `~/scripts` directory. To see if you are, type 

`pwd`

Hit `Enter`. If your terminal answers with `/Users/yourusername/scripts`, you're good to go. If it doesn't, then at the prompt type

`cd ~/scripts`

followed by `Enter`, and, try the `pwd` command again.

If you now enter the `ls` command at the prompt (`$`), you should see your `hello.sh` file listed.

Now type or copy-paste this at the prompt (`$`):

```
chmod 700 hello.sh
```
Hit `Enter` (`return`). You're done!

Now go back to `hello.sh` in the GUI and double-click it. If everything's working right, you'll see your new file, `hello_world.txt` open up in VS Code.

[Next &gt;&gt;](journal-script.md)