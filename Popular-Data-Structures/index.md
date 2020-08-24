# Popular Data Structures

*2020-08-16 by Hongliang Zhu*

<div id="toc">

- [Popular Data Structures](#popular-data-structures)
    - [1. Array](#1-array)
    - [2. Linked List](#2-linked-list)
    - [3. Hash Table](#3-hash-table)
    - [4. Stack](#4-stack)
    - [5. Queue](#5-queue)
    - [6. Set](#6-set)
    - [References](#references)

</div>

### 1. Array

* <details open><summary>Array In Java</summary>


  * Fixed length Array:
  
    ```java
    int[] array = new int[2];
    array[0] = 0;
    ```

  * Dynamic length Array(List):
  
    ```java
    // import java.util.ArrayList
    // import java.util.List
    
    List<Integer> list = new ArrayList<>();
    list.add(10);
    // >> { 10 }
    list.get(0);
    // >> 10
    list.remove(0);
    // >> {}
    ```
    [More Methods...](https://docs.oracle.com/javase/8/docs/api/java/util/List.html)

  * Immutable Array(List):

    ```java
    // import java.util.Arrays
    // import java.util.List

    List<Integer> list = Arrays.asList(1, 2, 3);
    list.add(10);
    // >> ERROR!!! <java.lang.UnsupportedOperationException>
    ```
    ```java
    // import java.util.ArrayList;
    // import java.util.Collections;
    // import java.util.List;

    List<Integer> list = new ArrayList<>();
    list.add(10);
    // >> { 10 }

    List<Integer> unmodifiableList = Collections.unmodifiableList(list);
    unmodifiableList.add(10);
    // >> ERROR!!! <java.lang.UnsupportedOperationException>

    // Notice: `list` Itself Is Still Modifiable! And Operations On `list` Update Both `list` And `UnmodifiableList`
    list.add(20);
    ```
  

### 2. Linked List

* <details open><summary>Comparison: Why <code>ArrayDeque</code> is Better than <code>LinkedList</code>?</summary>

  >Key differences:
  >   1. The `ArrayDeque` class is the resizable array implementation of the `Deque` interface and `LinkedList` class is the `List` implementation
  >   2. NULL elements can be added to `LinkedList` but not in `ArrayDeque`
  >   3. `ArrayDeque` is more efficient than the `LinkedList` for add and remove operation at both ends and `LinkedList` implementation is efficient for removing the current element during the iteration
  >   4. The `LinkedList` implementation consumes more memory than the `ArrayDeque`

  >It's "better" in some cases because you're not allocating a node for each item to insert; instead all elements are stored in a giant array, which is resized if it gets full.

  >The only better operation of a linked list is removing the current element during iteration.

  [Read More...](https://stackoverflow.com/questions/6163166/why-is-arraydeque-better-than-linkedlist)

### 3. Hash Table

### 4. Stack

### 5. Queue

### 6. Set

### References

* [Top 6 Data Structures Every Java Programmer Should Learn](https://www.java67.com/2013/08/ata-structures-in-java-programming-array-linked-list-map-set-stack-queue.html)
