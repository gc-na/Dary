<!--
Meta Description: # Understanding "non-sealed" in Java: A Comprehensive Guide ## Synopsis The "non-sealed" keyword in Java is a modifier used in the context of sealed c...
Meta Keywords: sealed, class, non, can, java
-->

# Understanding "non-sealed" in Java: A Comprehensive Guide

## Synopsis
The "non-sealed" keyword in Java is a modifier used in the context of sealed classes and interfaces, introduced in Java 17. It allows subclasses to extend a sealed class or interface without restrictions, promoting flexibility in type hierarchies.

## Documentation
### Purpose
The "non-sealed" modifier serves as a way to declare that a sealed class or interface can be extended freely by any class, thus breaking the sealed hierarchy. This provides developers with the ability to create a more ad-hoc extension of their sealed type while maintaining the benefits of sealed types elsewhere.

### Usage
- **Declaration**: The "non-sealed" modifier is applied to classes or interfaces that are intended to be open for extension. It can only be used in the context of a sealed class or interface.
- **Context**: It is primarily used when a developer wants to create a specific subclass of a sealed class or interface that can be extended further without restrictions.

### Details
- **Sealed Classes**: A sealed class restricts which other classes can extend it. When a class is declared as sealed, it can only be extended by specific classes that are explicitly declared as permitted subclasses.
- **Non-Sealed Subclasses**: By marking a subclass as "non-sealed", that subclass can be further extended by any other class, removing the restrictions imposed by the sealed parent class.

## Examples
### Basic Usage Example
```java
// Sealed class declaration
public sealed class Vehicle permits Car, Bike {
}

// Non-sealed subclass
public non-sealed class Car extends Vehicle {
}

// Another subclass that can extend Car
public class SportsCar extends Car {
}
```

### Explanation of Example
In the example above:
- `Vehicle` is a sealed class that only permits `Car` and `Bike` as its subclasses.
- `Car` is marked as `non-sealed`, allowing any other class to extend it, such as `SportsCar`.

## Explanation
### Common Pitfalls and Gotchas
- **Misuse of Non-Sealed**: Using "non-sealed" in a context where it's not applicable will lead to compile-time errors. It must be used specifically within a sealed class hierarchy.
- **Overextension**: While "non-sealed" provides flexibility, it can also lead to a more complex and less controlled type hierarchy, which may defeat the purpose of using sealed classes for type safety and clarity.
- **Compatibility**: Ensure that your Java version is 17 or later, as sealed types and the "non-sealed" modifier are not available in earlier versions.

## One Line Summary
The "non-sealed" keyword in Java allows unrestricted subclassing of a sealed class, enabling greater flexibility in extending type hierarchies.