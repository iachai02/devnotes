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
```bash
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
```bash
mv "move from" "to this/rename"
```
- `cp`: copy a file
```bash
cp "copy from" "copy to"
```
- `rm`: remove a file
- `rmdir`: remove a directory only if empty
- `mkdir`: make a new directory
- `man`: gives more information about a program's arguments, inputs, outputs, how it works in general
- `>`, `<`: redirection
```bash
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
```bash
cat < hello.txt >> hello2.txt
# uses the text in hello.txt as the input for cat and uses
# that input from cat to add another hello in hello2.txt
# does not print out anything
```
- `|`: take the output of the program on the left and mkae that the input for the program on the right
```bash
ls -l / | tail -n1
# gets the last line of the list of files/directories
```
- `cat`: when given file names as arguments, it prints the contents of each of the files in sequence to its output stream
```bash
cat hello.txt
# prints out "hello" from previous
```
- `sudo`: lets you do something as the root user which has access to every file on your computer
```bash
sudo su
# allows you to change to a super user shell
```
- `xdg-open`: opens a file
```bash
xdg-open lectures.html
```
- `--help`, `-h`: prints some help text that tells you what flags and options are available
- `chmod`: changes the permissions of a file or directory
```bash
chmod [options] mode file
chmod u+x filename
```

## USEFUL TOOLS

- To access variables (spaces are crucial)
```bash
foo=bar
echo $foo
-> bar
```
- Strings in bash are represented as `''` or `""`, but are not equal
```bash
foo=bar
echo "$foo"
# prints bar
echo '$foo'
# prints $foo
```
- Function in bash: `vim mcd.sh`
```bash
mcd () {
    mkdir -p "$1"
    cd "$1"
}
```
- Bash uses a variety of special variables to refer to arguments, error codes, relevant variables
    - `$0`: name of the script
    - `$1` to `$9`: Arguments to the script (`$1` is the first argument)
    - `$@`: All the arguments
    - `$#`: Number of arguments
    - `$?`: Return code of the previous command
    - `$$`: Process identification number (PID) for the current script
    - `!!`: Entire last command, including arguments
    - `$_`: Last argument from the last command
```bash
echo "Hello"
-> Hello
echo $?
-> 0 # this is because the previous code ran smoothly and has en error code of 0

mkdir test
cd $_ # goes to the test directory
```
- `||`: the or operator, `&&`: and operator
```bash
false || echo "Oops, fail"
-> Oops, fail
true || echo "Will not be printed"
-> # nothing is printed since the first part was true
true && echo "Things went well"
-> Things went well
```
- Command substitution: You can get the output of a command as a variable
```bash
echo "We are in $(pwd)"
-> We are in /../
```

- Process substitution: execute the `CMD` and place the output in a temporary file and substitute the `<()` with that file's name
```bash
diff <(ls foo) <(ls bar)
# this will show the differences between files in dirs foo and bar
```

