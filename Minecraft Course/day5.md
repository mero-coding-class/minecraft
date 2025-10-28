# Day 5: Classes and Methods in Java

## Objective
Understand **Object-Oriented Programming (OOP)** concepts in Java and how to create and use **classes** and **methods** to organize code logically.

---

## 1. Introduction to Object-Oriented Programming (OOP)
OOP is a programming paradigm that helps structure programs as collections of **objects** — real-world entities with **attributes (data)** and **behaviors (methods)**.

### Key OOP Concepts
1. **Class** – A blueprint for creating objects.
2. **Object** – An instance of a class.
3. **Attributes** – Variables that describe the properties of the object.
4. **Methods** – Functions that define the object’s behavior.

---

## 2. Basic Structure of a Class

```java
class ClassName {
    // attributes
    int attribute1;
    String attribute2;

    // methods
    void display() {
        System.out.println("Hello from Class!");
    }
}
```

### Explanation
- A **class** is declared using the `class` keyword.
- Attributes (variables) define the data of the class.
- Methods define what the class can do.

---

## 3. Creating and Using Objects

```java
public class Main {
    public static void main(String[] args) {
        Player player1 = new Player(); // creating an object
        player1.name = "Steve";
        player1.health = 100;
        player1.displayInfo();
    }
}

class Player {
    String name;
    int health;

    void displayInfo() {
        System.out.println("Player Name: " + name);
        System.out.println("Health: " + health);
    }
}
```

### Explanation
- `Player` is a **class**.
- `player1` is an **object** of `Player`.
- The dot (`.`) operator is used to access object attributes and methods.

**Output:**
```
Player Name: Steve
Health: 100
```

---

## 4. Using Constructors

A **constructor** initializes the object when it’s created. It has the same name as the class and **no return type**.

```java
class Player {
    String name;
    int health;

    // Constructor
    Player(String n, int h) {
        name = n;
        health = h;
    }

    void displayInfo() {
        System.out.println("Player Name: " + name);
        System.out.println("Health: " + health);
    }
}

public class Main {
    public static void main(String[] args) {
        Player p1 = new Player("Alex", 80);
        p1.displayInfo();
    }
}
```

**Output:**
```
Player Name: Alex
Health: 80
```

### Explanation
- The constructor `Player(String n, int h)` initializes `name` and `health`.
- When a new player is created, the constructor automatically runs.

---

## 5. Adding Multiple Methods

You can define different actions for an object by adding multiple methods.

```java
class Player {
    String name;
    int health;

    Player(String n, int h) {
        name = n;
        health = h;
    }

    void displayInfo() {
        System.out.println("Player: " + name + " | Health: " + health);
    }

    void takeDamage(int damage) {
        health -= damage;
        System.out.println(name + " took " + damage + " damage!");
    }

    void heal(int amount) {
        health += amount;
        System.out.println(name + " healed by " + amount + " points!");
    }
}

public class Main {
    public static void main(String[] args) {
        Player player = new Player("Steve", 100);
        player.displayInfo();
        player.takeDamage(20);
        player.heal(10);
        player.displayInfo();
    }
}
```

**Output:**
```
Player: Steve | Health: 100
Steve took 20 damage!
Steve healed by 10 points!
Player: Steve | Health: 90
```

### Explanation
- The player’s `health` decreases or increases based on method calls.
- The same object maintains its state throughout the program.

---

## 6. Adding Multiple Objects

You can create multiple instances of a class.

```java
public class Main {
    public static void main(String[] args) {
        Player p1 = new Player("Alex", 90);
        Player p2 = new Player("Steve", 100);

        p1.displayInfo();
        p2.displayInfo();
    }
}

class Player {
    String name;
    int health;

    Player(String n, int h) {
        name = n;
        health = h;
    }

    void displayInfo() {
        System.out.println("Player Name: " + name + " | Health: " + health);
    }
}
```

**Output:**
```
Player Name: Alex | Health: 90
Player Name: Steve | Health: 100
```

---

## 7. Activity: Enhanced Player System

### Task
Create a class `Player` with the following:
- Attributes: `name`, `health`, and `score`.
- Methods: `takeDamage()`, `increaseScore()`, and `displayStats()`.

### Sample Code

```java
public class Main {
    public static void main(String[] args) {
        Player player1 = new Player("Steve", 100, 0);
        player1.displayStats();
        player1.takeDamage(30);
        player1.increaseScore(50);
        player1.displayStats();
    }
}

class Player {
    String name;
    int health;
    int score;

    Player(String n, int h, int s) {
        name = n;
        health = h;
        score = s;
    }

    void takeDamage(int damage) {
        health -= damage;
        System.out.println(name + " took " + damage + " damage!");
    }

    void increaseScore(int points) {
        score += points;
        System.out.println(name + " gained " + points + " points!");
    }

    void displayStats() {
        System.out.println("Player: " + name + " | Health: " + health + " | Score: " + score);
    }
}
```

**Output:**
```
Player: Steve | Health: 100 | Score: 0
Steve took 30 damage!
Steve gained 50 points!
Player: Steve | Health: 70 | Score: 50
```

---

## 8. Homework
1. Add a new method `revive()` that resets the player’s health to 100.
2. Create another class `Enemy` with attributes `type` and `damage`. Add a method `attack(Player p)` that reduces the player’s health.
3. Modify the main program so that the `Enemy` can attack the `Player`.

---

## 9. Summary
- A **class** is a blueprint for creating **objects**.
- **Objects** hold data (attributes) and perform actions (methods).
- **Constructors** initialize objects when created.
- Using classes makes your code modular, reusable, and easier to expand for larger projects like Minecraft mods.