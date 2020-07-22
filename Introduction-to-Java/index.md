# Introduction to Java

- [Introduction to Java](#introduction-to-java)
    - [1. Setup](#1-setup)
    - [2. Variables & Constants](#2-variables--constants)
    - [3. Operators](#3-operators)
    - [4. Branching & Looping](#4-branching--looping)
    - [5. Debug](#5-debug)
    - [6. Classes](#6-classes)
    - [7. Inheritance & Polymorphism](#7-inheritance--polymorphism)
    - [8. Recursions](#8-recursions)
    - [9. Exception Handling](#9-exception-handling)
    - [10. Libraries](#10-libraries)
    - [11. Algorithms](#11-algorithms)

### 1. Setup
- Environment
- First Program: *Hello World*
- Compile & Run

### 2. Variables & Constants
- 
  <details>
  <summary> Primitive Types </summary>

  | Data Type |  Size   |                Description                 |
  | :-------: | :-----: | :----------------------------------------: |
  |  `byte`   | 1 byte  |  integer -2<sup>7</sup> ~ 2<sup>7</sup>-1  |
  |  `short`  | 2 bytes | integer -2<sup>15</sup> ~ 2<sup>15</sup>-1 |
  |   `int`   | 4 bytes | integer -2<sup>31</sup> ~ 2<sup>31</sup>-1 |
  |  `long`   | 8 bytes | integer -2<sup>63</sup> ~ 2<sup>63</sup>-1 |
  |  `float`  | 4 bytes |        decimal 6 ~ 7 decimal points        |
  | `double`  | 8 bytes |       decimal 15 ~ 16 decimal points       |
  | `boolean` |  1 bit  |             `true` or `false`              |
  |  `char`   | 1 byte  |         character or ASCII values          |

  *( 1 byte = 8 bits )*

  </details>

- Object Type ( Such as `String`, Array, Classes )

### 3. Operators
-
  <details>
  <summary> Arithmetic Operator </summary>

  | Operator | Description |
  | :------: | :---------: |
  |   `+`    |    plus     |
  |   `-`    |    minor    |
  |   `*`    |  multiple   |
  |   `/`    |   divide    |
  |   `%`    |     mod     |

  </details>

- 
  <details>
  <summary> Relational Operator </summary>
  
  | Operator |   Description    |
  | :------: | :--------------: |
  |   `==`   |      equal       |
  |   `!=`   |    not equal     |
  |   `>`    |     greater      |
  |   `>=`   | greater or equal |
  |   `<=`   |  less or equal   |
  
  </details>

- 
  <details>
  <summary> Logical Operator </summary>

  | Operator | Description |
  | :------: | :---------: |
  |   `&&`   |     and     |
  |   `||`   |     or      |
  |   `!`    |     not     |

  </details>

- 
  <details>
  <summary>Bitwise Operator (Optional)</summary>

  | Operator |     Description      |
  | :------: | :------------------: |
  |   `&`    |      binary and      |
  |   `|`    |      binary or       |
  |   `^`    |      binary xor      |
  |   `~`    |      binary not      |
  |   `>>`   |     right shift      |
  |   `<<`   |      left shift      |
  |  `>>>`   | unsigned right shift |

  </details>

- 
  <details>
  <summary>Assignment Operator</summary>

  | Operator | Description |
  | :------: | :---------: |
  |   `=`    |   assign    |
  |   `+=`   |  increment  |
  |   `-=`   |  decrement  |
  |          |             |
  |   `*=`   |     ...     |
  |   `/=`   |     ...     |
  |   `%=`   |     ...     |
  |          |             |
  |  `>>=`   |     ...     |
  |  `<<=`   |     ...     |
  |   `&=`   |     ...     |
  |   `|=`   |     ...     |
  |   `^=`   |     ...     |
  
  </details>

- 
  <details>
  <summary>Special Operator</summary>

  | Operator |  Description  |
  | :------: | :-----------: |
  |   `++`   | same as `+=1` |
  |   `--`   | same as `-=1` |

  </details>

- Ternary Operator 
  - `CONDITION ? BRANCH_1 : BRANCH_2;`

### 4. Branching & Looping
- Branching
  - `if` statement
  - `switch` statement
- Looping
  - `while` statement
  - `for` statement
    * Basic: `for (INIT; CONDITION; INCREMENT)` 
    * For each: `for (ITEM DEFINITION: COLLECTION)`

### 5. Debug
- Breakpoint
- Call Stack

### 6. Classes
- `static`
- `public` & `private` & `protected`
- `final`
- Methods
- `equals` & `hashcode`
- `enum` Class
- Nested Class

### 7. Inheritance & Polymorphism
- Abstract Class
- Interface
- `extends` & `implements`
- `override`

### 8. Recursions

### 9. Exception Handling

### 10. Libraries
- `java.util.Collections`
  - `List`
  - `Map`
  - `Set`
  - `Queue`
  - `Deque`
- `java.util.Stack`
- `java.util.PriorityQueue`
- `java.util.stream`
  - `map`
  - `filter`
  - `reduce`
  - `collect`

### 11. Algorithms
- Big O notation
- Sorting
  - Quick Sort
  - Bubble Sort
  - Heap Sort
  - [_Read More_](https://www.cs.cmu.edu/~adamchik/15-121/lectures/Sorting%20Algorithms/sorting.html#:~:text=Sorting%20is%20ordering%20a%20list,it%20is%20called%20external%20sorting.)
- Binary Search Tree
