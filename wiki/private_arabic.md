<!--
Meta Description: # الخاصية "private" في لغة JAVA: الخصوصية في البرمجة ## ملخص تعتبر الخاصية "private" في لغة JAVA واحدة من أهم أدوات التحكم في الوصول، حيث تحدد مستوى ا...
Meta Keywords: private, إلى, الوصول, المتغيرات, استخدام
-->

# الخاصية "private" في لغة JAVA: الخصوصية في البرمجة

## ملخص
تعتبر الخاصية "private" في لغة JAVA واحدة من أهم أدوات التحكم في الوصول، حيث تحدد مستوى الرؤية والقدرة على الوصول إلى المتغيرات والطرق في الكائنات.

## الوثائق
تستخدم "private" لتحديد عناصر البيانات (المتغيرات) والطرق (الدوال) التي لا يمكن الوصول إليها إلا من داخل نفس الفئة. هذا الأمر يساعد في حماية البيانات من التلاعب الخارجي، ويعزز مبادئ البرمجة كائنية التوجه (OOP) مثل التجريد والتغليف.

### الغرض
- حماية البيانات: تمنع الوصول غير المصرح به إلى المتغيرات.
- تعزيز الأمان: تقييد استخدام بعض الوظائف أو المتغيرات لضمان عدم التلاعب بها من قبل المستخدمين أو الفئات الأخرى.

### الاستخدام
يمكن استخدام "private" مع المتغيرات أو الطرق داخل الفئة كما يلي:

```java
class MyClass {
    private int privateVariable;

    private void privateMethod() {
        System.out.println("This is a private method.");
    }
}
```

## أمثلة
### مثال 1: استخدام "private" مع المتغيرات

```java
class Person {
    private String name;

    public Person(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }
}

// في الدالة الرئيسية
public class Main {
    public static void main(String[] args) {
        Person person = new Person("Ali");
        System.out.println(person.getName()); // يمكن الوصول إلى الاسم عبر الطريقة العامة
        // System.out.println(person.name); // سيؤدي إلى خطأ في الترجمة
    }
}
```

### مثال 2: استخدام "private" مع الطرق

```java
class Calculator {
    private int add(int a, int b) {
        return a + b;
    }

    public int calculateSum(int a, int b) {
        return add(a, b); // يمكن استدعاء الطريقة الخاصة من داخل نفس الفئة
    }
}

// في الدالة الرئيسية
public class Main {
    public static void main(String[] args) {
        Calculator calc = new Calculator();
        System.out.println(calc.calculateSum(5, 10)); // يطبع 15
        // System.out.println(calc.add(5, 10)); // سيؤدي إلى خطأ في الترجمة
    }
}
```

## الشرح
### الأخطاء الشائعة
- **محاولة الوصول إلى المتغيرات أو الطرق الخاصة من خارج الفئة**: سيؤدي ذلك إلى أخطاء في الترجمة، لذا يجب استخدام الطرق العامة للوصول إلى الخصائص الخاصة.
- **عدم فهم أهمية التغليف**: قد يعتقد البعض أن استخدام "private" غير ضروري، ولكنها تمثل جزءًا أساسيًا من تصميم البرمجيات الجيد.

### ملاحظات إضافية
- يمكن استخدام "private" مع الفئات الداخلية (inner classes) أيضًا، مما يزيد من مستوى الخصوصية.
- تذكر أن "private" لا تمنع الوصول إلى البيانات عبر الفئات الفرعية (subclasses) إذا كانت هذه الفئات ضمن نفس الحزمة (package).

## ملخص من جملة واحدة
"private" في لغة JAVA هي أداة تحكم وصول حيوية تضمن حماية البيانات من الوصول غير المصرح به وتعزز من الأمان في البرمجة كائنية التوجه.