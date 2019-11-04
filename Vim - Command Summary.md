# Vim - Command Summary Gist
## Modes
There are two modes in Vim. **Insert Mode** and **Command mode**.

In _insert mode_ (press '```i```') the keys function as you'd normally think and input the desired key as a normal word processor.

In _command mode_ (starts as default - ```ESC``` to leave _insert mode_) the keys are technically 'command keys' and many keys perform a specific command action.

***

## Vim Command Mode Navigation
```h``` - move cursor **left**.<br>
```l``` - move cursor **right**.<br>
```j``` - move cursor **up**.<br>
```k``` - move cursor **down**.<br>

```0 (zero)``` - move cursor to **beginning of line**.<br>
```$``` - move cursor to **end of line**.<br>

```w``` - move **forward one word**.<br>
```b``` - move **backwards one word**.<br>

```G``` - move cursor to **end of current LINE**.<br>
```gg``` - move cursor to **beginning of current LINE**.<br>

``` `(backtick)``` - move cursor to **last editing position**.

***

## Saving & Quitting
In **command mode**:<br>
```:w``` - write file.<br>
```:q``` - quit Vim.<br>
```:wq``` - write file & quit Vim.<br>
```:!q``` - quit Vim without saving.<br>

***

## Deleting a Character
While in **command mode** move the cursor to the desired position and press '```x```' to delete the character at that position.

***

## C-C-C-Combo Commands!
**```[OPERATION(ACTION)] [NUMBER] [MOTION]```**<br>
**Operators:**<br>
```d``` - delete<br>
```c``` - change<br>
```y``` - yank<br>
```p``` - insert (paste) last deleted text.<br>
```r``` - replace<br>

**Number:**<br>
Simply the number you want applied to the operation.

**Motions:**<br>
 ```w``` - Forward by **one word**.<br>
 ```b``` - Backward by **one word**.<br>
 ```)``` - Beginning of **next sentence**.<br>
 ```(``` - Beginning of **current sentence**.<br>
 ```}``` - Beginning of **next paragraph**.<br>
 ```{``` - Beginning of **current paragraph**.<br>
 ```]``` - Beginning of **next section**.<br>
 ```[``` - Beginning of **current section**.<br>

## Deleting Words
Move cursor to start (or desired) position and enter '```dw```' to "delete" - "word" (in forward direction).<br>
_Note: This does not include punctuation such as periods or commas, etc._

## Delete Line
The **command** '```d$```' will delete an entire line.<br>
This command represents _delete_ ('d') and _entire line_ (dollar sign).

_Note: As deleting an entire line is a very common task, there is also the '```dd```' shortcut that will do the same thing as '```d$```'._

***

## Undo & Redo
In **command mode**, 'u' will undo a command up to 500 buffered commands.<br>

```CTRL+r``` (lowercase) will "undo" the previous **undo**.

***

## Searching
Search document **AFTER** cursor position > forward:<br>
```:/[searchTerm]```<br>

Search document **PREVIOUS** to cursor position:<br>
```:?[searchTerm]```<br>

Clear highlighted search results:<br>
```:noh```<br>

Cycle through Search Results:<br>
```n``` - cycle next result<br>
```N``` - cycle previous result<br>

## Find & Replace
**Find & Replace**<br>
```:s/[searchTerm]/[replaceTerm]```<br>

**Find & Replace All**<br>
```:s/[searchterm]/[replaceTerm]/g```

***

## Copying & Pasting
### Summary of Copy / Paste Commands
```v``` - highlight one **character** at a time (lowercase 'v').<br>
```V``` - highlight one **line** at a time (uppercase 'v').<br>
```CTRL+v``` - highlight by columns.<br>
```p``` - paste text **after** the current line (lowercase 'p').<br>
```P``` - paste text **ON** the current line (uppercase 'p').<br>
```y``` - yank text into the copy buffer.<br>

Deleted and 'yanked' text is automatically copied into the buffer and available for pasting immediatly.

***

# Other Commands to be Memorized
```d``` - starts the delete operation.<br>
```dw``` - delete a word.<br>
```d0``` - delete to the beginning of the line.<br>
```d$``` - delete to the end of the line.<br>
```dgg``` - delete from cursor to the beginning of the file.<br>
```dG``` - delete from cursor to the end of the file.<br>
```u``` - undo last operation.<br>
```CTRL+r``` - undo last undo.<br>