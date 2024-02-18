# Working With Java Data Types


## Primitive and Object Types

- All classes are data types, but not all data types are classes.Some data types are built into the Java language and are called primitive data types.
- The difference is that primitive data types are stored in the stack, while objects are stored in the heap.
- The primitive data types are:
  - byte
  - short
  - int
  - long
  - float
  - double
  - char
  - boolean

- The difference between float and double is that float is a single-precision 32-bit IEEE 754 floating point, while double is a double-precision 64-bit IEEE 754 floating point.which means that double is more precise than float. and can represent larger numbers.

Example of the difference between float and double:
```java
public class FloatAndDouble {
    public static void main(String[] args) {
        float floatNumber = 3.4028235E38f;
        double doubleNumber = 1.7976931348623157E308;
        System.out.println(floatNumber);
        System.out.println(doubleNumber);
    }
}
```

## Primitive Type Casting

- Casting is the process of converting a value from one data type to another.
- There are two types of casting:
  - Widening casting (automatically) - converting a smaller type to a larger type size
  - Narrowing casting (manually) - converting a larger type to a smaller size type
- In java, when you perform arithmetic operations on byte, short, or char, the result is always an int.that's because java defines that arithmetic operations on byte, short, or char are performed as if they are on type (int,long,float,double).

Example of casting:
```java
public class Casting {
    public static void main(String[] args) {
        int myInt = 9;
        double myDouble = myInt; // Automatic casting: int to double
        System.out.println(myInt);      // Outputs 9
        System.out.println(myDouble);   // Outputs 9.0
    }
}
```

Example of Casting 
```java
public class Casting {
    public static void main(String[] args) {
        int myInt = 9;
        int myInt2 = 10;
        double myDouble = (double) myInt / myInt2; // Result is 0.9
        double myDouble2 = myInt / myInt2; // Result is 0.0
    }
}
```

Interesting notice :
```java
public class Casting {
    public static void main(String[] args) {
       byte b = 127;
       byte c = 1;
       byte d = (byte) (b + c); // Error: incompatible types: possible lossy conversion from int to byte => Result will be -128
       // because b + c will be 128 and 128 is out of the range of byte, so it will now go out of the range and start from the beginning of the range.
     }
}
```

Example with Char
```java
public class Casting {
    public static void main(String[] args) {
        char a = 'a';
        char b = ++a; // b will be b
        char x = a + 1;
        System.out.println(b); // b because ++ does not change the type of the variable , it just increments the value of the variable
        System.out.println(x); // error incompatible types: possible lossy conversion from int to char
    }
}
```

## Primitive wrapper classes

- Java provides classes that correspond to each of the primitive data types.
- These are called wrapper classes because they "wrap" the primitive data type into an object.
- The wrapper classes are:
  - Byte
  - Short
  - Integer
  - Long
  - Float
  - Double
  - Character
  - Boolean

- Moving from primitive to object is called autoboxing, and moving from object to primitive is called unboxing.
- For example,we can use the wrapper classes to convert a string to a primitive data type.but if we pass a string that is not a number, we will get a NumberFormatException. It is a runtime exception, so we don't need to catch it.

Example of autoboxing and unboxing:
```java
public class WrapperClasses {
    public static void main(String[] args) {
        Integer myInt = 5;
        Double myDouble = 5.99;
        Character myChar = 'A';
        System.out.println(myInt.intValue());
        System.out.println(myDouble.doubleValue());
        System.out.println(myChar.charValue());
    }
}
```

Example of converting a string to a primitive data type:
```java
public class WrapperClasses {
    public static void main(String[] args) {
        String myString = "10";
        int myInt = Integer.parseInt(myString);
        System.out.println(myInt);
    }
}
```

Concerning the case of a boolean, if we pass a wrong argument, we will not get a NumberFormatException. and the value of the boolean will be false.

Example of converting a string to a boolean:
```java
public class WrapperClasses {
    public static void main(String[] args) {
        String myString = "true";
        boolean myBoolean = Boolean.parseBoolean(myString); // true
        boolean myBoolean2 = Boolean.parseBoolean("boolean"); // false
        System.out.println(myBoolean);
    }
}
```

## Passing Parameters

- When you pass a primitive data type to a method, it is passed by value. This means that any changes to the parameter inside the method have no effect on the argument. Here, you are just creating a copy of the variable.

Example of passing a primitive data type to a method:
```java
public class PassingParameters {
    public static void main(String[] args) {
        int x = 3;
        change(x);
        System.out.println(x); // Outputs 3
    }

    static void change(int x) {
        x = 5;
    }
}
```

- When you pass an object to a method, the reference to the object is passed by value. This means that any changes to the object inside the method have an effect on the argument.

Example of passing an object to a method:
```java
public class PassingParameters {
    public static void main(String[] args) {
        Dog aDog = new Dog("Max");
        change(aDog);
        System.out.println(aDog.getName()); // Outputs Fifi
    }

    static void change(Dog dog) {
        dog.setName("Fifi");
    }
}
```

So basically, in java there is no passing by reference, only passing by value. but when we pass an object, we pass the reference to the object by value. so we can change the object, but we can't change the reference.

## Accessing Static Variables and Methods

- In a static method, you cannot access instance variables or instance methods directly. You can access them only through an object reference.
- In a static method, you cannot use the this keyword because there is no instance for this to refer to.
- You can access static variables and methods directly through the class name without using any object reference.

Example of accessing static variables and methods:
```java
public class StaticVariablesAndMethods {
    static int x = 10;
    int y = 20;

    public void myMethod() {
        System.out.println("Instance Method");
    }

    public static void main(String[] args) {
        System.out.println(x); // Outputs 10
        // System.out.println(y); // Error: non-static variable y cannot be referenced from a static context
        StaticVariablesAndMethods myObj = new StaticVariablesAndMethods();
        StaticVariablesAndMethods.myMethod(); // Error: non-static method myMethod() cannot be referenced from a static context
        System.out.println(myObj.y); // Outputs 20
    }
}
```