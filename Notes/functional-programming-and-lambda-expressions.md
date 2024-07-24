# 🌿 Functional Programming and Lambda Expressions in Java

![Java Functional Programming](https://img.shields.io/badge/Java-Functional%20Programming-green?style=for-the-badge&logo=java)

## 📋 Table of Contents
- [Introduction](#-introduction)
- [Key Concepts](#-key-concepts)
- [Lambda Expressions](#-lambda-expressions)
  - [Syntax](#-syntax)
  - [Examples](#-examples)
- [Functional Interfaces](#-functional-interfaces)
  - [Common Functional Interfaces](#-common-functional-interfaces)
- [Method References](#-method-references)
  - [Types of Method References](#-types-of-method-references)
  - [Examples](#-examples-1)
- [Streams API](#-streams-api)
  - [Key Stream Operations](#-key-stream-operations)
  - [Example](#-example)
- [Optional Class](#-optional-class)
- [Default Methods in Interfaces](#-default-methods-in-interfaces)
- [Benefits of Functional Programming](#-benefits-of-functional-programming)
- [Best Practices](#-best-practices)
- [Conclusion](#-conclusion)
- [Resources](#-resources)

## 🌟 Introduction

Functional Programming is a programming paradigm that emphasizes the application of functions to inputs to produce outputs without changing state and mutable data. Java 8 introduced several features to support functional programming, including lambda expressions, functional interfaces, method references, and the Stream API.

## 🔑 Key Concepts

1. **First-class functions**: Functions can be assigned to variables, passed as arguments, or returned from other functions.
2. **Pure functions**: Functions that always produce the same output for the same input and have no side effects.
3. **Immutability**: Once created, objects cannot be changed.
4. **Declarative programming**: Focusing on what to solve rather than how to solve it.

## 💡 Lambda Expressions

Lambda expressions provide a clear and concise way to represent one method interface using an expression. They are anonymous functions that can be used to implement a functional interface.

### 🛠️ Syntax

```java
(parameters) -> expression
```

or

```java
(parameters) -> { statements; }
```

### 📝 Examples

```java
// Simple lambda expression
Runnable r = () -> System.out.println("Hello World");

// Lambda with parameters
Comparator<String> c = (s1, s2) -> s1.compareToIgnoreCase(s2);

// Lambda with multiple statements
ActionListener listener = event -> {
    System.out.println("Button clicked!");
    System.out.println("Performing action...");
};
```

## 🔌 Functional Interfaces

A functional interface is an interface that contains exactly one abstract method. Java 8 introduced several built-in functional interfaces in the `java.util.function` package.

### 🧩 Common Functional Interfaces

1. **Function<T,R>**: Represents a function that accepts one argument and produces a result.
2. **Predicate<T>**: Represents a predicate (boolean-valued function) of one argument.
3. **Consumer<T>**: Represents an operation that accepts a single input argument and returns no result.
4. **Supplier<T>**: Represents a supplier of results.

## 🔍 Method References

Method references provide a way to refer to methods or constructors without executing them. They can be seen as shorthand for certain lambda expressions.

### 🌿 Types of Method References

1. Reference to a static method: `ContainingClass::staticMethodName`
2. Reference to an instance method of a particular object: `containingObject::instanceMethodName`
3. Reference to an instance method of an arbitrary object of a particular type: `ContainingType::methodName`
4. Reference to a constructor: `ClassName::new`

### 📝 Examples

```java
// Static method reference
Function<String, Integer> parseInt = Integer::parseInt;

// Instance method reference
String str = "Hello";
Supplier<String> upperCase = str::toUpperCase;

// Constructor reference
Supplier<List<String>> listSupplier = ArrayList::new;
```

## 🌊 Streams API

The Stream API is used to process collections of objects. A stream is a sequence of objects that supports various methods which can be pipelined to produce the desired result.

### 🔑 Key Stream Operations

1. **Intermediate Operations**: These operations return a new stream. They are always lazy.
   - `filter()`, `map()`, `flatMap()`, `distinct()`, `sorted()`, `peek()`, `limit()`, `skip()`

2. **Terminal Operations**: These operations produce a result or a side-effect. They are eager.
   - `forEach()`, `collect()`, `reduce()`, `count()`, `min()`, `max()`, `findFirst()`, `findAny()`, `anyMatch()`, `allMatch()`, `noneMatch()`

### 📝 Example

```java
List<String> names = Arrays.asList("Alice", "Bob", "Charlie", "David");

List<String> filteredNames = names.stream()
    .filter(name -> name.startsWith("C"))
    .map(String::toUpperCase)
    .collect(Collectors.toList());

System.out.println(filteredNames); // Output: [CHARLIE]
```

## 🎁 Optional Class

Optional is a container object used to contain not-null objects. It's used to represent null with absent value.

```java
Optional<String> optional = Optional.of("Hello");
System.out.println(optional.isPresent()); // Output: true
System.out.println(optional.get()); // Output: Hello

Optional<String> empty = Optional.empty();
System.out.println(empty.orElse("World")); // Output: World
```

## 🔧 Default Methods in Interfaces

Java 8 allows interfaces to have default methods with implementation.

```java
interface Vehicle {
    default void start() {
        System.out.println("Starting vehicle");
    }
}

class Car implements Vehicle {
    // Can use the default implementation or override it
}
```

## 🌟 Benefits of Functional Programming

1. More concise and readable code
2. Easier parallel programming
3. Improved code reusability
4. Encourages immutability, which leads to safer and more predictable code
5. Better support for declarative programming

## ✅ Best Practices

1. Keep lambda expressions short and readable
2. Use method references when possible for cleaner code
3. Prefer the use of standard functional interfaces
4. Use streams for processing collections when appropriate
5. Leverage the power of Optional to handle null values
6. Make use of default methods in interfaces to provide default behavior

## 🎓 Conclusion

Functional programming and lambda expressions in Java provide powerful tools for writing more concise, maintainable, and potentially more efficient code. By embracing these concepts, Java developers can write cleaner code, improve performance through easier parallelization, and adopt a more declarative programming style. As with any programming paradigm, it's important to understand when and how to apply these concepts effectively in your Java applications.

## 📚 Resources

- [Java 8 Lambdas and Streams](https://www.oracle.com/technical-resources/articles/java/architect-lambdas-streams.html)
- [Java Functional Interfaces](https://www.baeldung.com/java-8-functional-interfaces)
- [Java 8 Stream API Tutorial](https://www.mkyong.com/java8/java-8-streams-introduction/)

Happy functional programming! 💻🚀
