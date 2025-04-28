<!--
Meta Description: # Java 中的 `requires` 关键字详解 ## 概述 在 Java 的模块系统中，`requires` 关键字用于声明一个模块对另一个模块的依赖关系。这一特性自 Java 9 引入，旨在增强模块化编程的能力，使得开发者能够更好地管理大型应用程序的依赖性。 ## 文档 `requires`...
Meta Keywords: requires, java, module, info, sql
-->

# Java 中的 `requires` 关键字详解

## 概述
在 Java 的模块系统中，`requires` 关键字用于声明一个模块对另一个模块的依赖关系。这一特性自 Java 9 引入，旨在增强模块化编程的能力，使得开发者能够更好地管理大型应用程序的依赖性。

## 文档
`requires` 关键字的主要作用是指定当前模块所依赖的其他模块。这在 Java 模块系统（JPMS）中非常重要，因为它帮助定义模块之间的关系，确保所需的模块在编译和运行时可用。

### 用法
在模块描述文件 `module-info.java` 中使用 `requires` 来声明依赖关系。基本语法如下：

```java
module moduleName {
    requires dependencyModuleName;
}
```

### 细节
- **依赖性**: 使用 `requires` 声明的模块在当前模块运行时必须可用。
- **可选依赖**: 可以使用 `requires static` 来声明编译时依赖，但在运行时不需要该模块。
- **模块版本**: Java 9 及以上版本支持指定模块版本，例如 `requires some.module; // 定义无版本要求`。

## 示例
以下是一个简单的示例，展示如何在 `module-info.java` 中使用 `requires`。

```java
module my.application {
    requires java.sql; // 依赖 java.sql 模块
    requires static org.slf4j; // 编译时依赖 org.slf4j 模块
}
```

在这个例子中，`my.application` 模块依赖于 `java.sql` 模块，并且在编译时依赖于 `org.slf4j` 模块，但在运行时不需要它。

## 解释
- **常见问题**: 开发者常常在声明依赖时忘记加上 `requires` 关键字，导致编译错误。确保在每个模块的 `module-info.java` 文件中正确声明所有必要的依赖。
- **模块冲突**: 如果两个模块之间存在冲突，可能会导致运行时异常。使用 `requires transitive` 可以解决某些传递依赖的问题。
- **可见性**: 通过 `requires` 声明的模块对当前模块可见，但不一定对其他模块可见。使用 `exports` 关键字可以控制模块的可见性。

## 一句话总结
`requires` 关键字在 Java 模块系统中用于声明模块之间的依赖关系，是实现模块化编程的核心功能。