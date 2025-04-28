<!--
Meta Description: # Understanding "const" in Java: A Comprehensive Guide ## Synopsis In Java, the keyword "const" is not used as a part of the language. Instead, Java e...
Meta Keywords: final, java, class, keyword, variable
-->

# Understanding "const" in Java: A Comprehensive Guide

## Synopsis
In Java, the keyword "const" is not used as a part of the language. Instead, Java employs the `final` keyword to achieve similar functionality, allowing variables to be defined as constants. This article explores the concept of constants in Java and how to effectively use the `final` keyword to create immutable variables.

## Documentation
### Purpose
The `final` keyword in Java is used to declare constants. This means once a variable is assigned a value, it cannot be modified. This feature is essential for maintaining data integrity and ensuring that certain values remain constant throughout the program.

### Usage
- **Variables**: When a variable is declared as `final`, it can only be assigned once. For primitive data types, it means the value is fixed, while for reference types, it means the reference itself cannot change.
  
- **Methods**: A method declared as `final` cannot be overridden by subclasses, ensuring that the original method implementation remains intact.

- **Classes**: A class declared as `final` cannot be subclassed, which can be useful for creating immutable classes or preventing inheritance for security reasons.

### Details
- **Syntax**: The syntax for declaring a constant variable using `final` is as follows:
  ```java
  final dataType VARIABLE_NAME = value;
  ```
- **Scope**: The scope of a `final` variable can be local (inside a method), instance (belonging to an instance of a class), or static (shared across all instances of a class).

## Examples
### Declaring Final Variables
```java
final int MAX_VALUE = 100;
final String NAME = "Java Developer";
```

### Final in Methods
```java
class Parent {
    final void display() {
        System.out.println("This is a final method.");
    }
}

class Child extends Parent {
    // This will cause a compilation error
    // void display() { 
    //     System.out.println("Trying to override a final method.");
    // }
}
```

### Final Classes
```java
final class ImmutableClass {
    // Class implementation
}

// This will cause a compilation error
// class SubClass extends ImmutableClass { }
```

## Explanation
A common pitfall when using `final` is misunderstanding its behavior with reference types. Declaring a reference variable as `final` does not make the object it points to immutable. For example:

```java
final List<String> myList = new ArrayList<>();
myList.add("Hello"); // This is allowed
myList = new ArrayList<>(); // This will cause a compilation error
```

Another important note is that, while `final` prevents reassignment of a variable, it does not restrict the contents of mutable objects.

## One Line Summary
In Java, the `const` keyword is non-existent; instead, the `final` keyword is used to declare constants, methods that cannot be overridden, and classes that cannot be subclassed.