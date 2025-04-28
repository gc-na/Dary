<!--
Meta Description: # Understanding the "super" Keyword in Java: A Comprehensive Guide ## Synopsis The `super` keyword in Java is used to refer to the immediate parent cl...
Meta Keywords: class, parent, super, constructor, java
-->

# Understanding the "super" Keyword in Java: A Comprehensive Guide

## Synopsis
The `super` keyword in Java is used to refer to the immediate parent class of an object. It serves multiple purposes, including accessing parent class methods, constructors, and variables, thus facilitating inheritance and polymorphism in object-oriented programming.

## Documentation

### Purpose
In Java, the `super` keyword is primarily utilized in the context of inheritance. It enables a subclass to access members (fields and methods) of its parent class, which is crucial for extending functionality and ensuring code reuse.

### Usage
1. **Accessing Parent Class Methods**: When a subclass overrides a method from its parent class, the `super` keyword can be used to invoke the overridden method from the parent.
   
   ```java
   class Parent {
       void display() {
           System.out.println("Display from Parent");
       }
   }

   class Child extends Parent {
       void display() {
           super.display(); // Calls Parent's display method
           System.out.println("Display from Child");
       }
   }
   ```

2. **Accessing Parent Class Variables**: If a subclass has a field with the same name as a field in the parent class, `super` can be used to refer to the parent class's variable.
   
   ```java
   class Parent {
       String name = "Parent";
   }

   class Child extends Parent {
       String name = "Child";

       void display() {
           System.out.println(super.name); // Outputs: Parent
           System.out.println(this.name);   // Outputs: Child
       }
   }
   ```

3. **Calling Parent Class Constructors**: The `super` keyword can also be used to call a constructor from the parent class. This is typically done in the constructor of the subclass.
   
   ```java
   class Parent {
       Parent() {
           System.out.println("Parent Constructor");
       }
   }

   class Child extends Parent {
       Child() {
           super(); // Calls Parent constructor
           System.out.println("Child Constructor");
       }
   }
   ```

### Details
- **Location**: The `super` keyword must be the first statement in the constructor of a subclass if it is used to call a parent constructor.
- **Static Context**: `super` cannot be used in static contexts (e.g., static methods or static blocks) as it refers to instance-level members.
- **Multiple Inheritance**: Java does not support multiple inheritance through classes; thus, a class can only have one direct parent. However, it can implement multiple interfaces.

## Examples

### Example 1: Overriding Methods

```java
class Animal {
    void sound() {
        System.out.println("Animal makes sound");
    }
}

class Dog extends Animal {
    void sound() {
        super.sound(); // Calls Animal's sound method
        System.out.println("Dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.sound();
    }
}
```

### Example 2: Accessing Parent Variables

```java
class Vehicle {
    String type = "Vehicle";
}

class Car extends Vehicle {
    String type = "Car";

    void displayType() {
        System.out.println(super.type); // Outputs: Vehicle
        System.out.println(this.type);   // Outputs: Car
    }
}

public class Main {
    public static void main(String[] args) {
        Car car = new Car();
        car.displayType();
    }
}
```

### Example 3: Constructor Chaining

```java
class Base {
    Base() {
        System.out.println("Base class constructor");
    }
}

class Derived extends Base {
    Derived() {
        super(); // Calls Base constructor
        System.out.println("Derived class constructor");
    }
}

public class Main {
    public static void main(String[] args) {
        Derived derived = new Derived();
    }
}
```

## Explanation
- **Common Pitfalls**: Developers often forget to use `super` when they need to access a parent class method or variable that has been overridden or shadowed in the subclass. This can lead to unexpected behaviors.
- **Constructor Calls**: If the `super()` call is omitted in the constructor of a subclass, Java automatically calls the no-argument constructor of the parent class. However, if the parent class does not have a no-argument constructor, a compile-time error will occur.
- **Use in Static Contexts**: Attempting to use `super` in a static context will result in a compilation error, as `super` is meant for instance members of the parent class.

## One Line Summary
The `super` keyword in Java is essential for accessing parent class methods, variables, and constructors, facilitating effective inheritance in object-oriented programming.