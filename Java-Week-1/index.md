# Java Week 1

*2020-07-21 by Bryan*

- [Java Week 1](#java-week-1)
    - [1. First Program](#1-first-program)
    - [2. Comment](#2-comment)
    - [3. Definition](#3-definition)
    - [4. Operators](#4-operators)

### 1. First Program

* Create a new directory
  ```sh
  # In your terminal run following
  $ mkdir myProgram
  $ cd myProgram
  ```
* Create a file named `HelloWorld.java`
  ```java
  // HelloWorld.java file
  class HelloWorld {
    // This is the entry of your program
    // You cannot change the definition of this function
    public static void main(String[] argv) {
      System.out.println("Hello World!");
    }
  }
  ```
* Compile your code
  ```sh
  # In your terminal run following
  $ javac HelloWorld.java

  $ ls
  HelloWorld.class HelloWorld.java
  # Your should expect to see a new file `HelloWorld.class` generated
  ```
* Run your code
  ```sh
  $ java HelloWorld
  Hello World!
  # Done!
  ```

### 2. Comment

* <details open><summary>Single line comment</summary>

  ```java
  // This is a comment
  int a = 1; // content after '//' will be ignored
  ```
* <details open><summary>One or more lines of comment</summary>

  ```java
  /**
   * Content between '/**' and '*\/' will be ignored
   */
  int a = 1; /** You can also use this for single line comment */
  ```
* <details open><summary>Convention</summary>

  * use `//` between statements or after one statement
  * use `/** */` for documenting functions, classes or entire file

* <details open><summary>Optional: <em>Javadoc</em></summary>

    Documentation see [here](https://www.oracle.com/technical-resources/articles/java/javadoc-tool.html)
    ```java
    /** 
     * Get the sum of two numbers
     *
     * @param a First number
     * @param b Second number
     * @return int This returns sum of a and b
     */
    int add(int a, int b) {
      return a + b;
    }
    ```

### 3. Definition

* <details open><summary>Primitive variable types</summary>
  
  ```java
  // "int" has 4 bytes => 32 bits for storing binary digits
  // each digit can be 0 or 1
  // left-most digit for storing sign bit, positive(0) or negative(1)
  // therefore, "int" can store number from 2^(31)-1 ~ -2^31 (note: -1 because of 0)
  int a = 1;
  short b = 2;
  long c = 3;

  double d = 1.0;
  float e = 2.0;

  char character = 'a';

  boolean flag = true; // boolean is 1-bit variable type, can only be true(1) or false(0)

  final int x = 10; // with `final` keyword, x cannot be further reassigned
  ```
  *(Details about size of each type check `Introduction-to-Java`)*

* <details open><summary>None-primitive variable types</summary>
  
  ```java
  String s = "abc";
  
  String[] firstArray = { "1", "2", "3" };
  
  String[] secondArray = new String[3]; // 3 is the size of our desired array
  // Note: Any index starts from 0
  secondArray[0] = "1";
  secondArray[1] = "2";
  secondArray[2] = "3";
  ```
  There are some special characters in strings:
  ```java
  // '\n' new line character
  System.out.println("Hello\nWorld!");
  // Terminal:
  // Hello
  //
  // World!

  // '\t' tab character
  System.out.println("Hello\tWorld!");
  // Terminal:
  // Hello    World!

  // '\r' return character
  System.out.println("Hello\rWorld!");
  // Terminal:
  // World!

  // '\t' tab character
  System.out.println("Hello\bWorld!");
  // Terminal:
  // Hell World!

  // Escape characters:
  // for example, using '\\' to print '\'
  System.out.println("\\");
  // Terminal:
  // \
  
  ```

* <details open><summary>Convention</summary>

  * Meaningful names
    ```java
    /** 
     * Reader should be able easy to figure out what the variable does
     * without or with minimum reading of your implementation
     */
    String[] array = { "Monday", "Tuesday", "Wednesday" }; // Bad
    String[] weekdays = { "Monday", "Tuesday", "Wednesday" }; // Better
    ```
  
  * Camel case when using multiple words as name
    ```java
    String[] cpuBrands = { "Intel", "AMD" };
    ```

  * All capital for constants
   ```java
   int MAX_SIZE = 5;

   // Even better with `final` keyword
   final int THRESHOLD = 2;
   ```

* <details open><summary><em>Optional (but important): <b>How variables are stored in memory</b></em>*</summary>

  * Difference between *Value* and *Reference*
    * Primitive type: It store *values* directly (in binary)
      ```java
      // Assume our Operating System is 32-bit and size of address is 4 bytes

      int a = 1;
      // Assume variable `a` starts from 0x00000080
      //  0x00000080  => | 0x00 | 0x00 | 0x00 | 0x01 |

      short b = 1;
      // Assume variable `b` starts from 0x00000084
      // 0x00000084 => | 0x00 | 0x01 |
      ```
    * Non-primitive type: It stores the *reference* (or *address*) which points to the content.
      ```java
      // Note: String in java DOES NOT terminate with a '\0' character like C
      String s = "abc";
      // Assume the content `"abc"` stores at 0x00001000, each character is stored using its ASCII code
      // 0x00001000 => | 0x65 | 0x66 | 0x67 | 
      // Assume variable `s` starts from 0x0000008A, it stores the starting address of content
      // 0x0000008A => | 0x00 | 0x00 | 0x10 | 0x00 |

      String[] stringArray = new String[2];
      // Assume stringArray starts from 0x0000008E
      // According to the number of items in array, it presets (n x sizeof(address)) bytes and stores `null`, therefore 8 bytes in our case
      // 0x0000008E => | 0x00 | 0x00 | 0x00 | 0x00 | 0x00 | 0x00 | 0x00 | 0x00 |
      stringArray[1] = "abc";
      // This creates another content `"abc"` at a different address, assume at 0x8000100E
      // stringArray[1] here means what stores at stringArray and offset by (1 x sizeof(Address))
      // Therefore, first 4 bytes keep unchanged, and later 4 bytes stores 0x8000100E
      // 0x0000008E => | 0x00 | 0x00 | 0x00 | 0x00 | 0x80 | 0x00 | 0x10 | 0x0E |  
      stringArray[0] = s;
      // We can also assign address value directly;
      // Therefore, first 4 bytes store same value as `s`
      // 0x000008E => | 0x00 | 0x00 | 0x10 | 0x00| 0x80 | 0x00 | 0x10 | 0x0E |
      ```

### 4. Operators

* <details open><summary>Math</summary>

  ```java
  /** Basic */
  // Note: `=` in program means "assign" not "equal"

  int a = 2;
  int b = 3;
  int c = a + b; // c = 5
  c = b / a; // c = 1 because c is int cannot store floating points

  // Increment
  a += 2; // equivalent to a = a + 2; => a = 4;
  a -= 2; // equivalent to a = a - 2; => a = 2;

  a++; // equivalent to a += 1; or a = a + 1; => a = 3;
  a--; // equivalent to a -= 1; or a = a - 1; => a = 2;
  
  ++a; 
  // when used solely, same as a++; 
  // However, when used with other operator, (++a) will increment a first while (a++) will increment a last
  // For example:
  int counter = 0;
  System.out.println(counter++);  // print 0
  System.out.println(counter);  // print 1
  counter = 0
  System.out.println(++counter);  // print 1
  System.out.println(counter);  // print 0
  ```

* <details open><summary>Relational</summary>

  ```java
  /** Mostly used as condition */
  boolean flag = (1 == 1); // flag = true
  flag = (2 > 1); // flag = true
  flag = (2 >= 2); // flag = true 
  flag = (1 != 1); // flag = false
  flag = (true && true && false); // flag = false
  flag = (true && (true || false)); // flag = true
  flag = !(true && (true || false)); // flag = false
  ```
