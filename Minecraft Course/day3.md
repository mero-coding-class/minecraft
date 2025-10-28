# Day 3: Loops and Conditions in Java

## Goal
Master decision-making and repetition using `if`, `else`, `for`, and `while` loops.

By the end of this class, students should be able to:
- Write conditional statements (`if`, `else if`, `else`).
- Use looping structures (`for`, `while`, `do-while`).
- Combine logic to create interactive programs.
- Build a number guessing game using loops and conditions.

---

## Prerequisites
- Knowledge of Java syntax, variables, and input/output (from Day 2).
- IDE setup (IntelliJ IDEA or VS Code with Java Extension).

---

## Concepts to Cover
1. Conditional Statements (`if`, `else if`, `else`)
2. Comparison and Logical Operators
3. The `for` Loop
4. The `while` and `do-while` Loops
5. Nested Conditions and Loops
6. Mini Project — *Number Guessing Game*

---

## 1. Conditional Statements (`if`, `else if`, `else`)

### Example 1 – Simple If-Else
```java
public class Main {
    public static void main(String[] args) {
        int score = 85;

        if (score >= 90) {
            System.out.println("Excellent!");
        } else if (score >= 60) {
            System.out.println("Good job!");
        } else {
            System.out.println("Keep trying!");
        }
    }
}
```

## Explanation

| Line | Code                                | Explanation                                 |
| ---- | ----------------------------------- | ------------------------------------------- |
| 4    | `if (score >= 90)`                  | Checks if score is 90 or more.              |
| 5    | `System.out.println("Excellent!");` | Executes if condition is true.              |
| 7    | `else if (score >= 60)`             | Second condition checked if first is false. |
| 9    | `else { ... }`                      | Runs if none of the conditions are true.    |

**Teacher Tip:**
Emphasize how only **one block executes** among the if-else ladder.

---

## 2. Comparison and Logical Operators

| Operator | Description      | Example        | Result               |       |   |       |                  |
| -------- | ---------------- | -------------- | -------------------- | ----- | - | ----- | ---------------- |
| `==`     | Equal to         | `a == b`       | true if equal        |       |   |       |                  |
| `!=`     | Not equal        | `a != b`       | true if not equal    |       |   |       |                  |
| `>`      | Greater than     | `a > b`        | true if a is greater |       |   |       |                  |
| `<`      | Less than        | `a < b`        | true if a is smaller |       |   |       |                  |
| `>=`     | Greater or equal | `a >= b`       | true if a >= b       |       |   |       |                  |
| `<=`     | Less or equal    | `a <= b`       | true if a <= b       |       |   |       |                  |
| `&&`     | AND              | `(a>5 && b>5)` | true if both true    |       |   |       |                  |
| `        |                  | `              | OR                   | `(a>5 |   | b>5)` | true if one true |
| `!`      | NOT              | `!(a>5)`       | reverses condition   |       |   |       |                  |

---

## 3. The `for` Loop

### Example 2 – Counting from 1 to 5

```java
public class Main {
    public static void main(String[] args) {
        for (int i = 1; i <= 5; i++) {
            System.out.println("Count: " + i);
        }
    }
}
```

### Explanation

| Line | Code                                 | Explanation                                             |
| ---- | ------------------------------------ | ------------------------------------------------------- |
| 3    | `for (int i = 1; i <= 5; i++)`       | Initializes `i=1`, loops while `i<=5`, increments by 1. |
| 4    | `System.out.println("Count: " + i);` | Executes once each iteration.                           |

**Output**

```
Count: 1
Count: 2
Count: 3
Count: 4
Count: 5
```

**Teacher Tip:**
Explain the 3 parts of a for loop clearly:

1. **Initialization** – runs once
2. **Condition** – checked before every loop
3. **Increment/Decrement** – executed after each iteration

---

## 4. The `while` Loop

### Example 3 – Print Numbers using while

```java
public class Main {
    public static void main(String[] args) {
        int i = 1;
        while (i <= 5) {
            System.out.println("Value of i: " + i);
            i++;
        }
    }
}
```

### Explanation

| Line | Code             | Explanation                       |
| ---- | ---------------- | --------------------------------- |
| 3    | `int i = 1;`     | Initialize counter.               |
| 4    | `while (i <= 5)` | Executes while condition is true. |
| 6    | `i++;`           | Increments counter each time.     |

**Output**

```
Value of i: 1
Value of i: 2
Value of i: 3
Value of i: 4
Value of i: 5
```

