Download Link: https://assignmentchef.com/product/solved-a-simple-text-editor
<br>
<p class="ui header product-top-header" title="A simple text editor Solution"><strong>Goal</strong>

In this project, you will implement simple text editor. The editor will be able to read from a file, modify it, then allow you to save your edits.

<strong>Program Features</strong>

The editor is interactive and command driven. When you start the program, first a welcome message is printed, then the ” ” prompt is printed. Commands for the text editor are input at the“” prompt.

Here is a sample input file:

Abbott: You throw the ball to first base.

Costello: Then who gets it?

Abbott: Naturally.

Costello: Naturally.

And execution:

Welcome to the CSI 064

open example. txt

Abbott: You throw the

Text

ball

Editor.

to

Costello: Then who gets it?

Abbott: Naturally.

Costello: Naturally.

move 45

Abbott: You throw the ball to

Costello: Then who gets it?

Abbott: Naturally.

Costello: Naturally.

move 4 9

Abbott: You throw the ball to

Costello: Then who gets it?

Abbott: Naturally.

Costello: Naturally.

erase

Abbott:

Costell:

to

first

first

first

first

base.

base.

base.

base.

You throw the ball

Then who gets it?

41 |

42:

691

881

89: 1091

41 |

42:

691

881

89: 1091

41 |

42:

691

881

89: 1091

41 |

42:

681

Abbott: Naturally.

Costello: Naturally.

qui t

| 70: 881

| 89: 1091

Would you like to save before you exit? (Y/ N) : Y

Enter filename: example edited. txt

The example execution above reads example. txt from the disk then prints a formatted version of the file including the “cursor” (the A). The A (the cursor) is the place where edits occur in your file. After printing the file and cursor, the first two commands move the cursor:

the first command moves it to position 45, the next command moves it to position 49. We then start editing the file, we erase the character at position 49, and then we insert a new character “O”. Finally, we try to quit, and we are prompted to save the file.

As noted above, the way the file is printed by our program is different than the way the file is stored on disk. The formatted output contains additional information on each line, plus the cursor (A). The  0: 41 | at the end of the line are the positions (indexes) in the file of the first and last characters for that line. So, the following example shows the first line of the file, the cursor is initially at position 0 in the file, the first character on this line is at position 0 (the A) and the last character on this line (the ‘
’) is at position 41.

Abbott: You throw the ball to first base.

o: 411

Note that the file contents are printed along with the “cursor” (the A) after the file is opened and also after each command.

For simplicity, commands and the parameters for those commands will be separated by whitespace. This makes it easier to read the commands using the techniques you’ve already seen so far.

<strong>Representing the File</strong>

Computer programs rarely modify file data “in place”. Instead they load the data from a file into the program (into a list, string, etc.), let you to modify the data, and only when you explicitly save the file is something written to disk. So, the file data will “live” entirely inside of variables within your program. The file should be represented with a string (the actual file data) and an integer (the cursor).

Your program’s representation of the file (the string and integer) is what will be modified by each command entered into the program. For example, the open command loads the file data from the disk and stores it into the string. Every time you edit the file with insert or erase you are changing the string. When you move the cursor, you will change the integer value. In addition to the string and integer, you should also keep track of: the file name (string), whether or not the file has been opened (Boolean) and whether or not the file has been modified (Boolean).

f

