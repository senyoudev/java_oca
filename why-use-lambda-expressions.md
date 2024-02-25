# Lambda Expressions

lambda expressions are a new and important feature included in Java SE 8. They provide a clear and concise way to represent a single method interface using an expression. Lambda expressions also improve the Collection libraries making it easier to iterate through, filter, and extract data from a Collection. In addition, new concurrency features improve performance in multicore environments.

```java
public class LambdaExpressionExample {
    public static void main(String[] args) {
        // with lambda expression
        Thread t = new Thread(() -> {
            System.out.println("Thread is running");
        });
        t.start();
    }
}
```

## Why use Lambda Expressions ?

- Lambda expressions are used primarily to define inline implementation of a functional interface, i.e., an interface with a single method only. In other words, it is used to implement the abstract method of a functional interface.

## How to use Lambda Expressions ?

- A lambda expression is characterized by the following syntax.

```java
(parameters) -> expression
```

- Following are the important characteristics of a lambda expression.

    - Optional type declaration − No need to declare the type of a parameter. The compiler can inference the same from the value of the parameter.

    - Optional parenthesis around parameter − No need to declare a single parameter in parenthesis. For multiple parameters, parentheses are required.

    - Optional curly braces − No need to use curly braces in expression body if the body contains a single statement.

    - Optional return keyword − The compiler automatically returns the value if the body has a single expression to return the value. Curly braces are required to indicate that expression returns a value.