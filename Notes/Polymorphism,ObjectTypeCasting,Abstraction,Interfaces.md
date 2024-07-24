# 🦜 Polymorphism, Object Type Casting, Abstraction, and Interfaces in Java

![Java OOP](https://img.shields.io/badge/Java-OOP-blue?style=for-the-badge&logo=java)

## 📋 Table of Contents
- [Introduction](#-introduction)
- [Polymorphism](#-polymorphism)
  - [What is Polymorphism?](#-what-is-polymorphism)
  - [Types of Polymorphism](#-types-of-polymorphism)
  - [Method Overloading Example](#-method-overloading-example)
  - [Method Overriding Example](#-method-overriding-example)
- [Object Type Casting](#-object-type-casting)
  - [Upcasting](#-upcasting)
  - [Downcasting](#-downcasting)
- [Abstraction](#-abstraction)
  - [What is Abstraction?](#-what-is-abstraction)
  - [Abstract Classes](#-abstract-classes)
  - [Abstract Class Example](#-abstract-class-example)
  - [Key Points about Abstract Classes](#-key-points-about-abstract-classes)
- [Interfaces](#-interfaces)
  - [What are Interfaces?](#-what-are-interfaces)
  - [Interface Example](#-interface-example)
  - [Key Points about Interfaces](#-key-points-about-interfaces)
  - [Functional Interfaces](#-functional-interfaces)
- [Abstract Classes vs Interfaces](#-abstract-classes-vs-interfaces)
- [Best Practices](#-best-practices)
- [Conclusion](#-conclusion)
- [Resources](#-resources)

## 🌟 Introduction

Polymorphism, object type casting, abstraction, and interfaces are fundamental concepts in object-oriented programming (OOP) that allow for code flexibility, reusability, and modularity. This README explores these concepts in the context of Java programming.

## 🦜 Polymorphism

### 🤔 What is Polymorphism?

Polymorphism means "many forms". In Java, it allows objects of different types to be treated as objects of a common parent type. This is achieved through inheritance.

### 🌿 Types of Polymorphism

1. **Compile-time Polymorphism (Static Binding)**
   - Achieved through method overloading
   - Method resolution occurs at compile-time
2. **Runtime Polymorphism (Dynamic Binding)**
   - Achieved through method overriding  
   - Method resolution occurs at runtime

### 💡 Method Overloading Example

```java
public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }

    public double add(double a, double b) {
        return a + b;
    }

    public int add(int a, int b, int c) {
        return a + b + c;  
    }
}
```

### 💡 Method Overriding Example

```java
class Animal {
    public void makeSound() {
        System.out.println("The animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    public void makeSound() {
        System.out.println("The dog barks"); 
    }
}

// Usage
Animal myPet = new Dog();
myPet.makeSound();  // Outputs: The dog barks
```

## 🎭 Object Type Casting

Type casting treats an object of one type as an object of another type.

### ⬆️ Upcasting

Upcasting casts a subclass to a superclass. It's done implicitly by Java.

```java
Dog myDog = new Dog();
Animal myAnimal = myDog;  // Upcasting, no explicit cast needed
```

### ⬇️ Downcasting

Downcasting casts a superclass to a subclass. It requires an explicit cast and should be used with `instanceof` to avoid `ClassCastException`.

```java
Animal myAnimal = new Dog();
if (myAnimal instanceof Dog) {
    Dog myDog = (Dog) myAnimal;  // Downcasting, explicit cast 
    myDog.bark();
}
```

## 🎭 Abstraction

### 🤔 What is Abstraction?

Abstraction hides the implementation details and shows only the functionality to the user. It's achieved through abstract classes and interfaces.

### 🖌️ Abstract Classes

An abstract class is declared with the `abstract` keyword. It may contain abstract and non-abstract methods.

### 💡 Abstract Class Example

```java
public abstract class Shape {
    protected String color;

    public abstract double calculateArea();

    public void setColor(String color) {
        this.color = color;
    }
}

public class Circle extends Shape {
    private double radius;

    public Circle(double radius) {
        this.radius = radius;
    }

    @Override 
    public double calculateArea() {
        return Math.PI * radius * radius;
    }
}
```

### ✅ Key Points about Abstract Classes

- Cannot be instantiated
- May contain abstract and non-abstract methods
- Can have constructors and static methods
- Can have final methods to prevent overriding

## 🔌 Interfaces  

### 🤔 What are Interfaces?

An interface is a completely abstract class that contains only abstract methods. As of Java 8, it can also have default and static methods.

### 💡 Interface Example

```java
public interface Drawable {
    void draw();
    
    default void print() {
        System.out.println("Printing...");
    }

    static void staticMethod() { 
        System.out.println("Static method in interface");
    }
}

public class Rectangle implements Drawable {
    @Override
    public void draw() {
        System.out.println("Drawing a rectangle");  
    }
}
```

### ✅ Key Points about Interfaces

- All methods are public and abstract by default
- All variables are public, static, and final by default
- A class can implement multiple interfaces
- As of Java 8, interfaces can have default and static methods
- As of Java 9, interfaces can have private methods

### 🔧 Functional Interfaces

A functional interface is an interface with exactly one abstract method. They're used with lambda expressions.

```java
@FunctionalInterface
public interface Runnable {
    void run();
}

// Usage with lambda expression
Runnable r = () -> System.out.println("Hello World"); 
```

## 🆚 Abstract Classes vs Interfaces

| Feature | Abstract Class | Interface |
|---------|----------------|-----------|
| Methods | Can have abstract and non-abstract methods | All methods are abstract by default (can have default and static methods as of Java 8) |
| Variables | Can have non-static and non-final variables | Variables are static and final by default |
| Constructor | Can have a constructor | Cannot have a constructor |
| Multiple Inheritance | A class can extend only one abstract class | A class can implement multiple interfaces |
| Access Modifiers | Can use any access modifier for members | Members are public by default |

## ✅ Best Practices

1. Use interfaces to define types that can be implemented by unrelated classes
2. Use abstract classes to define incomplete types that have a common base implementation
3. Prefer interfaces over abstract classes when possible 
4. Use the `instanceof` operator before downcasting to avoid `ClassCastException`
5. Design with the "Program to an interface, not an implementation" principle

## 🎓 Conclusion

Polymorphism, object type casting, abstraction, and interfaces are essential tools in Java for creating flexible, reusable, and maintainable code. Polymorphism allows treating objects of different types uniformly. Type casting enables safe conversion between types. Abstraction through abstract classes and interfaces helps in defining contracts and hiding implementation details. Mastering these concepts is key to effective object-oriented design and programming in Java.

## 📚 Resources

- [Java Tutorials - Polymorphism](https://docs.oracle.com/javase/tutorial/java/IandI/polymorphism.html)
- [Java Tutorials - Abstract Classes and Interfaces](https://docs.oracle.com/javase/tutorial/java/IandI/abstract.html)
- [Java 8 Interfaces](https://www.baeldung.com/java-8-new-features)

Happy coding! 💻🚀
