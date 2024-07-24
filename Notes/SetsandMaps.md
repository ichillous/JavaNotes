# 🗃️ Java Sets and Maps: A Comprehensive Guide

![Java Collections](https://img.shields.io/badge/Java-Collections-orange?style=for-the-badge&logo=java)

## 📋 Table of Contents
- [Introduction](#-introduction)
- [Sets](#-sets)
  - [HashSet](#-hashset)
  - [LinkedHashSet](#-linkedhashset)
  - [TreeSet](#-treeset)
  - [EnumSet](#-enumset)
- [Maps](#-maps)
  - [HashMap](#-hashmap)
  - [LinkedHashMap](#-linkedhashmap)
  - [TreeMap](#-treemap)
  - [EnumMap](#-enummap)
- [Concurrent Versions](#-concurrent-versions)
- [Set and Map Views](#-set-and-map-views)
- [Best Practices](#-best-practices)
- [Common Operations](#-common-operations)
- [Performance Comparison](#-performance-comparison)
- [Conclusion](#-conclusion)

## 🌟 Introduction

Sets and Maps are fundamental data structures in Java's Collection Framework. Sets store unique elements, while Maps store key-value pairs. Understanding these structures is crucial for efficient data management in Java programming.

## 🧺 Sets

Sets are collections that cannot contain duplicate elements. Java provides several Set implementations, each with unique characteristics.

### 🎭 HashSet

HashSet is implemented using a hash table, offering constant-time performance for basic operations.

```java
Set<String> fruits = new HashSet<>();
fruits.add("Apple");
fruits.add("Banana");
fruits.add("Apple"); // This won't be added (duplicate)
System.out.println(fruits); // Output: [Apple, Banana]
```

#### 🔑 Key Points:
- Does not maintain insertion order
- Allows null element
- O(1) time complexity for add, remove, and contains operations

### 🔗 LinkedHashSet

LinkedHashSet is a HashSet with a linked list running through it, maintaining insertion order.

```java
Set<String> colors = new LinkedHashSet<>();
colors.add("Red");
colors.add("Green");
colors.add("Blue");
System.out.println(colors); // Output: [Red, Green, Blue]
```

#### 🔑 Key Points:
- Maintains insertion order
- Slightly slower than HashSet
- Useful when you need both unique elements and preservation of insertion order

### 🌳 TreeSet

TreeSet is implemented using a Red-Black tree, keeping elements sorted.

```java
Set<Integer> numbers = new TreeSet<>();
numbers.add(5);
numbers.add(2);
numbers.add(8);
System.out.println(numbers); // Output: [2, 5, 8]
```

#### 🔑 Key Points:
- Elements are sorted (natural order or by a provided Comparator)
- Does not allow null elements
- O(log n) time complexity for add, remove, and contains operations

### 🚩 EnumSet

EnumSet is a specialized Set implementation for use with enum types.

```java
enum Day { MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY }

EnumSet<Day> weekdays = EnumSet.range(Day.MONDAY, Day.FRIDAY);
System.out.println(weekdays); // Output: [MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY]
```

#### 🔑 Key Points:
- Very compact and efficient
- All elements must be of the same enum type

## 🗺️ Maps

Maps store key-value pairs, allowing you to retrieve a value using its associated key.

### 🏷️ HashMap

HashMap stores key-value pairs in a hash table, offering constant-time performance for basic operations.

```java
Map<String, Integer> ages = new HashMap<>();
ages.put("Alice", 25);
ages.put("Bob", 30);
System.out.println(ages.get("Alice")); // Output: 25
```

#### 🔑 Key Points:
- Does not maintain insertion order
- Allows one null key and multiple null values
- O(1) time complexity for get and put operations

### 🔗 LinkedHashMap

LinkedHashMap is a HashMap with a linked list running through it, maintaining insertion order.

```java
Map<String, String> capitals = new LinkedHashMap<>();
capitals.put("USA", "Washington D.C.");
capitals.put("UK", "London");
capitals.put("Japan", "Tokyo");
capitals.forEach((country, capital) -> System.out.println(country + ": " + capital));
// Output:
// USA: Washington D.C.
// UK: London
// Japan: Tokyo
```

#### 🔑 Key Points:
- Maintains insertion order
- Slightly slower than HashMap
- Useful when you need both key-value pairs and preservation of insertion order

### 🌳 TreeMap

TreeMap is implemented using a Red-Black tree, keeping keys sorted.

```java
Map<String, Integer> scores = new TreeMap<>();
scores.put("Charlie", 85);
scores.put("Alice", 90);
scores.put("Bob", 88);
scores.forEach((name, score) -> System.out.println(name + ": " + score));
// Output:
// Alice: 90
// Bob: 88
// Charlie: 85
```

#### 🔑 Key Points:
- Keys are sorted (natural order or by a provided Comparator)
- Does not allow null keys (values can be null)
- O(log n) time complexity for get, put, and remove operations

### 🚩 EnumMap

EnumMap is a specialized Map implementation for use with enum type keys.

```java
enum Day { MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY }

EnumMap<Day, String> schedule = new EnumMap<>(Day.class);
schedule.put(Day.MONDAY, "Work");
schedule.put(Day.SATURDAY, "Relax");
System.out.println(schedule.get(Day.MONDAY)); // Output: Work
```

#### 🔑 Key Points:
- Very compact and efficient
- All keys must be of the same enum type

## 🔒 Concurrent Versions

For multi-threaded environments, Java provides thread-safe versions of Sets and Maps:

- ConcurrentHashMap
- CopyOnWriteArraySet
- ConcurrentSkipListSet
- ConcurrentSkipListMap

```java
Map<String, Integer> concurrentMap = new ConcurrentHashMap<>();
Set<String> concurrentSet = Collections.newSetFromMap(new ConcurrentHashMap<>());
```

## 👁️ Set and Map Views

Java provides ways to get different views of Sets and Maps:

```java
Map<String, Integer> map = new HashMap<>();
map.put("One", 1);
map.put("Two", 2);

Set<String> keySet = map.keySet();
Collection<Integer> values = map.values();
Set<Map.Entry<String, Integer>> e
