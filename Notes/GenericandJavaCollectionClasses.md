# 🧬 Java Generics: A Comprehensive Guide

![Java Generics](https://img.shields.io/badge/Java-Generics-orange?style=for-the-badge&logo=java)

## 📋 Table of Contents
- [Introduction](#-introduction)
- [Benefits of Generics](#-benefits-of-generics)
- [Generic Classes](#-generic-classes)
- [Generic Methods](#-generic-methods)
- [Bounded Type Parameters](#-bounded-type-parameters)
- [Wildcards](#-wildcards)
- [Type Erasure](#-type-erasure)
- [Restrictions on Generics](#-restrictions-on-generics)
- [Best Practices](#-best-practices)
- [Advanced Topics](#-advanced-topics)
- [Conclusion](#-conclusion)

## 🌟 Introduction

Generics in Java allow you to create classes, interfaces, and methods that operate on objects of various types while providing compile-time type safety. They were introduced in Java 5 to enhance code reusability and type checking.

## 🎁 Benefits of Generics

1. 🛡️ **Type Safety**: Detect type-related errors at compile-time rather than runtime.
2. 🚫 **Elimination of Casts**: Reduce explicit type casting in your code.
3. 🔧 **Enable Generic Algorithms**: Implement algorithms that work on different types.

## 📦 Generic Classes

Generic classes allow you to parameterize the types used within the class.

```java
public class Box<T> {
    private T content;

    public void set(T content) {
        this.content = content;
    }

    public T get() {
        return content;
    }
}

// Usage
Box<Integer> intBox = new Box<>();
intBox.set(10);
Integer value = intBox.get(); // No casting needed
```

### 🔑 Key Points:
- Use `<T>` to declare a type parameter.
- `T` can be replaced with any valid Java identifier.
- You can use multiple type parameters: `class Pair<K, V> { ... }`

## 🛠️ Generic Methods

Generic methods allow you to introduce type parameters bound to a particular method.

```java
public static <E> void printArray(E[] array) {
    for (E element : array) {
        System.out.print(element + " ");
    }
    System.out.println();
}

// Usage
Integer[] intArray = { 1, 2, 3, 4, 5 };
Double[] doubleArray = { 1.1, 2.2, 3.3, 4.4 };
printArray(intArray);     // Outputs: 1 2 3 4 5
printArray(doubleArray);  // Outputs: 1.1 2.2 3.3 4.4
```

### 🔑 Key Points:
- The type parameter `<E>` is declared before the return type.
- Generic methods can be static or non-static.
- They can be declared in non-generic classes.

## 🔒 Bounded Type Parameters

Bounded type parameters allow you to restrict the types that can be used as type arguments.

```java
public <T extends Comparable<T>> T findMax(T x, T y, T z) {
    T max = x;
    if (y.compareTo(max) > 0) max = y;
    if (z.compareTo(max) > 0) max = z;
    return max;
}

// Usage
System.out.println(findMax(3, 7, 1));           // Outputs: 7
System.out.println(findMax("apple", "pear", "orange")); // Outputs: pear
```

### 🔑 Key Points:
- Use `extends` keyword for upper bounds (both classes and interfaces).
- You can have multiple bounds: `<T extends Number & Comparable<T>>`

## 🃏 Wildcards

Wildcards represent unknown types and are useful for creating flexible methods.

1. **Unbounded Wildcard**: `<?>`
2. **Upper Bounded Wildcard**: `<? extends T>`
3. **Lower Bounded Wildcard**: `<? super T>`

```java
// Unbounded Wildcard
public static void printList(List<?> list) {
    for (Object elem : list) {
        System.out.print(elem + " ");
    }
    System.out.println();
}

// Upper Bounded Wildcard
public static double sumOfList(List<? extends Number> list) {
    double sum = 0.0;
    for (Number num : list) {
        sum += num.doubleValue();
    }
    return sum;
}

// Lower Bounded Wildcard
public static void addNumbers(List<? super Integer> list) {
    for (int i = 1; i <= 10; i++) {
        list.add(i);
    }
}
```

### 🔑 Key Points:
- Use unbounded wildcards when you only care about the most general methods.
- Upper bounded wildcards allow reading from the list.
- Lower bounded wildcards allow writing to the list.

## 🔮 Type Erasure

Type erasure is the process by which the Java compiler removes all type parameters and replaces them with their bounds or Object if the type parameters are unbounded.

```java
// Before type erasure
public class Box<T> {
    private T t;
    public void set(T t) { this.t = t; }
    public T get() { return t; }
}

// After type erasure
public class Box {
    private Object t;
    public void set(Object t) { this.t = t; }
    public Object get() { return t; }
}
```

### 🔑 Key Points:
- Generics are a compile-time feature; at runtime, all generic types are erased.
- This ensures backwards compatibility with pre-generics code.

## 🚫 Restrictions on Generics

1. Cannot instantiate generic types with primitive types
   ```java
   List<int> list = new ArrayList<>(); // Compile-time error
   List<Integer> list = new ArrayList<>(); // OK
   ```

2. Cannot create instances of type parameters
   ```java
   public static <E> void append(List<E> list) {
       E elem = new E();  // Compile-time error
       list.add(elem);
   }
   ```

3. Cannot declare static fields whose types are type parameters
   ```java
   public class MobileDevice<T> {
       private static T os;  // Compile-time error
   }
   ```

4. Cannot use instanceof with generic types
   ```java
   if (obj instanceof List<String>) { } // Compile-time error
   if (obj instanceof List<?>) { } // OK
   ```

## 💡 Best Practices

1. 🎯 Use generics in your code to achieve type safety and reduce casting.
2. 📝 Always specify the type parameter when declaring a variable of generic type.
3. 🔄 Use bounded type parameters to increase API flexibility.
4. 🃏 Understand and use wildcards appropriately.
5. 🏗️ Design your APIs to be as flexible as possible by using generics.

## 🚀 Advanced Topics

1. **Recursive Type Bounds**: 
   ```java
   <T extends Comparable<T>>
   ```

2. **Type Inference**: 
   Java can often infer the type arguments for you.
   ```java
   Map<String, List<String>> myMap = new HashMap<>(); // Diamond operator
   ```

3. **Generic Type Inheritance**: 
   Generic classes can extend other generic classes.
   ```java
   class NumberBox<T extends Number> extends Box<T> { ... }
   ```

## 🎓 Conclusion

Generics are a powerful feature in Java that provide increased type safety and code reusability. By allowing classes and methods to operate on objects of various types while providing compile-time type checking, generics help catch errors early in the development process. While they come with some complexities and restrictions, mastering generics is crucial for writing robust and flexible Java code.

Remember:
- 🛡️ Use generics to enhance type safety
- 🔧 Leverage generic methods for flexible algorithms
- 🔒 Utilize bounded type parameters when you need to restrict type arguments
- 🃏 Understand and apply wildcards appropriately
- 🏗️ Design your APIs with generics in mind for maximum flexibility

Happy coding with generics! 💻🚀