---

## 5. The `do-while` Loop

### Example 4 – Run at least once

```java
public class Main {
    public static void main(String[] args) {
        int num = 1;
        do {
            System.out.println("Number: " + num);
            num++;
        } while (num <= 3);
    }
}
```

### Explanation

| Line | Code                                    | Explanation                        |
| ---- | --------------------------------------- | ---------------------------------- |
| 4    | `do {`                                  | Starts loop body.                  |
| 5    | `System.out.println("Number: " + num);` | Prints number.                     |
| 7    | `} while (num <= 3);`                   | Condition checked after execution. |

**Output**

```
Number: 1
Number: 2
Number: 3
```

---

## 6. Nested Conditions and Loops

### Example 5 – Checking Even/Odd Numbers

```java
public class Main {
    public static void main(String[] args) {
        for (int i = 1; i <= 5; i++) {
            if (i % 2 == 0) {
                System.out.println(i + " is even");
            } else {
                System.out.println(i + " is odd");
            }
        }
    }
}
```

### Explanation

* `%` gives the remainder.
* If remainder is 0, number is even.
* Otherwise, it’s odd.

**Output**

```
1 is odd
2 is even
3 is odd
4 is even
5 is odd
```

---

## 7. Mini Project – Number Guessing Game

### Complete Code

```java
import java.util.Scanner;
import java.util.Random;

public class NumberGuessingGame {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        Random rand = new Random();

        int secretNumber = rand.nextInt(10) + 1; // Random number 1–10
        int guess = 0;
        int attempts = 0;

        System.out.println("Welcome to the Number Guessing Game!");
        System.out.println("Guess the number between 1 and 10.");

        while (guess != secretNumber) {
            System.out.print("Enter your guess: ");
            guess = input.nextInt();
            attempts++;

            if (guess < secretNumber) {
                System.out.println("Too low! Try again.");
            } else if (guess > secretNumber) {
                System.out.println("Too high! Try again.");
            } else {
                System.out.println("Correct! The number was " + secretNumber);
                System.out.println("You guessed it in " + attempts + " tries.");
            }
        }
    }
}
```

### Line-by-Line Explanation

| Line  | Code                                        | Explanation                               |
| ----- | ------------------------------------------- | ----------------------------------------- |
| 1     | `import java.util.Scanner;`                 | For user input.                           |
| 2     | `import java.util.Random;`                  | For random number generation.             |
| 6     | `Random rand = new Random();`               | Creates a Random object.                  |
| 8     | `int secretNumber = rand.nextInt(10) + 1;`  | Random number between 1 and 10.           |
| 13    | `while (guess != secretNumber)`             | Loops until guess is correct.             |
| 16    | `guess = input.nextInt();`                  | Reads user’s guess.                       |
| 19–23 | `if / else if / else`                       | Checks if guess is low, high, or correct. |
| 25    | Displays success message and attempt count. |                                           |

**Output Example**

```
Welcome to the Number Guessing Game!
Guess the number between 1 and 10.
Enter your guess: 4
Too low! Try again.
Enter your guess: 7
Correct! The number was 7
You guessed it in 2 tries.
```

---

## Common Mistakes

| Mistake                | Why It Happens                            | Fix                                    |
| ---------------------- | ----------------------------------------- | -------------------------------------- |
| Infinite loop          | Forgot to update variable in `while` loop | Always change condition variable.      |
| Random always same     | Didn’t use `Random` class properly        | Use `rand.nextInt(range) + offset`.    |
| Using `==` for Strings | `==` compares memory, not content         | Use `.equals()` for String comparison. |

---

## Recommended Class Flow (90 min)

| Segment                       | Duration | Activity     |
| ----------------------------- | -------- | ------------ |
| Recap of Day 2                | 10 min   | Quick review |
| If-Else Conditions            | 15 min   | Example 1    |
| Loops (for, while, do-while)  | 25 min   | Examples 2–4 |
| Nested loops & logic          | 10 min   | Example 5    |
| Project: Number Guessing Game | 25 min   | Build & test |
| Q&A and Wrap-up               | 5 min    | Discussion   |

---

## Mini Challenge (Homework)

**Task:**
Write a program that:

1. Asks the player to enter their Minecraft level (1–10).
2. If the level is above 5, print “You are a Pro Builder!”.
3. Otherwise, print “Keep practicing, Builder!”.

Use both **if-else** and **while** to make it interactive.
