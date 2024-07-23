# SHELL

## USEFUL INFORMATION
- `$PATH`: lists which directories the shell should search for programs when it is given a command
- When using `ls -l`:
    - The first 3 letters are the permissions for the owner of the file
    - The second 3 letters are the permissions for the group of the file
    - The third 3 letters are the permissions for everyone else
    - letters:
        - `d`: tells us if it is a directory
        - `w`: modify (add/remove files) / change a file
        - `x`: search (allowed to enter the directory) / execute a file
        - `r`: read / read a file
        - `-`: you do not have that permission
- `ctrl+l`: clears terminal and goes back to top

## USEFUL COMMANDS

- `echo`: prints out arguments
```
echo hello
-> hello
```
- `which`: finds out which file is executed for a given program name
- `pwd`: prints which directory you are in
- `cd`: changes the directory
    - `.`: refers to the current directory
    - `..`: refers to the parent directory
    - `-`: goes to the directory you were previously in
    - `~`: brings you to your home directory
- `ls`: lists the files in the current directory
    - `-l`: prints out more information of each file/directory
- `mv`: rename/move a file
```
mv "move from" "to this/rename"
```
- `cp`: copy a file
```
cp "copy from" "copy to"
```
- `rm`: remove a file
- `rmdir`: remove a directory only if empty
- `mkdir`: make a new directory
- `man`: gives more information about a program's arguments, inputs, outputs, how it works in general
- `>`, `<`: redirection
```
echo hello > hello.txt
# the hello goes into the file hello.txt

cat < hello.txt
# the hello in hello.txt is now the input of cat and
# just prints out "hello"

cat < hello.txt > hello2.txt
# uses the text in hello.txt as the input for cat and uses
# that input from cat to put in hello2.txt
# does not print out anything
```
- `>>`: appends to a file
```
cat < hello.txt >> hello2.txt
# uses the text in hello.txt as the input for cat and uses
# that input from cat to add another hello in hello2.txt
# does not print out anything
```
- `|`: take the output of the program on the left and mkae that the input for the program on the right
```
ls -l / | tail -n1
# gets the last line of the list of files/directories
```
- `cat`: when given file names as arguments, it prints the contents of each of the files in sequence to its output stream
```
cat hello.txt
# prints out "hello" from previous



