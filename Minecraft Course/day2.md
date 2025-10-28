# Day 2: Understanding Java Basics (Input/Output)

## Goal
Learn basic Java syntax, variables, and how to take user input and print output.

By the end of this class, students should be able to:
- Write and run a simple Java program.
- Use `System.out.println()` to display output.
- Use `Scanner` to take input from the user.
- Understand data types (`int`, `String`, `double`, etc.).

---

## Prerequisites
- Java installed (from Day 1).
- Any IDE (IntelliJ IDEA or VS Code with Java extension).

---

## Concepts to Cover
1. Structure of a Java Program  
2. Printing Output (`System.out.println`)  
3. Taking Input (`Scanner`)  
4. Variables and Data Types  
5. Simple Arithmetic Operations  
6. Practice Program — *Greeting & Calculator*

---

## 1. Basic Structure of a Java Program

```java
public class Main {
    public static void main(String[] args) {
        // Code goes here
    }
}
```

### Explanation
| Line | Code | Explanation |
|------|------|--------------|
| 1 | `public class Main {` | Defines a public class named `Main`. |
| 2 | `public static void main(String[] args) {` | Java starts execution here. |
| 3 | `// Code goes here` | This is a comment. |
| 4 | `}` | Ends the method. |
| 5 | `}` | Ends the class. |

---

## 2. Printing Output

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Welcome to Minecraft Modding!");
        System.out.println("Java makes it all possible!");
    }
}
```

### Explanation
| Line | Code | Explanation |
|------|------|-------------|
| 3 | `System.out.println("Welcome to Minecraft Modding!");` | Prints a message followed by a new line. |
| 4 | `System.out.println("Java makes it all possible!");` | Prints another message. |

---

## 3. Taking Input from the User

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.print("Enter your name: ");
        String name = input.nextLine();

        System.out.println("Hello, " + name + "! Welcome to Java.");
    }
}
```

### Explanation
| Line | Code | Explanation |
|------|------|-------------|
| 1 | `import java.util.Scanner;` | Imports the Scanner class. |
| 4 | `Scanner input = new Scanner(System.in);` | Creates a Scanner object. |
| 6 | `System.out.print("Enter your name: ");` | Displays prompt without a new line. |
| 7 | `String name = input.nextLine();` | Reads a full line. |
| 9 | `System.out.println("Hello, " + name + "! Welcome to Java.");` | Displays greeting. |

---

## 4. Variables and Data Types

| Type | Example | Description |
|------|----------|-------------|
| `int` | 10 | Whole numbers |
| `double` | 12.5 | Decimal numbers |
| `String` | "Steve" | Text |
| `boolean` | true / false | Logical values |

```java
public class Main {
    public static void main(String[] args) {
        int age = 15;
        double height = 5.7;
        String name = "Alex";

        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Height: " + height + " feet");
    }
}
```

---

## 5. Simple Arithmetic Operations

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter first number: ");
        int num1 = sc.nextInt();

        System.out.print("Enter second number: ");
        int num2 = sc.nextInt();

        int sum = num1 + num2;
        int diff = num1 - num2;
        int product = num1 * num2;
        int quotient = num1 / num2;

        System.out.println("Sum: " + sum);
        System.out.println("Difference: " + diff);
        System.out.println("Product: " + product);
        System.out.println("Quotient: " + quotient);
    }
}
```

---

## 6. Practice Task – Greeting & Age Program

```java
import java.util.Scanner;

public class GreetingProgram {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.print("Enter your name: ");
        String name = input.nextLine();

        System.out.print("Enter your age: ");
        int age = input.nextInt();

        System.out.println("Hello " + name + "! You are " + age + " years old.");
        System.out.println("Next year, you will be " + (age + 1) + " years old!");
    }
}
```

---

## ⚠️ Common Mistakes to Watch For
| Mistake | Why It Happens | How to Fix |
|----------|----------------|------------|
| Missing semicolon `;` | Every statement ends with `;` | Check each line. |
| Class name mismatch | File name must match class name | Save as `Main.java`. |
| Scanner not imported | Forgot import statement | Add `import java.util.Scanner;`. |
| Mixing `nextInt()` and `nextLine()` | Scanner skips a line after reading number | Use `input.nextLine()` to clear buffer. |

---



---

## Mini Challenge (Homework)

**Task:**  
Write a Java program that asks the player for their Minecraft username and favorite block.  
Then print:  
`Hey [name], let's build with [block] today!`