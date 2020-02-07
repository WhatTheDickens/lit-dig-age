[&lt;&lt; Previous](shell-scripts.md)

# A shell script for creating journal files

Right now, every time you want to add to your markdown journal, you need to do the following:

- Open VS Code
- Open a new file and give it the name `journal_yyyy-mm-dd.md` where `yyyy-mm-dd` represents that day's actual date
- Save it to `/Users/yourusername/Documents/journal` on your computer's hard drive, where `yourusername` is your actual username

That's kind of a pain. What if we could automate this process by writing a couple of lines of executable code?

Now that you know how to write a shell script, you can do this quite easily.

## Write the script

Create a new file inside your `~/scripts` folder named `journal.sh`.

Copy-paste the following into your `journal.sh` file.

```
#!/bin/bash

touch ~/Documents/journal/journal_$( date '+%Y-%m-%d_%H-%M' ).md
code ~/Documents/journal/journal_$( date '+%Y-%m-%d_%H-%M' ).md
```

(Because the commands here are kind of finicky, we recommend copy-pasting for this script, rather than trying to re-type and get it exactly right.)

Save the file.

## Deep breath

What's here?

As in our [hello.sh](shell-scripts.md) script, the first line, `#!/bin/bash`, is like a hand-wave to your operating system, saying "Hey, look at me, I'm a bash script!"

The second line, beginning with `touch`, tells your computer to create a file whose name begins `journal_` and ends with the current year (`%Y`), month (`%m`), day (`%d`), hour (`%H`), and minute (`%M`), followed by the `.md` extension. The file is to be created in your `journal` folder, which is inside `Documents`.

(Hey, as long as we're automating, why not add the precise time, down to the hour and minute, right? This way if we accidentally run the script twice in one day, our new file won't overwrite our old one.)

The third line, beginning with `code`, tells your computer to open the file that the first line just created.

Each of these lines is its own command. When the script runs, the commands will be executed in sequence: (1) Create the file (2) Open the file in VS Code.

Wondering about the `~/` in the file path contained in each line of code? Remember, it's just shorthand for `/Users/yourusername`. 

## Make your script executable

If you're a Windows user, you should now be able to go to `/Users/yourusername/scripts` (aka `~/scripts`) in your GUI and double-click `journal.sh` to make the code run. If it runs successfully, you'll see a new, empty file open up in VS Code with the correct file name.

If you're a Mac user, you may have to go through the same extra steps covered in the [previous](shell-scripts.md) lesson. They're repeated below so you don't have to leave this page.

### Mac user step one

You may need to tell your Mac to treat your `.sh` file as executable code rather than a file you want to open and read. To do that, click once on `journal.sh`, go to File > Get Info (or simply type `command-I`), and use the dropdown near the bottom of the Info box to select `Terminal.app` as the application that should be used to open the file.

![Get Info](../images/get_info.png)

### Mac user step two

You may need to alter the file's permissions in order to run it. To do this, go back to your terminal window and make sure you're in your `~/scripts` directory. To see if you are, type 

`pwd`

Hit `Enter`. If your terminal answers with `/Users/yourusername/scripts`, you're good to go. If it doesn't, then at the prompt type

`cd ~/scripts`

followed by `Enter`, and, try the `pwd` command again.

If you now enter the `ls` command at the prompt (`$`), you should see your `journal.sh` file listed.

Now type or copy-paste this at the prompt (`$`):

```
chmod 700 journal.sh
```
Hit `Enter` (aka, on some keyboards, `return`). You're done!

Now go back to `journal.sh` in the GUI and double-click it. If everything's working right, you should end up with a new, empty file in VS Code with the current date and time in the file name.

Type away in the file and save periodically as you would normally. Perhaps you should jot down a few notes in the file right now about what you just learned, and include a link to these instructions so you can find your way back to them easily.

[&lt;&lt; Previous](shell-scripts.md)


