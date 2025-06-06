<!--
Meta Description: # التعداد (enum) في جافا: كل ما تحتاج معرفته ## الملخص تعتبر التعدادات (enums) في جافا نوعًا خاصًا من الفئات، حيث تسمح لك بتعريف مجموعة من القيم الثاب...
Meta Keywords: التعداد, التعدادات, مما, استخدام, double
-->

# التعداد (enum) في جافا: كل ما تحتاج معرفته

## الملخص
تعتبر التعدادات (enums) في جافا نوعًا خاصًا من الفئات، حيث تسمح لك بتعريف مجموعة من القيم الثابتة، مما يسهل التعامل مع الثوابت ويزيد من وضوح الكود.

## الوثائق
### الغرض
التعدادات في جافا تهدف إلى تحسين القابلية للقراءة والصيانة في الكود من خلال توفير طريقة لتعريف مجموعة من الثوابت ذات الصلة. عن طريق استخدام التعدادات، يمكنك تقليل الأخطاء الناتجة عن استخدام القيم السحرية (magic numbers) في الشيفرة.

### الاستخدام
يمكن تعريف التعداد باستخدام الكلمة الرئيسية `enum`. يمكن للتعداد أن يحتوي على متغيرات، طرق، وحتى بنى داخلية. على سبيل المثال:

```java
public enum Day {
    SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY
}
```

### التفاصيل
يتمتع التعداد بالعديد من الميزات مثل:
- **التقوية النوعية**: يوفر التعداد نوعًا محددًا، مما يمنع استخدام القيم غير الصحيحة.
- **الدوال**: يمكنك إضافة دوال إلى التعداد لتعزيز وظيفته.
- **الخصائص**: يمكنك إضافة خصائص لكل عنصر في التعداد، مما يمنحك مرونة أكبر.

## الأمثلة
### مثال 1: تعريف واستخدام تعداد بسيط
```java
public enum Color {
    RED, GREEN, BLUE
}

// استخدام التعداد
Color myColor = Color.RED;
```

### مثال 2: إضافة دوال إلى التعداد
```java
public enum Planet {
    MERCURY(3.303e+20, 2.4397e6),
    VENUS(4.869e+24, 6.0518e6),
    EARTH(5.976e+24, 6.37814e6);

    private final double mass;   // في كيلوجرامات
    private final double radius;  // في أمتار

    Planet(double mass, double radius) {
        this.mass = mass;
        this.radius = radius;
    }

    public double mass() { return mass; }
    public double radius() { return radius; }
}
```

## الشرح
### الأخطاء الشائعة
- **عدم استخدام التعدادات**: قد يلجأ المبرمجون لاستخدام الثوابت التقليدية بدلاً من التعدادات، مما يؤدي إلى كود أقل وضوحًا وأعلى عرضة للأخطاء.
- **تعديل عناصر التعداد**: لا يمكن تعديل عناصر التعداد بعد تعريفها، لذا يجب الحرص على تحديد العناصر بشكل صحيح منذ البداية.

### ملاحظات إضافية
- يمكن استخدام التعدادات كنوع من أنواع البيانات في العبارات الشرطية، مما يسهل من عملية التحقق من القيم.
- التعدادات تدعم التكرار (iteration) بسهولة باستخدام `values()`.

## ملخص من سطر واحد
التعدادات في جافا توفر وسيلة فعالة لتعريف مجموعة من الثوابت، مما يحسن من وضوح الكود ويقلل الأخطاء.