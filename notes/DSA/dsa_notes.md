# DSA Concepts

- way of organizing data so that it can be used effectively

## Abstract Data Type

- abstract data type is an abstraction of a data structure which provides interface to which a data structure must adhere to
- EXAMPLE
  - `ADT`: List
    - Implementation (Data structure): dynamic array, linked list
  - `Queue`
    - Implementation: linkedlist based queue, array based queue, stack based queue
  - `Map`
    - Implementation: Tree map, hash map/hash table
  - `Vehicle`
    - Implementation: Golf cart, smart car

## Complexity Analysis

- Big-O Notation gives the upper bound of the complexity in the worst case
- Big-O notation from smallest to largest where n = the size of the input
  - `Constant time`: O(1)
  - `Logarithmic time`: O(logn)
  - `Linear time`: O(n)
    - loop
  - `Linearithmic Time`: O(nlogn)
    - sorting using mergesort
  - `Quadric Time`: O(n^2)
    - nested loop
  - `Cubic Time`: O(n^3)
    - nested loop
  - `Exponential Time`: O(b^n), b > 1
    - finding all subsets of a set
  - `Factorial Time`: O(n!)
    - finding all permutations of a string

## Static and Dynamic Arrays

- What is a static array?
  - fixed length container containing n elements indexable from the range [0, n-1]
- When and where is a static array used?
  - storing and accessing sequential data
  - temporarily storing objects
  - used by IO routines as buffers
  - lookup tables and inverse lookup tables
  - can be used to return multiple values from a function
  - used in dynamic programming to cache answers to subproblems (knapsack or coin change problem)
- static array complexity
  - `Access`: O(1)
  - `Search`: O(n)
- dynamic array complexity
  - `Access`: O(1)
  - `Search`: O(n)
  - `Insertion`: O(n)
  - `Appending`: O(1)
  - `Deletion`: O(n)
- What is a dynamic array?
  - dynamic array can grow and shrink in size
- How to implement a dynamic array?
  - use a static array
  1. Create a static array with initial capacity
  2. Add elements to the underlying static array keeping track of the number of elements
  3. if adding another element will exceed the capacity, then create a static array twice the size and add the elements to the new array

## Singly and Doubly Linked Lists

- What is a linked list?
  - a sequential list of nodes that hold data which point to other nodes also containing data
- Where are linked lists used
  - used in many list, queue and stack, implementations
  - great for creating circular lists
  - can easily model real world objects such as trains
  - used in separate chaining, which is present certain Hashtable implementations to deal with hashing collisions
  - often used in the implementation of adjaceny lists for graphs
- `head`: first node in a linked list
- `tail`: last node in a linked list
- `pointer`: reference to another node
- `node`: an object containing data and pointer(s)
- `singly linked list`: only hold a reference to the next node
  - pros: uses less memory, simpler implementation
  - cons: cannot easily access previous elements
- `doubly linked list`: holds a reference to the next and previous node
  - pros: can be traversed backwards
  - cons: takes 2x memory
- singly linked complexity:
  - `search`: O(n)
  - `insert at head`: O(1)
  - `insert at tail`: O(1)
  - `remove at head`: O(1)
  - `remove at tail`: O(n)
  - `remove in middle`: O(n)
- doubly linked complexity:
  - `search`: O(n)
  - `insert at head`: O(1)
  - `insert at tail`: O(1)
  - `remove at head`: O(1)
  - `remove at tail`: O(1)
  - `remove in middle`: O(n)
