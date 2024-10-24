# Time Complexity

- time complexity: estimates how much time the algorithm will use for some input

```C++
// O(n)
for (int i = 1; i <= n; i++) {

}

// O(n^2)
for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= n; j++) {

    }
}
```

## Several Variables

- sometimes the time complexity depends on several factors

```C++
O(nm)
for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= m; j++) {

    }
}
```

## Recursion

- time complexity of a recursive function

```C++
// O(n) because f(n) causes n function calls and the time complexity of each call is O(1)
void f(int n) {
    if (n == 1) return;
    f(n-1);
}
```

## Complexity classes

- O(1): constant-time
- O(logn): logarithmic algorithm often halves the input size at each step
- O(sqrt(n)): square root algorithm is slower than O(logn) but faster than O(n)
- O(n): linear algorithm goes through th einput a constant nunmber of times
- O(nlogn): time complexity often indicates that the algorithm sorts the input, because the time comlexity of efficient sorting algorithms is O(nlogn)
- O(n^2): quadratic algorithm often contains two nested loops
- O(n^3): cubic algorithm often contains three nested loops
- O(2^n): indicates that the algorithm iterates through all permutations of the input elements
- O(n!): algorithm iterates through all permutations of the input elements

## Estimating efficiency

- input size:
  n <= 10: O(n!)
  n <= 20: O(2^n)
  n <= 500: O(n^3)
  n <= 5000: O(n^2)
  n <= 10^6: O(nlogn) or O(n)
  n is large: O(1) or O(logn)
