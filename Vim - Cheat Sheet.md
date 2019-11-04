# Mastering Vim Usage
## The Basics

Vim is apparently a text editor unlike any other. It's been said many times over that if a person invests time into truly learning and mastering Vim, it will be well worth it.

This shall be my first actual attempt at trying to learn Vim. Below I will randomly write jiberish or what have you to just practice with using this software.

## Two Modes of Vim
In Vim, we have two specific modes. **Command Mode** and **Insert Mode**.

To enter into **INSERT MODE** all we have to do is press the **```'i'```** key while _in_ command mode and Vim will put us into Insert Mode, which we can see by the "-- INSERT --"
at the bottom left of the screen.

To head back into **COMMAND MODE** once we're in _Insert Mode_ all we have to do is press the **```ESC```** key. This key _CAN_ be changed if desired in the **.vimrc** config file.

## Navigating in Vim
We _could_ use the arrow keys to navigate Vim, but there's a much better and much more recommended way to navigate and that's with the hot keys.

They are as follows:<br>
```h``` = Left one character.<br>
```j``` = Down one line.<br>
```k``` = Up one line.<br>
```l``` = Right one character.<br>
```0``` = Moves cursor to the **beginning of the line**.<br>
```$``` = Moves cursor to the **end of the line**.<br>
```w``` = Forward one word.<br>
```b``` = Backwards one word.<br>
```G``` = Move to **END OF LINE**.<br>
```gg``` = Move to **BEGINNING OF LINE**.<br>
``` `(backtick)``` = Move to the **last edit**.<br>

Prefacing a movement command with a number will execute that movement multiple times.<br> If we want to move up six lines, enter '6k' and the cursor will move up six times.<br>
If we want to move over five words, enter '5w'.<br>
If we want to move 10 words back, use '10b'.

## Writing (Saving) & Quitting
In order to write (save) a file to disk we just simply have to exit **INSERT MODE** with the escape key and then activate the special command key which is "```:```".
We then press "```w```" for _write_ and "```q```" for _quit_.<br>
These two letter commands can be combined into one command before pressing 'enter/return' to _save_ and _quit_ in one shot.

If in the event that we wish to just simply _quit_ Vim **WITHOUT** saving, then we can simply enter in "```:q!```". The **!** (exclamation mark) basically tells Vim to carry out the quit action even if the file fails a 'save-check' passed on the file.

## Text Editing - Deletion
It's one thing to delete text while we're in **INSERT MODE**, but we can also delete text from the **COMMAND MODE** if we desired.

We do this by navigating to any letter we want and simply pressing '```x```'.

## Text Editing - Insertion
Text editing simply requires that you enter **INSERT MODE**. We've already covered how to do that, but there's some other methods to do this that can help speed things up and save some keystrokes.

### Inserting - While in Command Mode
The '```i```' key will put the cursor **before the current position.**

### Appending
The '```a```' key will put the cursor **after the current position.**

### Open Commands
The '```o```' key puts the cursor **below the line.**<br>
And capital '```O```' puts the cursor **above the line.**

***

## Operators and Motions, Counts and Combining Them
Commands are where the true power and efficiency come into Vim.<br>
It takes time to start using them, but they all follow a similar pattern.<br>
**It's a good idea to learn how commands work, not memorize commands.**<br>
Commands are broken down into these parts.

 1. Operator
 2. Numbers
 3. Motions

When we put these together, the Vim command will look something like this:<br>
```
[OPERATOR][NUMBER][MOTION]
```

### Operators
Operators are actions. These are like the **verbs** of a sentence when _"speaking Vim"_.<br>
Here's a list of common operators:<br>
 ```d``` = Delete (acts like a 'cut' command though)<br>
 ```c``` - Change<br>
 ```y``` - Yank<br>
 ```p``` - Insert last deleted text after cursor.<br>
 ```r``` - Replace

### Motions
Motions provide **context** to your Operators. These execute the action in a particular way.
Here's a list of common motions:<br>
 ```w``` - Until the start of the next word, **EXCLUDING** it's first character.<br>
 ```e``` - To the end of the current word, **INCLUDING** the last character.<br>
 ```$``` - To the end of the line, **INCLUDING** the last character.

 Some Additional Motions:<br>
 ```w``` - Forward by one word.<br>
 ```b``` - Backward by one word.<br>
 ```)``` - Beginning of next sentence.<br>
 ```(``` - Beginning of current sentence.<br>
 ```}``` - Beginning of next paragraph.<br>
 ```{``` - Beginning of current paragraph.<br>
 ```]``` - Beginning of next section.<br>
 ```[``` - Beginning of current section.<br>
 ```H``` - Top line of screen.<br>
 ```L``` - Last line of screen.<br>

### Counts
Counts are optional and simply let you put a multiplier to your command and motion. We can see how these work in the examples below. But remember, the actual order of these power commands are:
```
[OPERATION] => [NUMBER] => [MOTION]
```

# Deleting Words
Navigating to the beginning of a word in the editor and entering the command '```dw```' will delete a word from the point the cursor is until the end of the word.<br>
_Note: This does not include final punctuation, such as period or comma after the world._

### Deleting to the End of a Line
The command '```d$```' will delete everything until the end of the line, from the point your cursor is currently at.

_Count Example:_ If we were to run the command '```d2$```' it will run the inputted command twice and therefore in this situation, _delete **TWO** lines after the cursor position._

_Note: Remember, as stated above, the operational order is: 
```
[OPERATOR][NUMBER][MOTION]
```

Deleting a line is a super common task. Vim has a shortcut built in for this. For example, to quickly delete a line you can always just do '```dd```' instead.

### Deleteing Four Words - An Example...
A common command for deleting four words is '```d4w```'.
Here we have 'd' for the **delete* command, multiplied by 4 and applied to **words** via the '```w```'.

# Undo'ing & Redo'ing
### The Undo Command
With all these commands, there's a good chance you might mess up once or twice. You can quickly undo a command with: '```u```'.<br>
_Note that Vim has multiple levels of undo. I have custom set it for 500 levels._

### The Redo Command
If we want to 'redo' or 'undo and undo' command, we can use:
```
CTRL+r
```

***

### Quick Page Navigation
Scrolling doesn't really exist in a terminal. So if we have to have a long that we're editing, it might get real boring navigating with the arrow keys or '```h, k, l, j```'.

#### Here's some quicker ways of moving about (in Command Mode):
```:G``` - Move to the **BOTTOM** of a File.<br>
```:gg``` - Move to the **START** of a File.

```:CTRL+g``` - View current page line.<br>
```:123+G``` - Jump to a specific line.

# Searching
We're pretty used to doing CTRL+F to jump around a page. Vim is actually really similar to this - except it's a _command_. By this point, we should be understanding that _everything_ is a command action.

### Seaching a Page After the Cursor Position
```
:/[search term]
```

### Searching a Page Before the Current Position
```
:?[serach term]
```

### Clearing Search Result Highlighting
```
:noh
```

### Go to Next or Previous Match
```n``` - Navigate to the next search match.<br>
```N``` - Navigate to the prevoius search match.

## Matching Search
By this point, we can jump around the page and search things, but it's still slow to locate various things in a file. In Vim, you can jump around based on opening and closing matching brackets.

For example, say we have:

```
function hippopotamus() {
    // insert 1 millions lines of code here.
}
```

If we go navigate to '{' and hit the following key **'```%```'**, we'll jump to it's matching counter part.

This is insanely useful for quickly jumping around functions.<br>
This works on the following:<br>
* ( and )<br>
* [ and ]<br>
* { and }<br>

## Search & Replace
Searching and jumping around the page is one thing, but maybe you want to change all instances of 'cat' to the 'dog'. This can very easily be done in Vim.

### Find and Replace
```
:s/[searchTerm]/[replaceTerm]
```

### Find and Replace All
_To replace all instances, you need to make the find and replace global._<br>
Here's how:<br>
```
:s/[searchTerm]/[replaceTerm]/g
```
Think of the above '```g```' as in **GLOBAL**.

_**Note:** This can get infinitely more complex, as we can utilize this with **regular expression** find and replaces, replace only on **certain lines, sections** and more._

## Copying & Pasting
We know how to delete text. The last text we deleted is stored in the buffer ready to be pasted back into the document. So if we've run '```dd```' and deleted an entire line, we can now hit '```p```' or '```P```' to paste it back into the document! This goes for single lines, multiple lines, and even entire documents.

Want to select text? In command mode, hit '```v```' and we're able to move the cursor usign the arror keys or the standard movement keys (```h, k, j, l```) to highlight text.<br>

This is pretty easy, but can be slow. If we want to copy entire lines at a time, we use ```'V' (capital-v)``` instead of ```'v' (lowercase-v)``` and we'll highlight entire lines at a time.
Again, we can use the movement keys to highlight additional lines.

Once we've highlighted what we want, hit '```y```' and we will "yank" the text into the buffer to be pasted later.<br>

So a usual paste operation might look like this:<br>
Hit '```v```' to highlight some text.<br>
Then hit '```y```' to yank it into the buffer.<br>
Then move the cursor to where we want it, and use '```p```' in **command mode**.

**Summary of Copy/Paste Commands:**<br>
```v``` - highlight one **character** at a time (lowercase 'v').<br>
```V``` - highlight one **line** at a time (uppercase 'v').<br>
```CTRL+v``` - highlight by columns.<br>
```p``` - paste text **after** the current line (lowercase 'p').<br>
```P``` - paste text **ON** the current line (uppercase 'p').<br>
```y``` - yank text into the copy buffer.<br>

# Executing External Commands
This creeps right out of the area of getting started with Vim to the intermediate parts of it. With Vim, the commands aren't just limited to the Vim syntax/language of operators and motions.

You can execute external commands as you normally would from the command line inside of an editor. All you need to do is start the command with an _exclamation mark_ (```!```).

Here's an example to **list all files**:
```
:!ls -al
```

As we continue to learn more about Vim, we'll see how insanely powerful this will be. We can do things like write to other files, grab code from other files, paste into other files, and more. In a sense, it's like your own little Sublime Sidebar on steriods.

# Configuring Vim
Vim can also do things like syntax highlighting. By default, this usually isn't enabled. to enable it on a file, simply enter the following command:
```
:syntax on
```

This is kind of annoying to have to re-enter this on each file though. That's where **configuring Vim** comes in handy. All Vim installs come witha file in our **HOME DIRECTORY** called .vimrc. If it's not there, we can create one.

From the command line we'll now enter into this file for edit using Vim and force enable 'syntax on' by simply entering "syntax on".

_Note: I personally find 'syntax highlighing' very annoying when it's enabled while writing a markdown file. Therefore, I personally **WOULD** rather enter it on an individual file basis._

# Useful Tips & Tricks
By now we should be fairly comfortable with Vim on the command line. Here's some miscellaneous useful tips and tricks.

## Set Vim as the Default Command Line Editor
Nano is usually the default CLE in most systems. On Ubuntu or other Debian-based systems, we run this command to switch:<br>
```
sudo update-alternatives --config editor
```

## Set Vim as your Default Editor for Git
```
git config --global core.editor "vim"
```

# Plugins
Vim also has the abilities to allow third-party to write plugins into the editor.<br>
For example, NERD Tree will essentially simulate a sidebar for the editor.
<https://github.com/scrooloose/nerdtree>


# Some Vim Commands to Memorize
```d``` - starts the delete operation.<br>
```dw``` - delete a word.<br>
```d0``` - delete to the beginning of the line.<br>
```d$``` - delete to the end of the line.<br>
```dgg``` - delete from cursor to the beginning of the file.<br>
```dG``` - delete from cursor to the end of the file.<br>
```u``` - undo last operation.<br>
```CTRL+r``` - undo last undo.<br>