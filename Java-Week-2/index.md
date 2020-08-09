# Java Week 2

*2020-08-01 by Hongliang Zhu*

<div id="toc">

- [Java Week 2](#java-week-2)
    - [1. Object Oriented Programming](#1-object-oriented-programming)
    - [2. Class](#2-class)
    - [3. Abstract](#3-abstract)
    - [4. Interface](#4-interface)

</div>


### 1. Object Oriented Programming

* Object

* Class
  * <details open><summary>Definition</summary>
  
    > A class is a blueprint or prototype from which objects are created
  
  * Field / Attribute (state)
  * <details open>
      <summary>Method / Function (behavior)</summary>

      >A method is a block of statements in order to perform some specific task from a set of arguments.* 

    * <details open><summary>Basic Syntax</summary>

      ```java
      class Example {
        // Define a function 
        int Foo() {
          return 0;
        }

        void Boo() {
        }

        void main() {
          int value = Foo();
          Boo();
        }
      }
      ```

* Inheritance
  * Subclass
  * Superclass

* Abstract

* Interface

* External Source [*here*](https://docs.oracle.com/javase/tutorial/java/concepts/index.html)


### 2. Class

* <details open><summary>How to define a <code>Bicycle</code> Class?</summary>

    ```java
    // source: https://docs.oracle.com/javase/tutorial/java/javaOO/classes.html

    public class Bicycle {
          
      // the Bicycle class has
      // three fields (attributes)
      public int cadence;
      public int gear;
      public int speed;
      private int id;

      // the Bicycle class has
      // one constructor
      public Bicycle(int startCadence, int startSpeed, int startGear) {
          gear = startGear;
          cadence = startCadence;
          speed = startSpeed;
      }
          
      // the Bicycle class has
      // four methods
      public void setCadence(int newValue) {
          cadence = newValue;
      }
          
      public void setGear(int newValue) {
          gear = newValue;
      }
          
      public void applyBrake(int decrement) {
          speed -= decrement;
      }
          
      public void speedUp(int increment) {
          speed += increment;
      }      
    }
    ```

* <details open><summary>Subclass</summary>

  * In Java, it is possible to inherit attributes and methods from one class to another

  * How to define a subclass `MountainBicycle` from class `Bicycle`?

    ```java
    public class MountainBike extends Bicycle {
            
        // the MountainBike subclass has
        // one field
        public int seatHeight;

        // the MountainBike subclass has
        // one constructor
        public MountainBike(int startHeight, int startCadence,
                            int startSpeed, int startGear) {
            super(startCadence, startSpeed, startGear);
            seatHeight = startHeight;
        }   
            
        // the MountainBike subclass has
        // one method
        public void setHeight(int newValue) {
            seatHeight = newValue;
        }   
    }
    ```

### 3. Abstract

* <details open><summary>Definition</summary>

  >An *abstract class* is a class that is declared abstract—it may or may not include abstract methods. Abstract classes cannot be instantiated, but they can be subclassed.

  >An *abstract method* is a method that is declared without an implementation (without braces, and followed by a semicolon)

* Note: A class must be declared as `abstract` if it contains one or more abstract methods; if its subclass does not provide implementations for **all** the abstract methods, the subclass must also be declared as `abstract`

* <details open><summary>Example</summary>

  ```java
  public abstract class Bike {
      // declare fields
      // declare non-abstract methods
      abstract void move();
  }

  public class MountainBike extends Bike {
    void move() {
      // implementations
    }
  }
  ```

### 4. Interface

* <details open><summary>Definition</summary>

  * >In the Java programming language, an interface is a reference type, similar to a class, that can contain only constants, method signatures, default methods, static methods, and nested types.

  * >Interfaces cannot be instantiated—they can only be implemented by classes or extended by other interfaces.

  * An interface only defines a 'contract' for classes that `extends` the interface or other interfaces that `implements` the interface.

* If methods declared in interface are not **all** implemented, the class must be declared as `abstract`
  * <details open><summary>Example:</summary>

    ```java
    public interface TransitTool {
      void move();
    } 

    abstract class Bike implements TransitTool {
    }

    class MountainBike extends Bike {
      void move() {}
    }
    ```
