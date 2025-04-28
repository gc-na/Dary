<!--
Meta Description: # Understanding "public" in Java: Access Modifiers Explained ## Synopsis In Java, the `public` keyword is an access modifier that sets the visibility ...
Meta Keywords: public, class, java, access, from
-->

# Understanding "public" in Java: Access Modifiers Explained

## Synopsis
In Java, the `public` keyword is an access modifier that sets the visibility of classes, methods, and variables, allowing them to be accessible from any other class in any package.

## Documentation
The `public` access modifier is one of the four visibility levels in Java, the others being `private`, `protected`, and package-private (default). When a class, method, or variable is declared with the `public` modifier, it can be accessed from any other class, irrespective of the package in which the accessing class resides. 

### Purpose
The primary purpose of the `public` modifier is to allow developers to define APIs and implement classes that can be used across different modules or applications. By marking classes or their members as public, developers enable broader accessibility, promoting code reusability and modularity.

### Usage
- **Public Class**: A class declared as public is accessible from anywhere.
- **Public Method**: A method declared as public can be called from any other class.
- **Public Variable**: A variable marked as public can be accessed directly from any class.

### Syntax
```java
public class ClassName {
    public int variableName;
    
    public void methodName() {
        // method implementation
    }
}
```

## Examples
### Example 1: Public Class
```java
// File: ExamplePublicClass.java
public class ExamplePublicClass {
    public void displayMessage() {
        System.out.println("Hello from a public class!");
    }
}

// File: Main.java
public class Main {
    public static void main(String[] args) {
        ExamplePublicClass example = new ExamplePublicClass();
        example.displayMessage(); // Accessible and will print the message
    }
}
```

### Example 2: Public Method
```java
class Sample {
    public void publicMethod() {
        System.out.println("This is a public method.");
    }
}

// File: Demo.java
public class Demo {
    public static void main(String[] args) {
        Sample sample = new Sample();
        sample.publicMethod(); // Accessible from another class
    }
}
```

### Example 3: Public Variable
```java
class Person {
    public String name; // public variable
}

// File: TestPerson.java
public class TestPerson {
    public static void main(String[] args) {
        Person person = new Person();
        person.name = "John Doe"; // Direct access to the public variable
        System.out.println("Person's name: " + person.name);
    }
}
```

## Explanation
While using the `public` modifier provides flexibility, it’s essential to be aware of some common pitfalls:

- **Encapsulation**: Making variables public can break encapsulation principles. It's usually better to keep variables private and provide public getter/setter methods for access.
  
- **Inheritance and Overriding**: Public methods can be overridden in subclasses, which may lead to unexpected behavior if not managed carefully.

- **Package Visibility**: If no access modifier is specified, the default package-private access is used, which restricts visibility to classes within the same package. Therefore, it's critical to explicitly declare access levels when required.

- **Performance Impact**: While access modifiers do not significantly impact performance, excessive use of public access may lead to tightly coupled code, making it harder to maintain.

## One Line Summary
The `public` access modifier in Java allows classes, methods, and variables to be accessible from any other class or package, promoting code reusability.