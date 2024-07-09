# Conditional Statements and Flow Control

Conditional statements and flow control structures are fundamental to programming in Java. They allow you to make decisions in your code and control the execution flow based on certain conditions.

## If-Else Statements

The if-else statement is used to execute a block of code only if a specified condition is true.

### Simple If Statement
```java
int age = 18;
if (age >= 18) {
    System.out.println("You are eligible to vote.");
}
```

### If-Else Statement

```java
int score = 75;
if (score >= 60) {
    System.out.println("You passed!");
} else {
    System.out.println("You failed.");
}
```

### If-Else If-Else Statement

```java
int grade = 85;
if (grade >= 90) {
    System.out.println("A");
} else if (grade >= 80) {
    System.out.println("B");
} else if (grade >= 70) {
    System.out.println("C");
} else {
    System.out.println("F");
}
```

### Nested If Statements

```java
boolean isWeekend = true;
boolean isRaining = false;

if (isWeekend) {
    if (!isRaining) {
        System.out.println("Let's go for a picnic!");
    } else {
        System.out.println("Let's watch a movie at home.");
    }
} else {
    System.out.println("It's a workday.");
}
```

## Switch Statement

The switch statement can have multiple possible execution paths based on the value of a variable.

```java
String day = "Monday";
switch (day) {
    case "Monday":
        System.out.println("Start of the work week");
        break;
    case "Tuesday":
    case "Wednesday":
    case "Thursday":
        System.out.println("Midweek");
        break;
    case "Friday":
        System.out.println("TGIF!");
        break;
    case "Saturday":
    case "Sunday":
        System.out.println("Weekend!");
        break;
    default:
        System.out.println("Invalid day");
}
```

Note: The `break` statement is important in each case to prevent fall-through to the next case.

## Ternary Operator

The ternary operator is a shorthand way of writing an if-else statement.

```java
int age = 20;
String status = (age >= 18) ? "Adult" : "Minor";
System.out.println(status);  // Outputs: Adult
```

## Short-Circuit Evaluation

Java uses short-circuit evaluation for logical AND (`&&`) and OR (`||`) operators.

```java
int x = 5;
int y = 10;

// AND short-circuit
if (x > 0 && y / x > 1) {
    System.out.println("Both conditions are true");
}

// OR short-circuit
if (x < 0 || y > 5) {
    System.out.println("At least one condition is true");
}
```

In the AND example, if `x > 0` is false, the second condition isn't evaluated. In the OR example, if `x < 0` is true, the second condition isn't evaluated.

## The `null` Check

It's a common practice to check if an object is null before using it to avoid NullPointerException.

```java
String str = null;
if (str != null && str.length() > 0) {
    System.out.println("String is not empty");
} else {
    System.out.println("String is null or empty");
}
```

## Best Practices

1. Keep your conditions simple and readable.
2. Use brackets `{}` even for single-line if statements to improve readability and prevent errors.
3. Be aware of the order of conditions in if-else if chains. Put the most specific or most likely conditions first.
4. Use switch statements when you have multiple conditions based on a single variable.
5. Be cautious with nested if statements - too many levels of nesting can make code hard to read and maintain.
6. Remember that switch statements in Java can now be used with Strings (since Java 7) and with multiple case labels (since Java 14).

Conditional statements and flow control are crucial for creating dynamic and responsive Java programs. They allow your code to make decisions and respond to different scenarios, forming the backbone of program logic.
