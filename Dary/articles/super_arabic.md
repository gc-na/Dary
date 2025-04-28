<!--
Meta Description: # استخدام الكلمة المحجوزة "super" في لغة جافا ## ملخص الكلمة المحجوزة "super" في لغة جافا تستخدم للإشارة إلى العناصر في السوبر (الأساسي) كلاس. يمكن اس...
Meta Keywords: super, كلاس, السوبر, system, out
-->

# استخدام الكلمة المحجوزة "super" في لغة جافا

## ملخص
الكلمة المحجوزة "super" في لغة جافا تستخدم للإشارة إلى العناصر في السوبر (الأساسي) كلاس. يمكن استخدامها لاستدعاء المُنشئ، أو الوصول إلى المتغيرات والطرق التي تم تعريفها في السوبر كلاس.

## الوثائق
تعتبر الكلمة المحجوزة "super" أداة قوية في البرمجة الكائنية (OOP) بلغة جافا، وتلعب دورًا مهمًا في وراثة الصفوف. تُستخدم "super" بشكل رئيسي في الحالات التالية:

1. **استدعاء المُنشئ**: يُمكن استخدام "super" لاستدعاء مُنشئ السوبر كلاس داخل مُنشئ الكلاس الفرعي.
2. **الوصول إلى المتغيرات**: يمكن استخدام "super" للوصول إلى المتغيرات العامة أو المحمية (protected) الموجودة في السوبر كلاس.
3. **استدعاء الطرق**: يمكن استخدام "super" لاستدعاء الطرق المعرّفة في السوبر كلاس، خاصة إذا تم تجاوزها في الكلاس الفرعي.

### الاستخدام
```java
class SuperClass {
    int number = 10;

    SuperClass() {
        System.out.println("SuperClass Constructor");
    }

    void display() {
        System.out.println("Display from SuperClass");
    }
}

class SubClass extends SuperClass {
    int number = 20;

    SubClass() {
        super(); // استدعاء مُنشئ السوبر كلاس
        System.out.println("SubClass Constructor");
    }

    void display() {
        super.display(); // استدعاء طريقة من السوبر كلاس
        System.out.println("Display from SubClass");
    }

    void showNumbers() {
        System.out.println("Number in SubClass: " + number);
        System.out.println("Number in SuperClass: " + super.number);
    }
}
```

## الأمثلة
إليك مثال يوضح كيفية استخدام "super":

```java
class Animal {
    String sound = "Animal sound";

    Animal() {
        System.out.println("Animal Constructor");
    }

    void makeSound() {
        System.out.println(sound);
    }
}

class Dog extends Animal {
    String sound = "Bark";

    Dog() {
        super(); // استدعاء مُنشئ السوبر كلاس
        System.out.println("Dog Constructor");
    }

    void makeSound() {
        super.makeSound(); // استدعاء طريقة من السوبر كلاس
        System.out.println(sound);
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.makeSound();
    }
}
```
**الإخراج المتوقع:**
```
Animal Constructor
Dog Constructor
Animal sound
Bark
```

## الشرح
عند استخدام "super"، يجب الانتباه إلى النقاط التالية:

- **تعارض الأسماء**: إذا كان هناك متغير بنفس الاسم في الكلاس الفرعي والسوبر كلاس، فإن "super" يمكن أن تساعد في التمييز بينهما.
- **الترتيب**: يجب استدعاء مُنشئ السوبر كلاس في بداية مُنشئ الكلاس الفرعي.
- **الوصول إلى العناصر المحمية**: تأكد من أن المتغيرات أو الطرق التي تحاول الوصول إليها باستخدام "super" هي متاحة (protected أو public).

## ملخص من سطر واحد
تستخدم الكلمة المحجوزة "super" في جافا للإشارة إلى العناصر في السوبر كلاس، مما يسهل الوصول إلى المتغيرات والطرق الأساسية.