open (file name,

# read all of the file data as string

data

f. read ( )

After the read function, da ta contains all of the text data, formatting information (“
”) and all.

So for the example above data would contain:

# Modify me!

“Abbott: You throw the ball to first base.  n Costello.

Naturally. 
Coste110: Naturally.

The Commands

Then who gets

Your program must implement the following six commands. The first part of each command is the name of the command itself. If the command takes any parameters, they are listed in after the command name. Parameters in square brackets are optional.

open filename

Opens filename and reads the file data into your program. The filename should be the full name with the extension (for example, example. txt). The name cannot have any spaces.

Initially a file is unmodified, so entering quit right after opening the file should not result in a “save” prompt. When opening the file, the cursor should start at 0.

save as filename

Saves the current file data (the string) into the specified f ilename. After this command the file is no longer modified. The filename should be the full name with the extension (for example, test . txt). The name cannot have any spaces.

move position

Takes one parameter that must be an integer, i.e. ‘move 86’. This would move the cursor to index 86 in the file. If the index is out of range (bigger than the file, negative, or not an integer) an error message is printed, and the original cursor (before the move command) value should be retained.

<strong>insert string</strong>

Inserts a string in the file at the cursor position. Takes one parameter i.e. ‘insert hello world’ would insert the string ‘hello world’ at the cursor position. String slicing may be of use here.

erase [number]

If no parameter is specified, erase deletes a single character at the cursor location, if a parameter is specified, it should be the number of characters to delete. So ‘erase 1’ is equivalent to just ‘erase’, while ‘erase 3’ would delete up to 3 characters starting at the cursor, erase will delete less than 3 if the erasures would go beyond the end of the string. If something other than a number is provided an error message should be printed and the string should be unchanged.

quit

“Terminates” the program. If the file is modified and hasn’t been saved, the user is prompted to the save the changes to another file. No further commands should be read after this and the program should exit normally (i.e. reach the end of your program, don’t use exit ( ) etc.).

<strong>Input and Output Files</strong>

The input file will simply contain characters and the file may be arbitrarily long. The file may contain multiple lines but there won’t be any further complex formatting. The output file would work the same way. When you saveas, you want to write whatever the current file data (which is represented by a string) is into a new file, preserving newlines.

Tricky Details

Here are some additional details that you need to aware of to get full credit. If a command is entered that is not one of the six listed above print an error message:

Costello: Naturally.

1419

: 4391

banj o

That ‘s

Abbott :

not an editor conunand.

You throw the ball to

first

base.

Opening a file.

If a file hasn’t been opened, no commands but “open” and “quit” are allowed, even nonsense commands result in an error message about the file not being open.

Welcome to the CS2304 Text

banj o

No file is currently open.

To open a file enter: open

open test . txt

Abbott: You throw the ball

Editor .

file name

to first base.

If the file can’t be opened print an error message, then print a prompt

Welcome to the CS2304 Text Editor.

open doesnotexist . txt

Could not open file: doesnotexist. txt.

quit

Move

Please try a different file.

If an invalid cursor is entered (a negative number, one bigger than the file size, or non integer)i.e. move 1000000, an error message should be printed, the cursor should remain unchanged, and then a prompt should be printed.

Costello: Naturally.

move 100000

89: 1091

CS1064

Invalid

Abbot t :

Quit

Spring 2017

cursor.

You throw the ball to first base.

If the file has been modified but not saved and you try to quit then the editor will prompt you to save first. If the file is unmodified or has already been saved the editor should quit quietly.

erase

bbott: You throw the ball to

Costello: Then who gets it?

Abbott: Naturally.

Costello: Naturally.

quit

first

base.

C). 401

681

69:

871

88: 1081

Would you like to save before you exit?

Enter filename: sample. txt

<strong>Plan of Attack</strong>

I’ve provided you with a starting Python file on the course website, this file contains a function (print file) that will print the file and cursor as shown above. After that, your program should contain a loop that reads commands until it sees the quit command. Commands can either

have a parameter or not, so you’ll have to handle that possibility. Use a sequence of if/else if statements to check which of the commands was entered and perform the correct action. If the command is quit, then break out of the loop so that you stop processing input.

Don’t try to write the whole program at once. Consider implementing the quit command first, just to make sure that your program exits the loop correctly when you type that. Then move on to open and saveas, and see if you can load a file and display it on the screen properly and then

write it back to a different file. After that, try implementing the remaining commands one at a time.