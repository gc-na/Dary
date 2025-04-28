<!--
Meta Description: # Understanding "extends" in Java: A Comprehensive Guide ## Synopsis The `extends` keyword in Java is a fundamental aspect of object-oriented programm...
Meta Keywords: class, extends, superclass, methods, java
-->

# Understanding "extends" in Java: A Comprehensive Guide

## Synopsis
The `extends` keyword in Java is a fundamental aspect of object-oriented programming that enables class inheritance, allowing one class to inherit properties and methods from another.

## Documentation
In Java, the `extends` keyword is used to establish an inheritance relationship between classes. This mechanism allows a subclass (child class) to inherit fields and methods from a superclass (parent class), promoting code reusability and establishing a hierarchical relationship among classes.

### Purpose
The primary purpose of using `extends` is to facilitate code reuse and establish a logical relationship between classes. By inheriting from a superclass, a subclass can utilize its properties and methods directly, without the need to redefine them.

### Usage
The syntax for using `extends` is straightforward. When defining a class, the `extends` keyword is placed after the class name, followed by the name of the superclass. 

```java
class Superclass {
    // properties and methods
}

class Subclass extends Superclass {
    // additional properties and methods
}
```

### Details
- A class can only inherit from one superclass (single inheritance), which helps avoid complexities associated with multiple inheritance.
- The subclass inherits all non-private fields and methods from the superclass.
- The subclass can override methods of the superclass to provide specific implementations.
- Constructors of the superclass are not inherited but can be called using the `super` keyword.

## Examples
### Basic Example of Inheritance
```java
class Animal {
    void eat() {
        System.out.println("This animal eats food.");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("The dog barks.");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.eat(); // Inherited method
        dog.bark(); // Subclass method
    }
}
```

### Overriding Methods
```java
class Vehicle {
    void start() {
        System.out.println("Vehicle is starting.");
    }
}

class Car extends Vehicle {
    void start() {
        System.out.println("Car is starting.");
    }
}

public class Main {
    public static void main(String[] args) {
        Vehicle myCar = new Car();
        myCar.start(); // Calls the overridden method in Car
    }
}
```

## Explanation
While using the `extends` keyword in Java simplifies code management, there are common pitfalls:

1. **Single Inheritance Limitation**: Java does not support multiple inheritance with classes, which can lead to design constraints. Developers must use interfaces to achieve similar functionality.
  
2. **Overriding Rules**: When overriding methods, it’s vital to maintain the same method signature. Failing to do so results in method overloading rather than overriding.

3. **Access Modifiers**: Only non-private members of the superclass are accessible in the subclass. Developers should keep this in mind when designing class hierarchies.

4. **Constructor Usage**: Remember that constructors are not inherited. If a subclass needs to call a superclass constructor, it must do so explicitly using the `super()` method.

## One Line Summary
The `extends` keyword in Java establishes an inheritance relationship between classes, allowing subclasses to inherit properties and methods from their superclasses.