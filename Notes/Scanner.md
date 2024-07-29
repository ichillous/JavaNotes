# 📚 Java Scanner Class: A Comprehensive Guide

![Java Scanner](https://img.shields.io/badge/Java-Scanner-orange?style=for-the-badge&logo=java)

## 📋 Table of Contents
- [Introduction](#-introduction)
- [Importing the Scanner Class](#-importing-the-scanner-class)
- [Creating a Scanner Object](#-creating-a-scanner-object)
- [Reading Different Data Types](#-reading-different-data-types)
- [Common Methods](#-common-methods)
- [Best Practices](#-best-practices)
- [Common Pitfalls](#-common-pitfalls)
- [Advanced Usage](#-advanced-usage)
- [Conclusion](#-conclusion)

## 🌟 Introduction

The Scanner class in Java is a powerful tool for parsing primitive types and strings using regular expressions. It's commonly used for reading input from the console, files, or strings.

## 📥 Importing the Scanner Class

Before using Scanner, you need to import it:

```java
import java.util.Scanner;
```

## 🛠️ Creating a Scanner Object

You can create a Scanner object to read from different sources:

```java
// Reading from System.in (console input)
Scanner consoleScanner = new Scanner(System.in);

// Reading from a String
String str = "Hello World";
Scanner stringScanner = new Scanner(str);

// Reading from a File
File file = new File("input.txt");
Scanner fileScanner = new Scanner(file);
```

## 📊 Reading Different Data Types

Scanner can read various data types:

```java
Scanner scanner = new Scanner(System.in);

// Reading a String
System.out.print("Enter a string: ");
String str = scanner.nextLine();

// Reading an int
System.out.print("Enter an integer: ");
int num = scanner.nextInt();

// Reading a double
System.out.print("Enter a double: ");
double dbl = scanner.nextDouble();

// Reading a boolean
System.out.print("Enter a boolean: ");
boolean bool = scanner.nextBoolean();
```

## 🔧 Common Methods

| Method | Description |
|--------|-------------|
| `next()` | 📜 Reads the next token as a String |
| `nextLine()` | 📃 Reads the next line of input |
| `nextInt()` | 🔢 Reads the next token as an int |
| `nextDouble()` | 🔢 Reads the next token as a double |
| `nextBoolean()` | ✅ Reads the next token as a boolean |
| `hasNext()` | 🔍 Returns true if there's another token |
| `hasNextLine()` | 🔍 Returns true if there's another line |
| `close()` | 🚪 Closes the scanner |

## 💡 Best Practices

1. 🚪 Always close the Scanner when you're done using it to free up resources.
2. 🔄 Use `nextLine()` after reading a number to consume the newline character.
3. 🧹 Clear the input buffer before reading sensitive data.
4. 🔢 Use appropriate methods for reading specific data types.
5. 🔍 Check if input exists before reading to avoid NoSuchElementException.

## ⚠️ Common Pitfalls

1. 🚫 Forgetting to close the Scanner.
2. 🔤 Mixing `nextLine()` with other `next*()` methods without proper handling.
3. 🔢 Using the wrong method for reading (e.g., `nextInt()` for decimal numbers).
4. 🔁 Infinite loops due to improper input validation.

## 🚀 Advanced Usage

### Using Delimiters

You can change the delimiter used by Scanner:

```java
Scanner scanner = new Scanner("apple,banana,cherry");
scanner.useDelimiter(",");
while (scanner.hasNext()) {
    System.out.println(scanner.next());
}
```

### Reading Patterns

Scanner can use regular expressions to read patterns:

```java
String input = "1 fish 2 fish red fish blue fish";
Scanner s = new Scanner(input);
s.findInLine("(\\d+) fish (\\d+) fish (\\w+) fish (\\w+)");
MatchResult result = s.match();
for (int i=1; i<=result.groupCount(); i++) {
    System.out.println(result.group(i));
}
```

## 🎓 Conclusion

The Scanner class is a versatile tool for input handling in Java. It simplifies the process of reading various data types from different sources. By understanding its methods and best practices, you can effectively use Scanner in your Java programs.

Remember:
- 📥 Always import java.util.Scanner
- 🚪 Close your Scanner when done
- 🔢 Use the appropriate method for each data type
- 🔍 Validate input to avoid errors

Happy coding with Scanner! 💻🚀
