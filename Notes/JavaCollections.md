# 📚 Java Collections: Lists, Stacks, Queues, and Priority Queues

![Java Collections](https://img.shields.io/badge/Java-Collections-orange?style=for-the-badge&logo=java)

## 📋 Table of Contents
- [Introduction](#-introduction)
- [Lists](#-lists)
  - [ArrayList](#arraylist-)
  - [LinkedList](#linkedlist-)
- [Stacks](#-stacks)
- [Queues](#-queues)
- [Priority Queues](#-priority-queues)
- [Common Operations](#-common-operations)
- [Best Practices](#-best-practices)
- [Performance Comparison](#-performance-comparison)
- [Conclusion](#-conclusion)

## 🌟 Introduction

Java provides a rich set of collection classes to store and manipulate groups of objects. This guide focuses on Lists, Stacks, Queues, and Priority Queues, which are fundamental data structures in Java programming.

## 📝 Lists

Lists are ordered collections that can contain duplicate elements. They provide positional access and allow elements to be inserted or accessed by their position in the list.

### ArrayList 📊

ArrayList is a resizable array implementation of the List interface.

```java
List<String> fruits = new ArrayList<>();
fruits.add("Apple");
fruits.add("Banana");
fruits.add("Cherry");
System.out.println(fruits.get(1)); // Outputs: Banana
```

#### Key Features:
- 🚀 Fast random access
- 🐢 Slow insertion/deletion in the middle
- 📈 Dynamic resizing

### LinkedList 🔗

LinkedList is a doubly-linked list implementation of the List and Deque interfaces.

```java
LinkedList<String> colors = new LinkedList<>();
colors.add("Red");
colors.add("Green");
colors.addFirst("Blue");
System.out.println(colors); // Outputs: [Blue, Red, Green]
```

#### Key Features:
- 🚀 Fast insertion/deletion
- 🐢 Slow random access
- 📊 Implements both List and Deque interfaces

## 📚 Stacks

A Stack is a Last-In-First-Out (LIFO) data structure.

```java
Stack<Integer> stack = new Stack<>();
stack.push(1);
stack.push(2);
stack.push(3);
System.out.println(stack.pop()); // Outputs: 3
```

#### Key Operations:
- 🔼 `push(E item)`: Adds an item to the top of the stack
- 🔽 `pop()`: Removes and returns the top item
- 👀 `peek()`: Returns the top item without removing it

## 🚶 Queues

A Queue is a First-In-First-Out (FIFO) data structure.

```java
Queue<String> queue = new LinkedList<>();
queue.offer("First");
queue.offer("Second");
queue.offer("Third");
System.out.println(queue.poll()); // Outputs: First
```

#### Key Operations:
- 🔼 `offer(E e)`: Adds an element to the rear of the queue
- 🔽 `poll()`: Removes and returns the front element
- 👀 `peek()`: Returns the front element without removing it

## 🏆 Priority Queues

A PriorityQueue is a queue where elements are ordered by their natural order or by a specified Comparator.

```java
PriorityQueue<Integer> pq = new PriorityQueue<>();
pq.offer(3);
pq.offer(1);
pq.offer(2);
System.out.println(pq.poll()); // Outputs: 1
```

#### Key Features:
- 🔢 Elements are ordered by priority
- 🚀 O(log n) time for enqueing and dequeing operations

## 🛠 Common Operations

| Operation | ArrayList | LinkedList | Stack | Queue | PriorityQueue |
|-----------|-----------|------------|-------|-------|---------------|
| Add       | add(E)    | add(E)     | push(E)| offer(E) | offer(E)   |
| Remove    | remove(int) | remove() | pop() | poll() | poll()       |
| Peek      | get(int)  | peek()     | peek()| peek() | peek()       |
| Size      | size()    | size()     | size()| size() | size()       |
| IsEmpty   | isEmpty() | isEmpty()  | isEmpty() | isEmpty() | isEmpty() |

## 💡 Best Practices

1. 🎯 Choose the right collection for your needs:
   - Use ArrayList for frequent access and rare modifications
   - Use LinkedList for frequent modifications
   - Use Stack for LIFO operations
   - Use Queue for FIFO operations
   - Use PriorityQueue when processing elements based on priority

2. 🔄 Use the interface type on the left side of assignments:
   ```java
   List<String> list = new ArrayList<>();
   Queue<Integer> queue = new LinkedList<>();
   ```

3. 🏃‍♂️ Use enhanced for loop for iterating when possible:
   ```java
   for (String item : list) {
       System.out.println(item);
   }
   ```

4. 🔒 Consider using thread-safe versions (e.g., ConcurrentLinkedQueue) for multi-threaded environments.

5. 📏 Initialize collections with a capacity if the size is known:
   ```java
   List<Integer> numbers = new ArrayList<>(100);
   ```

## 📊 Performance Comparison

| Operation | ArrayList | LinkedList | Stack | Queue | PriorityQueue |
|-----------|-----------|------------|-------|-------|---------------|
| Access    | O(1)      | O(n)       | O(1)  | O(1)  | O(1)          |
| Insert    | O(n)      | O(1)       | O(1)  | O(1)  | O(log n)      |
| Delete    | O(n)      | O(1)       | O(1)  | O(1)  | O(log n)      |
| Search    | O(n)      | O(n)       | O(n)  | O(n)  | O(n)          |

## 🎓 Conclusion

Understanding the characteristics and appropriate use cases for different collection types is crucial for writing efficient Java code. Each collection type has its strengths and weaknesses, and choosing the right one can significantly impact your application's performance.

Remember to consider factors such as:
- 🔢 The size of your data
- 🔄 How often you'll be modifying the collection
- 🔍 The type of access you need (random access, sequential access, etc.)
- 🧵 Whether you're working in a multi-threaded environment

By mastering these collection types, you'll be well-equipped to handle a wide variety of programming challenges in Java!

---

Happy Coding! 💻🚀
