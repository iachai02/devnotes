# C language notes

## Intro

- C is not object oriented
- C++ is an object oriented extension of C
- To compile and create executable: `gcc HelloWorld.c -o executable`

## Comments and Escape Sequences

- `\n`: newline
- `\t`: tab

## Variables

- variable: allocated space in memory to store a value
- examples:
  - `int age = 21;`
  - `float gpa = 2.05;`
    - 4 bytes
  - `double d = 3.1415926535897;`
    - 8 bytes
  - `char grade = 'C';`
    - 1 byte (-128 to + 127)
  - `unsigned char g = 256;`
    - 1 byte (0 to +255)
  - `char name[] = "Bro";`
  - `bool e = true;`
    - 1 byte (true or false)
    - need to include: `#include <stdbool.h>`
  - `short int h = 32767;`
    - 2 bytes (-32,768 to +32768)
  - `unsigned short int i = 65535;`
    - 2 bytes (0 to +65,535)
  - if you go further beyond the restrictions, it will go back to the minimum value

## Data Types

- format specifiers
  - `%c`: character type
  - `%d`: signed integer type
  - `%f`: float type
  - `%s`: string type
  - `%lf`: 15-16 digits double
  - `%.1`: decimal precision
  - `%1`: minimum field width

## Constants

- constant: fixed value that cannot be altered by the program during its execution
- `const float PI = 3.14159;`

## User Input

- Example for integer:

```C
int age;
printf("\nHow old are you?");
scanf("%d", &age);

printf("You are %d years old", age);
```

- Example for string (reads white spaces):

```C
char name[25];
fgets(name, 25, stdin);

printf("\nHello %s, how are you?", name);
```

## Math functions

- `#include <math.h>`
- `sqrt(9)`: square root
- `pow(2, 4)`: power
- `round(3.14)`: round to nearest int
- `ceil(3.14)`: round number up
- `floor(3.99)`: round number down
- `fabs(-100)`: make any number positive
- `log(3)`: log of number

## Switch statements

- switch: more efficient alternative to using many "else if" statements
  - allows a value to be tested for equality against many cases
- Example:

```C
char grade;
printf("\nEnter a letter grade: ");
scanf("%c", &grade);

switch(grade){
    case 'A':
        printf("perfect!\n");
        break;
    case 'B':
        printf("You did good!\n");
        break;
    default:
        printf("Please enter only valid grades");
        break;
}
```
