# Generic and Java Collection Classes

## Generics

Generics enable types (classes and interfaces) to be parameters when defining classes, interfaces and methods. They provide compile-time type safety that allows programmers to catch invalid types at compile time.

### Benefits of Generics:
1. Type safety
2. Elimination of casts
3. Enabling programmers to implement generic algorithms

### Generic Classes

```java
public class Box<T> {
    private T t;

    public void set(T t) {
        this.t = t;
    }

    public T get() {
        return t;
    }
}

// Usage
Box<Integer> integerBox = new Box<>();
integerBox.set(10);
Integer someInteger = integerBox.get();
```

### Generic Methods

```java
public static <E> void printArray(E[] array) {
    for (E element : array) {
        System.out.print(element + " ");
    }
    System.out.println();
}

// Usage
Integer[] intArray = { 1, 2, 3, 4, 5 };
Double[] doubleArray = { 1.1, 2.2, 3.3, 4.4 };
printArray(intArray);
printArray(doubleArray);
```

### Bounded Type Parameters

```java
public <T extends Comparable<T>> T findMax(T x, T y, T z) {
    T max = x;
    if (y.compareTo(max) > 0) {
        max = y;
    }
    if (z.compareTo(max) > 0) {
        max = z;
    }
    return max;
}
```

### Wildcards

1. Upper Bounded Wildcard: `<? extends T>`
2. Lower Bounded Wildcard: `<? super T>`
3. Unbounded Wildcard: `<?>`

```java
public static void printList(List<?> list) {
    for (Object elem : list) {
        System.out.print(elem + " ");
    }
    System.out.println();
}
```

## Java Collection Framework

The Java Collection Framework provides a set of interfaces and classes to store and manipulate groups of objects.

### Hierarchy of Collection Framework

1. Iterable
   - Collection
     - List
     - Set
     - Queue

2. Map (does not inherit from Collection)

### List Interface

Lists are ordered collections that can contain duplicate elements.

#### ArrayList

```java
List<String> arrayList = new ArrayList<>();
arrayList.add("Apple");
arrayList.add("Banana");
arrayList.add("Cherry");
System.out.println(arrayList.get(1)); // Outputs: Banana
```

#### LinkedList

```java
LinkedList<String> linkedList = new LinkedList<>();
linkedList.add("Red");
linkedList.add("Green");
linkedList.addFirst("Blue");
System.out.println(linkedList); // Outputs: [Blue, Red, Green]
```

### Set Interface

Sets are collections that cannot contain duplicate elements.

#### HashSet

```java
Set<Integer> hashSet = new HashSet<>();
hashSet.add(1);
hashSet.add(2);
hashSet.add(1); // This won't be added
System.out.println(hashSet); // Outputs: [1, 2]
```

#### TreeSet

```java
TreeSet<String> treeSet = new TreeSet<>();
treeSet.add("C");
treeSet.add("A");
treeSet.add("B");
System.out.println(treeSet); // Outputs: [A, B, C]
```

### Queue Interface

Queues typically, but not necessarily, order elements in a FIFO (first-in-first-out) manner.

#### LinkedList as Queue

```java
Queue<String> queue = new LinkedList<>();
queue.offer("First");
queue.offer("Second");
queue.offer("Third");
System.out.println(queue.poll()); // Outputs: First
```

#### PriorityQueue

```java
PriorityQueue<Integer> priorityQueue = new PriorityQueue<>();
priorityQueue.offer(3);
priorityQueue.offer(1);
priorityQueue.offer(2);
System.out.println(priorityQueue.poll()); // Outputs: 1
```

### Map Interface

Maps are object that map keys to values. A map cannot contain duplicate keys.

#### HashMap

```java
Map<String, Integer> hashMap = new HashMap<>();
hashMap.put("One", 1);
hashMap.put("Two", 2);
hashMap.put("Three", 3);
System.out.println(hashMap.get("Two")); // Outputs: 2
```

#### TreeMap

```java
TreeMap<String, Integer> treeMap = new TreeMap<>();
treeMap.put("C", 3);
treeMap.put("A", 1);
treeMap.put("B", 2);
System.out.println(treeMap); // Outputs: {A=1, B=2, C=3}
```

### Utility Classes

#### Collections

The Collections class provides static methods to operate on or return collections.

```java
List<String> list = Arrays.asList("banana", "apple", "cherry");
Collections.sort(list);
System.out.println(list); // Outputs: [apple, banana, cherry]

Collections.reverse(list);
System.out.println(list); // Outputs: [cherry, banana, apple]

String max = Collections.max(list);
System.out.println(max); // Outputs: cherry
```

#### Arrays

The Arrays class provides static methods to operate on arrays.

```java
int[] numbers = {5, 2, 8, 1, 9};
Arrays.sort(numbers);
System.out.println(Arrays.toString(numbers)); // Outputs: [1, 2, 5, 8, 9]

int index = Arrays.binarySearch(numbers, 5);
System.out.println(index); // Outputs: 2
```

## Best Practices

1. Use generics to achieve compile-time type safety.
2. Choose the right collection based on your needs:
   - Use ArrayList for fast iteration and fast random access.
   - Use LinkedList for fast insertion and deletion.
   - Use HashSet for fast lookups.
   - Use TreeSet when you need a sorted set.
   - Use HashMap for key-value associations.
   - Use TreeMap when you need a sorted map.
3. Use the interface type on the left side of assignments for flexibility:
   ```java
   List<String> list = new ArrayList<>();
   ```
4. Use enhanced for loop for iterating over collections when possible.
5. Consider using concurrent versions of collections (e.g., ConcurrentHashMap) for multi-threaded environments.
6. Use utility methods provided by Collections and Arrays classes for common operations.

## Conclusion

Generics and the Java Collection Framework are powerful features that allow for more flexible and robust code. Generics provide compile-time type safety and enable the creation of reusable code across different types. The Collection Framework offers a standardized way to handle groups of objects, with various implementations suited for different use cases. Understanding these concepts is crucial for writing efficient and maintainable Java code.
