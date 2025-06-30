# C++ Notes

## How C++ works

- `#include <iostream>`: preprocessor statement
  - processes before compilation
  - header files
  - copy and pastes that file into the new file
- every cpp file gets compiled individually
- every cpp file will get compiled into some obj file
- Linker takes the cpp and obj file and combines them together to create an exe file

## How C++ compiler works

- compilers job is to convert all the code to either constant data or instructions
- cpp files are called translation units
- file is just a way to feed the compiler source code
- files have no meaning
- compiler will compile the cpp files as translation units and create it an obj file from it
- `#define INTEGER int`: replaces any word INTEGER with int

## How C++ linker works

- linking: find where each symbol and function is and combine them together
- unresolved linker error: can't find something we need
- duplicate symbols linking error

## Variables

- the difference between the variables in C++ is the size/how much memory the variable can occupy
- signed int: holds 32 bits (4 bytes), but one needs to be used for the sign so there are 31 bits used for the value itself
- unsigned int: holds 32 bits (4 bytes), but can use all 32 bits for the value itself
- char: 1 byte
- bool: 1 byte
- short: 2 bytes
- long: 4 bytes
- float: 4 bytes
- double: 8 bytes
- long long: 8 bytes

## Header files

- files that get included into cpp files
- Example

```C++
// Main.cpp file
#include "Log.h"
#include <iostream>

int main()
{
    InitLog();
    Log("Hello World!");
}
// Log.h

void InitLog();
void Log(const char* message);

// Log.cpp
#include "Log.h"
#include <iostream>

void InitLog()
{
    Log("Initializing Log");
}

void Log(const char* message)
{
    std::cout << message << std::endl;
}
```

## Control Flow

- `continue`: will go to the next iteration of the loop
- `break`: exits the loop

## Pointers

- pointer: integer that holds a memory address
- `&var`: gets the memory address of the `var` variable
- examples
  - `char* buffer = new char[8]`: 8 bytes of memory
  - `memset(buffer, 0, 8)`: 8 bytes of memory set to 0
  - `delete[] buffer`: deletes the buffer
  - `char** ptr = &buffer`: pointer for the address of the buffer
    - the reverse of the address here would point to the address where the 8 bytes of memory are set to 0

## References (extension of pointers)

- pointers and references are pretty much the same thing
- declaring a reference requires an initialization
- once creating a reference, you can't change it to a different variable, it will just assign the reference to whatever value it was
  - int a = 5, int b = 8
  - int& var = a, var = b
  - a = 8, b = 8
- example

```C++
int a = 5;
int& ref = a;
ref = 2
LOG(ref)
// prints out 2 because ref is a reference to a
```

```C++
void Increment(int& value)
{
    value++;
}

int main()
{
    int a = 5;
    Increment(a);
    LOG(a);
}
```

## Classes

- a class is private by default
  - need `public` to make it public
- example

```C++
class Player
{
public:
    int x, y;
    int speed;
    void Move(int xa, int ya)
    {
        x += xa * speed;
        y += ya * speed;
    }
};

int main()
{
    Player player;
    player.Move(1, -1);
}
```

## Classes vs Structs

- classes are private by default, structs are public by default
- use structs when just talking about data
  - a bunch of variables
- use classes when dealing with inheritance or more complexities design wise

## Static

- use static inside or outside a class or struct
- `extern int s_Variable`: write this if there is another variable from a different file that has the exact same name
- `static int s_Variable`: makes this variable private and only internal to the file this variable is written in
- use static as much as you can if you don't need the variable to be global

## Enums

- enum: a set of values
- Example

```C++
enum Example : unsigned char
{
    A = 5, B, C
};

int a = 0;
int b = 1;
int c = 2;

int main()
{
    Example value = B;
}
```

- by default, the values start off at 0 and increment by 1

## Constructors

- constructor: special method that is ran when you instantiate an object
- Example

```C++
class Entity
{
public:
    float X, Y;

    // constructor
    Entity()
    {
        X = 0.0f;
        Y = 0.0f;
    }

    // constructor
    Entity(float x, float y)
    {
        X = x;
        Y = y;
    }

    void Print()
    {
        std::cout << X << ", " << Y << std::endl;
    }
};

int main()
{
    Entity e(10.0f, 5.0f);
    std::cout << e.X << std::endl;
    e.Print();
}
```

## Destructors

- destructor: uninitialize any data you have

```C++
class Entity
{
public:
    float X, Y;

    // constructor
    Entity()
    {
        X = 0.0f;
        Y = 0.0f;
    }

    // destructor
    ~Entity()
    {
        std::cout << "Destroyed Entity!" << std::endl;
    }

    void Print()
    {
        std::cout << X << ", " << Y << std::endl;
    }
};

void Function()
{
    Entity e;
    e.Print();
}

int main()
{
    Function();
    std::cin.get();
}
```

## Inheritance

- Inheritance: allows us to have a hierarchy of classes which relate to each other
  - helps avoid code duplication
- Example

```C++
class Entity
{
public:
    float X, Y;

    void Move(float xa, float ya)
    {
        X += xa;
        Y += ya;
    }
};

class Player : public Entity
{
public:
    const char* Name;

    void PrintName()
    {
        std::cout << Name << std::endl;
    }
};

int main()
{
    Player player;
    player.Move();
    player.PrintName();
    std::cin.get();
}
```

## Virtual Functions

- virtual functions: overwrite methods in subclasses
- contains additional memory
- Example

```C++
class Entity
{
public:
    // virtual function
    virtual std::string GetName() { return "Entity"; }
};

class Player : public Entity
{
private:
    std::string m_Name;
public:
    Player(const std::string& name)
        : m_Name(name) {}

    // overrided function
    std::string GetName() override { return m_Name; }
}

int main()
{
    Entity* e = new Entity();
    std::cout << e->GetName() << std::endl;

    Player* p = new Player("Cherno");
    std::cout << p->GetName() << std::endl;
    std::cin.get();
}
```

## Interfaces

- specific type of virtual function: pure virtual function
- pure virtual function: define a function in a base class that does not have an implementation and force subclasses to implement that function

```C++
class Printable
{
public:
    // pure virtual function
    virtual std::string GetClassName() = 0;
};

class Entity : public Printable
{
public:
    virtual std::string GetName() { return "Entity"; }
    // overrided function
    std::string GetClassName() override { return "Entity"; }
};

class Player : public Entity
{
private:
    std::string m_Name;
public:
    Player(const std::string& name)
        : m_Name(name) {}

    std::string GetName() override { return m_Name; }
    // overrided function
    std::string GetClassName() override { return "Player"; }
}

void PrintName(Entity* entity)
{
    std::cout << entity->GetName() << std::endl;
}

void Print(Printable* obj)
{
    std::cout << obj->GetClassName() << std::endl;
}

int main()
{
    Entity* e = new Player("");
    std::cout << e->GetName() << std::endl;

    Player* p = new Player("Cherno");
    std::cout << p->GetName() << std::endl;
    std::cin.get();
}
```
