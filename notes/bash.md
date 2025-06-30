# Bash Notes

## List some of the commonly used shell commands?

- `ls`: list files
- `cp`: copy
- `mv`: move
- `mkdir`: make new directory
- `touch`: create files
- `vim`: open files

## Write a simple shell script to list all processes

- `ps -ef`: lists all processes
- `ps -ef | awk -F" " '{print $2}'`: prints column 2 of all the processes

## Write a script to print only errors from a remote log

- `curl google.com | grep ERROR`: gets only the ERRORs from google.com
  - use curl, pipe, and grep
  - curl: retrieves the output
  - pipe: combines the two commands
  - grep: gets a section of the output

## Write a shell script to print numbers divided by 3 & 5 and not 15

- divisible by 3: 3, 6, 9, 12, 15
- divisible by 5: 5, 10, 15
- not divisible by 15:
- what is the range you want to print out

```bash
#!/bin/bash

###########
##
#
#
###########

# divisible by 3, divisible by 5, not 3*5 = 15
# from 1...100
for i in {1..100}; do
if ([ `expr $i % 3` == 0 ] || [ `expr $i % 5` == 0 ]) && [ `expr $i % 15` != 0 ];
then
    echo $i
fi;
done
```

## Write a script to print number of "S" in mississippi

```bash
#!/bin/bash

###########
##
#
#
###########

x=mississipi

# '-o' stands for only
# 'wc -l' gets number of lines
grep -o "s" <<<"$x" | wc -l
```

## How will you debug the shell script?

- `set -x`

## How to open a read-only file?

- `vim -r test.txt`

## What are some disadvantages of shell scripting?

- errors are frequent and costly
- execution speed is slow
- large or complex tasks are not best suited
- provides minimal data structure

## Is bash dynamic or statically typed and why?

- dynamically typed because you can just write x = 5, x = "string"

## How will you sort list of names in a file?

- `sort`

## Basic commands

- `echo`: display the text you put as the argument in the command line
- `cat`: displays the contents of a file
- shebang: `#!/bin/bash`
- `chmod u+x shelltest.sh`: gives the user executable modifications for shelltest.sh
- `grep`: filters out specific words

## Variables

- `$variable`: access the variable

## Positional Arguments

- `echo Hello $1 $2` -> ./test.sh Immanuel Chai
  - prints out 'Hello Immanuel Chai'

## Piping

- Send command output to other commands
- Example: `ls -l | grep BASH`

## Output redirection

- `>`: write to a file
  - `echo Hello World! > hello.txt`
- `>>`: append to a file
  - `echo Good day to you! >> hello.txt`
- `wc -w < hello.txt`: gets the word count of hello.txt file
- `<<`: redirects multiple lines of input to a command
- `<<<`: provides a way to feed a string directly to the standard input of a command

## IF/ELIF/ELSE statements

- Example

```bash
#!/bin/bash

# checks if the first positional argument = immanuel
#${1,,} is a parameter expansion and will allow to ignore upper and lower cases when comparing the two values
if [ ${1,,} = immanuel ]; then
    echo "Welcome!"
elif [ ${1,,} = help ]; then
    echo "Just enter your username!"
else
    echo "I don't know who you are"
fi
```

## Case statements

- better for checking multiple values
- easier to read
- Example

```bash
#!/bin/bash

case ${1,,} in
    immanuel | administrator)
        echo "Hello, you're the boss here"
        ;;
    help)
        echo "Just enter your username!"
        ;;
    *)
        echo "Hello there. You're not the bass of me"
esac
```

## Arrays

- `MY_FIRST_LIST=(one two three four five)`
  - to access: `echo ${MY_FIRST_LIST[@]}`

## For loop

- `for item in ${MY_FIRST_LIST[@]}; do echo -n $item | wc -c; done`

## Functions

- example

```bash
#!/bin/bash

showuptime() {
    local up=$(uptime -p | cut -c4-)
    local since=$(uptime -s)
    cat << EOF
-----
This machine has been up for ${up}
It has been running since ${since}
-----
EOF
}
showuptime
```

## Awk command

- analyze and manipulate text-based data
- `awk '{print $1}' testfile.txt`: prints out the first argument that is separated by a space afterwards
- `awk -F, '{print $1}' csvtest.csv`: pritns out the first argument that is separated by a comma

## Sed command

- `sed 's/fly/grasshopper/g' sedtest.txt`: 's' means replace and the next to words are saying replace fly with grasshopper and 'g' means to do it globally
