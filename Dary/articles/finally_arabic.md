<!--
Meta Description: # استخدام الكلمة المفتاحية "finally" في لغة JAVA ## نظرة عامة الكلمة المفتاحية "finally" في لغة JAVA هي جزء من معالجة الاستثناءات، حيث تُستخدم لضمان ت...
Meta Keywords: finally, try, catch, استخدام, تنفيذ
-->

# استخدام الكلمة المفتاحية "finally" في لغة JAVA

## نظرة عامة
الكلمة المفتاحية "finally" في لغة JAVA هي جزء من معالجة الاستثناءات، حيث تُستخدم لضمان تنفيذ كود معين بعد انتهاء كتلة try أو catch، بغض النظر عما إذا تم رمي استثناء أم لا. تُعتبر "finally" أداة مهمة للحفاظ على نظافة الموارد وإغلاقها بشكل مناسب.

## الوثائق
### الغرض
الغرض من استخدام "finally" هو ضمان تنفيذ كود محدد بعد محاولة تنفيذ كود قد يُسبب استثناء. تُستخدم عادةً لإغلاق الموارد مثل الملفات أو قواعد البيانات، مما يضمن تحرير هذه الموارد حتى في حالة حدوث خطأ.

### الاستخدام
تظهر "finally" في بنية try-catch-finally. تُكتب بعد كتلتي try و catch، ويُسمح بوجود كتلة finally واحدة فقط لكل كتلة try. يمكن استخدام "finally" دون "catch"، لكن لا يمكن استخدام "catch" دون "finally" في حالة وجود "try".

### التفاصيل
- **الصياغة**:
    ```java
    try {
        // كود قد يُسبب استثناء
    } catch (استثناء e) {
        // معالجة الاستثناء
    } finally {
        // كود للتنفيذ دائمًا
    }
    ```
- **ملاحظة**: إذا كان هناك استثناء غير مُعالج في كتلة try، فلن يتم تنفيذ كود finally إذا كان JVM مُنتهياً.

## أمثلة
### مثال 1: استخدام finally مع try و catch
```java
public class FinallyExample {
    public static void main(String[] args) {
        try {
            int result = 10 / 0; // سيؤدي إلى استثناء ArithmeticException
        } catch (ArithmeticException e) {
            System.out.println("تم التقاط استثناء: " + e.getMessage());
        } finally {
            System.out.println("تم تنفيذ كتلة finally.");
        }
    }
}
```
**الناتج**:
```
تم التقاط استثناء: / by zero
تم تنفيذ كتلة finally.
```

### مثال 2: استخدام finally مع موارد
```java
import java.io.FileWriter;
import java.io.IOException;

public class FileWriterExample {
    public static void main(String[] args) {
        FileWriter writer = null;
        try {
            writer = new FileWriter("file.txt");
            writer.write("Hello, World!");
        } catch (IOException e) {
            System.out.println("خطأ في الكتابة: " + e.getMessage());
        } finally {
            try {
                if (writer != null) {
                    writer.close();
                    System.out.println("تم إغلاق كاتب الملف.");
                }
            } catch (IOException e) {
                System.out.println("خطأ في إغلاق الكاتب: " + e.getMessage());
            }
        }
    }
}
```
**الناتج**:
```
تم إغلاق كاتب الملف.
```

## الشرح
### النقاط الشائعة
- **عدم تنفيذ finally**: إذا تم إنهاء JVM قبل تنفيذ finally، مثل استخدام `System.exit()`.
- **عدم استخدام finally في حالة عدم الحاجة**: إذا كنت متأكدًا من عدم وجود استثناءات، فإن استخدام finally قد يكون غير ضروري.
- **أداء**: استخدام finally يؤدي إلى تحسين إدارة الموارد، لكن يجب استخدامه بحذر لتجنب الكود غير الضروري.

## ملخص من سطر واحد
تضمن الكلمة المفتاحية "finally" في JAVA تنفيذ كود معين بعد كتلة try أو catch، مما يساعد في إدارة الموارد بشكل فعال.