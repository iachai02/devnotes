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

## Stack

- What is a stack?
  - one-ended linear data structure which models a real world stack by having two primary operations, namely push and pop
- When are where is a stack used?
  - used by undo mechanisms in text editors
  - used in compiler syntax checking for matching brackets and braces
  - can be used to model a pile of books or plate
  - used behind the scenes to support recursion by keeping track of previous function calls
  - can be used to do a depth first search on a graph
- complexity
  - `pushing`: O(1)
  - `popping`: O(1)
  - `peeking`: O(1)
  - `searching`: O(n)
  - `size`: O(1)

## Queues

- What is a queue?
  - a lienar data structure which models real wworld queues by having two primary operations, namely enqueue (adding) and dequeue (removing/polling)
- WHen and where is a queue used?
  - any waiting line models a queue, for example a lineup at a movie theater
  - can be used to efficiently keep track of the x most recently added items
  - web server request management where you want first come first serve
  - breadth first search graph traversal
- Complexity
  - `Enqueue`: O(1)
  - `Dequeue`: O(1)
  - `Peeking`: O(1)
  - `Contains`: O(n)
  - `Removal`: O(n)
  - `Is empty`: O(1)

## Priority Queues with an interlude on heaps

- What is a PQ?
  - an abstract data type that operates similar to a normal queue except that each element has a certain priority
  - NOTE: priority queues only supports comparable data, meaning the data inserted into the priority queue must be able to be ordered in some way either from least to greatest or greatest to least
  - uses a heap
- What is a heap?
  - a tree based DS that satisfies the heap invariant (also called heap property): If A is a parent node of B then A is ordered with respect to B for all nodes A, B in the heap
  - either the parent node is greater than all the child nodes or the parent node is less than all the child nodes
- When are where is a PQ used?
  - used in certain implementations of Dijkstra's Shortest path algorithm
  - anytime you need the dynamically fetch the 'next best' or 'next worst' element
  - used in huffman coding (which is often used for lossless data compression)
  - best first search algorithms such as A\* use PQs to continuously grab the next most promising node
  - used by minimum spanning tree
- Complexity PQ with binary heap
  - `binary heap construction`: O(n)
  - `polling`: O(logn)
  - `peeking`: O(1)
  - `Adding`: O(logn)
  - `naive removing`: O(n)
  - `advanced removing with help from a hash table`: O(logn)
  - `naive contains`: O(n)
  - `contains check with help of a hash table`: O(1)

## Turning Min PQ into Max PQ

- often times the standard library of most programming languages only provide a min PQ which sorts by smallest elements first, but sometimes we need a max PQ

## Adding Elements to Binary Heap

- What is a binary heap?
  - binary tree that supports the heap invariant. In a binary tree every node has exactly two children
- What is a complete binary tree?
  - a tree in which at every level, except possibly the last is completely filled and all the nodes are as far left as possible
- bubble up when inserting to keep the tree leveled and balanced

## Removing Elements from Binary Heap

- swap the element that you want to remove with the last element
- get rid of that element
- bubble up or down depending on the location and the value of the node

## Removing Elements from Binary Heap in O(logn)

- the inefficiency of the removal algorithm comes from the fact that we have to perform a linear search to find out where an element is indexed at. What if we used a Hashtable to find out where a node is indexed at?
- in the hashtable, swap the values of the indexes

## Union Find (disjoint set)

- What is union find?
  - a data structure that keeps track of elements which are split into one or more disjoint sets
  - two primary operations: find and union
- When and where is a union find used?
  - kruskal's minimum spanning tree algorithm
  - grid percolation
  - network connectivity
  - least common ancestor in trees
  - image processing
- complexity
  - `construction`: O(n)
  - `union`: amortized constant time
  - `find`: amortized constant time
  - `get component size`: amortized constant time
  - `check if connected`: amortized constant time
  - `count components`: O(1)
    - amortized constant time: average time taken for a series of operations is constant, even though the individual operations may take longer
