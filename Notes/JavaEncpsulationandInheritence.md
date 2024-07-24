# 🔒🌿 Java Encapsulation and Inheritance

![Java OOP](https://img.shields.io/badge/Java-OOP-blue?style=for-the-badge&logo=java)

## 📋 Table of Contents
- [Introduction](#-introduction)
- [Encapsulation](#-encapsulation)
  - [Key Principles of Encapsulation](#-key-principles-of-encapsulation)
  - [Benefits of Encapsulation](#-benefits-of-encapsulation)
  - [Example of Encapsulation](#-example-of-encapsulation)
- [Inheritance](#-inheritance)
  - [Key Concepts](#-key-concepts)
  - [Types of Inheritance](#-types-of-inheritance)
  - [Example of Inheritance](#-example-of-inheritance)
  - [Key Features of Inheritance](#-key-features-of-inheritance)
  - [The instanceof Operator](#-the-instanceof-operator)
  - [Best Practices](#-best-practices)
  - [Limitations of Inheritance](#-limitations-of-inheritance)
- [Conclusion](#-conclusion)

## 🌟 Introduction

Encapsulation and inheritance are two fundamental concepts in object-oriented programming (OOP) that help in creating robust, maintainable, and reusable code. In this README, we'll explore these concepts in the context of Java programming.

## 📦 Encapsulation

Encapsulation is the bundling of data with the methods that operate on that data, or the restricting of direct access to some of an object's components. It's often used to hide the internal representation, or state, of an object from the outside.

### 🔑 Key Principles of Encapsulation

1. 🔒 Declare the variables of a class as `private`
2. 🔓 Provide `public` setter and getter methods to modify and view the variables' values

### 🌟 Benefits of Encapsulation

1. 🕵️‍♂️ Data Hiding: The internal representation of an object is hidden from the outside world
2. 🔧 Increased Flexibility: We can change the internal implementation without affecting the code that uses the class
3. ♻️ Reusability: Encapsulated code is easier to reuse and maintain

### 💡 Example of Encapsulation

```java
public class BankAccount {
    private double balance;
    private String accountNumber;

    // Constructor
    public BankAccount(String accountNumber, double initialBalance) {
        this.accountNumber = accountNumber;
        this.balance = initialBalance;
    }

    // Getter and Setter methods
    public double getBalance() {
        return balance;
    }

    public String getAccountNumber() {
        return accountNumber;  
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

## 🌳 Inheritance

Inheritance is a mechanism in which one class acquires the properties (methods and fields) of another. It's a way to establish a relationship between classes, creating a hierarchy of classes.

### 🔑 Key Concepts

1. 👴 Superclass (Parent class): The class whose properties are inherited
2. 👶 Subclass (Child class): The class that inherits the properties

### 🌿 Types of Inheritance

1. 👨‍👦 Single Inheritance: A subclass inherits from one superclass
2. 👴👨‍👦👶 Multilevel Inheritance: A subclass inherits from a superclass, which in turn inherits from another superclass  
3. 👨‍👦‍👦 Hierarchical Inheritance: Multiple subclasses inherit from a single superclass

### 💡 Example of Inheritance

```java
// Superclass
public class Animal {
    protected String name;
    protected int age;

    public Animal(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void eat() {
        System.out.println(name + " is eating.");
    }

    public void sleep() {
        System.out.println(name + " is sleeping.");
    }
}

// Subclass  
public class Dog extends Animal {
    private String breed;

    public Dog(String name, int age, String breed) {
        super(name, age);  // Call to superclass constructor
        this.breed = breed;
    }

    public void bark() {
        System.out.println(name + " is barking.");  
    }

    // Method Overriding
    @Override
    public void eat() {
        System.out.println(name + " the dog is eating dog food.");
    }  
}
```

### 🌟 Key Features of Inheritance

1. ✍️ **Method Overriding**: A subclass can provide a specific implementation of a method that is already defined in its superclass
2. 👆 **super Keyword**: Used to refer to the superclass, either to call its constructor or to access its methods
3. 🚫 **final Keyword**:
   - When applied to a class, it prevents the class from being subclassed
   - When applied to a method, it prevents the method from being overridden in subclasses  
4. 🎨 **abstract Keyword**:
   - An abstract class cannot be instantiated and may contain abstract methods
   - An abstract method has no body and must be implemented by concrete subclasses

### 🔍 The `instanceof` Operator

The `instanceof` operator is used to test whether an object is an instance of a specific class or interface.

```java
Animal myPet = new Dog("Buddy", 5, "Labrador");

if (myPet instanceof Dog) {
    ((Dog) myPet).bark();
}
```  

### ✅ Best Practices

1. Use inheritance to model "is-a" relationships
2. Prefer composition over inheritance when possible ("has-a" relationship)
3. Keep the inheritance hierarchy simple and shallow
4. Use the `@Override` annotation when overriding methods
5. Be cautious with method overriding to maintain the Liskov Substitution Principle

### ⚠️ Limitations of Inheritance

1. Tight coupling between superclass and subclass
2. Changes in the superclass can affect all subclasses
3. Overuse can lead to complex and hard-to-maintain code

## 🎓 Conclusion

Encapsulation and inheritance are fundamental concepts in object-oriented programming. Encapsulation provides data hiding and increases the modularity of the program, while inheritance promotes code reuse and establishes a relationship between classes. Understanding these concepts is crucial for designing robust and maintainable Java applications. However, it's important to use these features judiciously, always considering the specific needs of your program and the principles of good software design.

Happy coding! 💻🚀
