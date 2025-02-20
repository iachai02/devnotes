# Sorting

- the efficient general sorting algorithms work in O(nlogn) time

## Sorting Theory

- Basic problem: given an array that contains n elements, your task is to sort the elements in increasing order
- bubble sort: consists of n rounds and on each round, the algorithm iterates through the elements of the array and when two consecuitve elements are found that are not in correct order, the algorithm swaps them.
  - Time: O(n^2)

```C++
for (int i = 0; i < n; i++) {
    for (int j = 0; j < n-1; j++) {
        if (array[j] > array[j+1]) {
            swap(array[j], array[j+1]);
        }
    }
}
```

- merge sort: sorts a subarray array[a...b] and calculates the position of the middle element k and recursively sort the subarray array[a...k] and recursively sort the subarray array[k+1...b] and merges the subarrays array[a...k] and array[k+1...b] into a sorted subarray array[a...b]
  - Time: O(nlogn)

## Sorting in C++

- Built-in C++ sort function

```C++
// sorts in increasing order
vector<int> v = {4, 2, 5, 3, 5, 8, 3};
sort(v.begin(), v.end());

// sorts in reverse order
sort(v.rbegin(), v.rend());

// sort an ordinary array
int n = 7;
int a[] = {4, 2, 5, 3, 5, 7, 3}
sort(a, a+n);
```

### Comparison operators

- `sort` requires a comparison operator
- pairs are sorted primarily according to their first elements and if their first elements are equal, they are sorted according to their second elements

### User-defined structs

- user-defined structs do not have a comparison operator automatically
- the operator should return true if the element is smaller than the parameter, and false otherwise

```C++
struct P {
    int x, y;
    bool operator<(const P &p) {
        if (x != p.x) return x < p.x;
        else return y < p.y;
    }>
};
```

## Binary Search

- general method for searching for an element in an array is to use a for loop that iterates through the elements of the array

```C++
// Time: O(n)
for (int i = 0; i < n; i++) {
    if (array[i] == x) {
        // x found at index i
    }
}
```

- if the array is sorted, binary search algorithm efficiently searches for an element in the sorted array in O(logn) time

```C++
// method 1
// Time: O(logn)
int a = 0, b = n - 1;
while (a <= b) {
    int k = (a + b) / 2;
    if (array[k] == x) {
        // x found at index k
    }
    if (array[k] > x) b = k - 1;
    else a = k + 1;
}
```

### C++ functions

- C++ standard library contians functions that are based on binary search and work in logarithmic time
  - lower_bound: returns a pointer to the first array element whose value is at least x
  - upper_bound: returns a pointer to the first array element whose value is larger than x
  - equal_range: returns both above pointers

```C++
// finds the position of x using lower_bound
auto k = lower_bound(array, array+n, x) - array;
if (k < n && array[k] == x) {
    // x found at index k
}

// counting occurrences of x using lower_bound and upper_bound
auto a = lower_bound(array, array + n, x);
auto b = upper_bound(array, array + n, x);
cout << b - a << "\n";

// shorter version using equal_range
// r.second = upper_bound(array, array + n, x)
// r.first = lower_bound(array, array + n, x)
auto r = equal_range(array, array + n, x);
cout << r.second - r.first << "\n";
```

## Finding the smallest solution

- we are given a function ok(x) that returns true if x is a vlid solution and false otherwise

```C++
// finds the largest value of x for which ok(x) is false and returns the smallest possible k value
int x = -1;
for (int b = z; b >= 1; b /= 2) {
    while (!ok(x+b)) x += b;
}
int k = x+1;
```
