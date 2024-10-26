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
