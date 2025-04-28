<!--
Meta Description: # Understanding the "final" Keyword in Java: A Comprehensive Guide ## Synopsis The `final` keyword in Java is used to declare constants, prevent metho...
Meta Keywords: final, class, java, method, variables
-->

# Understanding the "final" Keyword in Java: A Comprehensive Guide

## Synopsis
The `final` keyword in Java is used to declare constants, prevent method overriding, and restrict inheritance. It plays a crucial role in defining immutability and securing class designs.

## Documentation
### Purpose
The `final` keyword serves three primary purposes in Java programming:
1. **Final Variables**: When applied to variables, it makes them constants, meaning their values cannot be changed once assigned.
2. **Final Methods**: When applied to methods, it prevents those methods from being overridden in subclasses.
3. **Final Classes**: When applied to classes, it prohibits the creation of subclasses, effectively making the class non-inheritable.

### Usage
- **Final Variables**: Declare a variable as `final` to ensure its value remains constant throughout its lifecycle.
- **Final Methods**: Use `final` before a method declaration to prevent subclasses from modifying its implementation.
- **Final Classes**: Use `final` before a class declaration to prevent other classes from extending it.

### Details
- **Final Variables**: Must be initialized once, either during declaration or in a constructor.
  
  ```java
  final int CONSTANT_VALUE = 10;
  ```

- **Final Methods**: Can still be called by subclasses but cannot be overridden.
  
  ```java
  class Parent {
      final void display() {
          System.out.println("Final method in Parent class");
      }
  }
  
  class Child extends Parent {
      // This would cause a compile-time error
      // void display() {
      //     System.out.println("Trying to override");
      // }
  }
  ```

- **Final Classes**: Cannot be subclassed, providing a way to create immutable classes.
  
  ```java
  final class ImmutableClass {
      // Class implementation
  }
  
  // The following would cause a compile-time error
  // class SubClass extends ImmutableClass {}
  ```

## Examples
### Final Variable Example

```java
public class FinalVariableExample {
    final int MAX_VALUE = 100;

    public void display() {
        System.out.println("Max Value: " + MAX_VALUE);
    }
}
```

### Final Method Example

```java
class FinalMethodExample {
    final void show() {
        System.out.println("This is a final method.");
    }
}

class AnotherClass extends FinalMethodExample {
    // Attempting to override show() will cause an error
}
```

### Final Class Example

```java
final class FinalClassExample {
    // Class details
}

// Attempting to extend this class will result in a compile-time error
// class SubClass extends FinalClassExample {}
```

## Explanation
### Common Pitfalls and Gotchas
- **Initialization**: Final variables must be initialized, either at the point of declaration or in a constructor. Failing to do so will result in a compilation error.
- **Inheritance**: Declaring a class as `final` does not prevent the use of its instances; it merely restricts subclassing. Be cautious when designing your class hierarchy.
- **Static Final Variables**: It’s common to use `static final` for constants, as it allows shared constant values among all instances of a class.

```java
public class Constants {
    public static final String APP_NAME = "My Application";
}
```

## One Line Summary
The `final` keyword in Java is essential for creating constants, preventing method overriding, and restricting inheritance in class designs.