# Popular Data Structures

*2020-08-16 by Hongliang Zhu*

<div id="toc">

- [Popular Data Structures](#popular-data-structures)
    - [1. Array](#1-array)
    - [2. Linked List](#2-linked-list)
    - [2. Stack](#2-stack)
    - [3. Queue](#3-queue)
    - [4. Hash Table (`Map` or `Dictionary`)](#4-hash-table-map-or-dictionary)
    - [5. Set](#5-set)
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

* There is a key concept in linked list structure: **node**, **head**. Each **node** contains a *value* of current **node** and a *pointer* which points to next **node**; **head** is the first **node** of a linked list.

* Illusion:

  ![illusion.png](https://media.geeksforgeeks.org/wp-content/uploads/singly-linkedlist.png)

* Key Features:

  1. Each **node** contains a link to next **node**.
  2. You can only directly access **head** or current **node**.
  3. Random access O(n).

* This structure is **ORDERED**, following the linked order, and in order to find a specific node, it takes linear time.

* <details open><summary>In Java, <code>Deque</code> is a replacement for <code>LinkedList</code></summary>

  ```java
  Deque<Integer> deque = new ArrayDeque<>();
  deque.offerFirst(1);
  deque.offerLast();
  deque.pollFirst();
  deque.pollLast();
  ```
  - [More Methods...](https://docs.oracle.com/javase/8/docs/api/java/util/Deque.html)

  - <details open><summary>Comparison: Why <code>ArrayDeque</code> is Better than <code>LinkedList</code>?</summary>

    >Key differences:
    >   1. The `ArrayDeque` class is the resizable array implementation of the `Deque` interface and `LinkedList` class is the `List` implementation
    >   2. NULL elements can be added to `LinkedList` but not in `ArrayDeque`
    >   3. `ArrayDeque` is more efficient than the `LinkedList` for add and remove operation at both ends and `LinkedList` implementation is efficient for removing the current element during the iteration
    >   4. The `LinkedList` implementation consumes more memory than the `ArrayDeque`

    >It's "better" in some cases because you're not allocating a node for each item to insert; instead all elements are stored in a giant array, which is resized if it gets full.

    >The only better operation of a linked list is removing the current element during iteration.

    [Read More...](https://stackoverflow.com/questions/6163166/why-is-arraydeque-better-than-linkedlist)


### 2. Stack

* This structure is called `Stack` because every time when you add a new element to it, you can imagine that you are putting it at the top of a stack; and when you deconstruct it, you are removing from top one by one.

* Key Features:
  
  1. LIFO (Last In First Out)
  2. You can only directly get last element.
  3. Random access O(n)

* This structure is **ORDERED**, following insertion order, but in order to find a specific element, it takes linear time.

* <details open><summary>In Java, it refers to <code>Stack></code></summary>

  ```java
  Stack stack = new Stack();
  stack.push(1);
  stack.push("a");
  // basically, you can push whatever you want
  stack.pop(); // return "a"
  ```
  [More Methods...](https://docs.oracle.com/javase/7/docs/api/java/util/Stack.html)


### 3. Queue

* Similar to `Stack`, but it works like a queue, following first in first out.

* Key Features:
  
  1. FIFO (First in First Out)
  2. You can only directly get first element
  3. Random Access O(n)

* This structure is **ORDERED**, following insertion order, but to find a specific element, it takes linear time.

* <details open><summary>In Java, it refers to <code>Queue</code></summary>

  ```java
  Queue<Integer> q = new PriorityQueue<>();
  q.offer(1);
  q.offer(2); 
  q.poll(); // return 2
  ```
  [More Methods...](https://docs.oracle.com/javase/8/docs/api/java/util/Queue.html)


### 4. Hash Table (`Map` or `Dictionary`)

* This is 1-1 mapping structure, There are two key concepts in such structure: **key** and **value**, and they are stored in pairs. Each **key** is mapped to a **value**, and a **value** can only accessed by using its corresponding **key**.

* Key Features:
  
  1. It stores **key** and **value** pairs.
  2. Each **key** is unique.
  3. Type of **key** has to be *hashable*;
  4. Each **key** can map to at most **1** **value**.
  5. Access speed is O(1).
  6. Deletion speed is O(1).

* By Default, this structure is **NOT ORDERED**, so you cannot access a specific element by index.

* <details open><summary>In Java, it refers to<code>Map</code></summary>

  ```java
  Map<String, Integer> map = new HashMap<>();
  map.put("Bottle Water", 3); // return previous value associated with "Bottle Water", in this case, null
  map.put("Bottle Water", 5); // return 3
  map.put("Chocolate", 2);  // return null
  map.get("Chocolate"); // return 2
  map.remove("Bottle Water"); // return 5
  ```
  - [More Methods...](https://docs.oracle.com/javase/8/docs/api/java/util/Map.html)
  - [Differences Between `HashTable` And `HashMap`...](https://beginnersbook.com/2014/06/difference-between-hashmap-and-hashtable/)


### 5. Set

* Similar to `Map`, but this structure only stores **key**s.

* Key Features:
  
  1. Each element is unique
  2. Access speed is O(1).
  3. Deletion speed is O(1).

* By default, this structure is also **NOT ORDERED**, and you cannot access its element by index.

* <details open><summary>In Java, it refers to <code>Set</code></summary>

  ```java
  Set<Integer> numbers = new HashSet<>();
  numbers.add(1); // return true
  numbers.add(1); // return false
  numbers.remove(1); // return true
  numbers.remove(0); // return false
  ```

### References

* [Top 6 Data Structures Every Java Programmer Should Learn](https://www.java67.com/2013/08/ata-structures-in-java-programming-array-linked-list-map-set-stack-queue.html)
