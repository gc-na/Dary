<!--
Meta Description: # استخدام الكلمة المحجوزة "default" في لغة البرمجة JAVA ## الملخص تُستخدم الكلمة المحجوزة "default" في لغة البرمجة JAVA لتحديد القيم الافتراضية للمتغي...
Meta Keywords: default, system, out, println, java
-->

# استخدام الكلمة المحجوزة "default" في لغة البرمجة JAVA

## الملخص
تُستخدم الكلمة المحجوزة "default" في لغة البرمجة JAVA لتحديد القيم الافتراضية للمتغيرات، ولتحديد الأساليب الافتراضية في الواجهات. تعزز هذه الكلمة من مرونة الكود وتوفر إمكانية تنفيذ كيفية عمل الوظائف بشكل أكثر ديناميكية.

## الوثائق
تعتبر "default" جزءًا أساسيًا من لغة JAVA، حيث تستخدم في سياقات متعددة:

1. **في الواجهات**: تسمح "default" بتعريف أساليب داخل الواجهات، مما يمكّن الواجهات من توفير تنفيذ افتراضي. استخدم هذه الميزة لتقليل الحاجة إلى كتابة كود مكرر في الفئات التي تنفذ الواجهة.
   
   ```java
   interface MyInterface {
       default void display() {
           System.out.println("هذا تنفيذ افتراضي.");
       }
   }
   ```

2. **في عبارات switch**: تُستخدم "default" كعبارة افتراضية تُنفذ عندما لا تتطابق أي من التعبيرات الموجودة في عبارات switch مع القيم المحددة.

   ```java
   switch (day) {
       case 1:
           System.out.println("الأحد");
           break;
       case 2:
           System.out.println("الإثنين");
           break;
       default:
           System.out.println("يوم غير معروف");
   }
   ```

## الأمثلة
### 1. استخدام "default" في الواجهات:
```java
interface Animal {
    default void sound() {
        System.out.println("حيوانات تصدر صوت.");
    }
}

class Dog implements Animal {
    // يمكن أن تتجاوز الكلاس Dog تنفيذ الصوت الافتراضي
    public void sound() {
        System.out.println("نباح.");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.sound(); // يطبع: نباح.
    }
}
```

### 2. استخدام "default" في جملة switch:
```java
public class Main {
    public static void main(String[] args) {
        int day = 5;
        switch (day) {
            case 1:
                System.out.println("الأحد");
                break;
            case 2:
                System.out.println("الإثنين");
                break;
            default:
                System.out.println("يوم غير معروف"); // يتم تنفيذ هذا الجزء
        }
    }
}
```

## الشرح
على الرغم من أن استخدام "default" يقدم فوائد عديدة، إلا أن هناك بعض النقاط التي يجب أخذها في الاعتبار:

- **تجاوز الأساليب**: عند استخدام "default" في الواجهات، يمكن للفئات التي تنفذ الواجهة تجاوز الأساليب الافتراضية، وهو ما قد يؤدي إلى سلوك غير متوقع إذا لم يتم إدارة ذلك بشكل جيد.
  
- **عدم وجود "default" في الفئات**: لا يمكن استخدام "default" لتعريف متغيرات أو أساليب افتراضية في الفئات، لذا يجب أن تكون حذرًا في تحديد السياق الصحيح.

- **في عبارات switch**: تأكد من وضع "default" في نهاية قائمة الحالات إذا كنت تريد التقاط أي حالة غير محددة، حيث سيتم تنفيذها إذا لم تتطابق أي من القيم الأخرى.

## ملخص من جملة واحدة
تعتبر "default" كلمة محجوزة في JAVA تُستخدم لتعريف تنفيذات افتراضية في الواجهات ولتحديد سلوك افتراضي في عبارات switch.