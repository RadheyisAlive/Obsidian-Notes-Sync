- to set number of lines in your program then = :set number

this is a bash command

![[Untitled 16.png]]

- press yy to copy the whole line and paste it again makes things faster if wanna copy the same code again In bash
- set syntax color in VI editor

then press ess and then

```JavaScript
:syntax off

:syntax on
```

- i - to insert in Vim mode
- For forcefully deleting a file whether the file exists on the system or the file is write-protected, you can use the syntax: rm -f file_name
- For deleting is not happening forcefully by rm -f then try rm -rf , just believe this is more forcefully to delete a file or directory

|   |   |   |   |   |
|---|---|---|---|---|
|Command|Description|Examples|||
|ls|Lists all files in the current directory, if an argument is provided  <br>lists all files in the specified directory.|ls, ls –l, ls –la|||
|cp|Copies the file from source to destination.|cp Downloads/test.py ., cp test.py test2.py|||
|mv|Moves the file from source to destination. If the destination ends  <br>in a file name it will rename the file.|mv test.py Prac1, mv test.py mytest.py|||
|pwd|Lists the directory you are currently in (Print Working  <br>Directory)|pwd|||
|cd|Moves to||||
|mkdir|Creates a new directory|mkdir Prac1|||
|rm|Removes a file||||
|rmdir|Removes a directory (must be empty first)|rmdir Prac12|||

  

- ls -R will GIve you the files that is in the Directory and more over the details of it !!\

  
Press  
`<esc>` to exit insert mode, then :wq to save  
the file (w) and exit vim (q). Type  
  
Some other shortcuts  

You will probably get an error message as a response (unless you  
typed it in perfectly). Don’t worry, check through your code for the  
error and try running it again. Go back into the file and make  
corrections – use the cursor keys to get to the position (G).  
Some handy editing commands are:  

- to delete a character type “x”
- to delete a line “dd”
- to delete a word “dw”
- to change a word “cw”
- to insert/append after the end of the current line, type “A”
- to undo the last command, type “u”
- to redo the last command, type “.”

ls –la —> list the contents of a directory  
 cd —> COMP1005/Prac1 change directory  
 cp file1.txt file2.txt —> copy file1 to file2  

![[Screenshot_(13).png]]

![[Screenshot_2024-04-27_180223.png]]

![[Screenshot_2024-04-27_180906.png]]

ls -la ——> lists the hidden files too

![[Untitled 1 4.png]]

  

- ls-a ——> also shows you the hidden files