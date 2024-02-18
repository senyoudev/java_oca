# Java Basics

### Java Basics
- Java is a high-level programming language that is platform-independent and object-oriented.
- Java is a strongly typed language, which means that all variables must first be declared before they can be used.

### The Java Technology and Development Environment
- The Java Development Kit (JDK) is a software development environment used for developing Java applications and applets.
- The Java Runtime Environment (JRE) is a part of the JDK that contains the JVM, which is used to run Java applications and applets.
- The Java Virtual Machine (JVM) is a part of the JRE that executes Java bytecode.

## Scope of Variables

- Local variables: A local variable is a variable that’s declared within a method.
- Instance variables: An instance variable is a variable that’s declared within a class but outside any method.
- Class variables: A class variable is a variable that’s declared as static within a class.

Example of local variable:
```java
public void eat(int piecesOfCheese) {
    int bitesOfCheese = 1; // local variable
}
```
Example of instance variable:
```java
public class Mouse {
    int numTeeth;
    static int numWhiskers;
    int getTeeth() { return numTeeth; }

    // numTeeth is an instance variable
    // numWhiskers is a class variable
}
```

## Structure of a Java Class

- A class is a blueprint from which objects are created.
- A class can contain fields, methods, constructors, and blocks.
- Fields are variables that store data.
- Methods operate on the data.
- Constructors create the object.
- Blocks of code are used to initialize fields.

Example of a class:
```java
public class Animal {
    // instance variables
    String name;

    // constructor
    Animal() {
        name = "unknown";
    }

    // method 
    public String getName() {
        return name;
    }

    public void setName(String newName) {
        name = newName;
    }

    // main method 
    public static void main(String[] args) {
        Animal myPet = new Animal();
        myPet.setName("Lassie");
        System.out.println(myPet.getName());
    }
}
```

## Create executable Java applications with a main method; run a Java program from the command line; produce console output

- The main method is the entry point of a Java application.
- The main method has the following syntax:

Example of a main method:
```java
public class Zoo {
    public static void main(String[] args) {
        System.out.println("Welcome to the Zoo!");
    }
}
```

- The main method is declared public so that it can be accessed by any object.
- The main method is declared static so that it can be called without creating an instance of the class.
- The main method is declared void because it doesn’t return a value.
- The main method has a single argument of type String array.

## Import other Java packages to make them accessible in your code

- The import statement is used to make classes and interfaces available to your code.
- The import statement has the following syntax:

Example of an import statement:
```java
import java.util.Random;
```

## Compare and contrast the features and components of Java such as: platform independence, object orientation, encapsulation, etc.

- Java is platform-independent, which means that Java applications can run on any operating system that has a Java Runtime Environment (JRE) installed.

- Java is object-oriented, which means that Java programs are made up of classes and objects.

- Encapsulation is the mechanism that binds together code and the data it manipulates, and keeps both safe from outside interference and misuse.

- Inheritance is the mechanism that allows one class to inherit the properties of another class.

- Polymorphism is the mechanism that allows one interface to be used for a general class of actions.

- Abstraction is the mechanism that allows you to define the interface for a class, hiding the implementation details.

- The is no multiple inheritance in Java, a class can only extend one class.


