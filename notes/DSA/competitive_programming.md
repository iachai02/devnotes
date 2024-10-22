# Competitive Programming introduction

- Most people prefer C++ because of the use of its standard library having many data structures and algorithms
- C++ code template
  - `#include <bits/stdc++.h>`: feature of the g++ compiler that allows us to include the entire standard library
  - `using namespace std`: declares that the classes and functions of the standard library can be used directly in the code (don't need to use "std::cout" can just use "cout")

## Input and Output

- C++ standard streams:
  - `cin`: for input
  - `cout`: for output
- `ios::sync_with_stdio(0);` and `cin.tie(0);` make the input and output more efficient when placed at the beginning
- `\n` works faster than `endl` because `endl` always causes a flush operation
- if the amount of data is unknown, use this loop:

```C++
while (cin >> x) {
    // code
}
```

- read the whole line from the input

```C++
string s;
getline(cin, s);
```

## Floating Point Numbers

- it is risky to compare floating point numbers with the == operator, because it is possible that the values should be equal but they are not because of precision errors

```C++
if (abs(a-b) < 1e-9) {
    // a and b are equal
}
```

## Shortening code

### Type names

- `typedef`: can give a shorter name to a datatype
  - `typedef long long ll;`

```C++
long long a = 123456789
long long b = 987654321
cout << a*b  << "\n";

// shortened

ll a = 123456789;
ll b = 987654321;
cout << a*b << "\n"
```

- can also be used with more complex types
  - `typedef vector<int> vi;`
  - `typedef pair<int, int> pi;`

### Macros

- macro: certain strings in the code will be changed before the compilation by using `#define`

```C++
#define F first
#define S second
#define PB push_back
#define MP make_pair

v.push_back(make_pair(y1, x1));
v.push_back(make_pair(y2, x2));
int d = v[i].first+v[i].second;

// shortened

v.PB(MP(y1, x1));
v.PB(MP(y2, x2));
int d = v[i].F+v[i].S;
```
