# 📁 Java Files and Java I/O

![Java I/O](https://img.shields.io/badge/Java-I%2FO-blue?style=for-the-badge&logo=java)

## 📋 Table of Contents
- [Introduction](#-introduction)
- [Streams](#-streams)
- [File Handling](#-file-handling)
  - [File Class](#-file-class)
  - [Basic File Operations](#-basic-file-operations)
- [Java NIO](#-java-nio)
- [Working with Directories](#-working-with-directories)
- [Serialization](#-serialization)
- [Working with CSV Files](#-working-with-csv-files)
- [Java 8 Files API](#-java-8-files-api)
- [Best Practices](#-best-practices)
- [Conclusion](#-conclusion)
- [Resources](#-resources)

## 🌟 Introduction

Imagine you're writing in your journnal. The paper you write on is like a file in Java. Just as you can write in your journal or read from it later, in Java, we can create files to store information (write) and access that information later (read).
Java IO, which stands for Input/Output, is like the pen you use to write in your journal or the eyes you use to read it. It's a set of tools Java gives us to work with files and other sources of information.

Java I/O (Input/Output) is used to process the input and produce the output. Java uses the concept of streams to make I/O operations fast and efficient. The `java.io` package contains all the classes required for input and output operations.


## 🌊 Streams

A stream is a sequence of data. In Java, a stream is composed of bytes. There are two types of streams:

1. **InputStream**: Used to read data from a source.
2. **OutputStream**: Used to write data to a destination.

## 📂 File Handling

Java provides several classes to work with files. The most commonly used classes are:

- `File`
- `FileInputStream` / `FileOutputStream`
- `FileReader` / `FileWriter`
- `BufferedReader` / `BufferedWriter`

### 📁 File Class

The `File` class is an abstract representation of file and directory pathnames.

```java
File file = new File("example.txt");
boolean fileExists = file.exists();
long fileSize = file.length();
boolean isDirectory = file.isDirectory();
```

### 💾 Basic File Operations

- **Creating a New File**:
  ```java
  File file = new File("newfile.txt");
  boolean fileCreated = file.createNewFile();
  ```

- **Writing to a File**:
  ```java
  try (FileWriter writer = new FileWriter("output.txt")) {
      writer.write("Hello, World!");
  }
  ```

- **Reading from a File**:
  ```java
  try (BufferedReader reader = new BufferedReader(new FileReader("input.txt"))) {
      String line;
      while ((line = reader.readLine()) != null) {
          System.out.println(line);
      }
  }
  ```

## 🆕 Java NIO

Java NIO (New I/O) is an alternative I/O API for Java, providing a different way of working with I/O than the standard I/O API. It introduces concepts like channels, buffers, and selectors.

Example of using NIO for file reading:
```java
Path path = Paths.get("example.txt");
List<String> lines = Files.readAllLines(path, StandardCharsets.UTF_8);
```

## 📁 Working with Directories

- **Creating a Directory**:
  ```java
  File directory = new File("newDirectory");
  boolean created = directory.mkdir();
  ```

- **Listing Files in a Directory**:
  ```java
  File directory = new File(".");
  String[] fileList = directory.list();
  ```

## 💾 Serialization

Serialization is the process of converting an object into a byte stream. Deserialization is the reverse process.

```java
// Serialization
try (ObjectOutputStream out = new ObjectOutputStream(new FileOutputStream("person.ser"))) {
    Person person = new Person("John Doe", 30);
    out.writeObject(person);
}

// Deserialization
try (ObjectInputStream in = new ObjectInputStream(new FileInputStream("person.ser"))) {
    Person person = (Person) in.readObject();
}
```

## 📊 Working with CSV Files

```java
// Writing to CSV
try (PrintWriter writer = new PrintWriter(new File("data.csv"))) {
    writer.write("Name,Age,City\n");
    writer.write("John,30,New York\n");
    writer.write("Jane,25,London\n");
}

// Reading from CSV
try (BufferedReader br = new BufferedReader(new FileReader("data.csv"))) {
    String line;
    while ((line = br.readLine()) != null) {
        String[] values = line.split(",");
        System.out.println(Arrays.toString(values));
    }
}
```

## 🆕 Java 8 Files API

Java 8 introduced new methods in the `Files` class to make file I/O operations more convenient.

```java
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

## ✅ Best Practices

1. Always close resources (use try-with-resources when possible).
2. Use buffered streams for better performance.
3. Use character streams for text files and byte streams for binary files.
4. Handle exceptions properly.
5. Use NIO for large files or when you need non-blocking I/O.
6. Be careful with file permissions.
7. Use meaningful names for files and directories.

## 🎓 Conclusion

Java provides a rich set of I/O classes and methods to handle various file operations. Understanding these concepts is crucial for developing robust Java applications that interact with the file system. From basic file operations to advanced concepts like NIO and serialization, mastering Java I/O will significantly enhance your ability to work with external data and resources in your Java programs.

## 📚 Resources

- [Java I/O Tutorial](https://docs.oracle.com/javase/tutorial/essential/io/)
- [Java NIO Tutorial](https://docs.oracle.com/javase/tutorial/essential/io/fileio.html)
- [Java 8 Files API](https://docs.oracle.com/javase/8/docs/api/java/nio/file/Files.html)

Happy file handling! 💻📂🚀
