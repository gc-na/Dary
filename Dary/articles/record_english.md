<!--
Meta Description: # Understanding Records in Java: A Comprehensive Guide ## Synopsis Java Records, introduced in Java 14 as a preview feature and standardized in Java 1...
Meta Keywords: java, record, records, fields, methods
-->

# Understanding Records in Java: A Comprehensive Guide

## Synopsis
Java Records, introduced in Java 14 as a preview feature and standardized in Java 16, provide a concise way to create data-carrying classes. They simplify the creation of immutable data objects without the boilerplate code typically associated with Java classes.

## Documentation
### Purpose
Records are a special kind of class in Java designed to hold immutable data. They automatically generate common methods such as `equals()`, `hashCode()`, and `toString()` based on the fields defined in the record.

### Usage
To declare a record in Java, use the `record` keyword followed by the record name and its fields in parentheses. For instance:

```java
public record Person(String name, int age) {}
```

This declaration creates a `Person` record with two fields: `name` and `age`.

### Key Features
- **Immutable**: Once instantiated, the values of a record's fields cannot be changed.
- **Automatic Methods**: The compiler generates useful methods automatically:
  - `equals()`: Compares records based on their fields.
  - `hashCode()`: Generates a hash code based on the fields.
  - `toString()`: Provides a string representation of the record.
- **Compact Syntax**: Reduces boilerplate code, making your code cleaner and easier to maintain.

## Examples
### Basic Usage Example
Here’s a simple example of how to use a record in Java:

```java
public record Book(String title, String author) {}

public class Main {
    public static void main(String[] args) {
        Book book = new Book("1984", "George Orwell");
        System.out.println(book.title()); // Output: 1984
        System.out.println(book.author()); // Output: George Orwell
        System.out.println(book); // Output: Book[title=1984, author=George Orwell]
    }
}
```

### Example with Custom Methods
You can also add custom methods to records:

```java
public record Circle(double radius) {
    public double area() {
        return Math.PI * radius * radius;
    }
}

public class Main {
    public static void main(String[] args) {
        Circle circle = new Circle(5);
        System.out.println("Area: " + circle.area()); // Output: Area: 78.53981633974483
    }
}
```

## Explanation
### Common Pitfalls
- **Inheritance**: Records cannot extend other classes, but they can implement interfaces. This can be a limitation for developers accustomed to typical class hierarchies.
- **Mutable Fields**: Although records are immutable, if you use mutable objects as fields, changes to those objects can affect the integrity of the record.
- **No Setter Methods**: Records do not support setter methods since their fields are final and cannot be modified after instantiation.

### Gotchas
- **No `this` Reference**: Inside the constructor, you cannot use `this` to refer to fields, which might be surprising for those used to regular class constructors.
- **Compatibility**: Records are only available in Java 14 and later. Ensure that your development environment is set up for a compatible version.

## One Line Summary
Java Records are a streamlined way to create immutable data-carrying classes with minimal boilerplate code, automatically providing essential methods like `equals()`, `hashCode()`, and `toString()`.