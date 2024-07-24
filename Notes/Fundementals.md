# 🧱 Java Programming Fundamentals

![Java Fundamentals](https://img.shields.io/badge/Java-Fundamentals-orange?style=for-the-badge&logo=java)

## 📋 Table of Contents
- [Variables and Data Types](#-variables-and-data-types)
- [Operators](#-operators)
- [Control Flow Statements](#-control-flow-statements)

Java programming fundamentals form the backbone of any Java application. These concepts are essential for writing efficient and effective Java code.

## 📊 Variables and Data Types

In Java, variables are containers for storing data values. Java is a strongly-typed language, which means you must declare the type of a variable before using it.

### 🔢 Primitive Data Types

Java has eight primitive data types:

| Type | Size | Description |
|------|------|-------------|
| `byte` | 8-bit | Signed two's complement integer |
| `short` | 16-bit | Signed two's complement integer |
| `int` | 32-bit | Signed two's complement integer |
| `long` | 64-bit | Signed two's complement integer |
| `float` | 32-bit | IEEE 754 floating point |
| `double` | 64-bit | IEEE 754 floating point |
| `boolean` | - | true or false |
| `char` | 16-bit | Unicode character |

Example:

```java
byte myByte = 127;
short myShort = 32767;
int myInt = 2147483647;
long myLong = 9223372036854775807L;
float myFloat = 3.14f;
double myDouble = 3.14159265359;
boolean isJavaFun = true;
char myChar = 'A';
```

### 📦 Reference Data Types

Reference data types are used to store complex values like objects and arrays. The most commonly used reference type is the `String`.

Example:

```java
String myString = "Hello, Java!";
int[] myArray = {1, 2, 3, 4, 5};
```

## 🔣 Operators

Java provides a rich set of operators to perform various operations on variables and values.

### ➕ Arithmetic Operators

Used for mathematical calculations:

| Operator | Description |
|----------|-------------|
| `+` | Addition |
| `-` | Subtraction |
| `*` | Multiplication |
| `/` | Division |
| `%` | Modulus |

Example:

```java
int a = 10, b = 3;
int sum = a + b;  // 13
int difference = a - b;  // 7
int product = a * b;  // 30
int quotient = a / b;  // 3
int remainder = a % b;  // 1
```

### 🔍 Relational Operators

Used for comparing values:

| Operator | Description |
|----------|-------------|
| `==` | Equal to |
| `!=` | Not equal to |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal to |
| `<=` | Less than or equal to |

Example:

```java
int x = 5, y = 8;
boolean isEqual = (x == y);  // false
boolean isNotEqual = (x != y);  // true
boolean isGreater = (x > y);  // false
boolean isLess = (x < y);  // true
```

### 🧠 Logical Operators

Used to determine the logic between variables or values:

| Operator | Description |
|----------|-------------|
| `&&` | Logical AND |
| `||` | Logical OR |
| `!` | Logical NOT |

Example:

```java
boolean a = true, b = false;
boolean result1 = a && b;  // false
boolean result2 = a || b;  // true
boolean result3 = !a;  // false
```

### ✍️ Assignment Operators

Used to assign values to variables:

| Operator | Description |
|----------|-------------|
| `=` | Simple assignment |
| `+=`, `-=`, `*=`, `/=`, `%=` | Compound assignment |

Example:

```java
int num = 10;
num += 5;  // num is now 15
num *= 2;  // num is now 30
```

## 🔀 Control Flow Statements

Control flow statements allow you to control the flow of your program's execution based on certain conditions.

### 🔀 If-Else Statement

Used for conditional branching in code:

```java
int score = 85;

if (score >= 90) {
    System.out.println("A grade");
} else if (score >= 80) {
    System.out.println("B grade");
} else {
    System.out.println("C grade or below");
}
```

### 🔀 Switch Statement

Used when you have multiple conditions to check:

```java
String day = "Monday";
switch (day) {
    case "Monday":
        System.out.println("Start of the work week");
        break;
    case "Friday":
        System.out.println("TGIF!");
        break;
    case "Saturday":
    case "Sunday":
        System.out.println("Weekend!");
        break;
    default:
        System.out.println("Midweek");
}
```

### 🔁 Loops

Used for repetitive tasks:

1. 🔢 For Loop:

```java
for (int i = 0; i < 5; i++) {
    System.out.println("Iteration: " + i);
}
```

2. 🔄 While Loop:

```java
int count = 0;
while (count < 5) {
    System.out.println("Count: " + count);
    count++;
}
```

3. 🔂 Do-While Loop:

```java
int num = 1;
do {
    System.out.println("Number: " + num);
    num *= 2;
} while (num < 100);
```

## 🎓 Conclusion

These fundamentals provide the building blocks for more complex Java programs. As you progress, you'll learn how to combine these concepts to create robust and efficient applications.

Remember:
- 🏗️ Variables and data types are the foundation of your Java programs
- 🧮 Operators allow you to perform operations and make decisions
- 🔀 Control flow statements give your programs logic and structure

Keep practicing these concepts, and soon you'll be writing complex Java applications with ease! 💻🚀
