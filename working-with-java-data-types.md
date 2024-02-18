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
