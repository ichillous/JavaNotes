# 🔒🌿 Java Encapsulation and Inheritance

![Java OOP](https://img.shields.io/badge/Java-OOP-blue?style=for-the-badge&logo=java)

## 📋 Table of Contents
- [Introduction](#-introduction)
- [Encapsulation](#-encapsulation)
  - [What is Encapsulation?](#-what-is-encapsulation)
  - [Applying Encapsulation](#-applying-encapsulation)
  - [Encapsulation Example](#-encapsulation-example)
  - [Why Use Encapsulation?](#-why-use-encapsulation)
- [Inheritance](#-inheritance)
  - [What is Inheritance?](#-what-is-inheritance)
  - [Inheritance Concepts](#-inheritance-concepts)
  - [Types of Inheritance in Java](#-types-of-inheritance-in-java)
  - [Inheritance Example](#-inheritance-example) 
  - [Key Features of Inheritance](#-key-features-of-inheritance)
  - [instanceof Operator](#-instanceof-operator)
  - [Inheritance Best Practices](#-inheritance-best-practices)
  - [Pitfalls of Inheritance](#-pitfalls-of-inheritance)
- [Conclusion](#-conclusion)
- [Resources](#-resources)

## 🌟 Introduction

Object-oriented programming (OOP) is a paradigm that organizes software design around objects, which are instances of classes. Encapsulation and inheritance are two of the four fundamental concepts in OOP (along with abstraction and polymorphism). They help create code that is modular, reusable, and easy to maintain. This README explores encapsulation and inheritance in the context of Java programming.

## 📦 Encapsulation

### 🤔 What is Encapsulation?

Encapsulation is the practice of bundling data and methods that operate on that data within a single unit, i.e., a class in Java. The goal is to hide the internal state of an object from the outside world.

### ✅ Applying Encapsulation

To apply encapsulation in Java:

1. Declare the variables of a class as `private`. This prevents direct access from outside the class.
2. Provide `public` getter and setter methods to retrieve and modify the values of these private variables.

### 💡 Encapsulation Example

```java
public class BankAccount {
    private double balance;
    private String accountNumber;

    public BankAccount(String accountNumber, double initialBalance) {
        this.accountNumber = accountNumber;
        this.balance = initialBalance;
    }

    public double getBalance() {
        return balance;
    }

    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }

    public void withdraw(double amount) {
        if (amount > 0 && balance >= amount) {
            balance -= amount;  
        }
    }
}
```

### 🤷‍♀️ Why Use Encapsulation?

Encapsulation provides several benefits:

1. 🕵️‍♂️ **Data Hiding**: The internal state of the object is hidden from the outside world, protecting it from unauthorized access.
2. 🔧 **Flexibility**: The internal implementation can be changed without affecting the code that uses the class.
3. ♻️ **Maintainability**: Encapsulated code is easier to maintain and refactor.

## 🌳 Inheritance  

### 🤔 What is Inheritance?

Inheritance is a mechanism where one class acquires properties (methods and fields) of another class. It allows you to create new classes that are built upon existing classes.

### 🧩 Inheritance Concepts

- **Superclass**: The class whose properties are inherited. Also called the parent or base class.
- **Subclass**: The class that inherits the properties of another class. Also called the child or derived class.  

### 🌿 Types of Inheritance in Java

1. **Single Inheritance**: A subclass inherits from a single superclass.
2. **Multilevel Inheritance**: A subclass inherits from a superclass, which itself inherits from another class, and so on.
3. **Hierarchical Inheritance**: Multiple subclasses inherit from a single superclass.

Note: Java does not support multiple inheritance of classes, but it does support multiple inheritance of interfaces.

### 💡 Inheritance Example

```java
public class Animal {
    protected String name;
    public void eat() {
        System.out.println(name + " is eating.");
    }
}

public class Dog extends Animal {
    private String breed;

    public Dog(String name, String breed) {
        this.name = name;
        this.breed = breed;  
    }

    public void bark() {
        System.out.println(name + " is barking.");
    }  
}
```

### 🌟 Key Features of Inheritance

1. **Method Overriding**: A subclass can provide a specific implementation of a method that is already provided by its superclass.
2. **super Keyword**: Used to refer to immediate parent class object.
3. **final Keyword**: A final class can't be subclassed, and a final method can't be overridden by subclasses.
4. **abstract Keyword**: An abstract class can't be instantiated, and an abstract method has no body and must be implemented by subclasses.

### 🔍 instanceof Operator  

The `instanceof` operator tests whether an object is an instance of a specific class or interface.

```java 
Animal animal = new Dog("Buddy", "Labrador");
if (animal instanceof Dog) {
    System.out.println("animal is a Dog");
}
```

### ✅ Inheritance Best Practices

1. Use inheritance to model "is-a" relationships.
2. Favor composition over inheritance for "has-a" relationships.
3. Keep inheritance hierarchies shallow and narrow.
4. Use the `@Override` annotation when overriding methods for clarity.
5. Follow the Liskov Substitution Principle: Subclasses should be substitutable for their base classes.

### ⚠️ Pitfalls of Inheritance  

1. **Tight Coupling**: Inheritance can lead to tight coupling between classes, making the code harder to modify.
2. **Fragile Base Class Problem**: Changes in a superclass can unintentionally break subclasses.  
3. **Inflexible Hierarchy**: An inheritance hierarchy is difficult to change once it's established.

## 🎓 Conclusion

Encapsulation and inheritance are powerful tools in object-oriented programming. Encapsulation bundles data and methods together and hides internal object details, while inheritance allows classes to inherit properties from other classes. When used correctly, they can lead to code that is modular, reusable, and maintainable. However, they should be used judiciously, as overuse or misuse can lead to complex, fragile code.

## 📚 Resources

- [Java Tutorials - Inheritance](https://docs.oracle.com/javase/tutorial/java/IandI/subclasses.html)
- [Java Tutorials - Encapsulation](https://docs.oracle.com/javase/tutorial/java/javaOO/variables.html)
- [Inheritance vs Composition](https://www.thoughtworks.com/insights/blog/composition-vs-inheritance-how-choose)

Happy coding! 💻🚀
