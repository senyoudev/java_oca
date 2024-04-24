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

