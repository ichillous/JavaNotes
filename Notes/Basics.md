# ☕ Java Course Notes: From Basics to Loops

![Java Logo](https://img.shields.io/badge/Java-Programming-orange?style=for-the-badge&logo=java)

## 📋 Table of Contents
- [Introduction to Java Basics](#-introduction-to-java-basics)
- [Java Programming Fundamentals](#-java-programming-fundamentals)
- [Java Wrapper Classes, Math, Character, and String Class](#-java-wrapper-classes-math-character-and-string-class)
- [Conditional Statements and Flow Control](#-conditional-statements-and-flow-control)
- [Iteration Statements (Loops)](#-iteration-statements-loops)

## 🌟 Introduction to Java Basics

Java is a popular, object-oriented programming language known for its "write once, run anywhere" capability. 

### 🔑 Key Points:
- 🏭 Java programs are compiled into bytecode, which runs on the Java Virtual Machine (JVM)
- 📝 Java syntax is similar to C and C++
- 🔒 Java is strongly typed and uses curly braces to define code blocks

Here's a simple "Hello World" program in Java:

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

## 🧱 Java Programming Fundamentals

Java fundamentals include:

1. 📊 Variables and Data Types
2. 🔣 Operators
3. 🔀 Control Flow Statements

### 📊 Variables and Data Types

Java has two categories of data types:

- 🔢 Primitive types: `byte`, `short`, `int`, `long`, `float`, `double`, `boolean`, `char`
- 📦 Reference types: Objects, Arrays, etc.

Example:

```java
int age = 25;
double salary = 50000.50;
boolean isEmployed = true;
String name = "John Doe";
```

### 🔣 Operators

Java supports various operators:

| Category | Operators |
|----------|-----------|
| Arithmetic | `+`, `-`, `*`, `/`, `%` |
| Relational | `==`, `!=`, `>`, `<`, `>=`, `<=` |
| Logical | `&&`, `||`, `!` |
| Assignment | `=`, `+=`, `-=`, `*=`, `/=` |

Example:

```java
int a = 10, b = 5;
int sum = a + b;
boolean isGreater = a > b;
```

## 🧰 Java Wrapper Classes, Math, Character, and String Class

Java provides wrapper classes for primitive types, as well as utility classes like Math and Character.

### 🎁 Wrapper Classes

Wrapper classes allow primitive types to be used as objects:

```java
Integer wrappedInt = Integer.valueOf(42);
Double wrappedDouble = Double.valueOf(3.14);
```

### 🧮 Math Class

The Math class provides mathematical operations:

```java
double squareRoot = Math.sqrt(25);
int absoluteValue = Math.abs(-10);
double randomNumber = Math.random();
```

### 📝 String Class

Strings in Java are immutable objects:

```java
String greeting = "Hello";
String fullGreeting = greeting + " World!";
int length = fullGreeting.length();
char firstChar = fullGreeting.charAt(0);
```

## 🔀 Conditional Statements and Flow Control

Java uses if-else statements and switch-case for conditional execution:

```java
int score = 85;
if (score >= 90) {
    System.out.println("A grade");
} else if (score >= 80) {
    System.out.println("B grade");
} else {
    System.out.println("C grade or below");
}

String day = "Monday";
switch (day) {
    case "Monday":
        System.out.println("Start of the week");
        break;
    case "Friday":
        System.out.println("TGIF!");
        break;
    default:
        System.out.println("Regular day");
}
```

## 🔁 Iteration Statements (Loops)

Java supports several types of loops:

1. 🔢 for loop
2. 🔄 while loop
3. 🔂 do-while loop
4. 🔀 for-each loop (enhanced for loop)

Examples:

```java
// for loop
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}

// while loop
int count = 0;
while (count < 5) {
    System.out.println(count);
    count++;
}

// do-while loop
int j = 0;
do {
    System.out.println(j);
    j++;
} while (j < 5);

// for-each loop
int[] numbers = {1, 2, 3, 4, 5};
for (int num : numbers) {
    System.out.println(num);
}
```

## 🎓 Conclusion

These Java course notes cover the fundamental concepts of Java programming, from basic syntax to control structures and loops. As you progress, you'll build upon these foundations to create more complex and powerful Java applications.

Remember:
- 📚 Practice regularly to reinforce your understanding
- 🧪 Experiment with different code examples
- 🔍 Don't hesitate to explore Java's extensive documentation for more details

Happy coding! 💻🚀
