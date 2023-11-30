# Object-Oriented Programming Concepts

## Abstract

As a newcomer to the project, tasked with researching and refactoring complex code, this paper aims to explore Object-Oriented Programming (OOP) concepts and their application in the existing codebase. The goal is to improve code maintainability, extensibility, and overall software quality.

## Introduction

Understanding and applying Object-Oriented Programming (OOP) principles is important for enhancing code readability and scalability. This paper outlines object-oriented programming concepts like encapsulation, inheritance, and polymorphism, and demonstrates how they can be leveraged to refactor and improve the existing codebase. The quality and Lines of code(LOC) play a great role in software development and oops exactly do it.

## 1. Abstraction

Abstraction tells us to hide data that is not important to the user. It helps avoid adding unessential data.

```Java
abstract class Animal {
  // Abstract method
  abstract void makeSound();
}

class Dog extends Animal {
  @Override
  void makeSound() {
    System.out.println("Woof!");
  }
}

public class Main {
  public static void main(String[] args) {
    Dog dog = new Dog();

    // Call the makeSound() method
    dog.makeSound();
  }
}
```

## 2. Encapsulation

* Encapsulation is the bundling of data and methods that operate on that data into a single unit, known as a class.
* This promotes data hiding and reduces the impact of changes on other parts of the code. It not only improves the readability but also increases the reusability of the code.

```Java
public class User {
    private String username;
    private String password; // Encapsulated password

    public User(String username, String password) {
        this.username = username;
        this.password = password;
    }

    public boolean authenticate(String enteredPassword) {
        return this.password.equals(enteredPassword);
    }

    public static void main(String[] args) {
        // Usage
        User user = new User("john_doe", "secure_password");
        boolean result = user.authenticate("incorrect_password");  // Returns false
    }
}


# Usage
user = User("john_doe", "secure_password")
result = user.authenticate("incorrect_password")  # Returns False
```

## 3. Inheritance

* Inheritance is a mechanism that allows a new class to inherit properties and behaviors from an existing class. 
* This promotes code reuse and establishes a hierarchy among classes.
* Identifying common functionalities and creating a proper inheritance structure will be explored during the refactoring process. 
* Instead of rewriting the methods again and again in the different classes, we can simply use the extended keyword and use the method in any other class we want.

```Java
abstract class Shape {
    protected String color;

    public Shape(String color) {
        this.color = color;
    }

    public abstract void draw();
}

class Circle extends Shape {
    private int radius;

    public Circle(String color, int radius) {
        super(color);
        this.radius = radius;
    }

    @Override
    public void draw() {
        System.out.println("Drawing a " + color + " circle with radius " + radius);
    }
}
```

## 4. Polymorphism

Polymorphism allows objects of different types to be treated as objects of a common type. This is achieved through method overloading or method overriding. The refactoring process will involve identifying opportunities to apply polymorphism, making the code more flexible and extensible.

```Java
abstract class Printer {
    public abstract void printContent(String content);
}

class TextPrinter extends Printer {
    @Override
    public void printContent(String content) {
        System.out.println("Printing text: " + content);
    }
}

class ImagePrinter extends Printer {
    @Override
    public void printContent(String content) {
        System.out.println("Printing image: " + content);
    }
}


```

## 5. Conclusion

In conclusion, adopting Object-Oriented Programming principles is essential for the successful refactoring of complex code. Encapsulation, inheritance, and polymorphism are essential for enhancing code quality, promoting reusability, and facilitating future development. The code snippets provided serve as examples of how these principles can be applied in a real-world project. As a newcomer, understanding and implementing these concepts will contribute to the ongoing improvement of the project's codebase.

## References

* [Object-Oriented Programming Concepts](https://www.geeksforgeeks.org/introduction-of-object-oriented-programming/)
* [Refactoring Strategies](https://www.codesee.io/learning-center/java-refactoring#:~:text=Refactoring%20Code%20Using%20an%20OO%20Approach,-The%20OO%20approach&text=Extract%20class%3A%20Divide%20a%20large,each%20handling%20a%20single%20responsibility)

