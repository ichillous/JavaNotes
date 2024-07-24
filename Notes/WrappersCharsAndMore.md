# 🧰 Java Wrapper Classes, Math, Character, and String Class

![Java Utilities](https://img.shields.io/badge/Java-Utilities-orange?style=for-the-badge&logo=java)

## 📋 Table of Contents
- [Wrapper Classes](#-wrapper-classes)
- [Math Class](#-math-class)
- [Character Class](#-character-class)
- [String Class](#-string-class)

## 🎁 Wrapper Classes

Wrapper classes in Java provide a way to use primitive data types as objects. Each primitive data type has a corresponding wrapper class:

| Primitive | Wrapper |
|-----------|---------|
| `byte`    | `Byte`  |
| `short`   | `Short` |
| `int`     | `Integer` |
| `long`    | `Long`  |
| `float`   | `Float` |
| `double`  | `Double` |
| `boolean` | `Boolean` |
| `char`    | `Character` |

### 🔍 Usage Examples:

```java
// Boxing: Converting primitive to wrapper
Integer wrappedInt = Integer.valueOf(42);
Double wrappedDouble = Double.valueOf(3.14);

// Unboxing: Converting wrapper to primitive
int primitiveInt = wrappedInt.intValue();
double primitiveDouble = wrappedDouble.doubleValue();

// Autoboxing and Auto-unboxing
Integer autoBoxed = 100;  // Autoboxing
int autoUnboxed = autoBoxed;  // Auto-unboxing
```

### 🛠️ Utility Methods:

Wrapper classes provide useful utility methods:

```java
String strNumber = "123";
int parsedInt = Integer.parseInt(strNumber);

int max = Integer.max(10, 20);  // Returns 20
int min = Integer.min(10, 20);  // Returns 10

String binaryString = Integer.toBinaryString(42);  // Returns "101010"
```

## 🧮 Math Class

The `Math` class in Java provides a collection of methods for performing basic numeric operations.

### 📊 Common Math Methods:

```java
double pi = Math.PI;  // 3.141592653589793
double e = Math.E;    // 2.718281828459045

double squareRoot = Math.sqrt(25);  // 5.0
double powerOf = Math.pow(2, 3);    // 8.0

double sinValue = Math.sin(Math.PI / 2);  // 1.0
double cosValue = Math.cos(0);            // 1.0

double maxValue = Math.max(10.5, 20.7);  // 20.7
double minValue = Math.min(10.5, 20.7);  // 10.5

double randomValue = Math.random();  // Returns a random number between 0.0 and 1.0

int roundedValue = Math.round(3.7f);  // 4
int floorValue = (int) Math.floor(3.7);  // 3
int ceilValue = (int) Math.ceil(3.2);    // 4

double absoluteValue = Math.abs(-10.5);  // 10.5
```

## 🔤 Character Class

The `Character` class wraps a value of the primitive type `char` in an object. It also offers various utility methods for manipulating characters.

### 🔠 Character Methods:

```java
char ch = 'A';
boolean isDigit = Character.isDigit(ch);  // false
boolean isLetter = Character.isLetter(ch);  // true
boolean isLetterOrDigit = Character.isLetterOrDigit(ch);  // true
boolean isUpperCase = Character.isUpperCase(ch);  // true
boolean isLowerCase = Character.isLowerCase(ch);  // false

char lowerCaseChar = Character.toLowerCase('A');  // 'a'
char upperCaseChar = Character.toUpperCase('a');  // 'A'

int numericValue = Character.getNumericValue('5');  // 5
```

## 📝 String Class

The `String` class represents character strings. Strings are immutable, which means once created, their values cannot be changed.

### 🏗️ String Creation:

```java
String str1 = "Hello";  // String literal
String str2 = new String("World");  // Using new keyword
```

### 🔧 Common String Methods:

```java
String s = "Hello, World!";

int length = s.length();  // 13
char charAtIndex = s.charAt(0);  // 'H'

String substring = s.substring(0, 5);  // "Hello"
String lowerCase = s.toLowerCase();  // "hello, world!"
String upperCase = s.toUpperCase();  // "HELLO, WORLD!"

boolean startsWith = s.startsWith("Hello");  // true
boolean endsWith = s.endsWith("World!");  // true
int indexOfComma = s.indexOf(",");  // 5

String trimmed = "  Hi  ".trim();  // "Hi"

String replaced = s.replace("Hello", "Hi");  // "Hi, World!"

String[] split = s.split(", ");  // ["Hello", "World!"]

boolean equals = s.equals("Hello, World!");  // true
boolean equalsIgnoreCase = s.equalsIgnoreCase("hello, world!");  // true

boolean contains = s.contains("World");  // true
```

### 🔗 String Concatenation:

```java
String concat1 = "Hello" + " " + "World";  // "Hello World"
String concat2 = "Hello".concat(" World");  // "Hello World"
```

### 🏗️ StringBuilder:

For mutable strings, use `StringBuilder`:

```java
StringBuilder sb = new StringBuilder("Hello");
sb.append(" World");
sb.insert(5, ",");
String result = sb.toString();  // "Hello, World"
```

## 🎓 Conclusion

Understanding these utility classes is crucial for effective Java programming:

- 🎁 Wrapper classes bridge the gap between primitive types and objects
- 🧮 The Math class provides essential mathematical operations
- 🔤 The Character class offers useful methods for working with individual characters
- 📝 The String class is fundamental for text manipulation in Java

Remember, `String` objects are immutable, while `StringBuilder` objects are mutable. Use `StringBuilder` when you need to make many modifications to a string, as it's more efficient than creating multiple `String` objects.

Happy coding! 💻🚀
