# DSA Concepts

- way of organizing data so that it can be used effectively

## Abstract Data Type

- abstract data type is an abstraction of a data structure which provides interface to which a data structure must adhere to
- EXAMPLE
  - ADT: List
    - Implementation (Data structure): dynamic array, linked list
  - Queue
    - Implementation: linkedlist based queue, array based queue, stack based queue
  - Map
    - Implementation: Tree map, hash map/hash table
  - Vehicle
    - Implementation: Golf cart, smart car

## Complexity Analysis

- Big-O Notation gives the upper bound of the complexity in the worst case
- Big-O notation from smallest to largest where n = the size of the input
  - Constant time: O(1)
  - Logarithmic time: O(logn)
  - Linear time: O(n)
    - loop
  - Linearithmic Time: O(nlogn)
    - sorting using mergesort
  - Quadric Time: O(n^2)
    - nested loop
  - Cubic Time: O(n^3)
    - nested loop
  - Exponential Time: O(b^n), b > 1
    - finding all subsets of a set
  - Factorial Time: O(n!)
    - finding all permutations of a string
