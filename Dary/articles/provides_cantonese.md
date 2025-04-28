<!--
Meta Description: # Java 中的 "provides" 關鍵字 ## 簡介 "provides" 是 Java 9 中引入的模塊系統 (Module System) 的一部分，主要用於定義模塊所提供的服務接口。這一特性使得模塊之間的依賴關係更加明確，並促進了代碼的重用和管理。 ## 文檔 在 Java 中，模塊是...
Meta Keywords: java, provides, com, example, module
-->

# Java 中的 "provides" 關鍵字

## 簡介
"provides" 是 Java 9 中引入的模塊系統 (Module System) 的一部分，主要用於定義模塊所提供的服務接口。這一特性使得模塊之間的依賴關係更加明確，並促進了代碼的重用和管理。

## 文檔
在 Java 中，模塊是用來組織代碼的單位，"provides" 關鍵字用來聲明一個模塊所提供的服務。這樣可以讓其他模塊依賴這些服務，而不必關心具體的實現類。這是通過在模塊描述文件 (`module-info.java`) 中使用 "provides" 來實現的。

### 目的
"provides" 主要是幫助開發者定義模塊所提供的服務接口，並與其相應的實現類進行關聯，從而實現依賴注入。

### 使用方法
在您模塊的 `module-info.java` 文件中，您可以使用以下語法來聲明提供的服務：
```java
provides <ServiceType> with <ImplementationClass>;
```
- `<ServiceType>` 是您要提供的服務接口。
- `<ImplementationClass>` 是實現該服務接口的具體類。

## 範例
以下是一個簡單的示例，展示如何使用 "provides" 來聲明服務：

```java
// module-info.java
module com.example.myModule {
    provides com.example.MyService with com.example.MyServiceImpl;
}

// MyService.java
package com.example;

public interface MyService {
    void performService();
}

// MyServiceImpl.java
package com.example;

public class MyServiceImpl implements MyService {
    @Override
    public void performService() {
        System.out.println("Service is being performed.");
    }
}
```

在上述代碼中，`com.example.myModule` 模塊提供了 `MyService` 接口的實現 `MyServiceImpl`。

## 解釋
使用 "provides" 時，開發者應注意以下幾點：
- **模塊依賴**: 確保依賴的模塊已正確聲明，否則會導致編譯錯誤。
- **多重實現**: 如果有多個實現提供同一服務接口，Java 會根據排序（如果有定義）來選擇具體的實現。
- **查找服務**: 使用 `ServiceLoader` 可以動態加載服務實現，這樣可以在運行時根據需要選擇不同的實現。
- **版本兼容**: 不同版本的服務實現可能會導致不兼容問題，需謹慎管理版本。

## 一句總結
"provides" 關鍵字在 Java 模塊系統中用於聲明模塊所提供的服務接口及其實現，促進了代碼的重用和依賴管理。