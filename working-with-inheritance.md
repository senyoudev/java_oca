# Working with Inheritance

## Extending a Class

- A java class can only extend one class.All classes in Java extend from the Object class.
- A subclass inherits all the members (fields, methods, and nested classes) from its superclass.
- A subclass can override methods from its superclass.
- A subclass can hide fields and methods from its superclass.
- A subclass can add new fields and methods.
- A subclass can call the constructor of its superclass using the `super()` keyword.

```java
public class Product {
    private String name;
    public double price;

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

```java
public class Book extends Product {
    private String author;
    //hide the price field from the superclass
    private double price; // this field hides the price field from the superclass

    public Book(String name, double price, String author) {
        super(name, price); // super keyword to call the constructor of the superclass
        this.author = author;
    }

    public String getAuthor() {
        return author;
    }
}
```

- if book doesnt call super(name,price) then it will call the default constructor of the superclass which is not defined in the superclass so it will give a compilation error. 

## Constructing new Objects

- When a new object is created, the constructor of the superclass is called first, and then the constructor of the subclass is called.


```java
new Book("Java", 45.0, "John Doe"); // calls the constructor of the superclass and then the constructor of the subclass
```

## Using Reference

- A reference variable of a superclass can refer to an object of its subclass.
- A reference variable of a subclass cannot refer to an object of its superclass.

```java
Product product = new Book("Java", 45.0, "John Doe"); // Book is a subclass of Product
```

```java
Book book = new Product("Java", 45.0); // Compilation error because Product is a superclass of Book
```
-The reference doesnt determine the object that is created, it only determines the methods and fields that can be accessed.

```java
Product product = new Book("Java", 45.0, "John Doe"); // the reference is of type Product, but the object is of type Book
System.out.println(product.getName()); // Java
System.out.println(product.getPrice()); // 45.0
```

## Assigning reference

- A reference variable of a subclass can be assigned to a reference variable of its superclass.
- An explicit cast is required to assign a reference variable of a superclass to a reference variable of its subclass.

```java
Product product = new Book("Java", 45.0, "John Doe");
Book book = (Book) product; // explicit cast
```

Basically, when we cast an object, it does not change the object itself, it only changes the reference to the object.The object in the heap is the same, only the reference is changed.

Let's see the following example:
    
```java
Product  p1 = new Book("Java", 45.0, "John Doe");
Product p2 = new Item("Pen", 2.0); // another subclass of Product
Product p3 = p2; // p3 refers to the same object as p2
// if we do 
p2.setName("Pencil");
System.out.println(p3.getName()); // Pencil
```

## Overriding Methods

- A subclass can override a method from its superclass.
- The method in the subclass must have the same signature as the method in the superclass.
- The method in the subclass must have the same return type or a subtype of the return type of the method in the superclass.
- The method in the subclass cannot have a lower access modifier than the method in the superclass.
- The method in the subclass cannot throw a broader exception than the method in the superclass.

```java
public class Product {
    public void print() {
        System.out.println("Product");
    }
}
```

```java
public class Book extends Product {
    @Override
    public void print() {
        System.out.println("Book");
    }
    // same signature, same return type, same or higher access modifier, same or narrower exception
}
```

```java
Product product = new Book();
product.print(); // Book
```

### Polymorphism

- Polymorphism is the ability of an object to take on many forms.
- A reference variable can refer to different types of objects, and the correct method will be called at runtime.
- Polymorphism is the ability of a method to do different things based on the object that it is acting upon.



```java
public class Product {
    public String getName() {
        return "Product";
    }
}
```

```java
public class Book extends Product {
    @Override
    public String getName() {
        return "Book";
    }
}
```
```java
Product product = new Book("Java", 45.0, "John Doe");
System.out.println(product.getName()); // Java
```

- The method getName() in the subclass Book overrides the method getName() in the superclass Product. polymorphism allows the method getName() in the subclass Book to be called at runtime.


## Creating Abstract Classes

- An abstract class cannot be instantiated.
- An abstract class can have abstract methods.
- An abstract class can have concrete methods.
- A subclass of an abstract class must implement all the abstract methods of the superclass, unless the subclass is also an abstract class.

```java
public abstract class Product {
    public abstract String getName();
    public abstract double getPrice();
}
```

```java
public class Book extends Product {
    @Override
    public String getName() {
        return "Book";
    }

    @Override
    public double getPrice() {
        return 45.0;
    }
}
```

- If a subclass of an abstract class does not implement all the abstract methods of the superclass, then the subclass must also be declared abstract.

```java
public abstract class Book extends Product {
    @Override
    public String getName() {
        return "Book";
    }
    // getPrice() is not implemented
}
```

- Do we have abstract fields? No, we don't have abstract fields in Java. Fields are always initialized with a default value.Even if we don't initialize them, they will be initialized with a default value unless they are static,they should be initialized by the programmer or an exception will be thrown.

## Extending an abstract class

```java
public abstract class Product {
    public abstract String getName();
    public abstract double getPrice();
}
```

```java
public abstract class Book extends Product {
    @Override
    public String getName() {
        return "Book";
    }
    // getPrice() is not implemented
}
```

```java
public class Fiction extends Book {
    @Override
    public double getPrice() {
        return 45.0;
    }
}
```

```java
Product product = new Fiction();
System.out.println(product.getName()); // Book
System.out.println(product.getPrice()); // 45.0
```

## Interfaces

- An interface is a fully abstract class.
- An interface cannot have concrete methods.
- An interface can have default methods.
- An interface can have static methods.
- An interface can have static fields.
- An interface can have constant fields.
- All the methods of an interface must are public abstract.
- All the fields of an interface must be public static final.
- An interface can extend another interface.

```java
public interface Product {
    public final static String NAME = "Product";
    public abstract String getName();
    // default method
    public default double getPrice() {
        return 0;
    }
    String getName();
    double getPrice();
}
```

```java
public class Book implements Product {
    @Override
    public String getName() {
        return "Book";
    }
    @Override
    public double getPrice() {
        return 45.0;
    }
}
```

## Using an interface for multiple inheritance

- A class can implement multiple interfaces.
- A class cannot extend multiple classes.

```java
public interface Product {
    public abstract String getName();
    public abstract double getPrice();
}
```

```java
public interface Saleable {
    public abstract double getDiscount();
}
```

```java
public class Book implements Product, Saleable {
    @Override
    public String getName() {
        return "Book";
    }
    @Override
    public double getPrice() {
        return 45.0;
    }
    @Override
    public double getDiscount() {
        return 5.0;
    }
}
```

