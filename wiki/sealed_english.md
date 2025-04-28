<!--
Meta Description: # Understanding Sealed Classes in Java: Enhancing Type Safety and Extensibility ## Synopsis Sealed classes in Java introduce a powerful feature for co...
Meta Keywords: sealed, class, classes, public, methods
-->

# Understanding Sealed Classes in Java: Enhancing Type Safety and Extensibility

## Synopsis
Sealed classes in Java introduce a powerful feature for controlling class inheritance, allowing developers to define a restricted hierarchy of classes. This feature, introduced in Java 15 as a preview and standardized in Java 17, enhances type safety and makes the codebase more maintainable.

## Documentation
### Purpose
Sealed classes provide a mechanism for restricting which classes can subclass them. This is crucial in scenarios where you want to maintain control over the inheritance hierarchy for reasons such as security, maintainability, or clarity of design.

### Usage
To declare a sealed class, use the `sealed` modifier in the class declaration. A sealed class must specify which classes are permitted to extend it using the `permits` clause.

### Syntax
```java
public sealed class ClassName permits SubClass1, SubClass2 {
    // Class body
}
```

### Example
Here’s a simple example demonstrating a sealed class with permitted subclasses:

```java
public sealed class Shape permits Circle, Rectangle {
    // Common properties and methods for shapes
}

public final class Circle extends Shape {
    // Circle specific properties and methods
}

public final class Rectangle extends Shape {
    // Rectangle specific properties and methods
}
```

In this example, `Shape` is a sealed class, allowing only `Circle` and `Rectangle` to inherit from it. The `final` modifier indicates that these subclasses cannot be further extended.

### Details
- **Modifiers**: In addition to `sealed`, subclasses can be declared as `final`, `non-sealed`, or `abstract`.
  - `final`: Prevents further subclassing.
  - `non-sealed`: Allows unrestricted subclassing.
  - `abstract`: Makes the subclass abstract, requiring further implementation by its subclasses.
  
- **Benefits**: 
  - Improved type safety by restricting the subclassing of critical classes.
  - Enhanced code readability and maintainability by clearly defining permitted subclasses.
  - Better pattern matching capabilities in switch expressions.

## Examples
### Example 1: Basic Sealed Class
```java
public sealed class Vehicle permits Car, Truck {
    // Vehicle properties and methods
}

public final class Car extends Vehicle {
    // Car specific properties and methods
}

public final class Truck extends Vehicle {
    // Truck specific properties and methods
}
```

### Example 2: Using Non-Sealed Subclass
```java
public sealed class Animal permits Dog, Cat {
    // Animal properties and methods
}

public non-sealed class Dog extends Animal {
    // Dog specific properties and methods
}

public final class Cat extends Animal {
    // Cat specific properties and methods
}
```

In this example, `Dog` is a non-sealed subclass, allowing it to be extended by other classes.

## Explanation
### Common Pitfalls
- **Missing Permits Clause**: Failing to declare the `permits` clause will result in a compilation error. Ensure that all subclasses are explicitly listed.
- **Inconsistent Modifiers**: If a sealed class is declared, all permitted subclasses must adhere to the rules of sealed classes. Mixing final, non-sealed, and abstract may lead to confusion.
- **Abstract Sealed Classes**: If a sealed class is declared abstract, it cannot have any non-abstract subclasses, as they must implement its abstract methods.

### Additional Notes
- Sealed classes are especially useful in domain modeling, where you might want to represent a fixed set of types.
- Consider using sealed classes alongside record types for immutable data structures that require a bounded inheritance.

## One Line Summary
Sealed classes in Java offer a robust mechanism for controlling class inheritance, enhancing type safety and code maintainability by specifying permitted subclasses.