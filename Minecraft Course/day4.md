# Day 4: Functions in Java

## Objective
Understand how to create and use **functions (methods)** in Java to make code reusable, organized, and efficient.

---

## 1. Introduction to Functions
Functions (called *methods* in Java) are reusable blocks of code that perform a specific task.

### Why Use Functions?
- Avoid repeating code.
- Make code organized and modular.
- Improve debugging and maintenance.

### Syntax of a Function
```java
returnType functionName(parameters) {
    // function body
    return value;
}
```

### Example:
```java
public static int addNumbers(int a, int b) {
    int sum = a + b;
    return sum;
}
```

---

## 2. Types of Functions
1. **No Parameters, No Return Value**
2. **Parameters, No Return Value**
3. **Parameters with Return Value**

### Example 1: No Parameters, No Return Value
```java
public static void greet() {
    System.out.println("Hello, welcome to Java!");
}
```
**Explanation:**
- `void` means the function doesn’t return any value.
- The function prints a message when called.

---

### Example 2: Parameters, No Return Value
```java
public static void printSum(int x, int y) {
    int sum = x + y;
    System.out.println("Sum: " + sum);
}
```
**Explanation:**
- Takes two numbers `x` and `y` as input.
- Prints their sum but doesn’t return it.

---

### Example 3: Parameters with Return Value
```java
public static int multiply(int a, int b) {
    return a * b;
}
```
**Explanation:**
- Returns the result of multiplication using `return` keyword.

---

## 3. Calling Functions
Functions must be **called** to execute.

```java
public class Main {
    public static void greet() {
        System.out.println("Hello, Java!");
    }

    public static void main(String[] args) {
        greet(); // function call
    }
}
```

**Output:**
```
Hello, Java!
```

---

## 4. Passing Values to Functions (Parameters)
You can send information into functions.

```java
public class Main {
    public static void printMessage(String name) {
        System.out.println("Welcome, " + name + "!");
    }

    public static void main(String[] args) {
        printMessage("Alex");
        printMessage("Sam");
    }
}
```

**Output:**
```
Welcome, Alex!
Welcome, Sam!
```

---

## 5. Returning Values from Functions
A function can return a value back to the caller.

```java
public class Main {
    public static int square(int num) {
        return num * num;
    }

    public static void main(String[] args) {
        int result = square(5);
        System.out.println("Square: " + result);
    }
}
```

**Output:**
```
Square: 25
```

---

## 6. Combining Multiple Functions
You can call one function from another.

```java
public class Calculator {
    public static int add(int a, int b) {
        return a + b;
    }

    public static int subtract(int a, int b) {
        return a - b;
    }

    public static void main(String[] args) {
        int sum = add(10, 5);
        int diff = subtract(10, 5);
        System.out.println("Sum: " + sum);
        System.out.println("Difference: " + diff);
    }
}
```

**Output:**
```
Sum: 15
Difference: 5
```

---

## 7. Activity: Create a Simple Calculator

### Task
Create a calculator that performs:
- Addition
- Subtraction
- Multiplication
- Division

### Sample Code
```java
import java.util.Scanner;

public class SimpleCalculator {

    public static int add(int a, int b) {
        return a + b;
    }

    public static int subtract(int a, int b) {
        return a - b;
    }

    public static int multiply(int a, int b) {
        return a * b;
    }

    public static double divide(int a, int b) {
        if (b != 0)
            return (double) a / b;
        else {
            System.out.println("Error! Division by zero.");
            return 0;
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter first number: ");
        int num1 = sc.nextInt();

        System.out.print("Enter second number: ");
        int num2 = sc.nextInt();

        System.out.println("Addition: " + add(num1, num2));
        System.out.println("Subtraction: " + subtract(num1, num2));
        System.out.println("Multiplication: " + multiply(num1, num2));
        System.out.println("Division: " + divide(num1, num2));
    }
}
```

### Explanation
- Four functions perform the operations.
- User enters two numbers.
- Program displays all results.

**Output Example:**
```
Enter first number: 8
Enter second number: 2
Addition: 10
Subtraction: 6
Multiplication: 16
Division: 4.0
```

---

## 8. Homework
1. Create a function `findLargest()` that takes three numbers and returns the largest.
2. Create a function `isEven()` that returns `true` if a number is even, otherwise `false`.
3. Modify the calculator to allow the user to choose the operation before entering numbers.

---

## 9. Summary
- Functions help organize and reuse code.
- You can pass values into functions and get results back.
- Using functions makes your programs cleaner and easier to manage.