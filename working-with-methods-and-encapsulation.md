# Methods and Encapsulation

## Access Modifiers

- **public**: The method can be called from any class.
- **protected**: The method can only be called from classes in the same package or from subclasses.
- **default**: The method can only be called from classes in the same package.
- **private**: The method can only be called from the same class.

# Encapsulation

- **Encapsulation** is the mechanism that binds together code and the data it manipulates, and keeps both safe from outside interference and misuse.

- Make variables private.
- Provide constructors to initialize objects.
- Provide Accessor methods to read data.

```java
public class Product {
    // private variables
    private String name;
    private double price;

    // constructor
    public Product(String name, double price) {
        this.name = name;
        this.price = price;
    }

    // accessor methods : Getters and Setters
    public String getName() {
        return name;
    }

    public double getPrice() {
        return price;
    }
}
```

## Reminder : Passing parameters

- Concerning primitive types, the value of the variable is passed to the method.
- Concerning objects, the reference of the object is passed to the method.

## Overloading

- **Overloading** is the ability to define two or more methods with the same name in a class, but with different parameters (number or type).Overloaded methods must have same name and same return type.

-varargs can be used to define a method that can take a variable number of arguments.
    
```java
public void print(int... numbers) {
    for (int number : numbers) {
        System.out.println(number);
    }
}
```

- The varargs must be the last parameter in the method signature.

## Constructors

- A default constructor is added to a class if no constructor is defined.
- A constructor can call another constructor in the same class using `this()`.
- A `super()` call invokes the constructor of the superclass.

```java
public class Product {
    private String name;
    private double price;

    public Product() {
        this("Unknown", 0);
    }

    public Product(String name, double price) {
        this.name = name;
        this.price = price;
    }
}
```

```java
public class Book extends Product {
    private String author;

    public Book(String name, double price, String author) {
        super(name, price); // super keyword to call the constructor of the superclass
        this.author = author;
    }
}
```

## Static Methods

- A static method belongs to the class and not to the instances of the class.
- A static method can be called directly from the class name without creating an instance of the class.
- A static method can only access other static members of the class.

```java
public class Product {
    private static int count;

    public Product() {
        count++;
    }

    public static int getCount() {
        return count;
    }
}
```

## Immutability 

- An object is considered immutable if its state cannot change after it is constructed.which means that the object cannot be modified after it is created.for example, an object of the String class is immutable.
- An immutable variable is a variable that once assigned a value, cannot be changed.which means that is a final variable.
- An immutable class is a class that once created, its instances cannot be modified.
- An immutable me

- To create an immutable class, you need to:
    - Make the class final, so it can't be extended.
    - Make all fields private, so they can't be accessed directly.
    - Don't provide any setter methods.
    - Make all mutable fields final, so they can't be changed after the object is constructed.
    - Initialize all fields via a constructor performing deep copy.

```java
public final class Product {
    private final String name;
    private final double price;

    public Product(String name, double price) {
        this.name = name;
        this.price = price;
    }

    public String getName() {
        return name;
    }

    public double getPrice() {
        return price;
    }
}
```

