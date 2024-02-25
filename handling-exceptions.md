# Handling Exceptions in Java


- The parent class for all exceptions is `Throwable`.
- `Error` is used to indicate serious problems that a reasonable application should not try to catch.but `Exception` is used to indicate conditions that a reasonable application might want to catch.
- `RuntimeException` is used to indicate programming errors.
- so basically, there are two types of exceptions: checked and unchecked.and `Error` is not an exception, it is a problem that should not be caught.
- Checked exceptions are exceptions that are checked at compile time. If some code within a method throws a checked exception, then the method must either handle the exception or it must specify the exception using throws keyword.
- Unchecked exceptions are exceptions that are not checked at compile time. It is up to the programmer to check for these exceptions.

## How to catch exceptions (Checked Exceptions of course)

```java
try {
    // code that may throw an exception
} catch (Exception e) {
    // code to handle the exception
}
```

- The `try` block contains the code that may throw an exception.
- The `catch` block contains the code that will handle the exception.
- The `catch` block is only executed if an exception is thrown in the `try` block.
- The `catch` block takes an argument of type `Exception` which is the type of the exception that was thrown.

I was always wondering why some people do try(expression) {} instead of try{} like in the following example:

```java
try (BufferedReader reader = new BufferedReader(new FileReader("file.txt"))) {
    // code that may throw an exception
} catch (IOException e) {
    // code to handle the exception
}
```

The answer has a relationship with 'try-with-resources' statement. The try-with-resources statement is a try statement that declares one or more resources. A resource is an object that must be closed after the program is finished with it. The try-with-resources statement ensures that each resource is closed at the end of the statement. Any object that implements `java.lang.AutoCloseable`, which includes all objects which implement `java.io.Closeable`, can be used as a resource.

## Catching multiple exceptions

```java
try {
    // code that may throw an exception
} catch (IOException e) {
    // code to handle the exception
} catch (SQLException e) {
    // code to handle the exception
} catch (Exception e) {
    // code to handle the exception
} finally {
    // code that will always be executed
}
j()
```

-In the case above, the `catch` blocks are executed in order. If an `IOException` is thrown, the first `catch` block is executed. If a `SQLException` is thrown, the second `catch` block is executed. If any other exception is thrown, the third `catch` block is executed.so basically,theere is a possibility that all the catch blocks will be executed.
- The `finally` block is always executed, regardless of whether an exception was thrown or not.
- The method `j()` will be executed after the `finally` block.it will be executed regardless of whether an exception was thrown or not.