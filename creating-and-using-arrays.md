# Creating and Using Arrays

## Declar Array Object

```java
int[] numbers;
int numbers[];
// Both are valid
```

## Create Array Object

```java
int[] numbers = new int[3];
int numbers[] = new int[3];
// Both are valid
```

## Initialize Array

```java
int[] numbers = {1, 2, 3};
int numbers[] = {1, 2, 3};
// Both are valid
```

- Example with a class type Product:


```java
Product[] products = new Product[3];
products[0] = new Product();
products[1] = new Product();
products[2] = new Product();
```

## Accessing Array Elements

```java
int[] numbers = {1, 2, 3};
System.out.println(numbers[0]); // 1
System.out.println(numbers[1]); // 2
System.out.println(numbers[2]); // 3
```

=> Produce : ArrayIndexOutOfBoundsException

```java
int[] numbers = {1, 2, 3};
System.out.println(numbers[3]); // ArrayIndexOutOfBoundsException
```
ArrayIndexOutOfBoundsException is a runtime exception, so it doesn't need to be caught or declared.

=> Produce : ArithmeticException

```java
int[] numbers;
numbers[0] = 1;
numbers[1] = 2;
System.out.println(numbers[1] / numbers[2]); // ArithmeticException
// because numbers[2] is not initialized, so it will be 0 by default
```

=> Produce : NullPointerException

```java
Product[] products = new Product[3];
products[0].setName("Product 1"); // NullPointerException because products[0] is not initialized
```

## Using multi-dimensional arrays

```java
int[][] twoDArray = new int[3][2];
twoDArray[0][0] = 1;
twoDArray[0][1] = 2;
twoDArray[1][0] = 3;
twoDArray[1][1] = 4;
twoDArray[2][0] = 5;
twoDArray[2][1] = 6;
```

### Iterate over multi-dimensional arrays

```java
int[][] twoDArray = new int[3][2];
for (int i = 0; i < twoDArray.length; i++) {
    for (int j = 0; j < twoDArray[i].length; j++) {
        System.out.println(twoDArray[i][j]);
    }
}
```

### Array copy to resize

Array copy normally doesn't resize the array, it just copies the elements from the old array to the new array. If the new array is larger than the old array, the remaining elements will be initialized to the default value for the type. this is because once you create an array, its size is fixed.

```java
int[] numbers = {1, 2, 3};
int[] newNumbers = new int[5];
System.arraycopy(numbers, 0, newNumbers, 0, numbers.length); // old array, start index, new array, start index, length
```