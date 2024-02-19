# Using Loop Constructs

## For Loop

```java
for (int i = 0; i < 10; i++) {
    System.out.println(i); // 0 1 2 3 4 5 6 7 8 9
}
```

## Enhanced For Loop

```java
int[] numbers = {1, 2, 3};
for (int number : numbers) {
    System.out.println(number); // 1 2 3
}
```

## While Loop

```java
int i = 0;
while (i < 10) {
    System.out.println(i); // 0 1 2 3 4 5 6 7 8 9
    i++;
}
```

## Do-While Loop

```java
int i = 0;
do {
    System.out.println(i); // 0 1 2 3 4 5 6 7 8 9
    i++;
} while (i < 10);
```

The difference between `while` and `do-while` is that `do-while` will always execute the block of code at least once, because the condition is checked after the block of code is executed.

## Break and Continue

```java
for (int i = 0; i < 10; i++) {
    if (i == 5) {
        break; // exit the loop
    }
    System.out.println(i); // 0 1 2 3 4
}
```

```java
for (int i = 0; i < 10; i++) {
    if (i == 5) {
        continue; // skip the iteration
    }
    System.out.println(i); // 0 1 2 3 4 6 7 8 9
}
```

## Labels

```java
outer:
for (int i = 0; i < 10; i++) {
    inner:
    for (int j = 0; j < 10; j++) {
        if (i == 5 && j == 5) {
            break outer; // exit the outer loop
        }
        System.out.println(i + " " + j);
    }
}
```

how label works:
- `break outer;` will exit the outer loop and continue the code after the outer loop, why ? because the label `outer` is defined before the outer loop.
- `break inner;` will exit the inner loop and continue the code after the inner loop, why ? because the label `inner` is defined before the inner loop.

## Infinite Loop

```java
for (;;) {
    System.out.println("Infinite loop");
}
```