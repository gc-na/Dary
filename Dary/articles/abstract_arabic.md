<!--
Meta Description: # الكلمة المفتاحية "abstract" في لغة جافا: المفهوم والاستخدامات ## الملخص الكلمة المفتاحية "abstract" في جافا تُستخدم لتحديد الفئات (Classes) والطرق (...
Meta Keywords: abstract, المجردة, class, void, مجردة
-->

# الكلمة المفتاحية "abstract" في لغة جافا: المفهوم والاستخدامات

## الملخص
الكلمة المفتاحية "abstract" في جافا تُستخدم لتحديد الفئات (Classes) والطرق (Methods) التي لا يمكن تنفيذها بشكل كامل، مما يسمح بإنشاء هياكل برمجية مرنة وقابلة للتوسع.

## الوثائق
تُعتبر "abstract" جزءًا أساسيًا من البرمجة الكائنية (Object-Oriented Programming) في جافا. تستخدم هذه الكلمة المفتاحية في:

1. **الفئات المجردة (Abstract Classes)**: وهي فئات لا يمكن إنشاء كائنات (Instances) منها مباشرة. يمكن أن تحتوي على طرق مجردة (Abstract Methods) وطرق عادية (Concrete Methods).
  
2. **الطرق المجردة (Abstract Methods)**: هي طرق تُعلن في الفئة المجردة دون تنفيذ. يتعين على الفئات الفرعية (Subclasses) تنفيذ هذه الطرق.

### الاستخدام
- **إنشاء فئة مجردة**:
  ```java
  abstract class Animal {
      abstract void sound();
  }
  ```

- **تنفيذ الطرق المجردة في الفئات الفرعية**:
  ```java
  class Dog extends Animal {
      void sound() {
          System.out.println("Woof");
      }
  }
  ```

## الأمثلة
### مثال 1: فئة مجردة مع طريقة مجردة
```java
abstract class Shape {
    abstract void draw();
}

class Circle extends Shape {
    void draw() {
        System.out.println("Drawing a Circle");
    }
}

class Square extends Shape {
    void draw() {
        System.out.println("Drawing a Square");
    }
}

public class Main {
    public static void main(String[] args) {
        Shape circle = new Circle();
        circle.draw();
        
        Shape square = new Square();
        square.draw();
    }
}
```

### مثال 2: استخدام فئة مجردة دون طرق مجردة
```java
abstract class Vehicle {
    int speed;
    
    void setSpeed(int s) {
        speed = s;
    }
}

class Car extends Vehicle {
    void displaySpeed() {
        System.out.println("Speed: " + speed);
    }
}

public class Main {
    public static void main(String[] args) {
        Car car = new Car();
        car.setSpeed(100);
        car.displaySpeed();
    }
}
```

## الشرح
### المزالق الشائعة
- **عدم تنفيذ الطرق المجردة**: إذا لم تقم الفئة الفرعية بتنفيذ جميع الطرق المجردة المعلنة في الفئة المجردة، ستظهر رسالة خطأ.
  
- **فئات مجردة مع طرق عادية**: يمكنك دمج الطرق العادية مع الطرق المجردة في الفئة المجردة، مما يسمح بإعادة استخدام الكود.

- **لا يمكن إنشاء كائنات من الفئات المجردة مباشرة**: محاولة القيام بذلك ستؤدي إلى خطأ في وقت التشغيل.

## ملخص من سطر واحد
تستخدم الكلمة المفتاحية "abstract" في جافا لتعريف الفئات والطرق التي لا يمكن تنفيذها بشكل كامل، مما يسهل تصميم هياكل برمجية مرنة وقابلة للتوسع.