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

## Make sure your script file is executable

Follow the [instructions for the `hello.sh` script](shell-scripts.md) to ensure that `journal.sh` is executable.

## Let's do this

Use the `pwd` command to confirm that you're in your `scripts` directory. Now type the following at the prompt:

`./journal.sh`

Hit `Enter/return`. What do you see?

## Running your script from the GUI

Follow the [instructions for the `hello.sh` script](shell-scripts.md) to run `journal.sh` by double-clicking it in the GUI.


