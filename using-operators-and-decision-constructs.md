## Using Operators and Decision Constructs

## Conditionals

### if and else

```java
public class IfElse {
    public static void main(String[] args) {
        int x = 10;
        if (x == 10) {
            System.out.println("Yes, x is 10");
        } else {
            System.out.println("No, x is not 10");
        }
    }
}
```

- The `if` statement is used to test a condition. If the condition is true, the code inside the `if` block is executed. `else` is optional and is executed if the condition is false.
- In java,there is no `elif` keyword, but you can use `else if` to test multiple conditions.it is just a combination of `else` and `if`.

```java
public class ElseIf {
    public static void main(String[] args) {
        int x = 10;
        if (x == 10) {
            System.out.println("Yes, x is 10");
        } else if (x == 20) {
            System.out.println("No, x is 20");
        } else {
            System.out.println("No, x is not 10 or 20");
        }
    }
}
```

### Switch

```java
public class Switch {
    public static void main(String[] args) {
        int x = 10;
        switch (x) {
            case 10:
                System.out.println("x is 10");
                break;
            case 20:
                System.out.println("x is 20");
                break;
            default:
                System.out.println("x is not 10 or 20");
        }
    }
}
```

- The condition in a `switch` statement must be an integer, a string, or an enumerated type.
- The execution of the `switch` statement starts with the first `case` whose value matches the value of the expression. If no `case` matches the value of the expression, the `default` block is executed.which means, you go through all cases not only the matching one, it is like `goto` statement in C language. you can use `break` to stop the execution of the `switch` statement. 

### Ternary Operator

```java
public class TernaryOperator {
    public static void main(String[] args) {
        int x = 10;
        String result = (x == 10) ? "Yes, x is 10" : "No, x is not 10";
        System.out.println(result);
    }
}
```

- The ternary operator is a shorthand way of writing an `if-then-else` statement. It has three parts: a condition, an expression to execute if the condition is true, and an expression to execute if the condition is false.

- Talking about `&&` and `&` in conditional statements, `&&` is a short-circuit operator, which means that it evaluates the right-hand side of the expression only if the left-hand side is true. `&` is a non-short-circuit operator, which means that it evaluates both sides of the expression, regardless of the result of the left-hand side.
- Basically, `&` is used for example if you do an operation in the right-hand side that has a side effect in the block of code, and you want to execute it regardless of the result of the left-hand side.

### Comparing Objects

- When comparing objects, you should use the `equals` method instead of the `==` operator. The `==` operator compares the references of the objects, while the `equals` method compares the content of the objects.

```java
public class ComparingObjects {
    public static void main(String[] args) {
        String s1 = new String("Hello");
        String s2 = new String("Hello");
        System.out.println(s1 == s2); // Outputs false
        System.out.println(s1.equals(s2)); // Outputs true
    }
}
```

