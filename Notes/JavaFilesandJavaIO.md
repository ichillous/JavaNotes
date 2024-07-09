# Java Files and Java I/O

## Introduction to Java I/O

Java I/O (Input/Output) is used to process the input and produce the output. Java uses the concept of a stream to make I/O operation fast. The java.io package contains all the classes required for input and output operations.

## Streams

A stream is a sequence of data. In Java, a stream is composed of bytes. It's called a stream because it's like a stream of water that continues to flow.

There are two types of Streams:

1. **InputStream**: Used to read data from a source.
2. **OutputStream**: Used to write data to a destination.

## File Handling in Java

Java provides several ways to work with files. The most commonly used classes are:

1. File
2. FileInputStream / FileOutputStream
3. FileReader / FileWriter
4. BufferedReader / BufferedWriter

### File Class

The File class is an abstract representation of file and directory pathnames.

```java
import java.io.File;

File file = new File("example.txt");
boolean fileExists = file.exists();
long fileSize = file.length();
boolean isDirectory = file.isDirectory();
```

### Basic File Operations

#### Creating a New File

```java
File file = new File("newfile.txt");
try {
    boolean fileCreated = file.createNewFile();
    System.out.println("File created: " + fileCreated);
} catch (IOException e) {
    e.printStackTrace();
}
```

#### Writing to a File

```java
try (FileWriter writer = new FileWriter("output.txt")) {
    writer.write("Hello, World!");
} catch (IOException e) {
    e.printStackTrace();
}
```

#### Reading from a File

```java
try (BufferedReader reader = new BufferedReader(new FileReader("input.txt"))) {
    String line;
    while ((line = reader.readLine()) != null) {
        System.out.println(line);
    }
} catch (IOException e) {
    e.printStackTrace();
}
```

## Java NIO (New I/O)

Java NIO (New I/O) is an alternative I/O API for Java (from Java 1.4), providing a different way of working with I/O than the standard I/O API.

### Key Concepts in NIO:

1. **Channels and Buffers**: Data is always read from a channel into a buffer, or written from a buffer to a channel.
2. **Selectors**: Allow a single thread to manage multiple channels.

### Example of using NIO for file reading:

```java
import java.nio.file.*;
import java.nio.charset.StandardCharsets;

Path path = Paths.get("example.txt");
try {
    List<String> lines = Files.readAllLines(path, StandardCharsets.UTF_8);
    for (String line : lines) {
        System.out.println(line);
    }
} catch (IOException e) {
    e.printStackTrace();
}
```

## Working with Directories

### Creating a Directory

```java
File directory = new File("newDirectory");
boolean created = directory.mkdir();
System.out.println("Directory created: " + created);
```

### Listing Files in a Directory

```java
File directory = new File(".");
String[] fileList = directory.list();
for (String name : fileList) {
    System.out.println(name);
}
```

## Serialization

Serialization is the process of converting an object into a byte stream. Deserialization is the reverse process.

```java
import java.io.*;

class Person implements Serializable {
    private String name;
    private int age;

    // Constructor, getters, setters
}

// Serialization
try (ObjectOutputStream out = new ObjectOutputStream(new FileOutputStream("person.ser"))) {
    Person person = new Person("John Doe", 30);
    out.writeObject(person);
} catch (IOException e) {
    e.printStackTrace();
}

// Deserialization
try (ObjectInputStream in = new ObjectInputStream(new FileInputStream("person.ser"))) {
    Person person = (Person) in.readObject();
    System.out.println(person.getName() + ", " + person.getAge());
} catch (IOException | ClassNotFoundException e) {
    e.printStackTrace();
}
```

## Working with CSV Files

```java
import java.io.*;
import java.util.*;

// Writing to CSV
try (PrintWriter writer = new PrintWriter(new File("data.csv"))) {
    StringBuilder sb = new StringBuilder();
    sb.append("Name,Age,City\n");
    sb.append("John,30,New York\n");
    sb.append("Jane,25,London\n");
    writer.write(sb.toString());
} catch (FileNotFoundException e) {
    e.printStackTrace();
}

// Reading from CSV
try (BufferedReader br = new BufferedReader(new FileReader("data.csv"))) {
    String line;
    while ((line = br.readLine()) != null) {
        String[] values = line.split(",");
        System.out.println(Arrays.toString(values));
    }
} catch (IOException e) {
    e.printStackTrace();
}
```

## Java 8 Files API

Java 8 introduced new methods in the Files class to make file I/O operations more convenient.

```java
import java.nio.file.*;

// Reading all lines
List<String> lines = Files.readAllLines(Paths.get("example.txt"));

// Writing lines
List<String> linesToWrite = Arrays.asList("Line 1", "Line 2", "Line 3");
Files.write(Paths.get("output.txt"), linesToWrite);

// Creating directories
Files.createDirectories(Paths.get("path/to/directory"));

// Copying files
Files.copy(Paths.get("source.txt"), Paths.get("destination.txt"), StandardCopyOption.REPLACE_EXISTING);

// Moving files
Files.move(Paths.get("old.txt"), Paths.get("new.txt"), StandardCopyOption.REPLACE_EXISTING);

// Deleting files
Files.deleteIfExists(Paths.get("fileToDelete.txt"));
```

## Best Practices

1. Always close resources (use try-with-resources when possible).
2. Use buffered streams for better performance.
3. Use character streams for text files and byte streams for binary files.
4. Handle exceptions properly.
5. Use NIO for large files or when you need non-blocking I/O.
6. Be careful with file permissions.
7. Use meaningful names for files and directories.

## Conclusion

Java provides a rich set of I/O classes and methods to handle various file operations. Understanding these concepts is crucial for developing robust Java applications that interact with the file system. From basic file operations to advanced concepts like NIO and serialization, mastering Java I/O will significantly enhance your ability to work with external data and resources in your Java programs.
