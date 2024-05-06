# Working with Selected classes from the Java API

## Working with the String class

### String initialization

- A String object can be created in two ways:
  - By using a string literal: `String str = "Hello";`
  - By using the `new` keyword: `String str = new String("Hello");`

### String manipulation

- Strings are immutable in Java, which means that once a string is created, it cannot be changed. Any operation that appears to modify a string actually creates a new string object.
- Accessing characters in a string: `char ch = str.charAt(0);`
- Concatenating strings: `String newStr = str1 + str2;`
- Comparing strings: `boolean isEqual = str1.equals(str2);`
- Searching for substrings: `int index = str.indexOf("substring");`
- Extracting substrings: `String subStr = str.substring(0, 5);`


### Working with the StringBuilder class

- The `StringBuilder` class is used to create mutable strings in Java.
- By default, a `StringBuilder` object has a capacity of 16 characters. If the capacity is exceeded, the `StringBuilder` class automatically increases the capacity.

### StringBuilder methods

- Appending strings: `StringBuilder.append("string");`
- Inserting strings: `StringBuilder.insert(0, "string");`
- Deleting characters: `StringBuilder.delete(0, 5);`
- Reversing the string: `StringBuilder.reverse();`
- Converting to a string: `String str = StringBuilder.toString();`

## LocalDate, LocalTime, and LocalDateTime

### LocalDate

- Represents a date without a time zone.
- Example: `LocalDate date = LocalDate.of(2022, 1, 1);`

The result of the above code will be `2022-01-01`.  
=> This is a local date related to the current time zone of the system, so for example if you run this code in New York, the date will be `2022-01-01` in New York time zone.

### LocalTime

- Represents a time without a time zone.(not the date) 
- Example: `LocalTime time = LocalTime.of(12, 0);`

The result of the above code will be `12:00`.
=> This is a local time related to the current time zone of the system, so for example if you run this code in New York, the time will be `12:00` in New York time zone.

### LocalDateTime

- Represents a date and time without a time zone.
- Example: `LocalDateTime dateTime = LocalDateTime.of(2022, 1, 1, 12, 0);`

The result of the above code will be `2022-01-01T12:00`.
=> This is a local date and time related to the current time zone of the system, so for example if you run this code in New York, the date and time will be `2022-01-01T12:00` in New York time zone.


## Working With ArrayList

### ArrayList Initialization

- An `ArrayList` is a resizable array that can grow or shrink in size.
- To create an `ArrayList`, you need to import the `ArrayList` class from the `java.util` package.
- Example: `ArrayList<String> list = new ArrayList<>();`

### ArrayList Methods

- Adding elements: `list.add("element");`
- Removing elements: `list.remove(0);`
- Getting elements: `String element = list.get(0);`
- Checking if an element exists: `boolean exists = list.contains("element");`
- Getting the size of the list: `int size = list.size();`

### Sort ArrayList

- To sort an `ArrayList`, you can use the `Collections.sort()` method.
- Example: `Collections.sort(list);`

## Lambda Expressions

### Lambda Expressions Overview

- Lambda expressions are a feature introduced in Java 8 that allow you to write code in a more concise and expressive way.
- Lambda expressions are used to define anonymous functions, which can be passed as arguments to methods or stored in variables.
- Lambda expressions are made up of three parts: the parameter list, the arrow token `->`, and the body.

### Syntax

- The basic syntax of a lambda expression is as follows:
  - `(parameters) -> expression`
  - `(parameters) -> { statements; }`

### Example

- Here is an example of a lambda expression that adds two numbers:
  - `(int a, int b) -> a + b`

### Using lambda with ArrayList

- You can use lambda expressions with the `ArrayList` class to perform operations on the elements of the list.

```java
ArrayList<Integer> list = new ArrayList<>();
list.add(1);
list.add(2);
list.add(3);

// Using lambda expression to print all elements of the list
list.forEach(element -> System.out.println(element));
// Using lambda expression to remove elements that are greater than 2
list.removeIf(element -> element > 2);
```




