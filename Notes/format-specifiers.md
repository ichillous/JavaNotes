# Java Format Specifiers Guide

## Table of Contents
1. [Introduction](#introduction)
2. [Basic Syntax](#basic-syntax)
3. [Integer Specifiers](#integer-specifiers)
4. [Floating-Point Specifiers](#floating-point-specifiers)
5. [String Specifiers](#string-specifiers)
6. [Character Specifiers](#character-specifiers)
7. [Boolean Specifiers](#boolean-specifiers)
8. [Date and Time Specifiers](#date-and-time-specifiers)
9. [Other Specifiers](#other-specifiers)
10. [Flags and Modifiers](#flags-and-modifiers)
11. [Examples](#examples)

## Introduction

Java format specifiers are used with `System.out.printf()` or `String.format()` to control the formatting of output. They provide a powerful way to present data in a structured and readable format.

## Basic Syntax

The basic syntax for a format specifier is:

```
%[argument_index$][flags][width][.precision]conversion
```

- `argument_index`: Optional decimal integer followed by `$`, specifying which argument to format.
- `flags`: Optional characters that modify the output format.
- `width`: Optional decimal integer specifying the minimum number of characters to be written to the output.
- `.precision`: Optional decimal integer specifying how many decimal places to display for floating-point numbers, or the maximum number of characters for strings.
- `conversion`: Required character specifying how to format the argument.

## Integer Specifiers

| Specifier | Description | Example |
|-----------|-------------|---------|
| `%d` | Decimal integer | `System.out.printf("%d", 42);` → `42` |
| `%x` | Hexadecimal integer | `System.out.printf("%x", 255);` → `ff` |
| `%X` | Uppercase hexadecimal integer | `System.out.printf("%X", 255);` → `FF` |
| `%o` | Octal integer | `System.out.printf("%o", 8);` → `10` |

## Floating-Point Specifiers

| Specifier | Description | Example |
|-----------|-------------|---------|
| `%f` | Decimal floating-point | `System.out.printf("%.2f", 3.14159);` → `3.14` |
| `%e` | Scientific notation | `System.out.printf("%e", 1000.0);` → `1.000000e+03` |
| `%g` | General floating-point (shortest representation) | `System.out.printf("%g", 10000.0);` → `10000.0` |

## String Specifiers

| Specifier | Description | Example |
|-----------|-------------|---------|
| `%s` | String | `System.out.printf("%s", "Hello");` → `Hello` |
| `%S` | Uppercase string | `System.out.printf("%S", "Hello");` → `HELLO` |

## Character Specifiers

| Specifier | Description | Example |
|-----------|-------------|---------|
| `%c` | Character | `System.out.printf("%c", 'A');` → `A` |
| `%C` | Uppercase character | `System.out.printf("%C", 'a');` → `A` |

## Boolean Specifiers

| Specifier | Description | Example |
|-----------|-------------|---------|
| `%b` | Boolean | `System.out.printf("%b", true);` → `true` |
| `%B` | Uppercase boolean | `System.out.printf("%B", false);` → `FALSE` |

## Date and Time Specifiers

| Specifier | Description | Example |
|-----------|-------------|---------|
| `%tD` | Date as MM/dd/yy | `System.out.printf("%tD", new Date());` → `07/04/23` |
| `%tF` | ISO 8601 date | `System.out.printf("%tF", new Date());` → `2023-07-04` |
| `%tT` | 24-hour time | `System.out.printf("%tT", new Date());` → `13:45:30` |
| `%tr` | 12-hour time | `System.out.printf("%tr", new Date());` → `01:45:30 PM` |

## Other Specifiers

| Specifier | Description | Example |
|-----------|-------------|---------|
| `%%` | Literal percent sign | `System.out.printf("100%%");` → `100%` |
| `%n` | Platform-specific line separator | `System.out.printf("Line 1%nLine 2");` → `Line 1<newline>Line 2` |

## Flags and Modifiers

| Flag | Description | Example |
|------|-------------|---------|
| `-` | Left-justify | `System.out.printf("%-10s", "Left");` → `Left      ` |
| `0` | Zero-pad | `System.out.printf("%05d", 42);` → `00042` |
| `+` | Always show sign | `System.out.printf("%+d", 42);` → `+42` |
| ` ` (space) | Add space for positive numbers | `System.out.printf("% d", 42);` → ` 42` |
| `,` | Add grouping separators | `System.out.printf("%,d", 1000000);` → `1,000,000` |
| `(` | Enclose negative numbers in parentheses | `System.out.printf("%(d", -42);` → `(42)` |

## Examples

Here's a comprehensive example demonstrating various format specifiers:

```java
public class FormatSpecifiersDemo {
    public static void main(String[] args) {
        int i = 42;
        double d = 3.14159;
        String s = "Hello";
        boolean b = true;
        
        System.out.printf("Integer: %d%n", i);
        System.out.printf("Padded Integer: %05d%n", i);
        System.out.printf("Hexadecimal: %x%n", i);
        
        System.out.printf("Float: %f%n", d);
        System.out.printf("Rounded Float: %.2f%n", d);
        System.out.printf("Scientific Notation: %e%n", d);
        
        System.out.printf("String: %s%n", s);
        System.out.printf("Uppercase String: %S%n", s);
        
        System.out.printf("Boolean: %b%n", b);
        
        System.out.printf("Multiple Arguments: %d %.2f %s%n", i, d, s);
        
        java.util.Date date = new java.util.Date();
        System.out.printf("Date: %tF%n", date);
        System.out.printf("Time: %tT%n", date);
    }
}
```

This guide covers the most commonly used Java format specifiers. For more detailed information, refer to the official Java documentation on [Formatter](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/Formatter.html).
