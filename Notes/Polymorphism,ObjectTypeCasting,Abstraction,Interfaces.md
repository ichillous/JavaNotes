# Polymorphism, Object Type Casting, Abstraction, and Interfaces

## Polymorphism

Polymorphism is a core concept in object-oriented programming that allows objects of different types to be treated as objects of a common super type. The word polymorphism means "many forms", and it occurs when we have many classes that are related to each other by inheritance.

### Types of Polymorphism

1. **Compile-time Polymorphism (Static Binding)**
   - Achieved through method overloading
   - Resolved during compile time

2. **Runtime Polymorphism (Dynamic Binding)**
   - Achieved through method overriding
   - Resolved during runtime

### Method Overloading (Compile-time Polymorphism)

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

### Method Overriding (Runtime Polymorphism)

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

class Cat extends Animal {
    @Override
    public void makeSound() {
        System.out.println("The cat meows");
    }
}

// Usage
Animal myPet = new Dog();
myPet.makeSound();  // Outputs: The dog barks
```

## Object Type Casting

Type casting is used to treat an object of one type as another type. In Java, we can cast both primitives and objects.

### Upcasting

Upcasting is casting a subclass to a superclass. This is done implicitly by Java.

```java
Dog myDog = new Dog();
Animal myAnimal = myDog;  // Upcasting, no explicit cast needed
```

### Downcasting

Downcasting is casting a superclass to a subclass. This requires an explicit cast.

```java
Animal myAnimal = new Dog();
Dog myDog = (Dog) myAnimal;  // Downcasting, explicit cast required

// It's good practice to use instanceof before downcasting
if (myAnimal instanceof Dog) {
    Dog myDog = (Dog) myAnimal;
    myDog.bark();
}
```

## Abstraction

Abstraction is the process of hiding the implementation details and showing only the functionality to the user. In Java, we can achieve abstraction in two ways:

1. Abstract classes (0 to 100% abstraction)
2. Interfaces (100% abstraction)

### Abstract Classes

An abstract class is a class that is declared with the `abstract` keyword. It may or may not include abstract methods.

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

### Key points about abstract classes:

- Cannot be instantiated
- May contain abstract and non-abstract methods
- Can have constructors and static methods
- Can have final methods which will force the subclass not to change the body of the method

## Interfaces

An interface is a completely abstract class that contains only abstract methods. As of Java 8, it can have default and static methods as well.

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

### Key points about interfaces:

- All methods are public and abstract by default
- All variables are public, static, and final by default
- A class can implement multiple interfaces
- As of Java 8, interfaces can have default and static methods
- As of Java 9, interfaces can have private methods

### Functional Interfaces

A functional interface is an interface that contains exactly one abstract method. They can be used with lambda expressions.

```java
@FunctionalInterface
public interface Runnable {
    void run();
}

// Usage with lambda expression
Runnable r = () -> System.out.println("Hello World");
```

## Comparison: Abstract Classes vs Interfaces

| Feature | Abstract Class | Interface |
|---------|----------------|-----------|
| Methods | Can have abstract and non-abstract methods | All methods are abstract by default (can have default and static methods as of Java 8) |
| Variables | Can have non-static and non-final variables | Variables are static and final by default |
| Constructor | Can have a constructor | Cannot have a constructor |
| Multiple Inheritance | A class can extend only one abstract class | A class can implement multiple interfaces |
| Access Modifiers | Can use any access modifier for members | Members are public by default |

## Best Practices

1. Use interfaces to define types that can be implemented by unrelated classes
2. Use abstract classes to define incomplete types that have a common base implementation
3. Prefer interfaces over abstract classes when possible
4. Use the `instanceof` operator before downcasting to avoid ClassCastException
5. Design your classes with the "Program to an interface, not an implementation" principle in mind

## Conclusion

Polymorphism, object type casting, abstraction, and interfaces are fundamental concepts in Java that provide powerful tools for creating flexible and maintainable code. Polymorphism allows for code reusability and runtime method binding. Type casting enables treating objects of different types uniformly. Abstraction through abstract classes and interfaces helps in hiding implementation details and defining contracts for classes to follow. Understanding and properly utilizing these concepts is crucial for effective object-oriented design and programming in Java.
