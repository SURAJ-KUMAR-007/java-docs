# 📘 Java Basics Guide

## 🔎 Table of Contents
- [📦 Package](#package)
- [🔗 Java Variables](#-java-variables)
- [📘 Types of Variables in Java](#-types-of-variables-in-java)
    - [🔹 Instance Variables](#-instance-variables-non-static-fields)
    - [🔹 Class Variables](#-class-variables-static-fields)
    - [🔹 Local Variables](#-local-variables)
    - [🔹 Parameters](#-parameters)
- [🧠 Modifiers Explained](#-modifiers-explained)
- [📊 Fields vs Variables](#-difference-between-fields-and-variables-in-java)
- [💡 Example Code for Variable Types](#-example-code)
- [🧵 Breakdown of main Method](#-breakdown-of-public-static-void-mainstring-args)
- [🖨️ Breakdown of System.out.println()](#-breakdown-of-systemoutprintln)

---

# Package

- Think of packages similar to different folders on our computers.
- software written in the Java programming language can be composed of hundreds or thousands of individual classes, it makes sense to keep things organized by placing related classes and interfaces into packages.
- Java platform provides an enormous class library (a set of packages) suitable for use in your own applications. This library is known as the "Application Programming Interface", or "API" for short.

#  🔗 [Java Variables ](https://dev.java/learn/language-basics/variables/#creating)
## 📘 Types of Variables in Java

### 🔹 Instance Variables (Non-Static Fields)
- Declared without the `static` keyword.
- Belong to each instance of the class (i.e., object-specific).
- Each object has its **own copy** of the variable.
- Example use: `int currentSpeed;`

> 🧠 *Used to store the unique state of each object.*

---

### 🔹 Class Variables (Static Fields)
- Declared with the `static` modifier (keyword).
- Shared among **all instances** of the class.
- Only **one copy** exists for the entire class, not per object.
- Often marked `final` if the value should never change.
- Example use: `static int numGears = 6;`

> 🧠 *Used to store common/shared properties across all objects.*

---

### 🔹 Local Variables
- Declared **within methods**, constructors, or blocks.
- Not accessible outside the method/block they're declared in.
- No keyword like `static` or `final` by default (unless you add them).
- Example use: `int count = 0;`

> 🧠 *Used for temporary/short-term storage during method execution.*

---

### 🔹 Parameters
- Inputs passed to methods or constructors.
- Act like **local variables** inside the method.
- Defined in the method signature.
- Example use: `void setSpeed(int newSpeed)`

> 🧠 *Used to receive data from the caller when a method is invoked.*


## 🧠 Modifiers Explained

1. A **modifier** is a specific type of **keyword** used to change the behavior of:
    - Classes
    - Methods
    - Variables

2. **Types:**
    - `public` → access modifier
    - `static` → class-level modifier
    - `final` → value/immutability modifier



## 🔍 Difference Between Fields and Variables in Java

| Aspect              | Field                                                     | Variable                                                   |
|---------------------|-----------------------------------------------------------|-------------------------------------------------------------|
| **Definition**       | A variable declared inside a class but outside any method | A general term for any data container in Java               |
| **Scope**            | Belongs to the class or object                            | Can be local, parameter, or field                           |
| **Types**            | - Instance fields (`non-static`)<br>- Class fields (`static`) | - Fields<br>- Local variables<br>- Parameters               |
| **Declared In**      | Directly in the class body                                | In a class, method, or constructor                          |
| **Lifetime**         | Lives as long as the object/class exists                  | Lives based on scope (e.g., local variables die after method ends) |
| **Access Modifiers** | Can have `public`, `private`, `protected`                | Local variables and parameters **cannot** have access modifiers |
| **Example**          | `int speed;` inside class                                 | `int i = 0;` inside a method                                |

> 🧠 **All fields are variables, but not all variables are fields.**

---

### ✅ Example Code

```java
public class Bicycle {
    // 🔹 Fields
    int speed;              // instance field
    static int count = 0;   // static/class field

    public void ride(int distance) {
        // 🔸 Parameter: distance
        int time = 5;       // local variable
        System.out.println("Speed: " + speed);
    }
}
```

## 🔍 Breakdown of `public static void main(String[] args)`

This is the standard entry point of any Java application. Here's what each keyword means:

---

### ✅ `public`
- **Access modifier**.
- Makes the `main()` method **accessible from anywhere**.
- Required so the **JVM can access it to start the program**.

---

### ✅ `static`
- Declares the method as **class-level**, not object-level.
- JVM does **not create an object** to run the `main()` method — it calls it directly on the class.
- Hence, `main()` must be `static`.

---

### ✅ `void`
- **Return type**.
- Indicates that the method **does not return any value**.

---

### ✅ `main`
- This is the **method name**.
- It’s a **special method recognized by the JVM** as the entry point of the program.

---

### ✅ `String[] args`
- A **parameter**: an array of strings.
- Represents the **command-line arguments** passed when running the program.
- Example:
  ```bash
  java MyApp Hello World


## 🔍 Breakdown of `System.out.println()`

Understanding how Java prints to the console:

---

### ✅ `System`
- A **built-in Java class** from the `java.lang` package.
- Represents the **system your program is running on**.
- Provides useful static fields and methods like:
    - `System.in` → standard input
    - `System.out` → standard output
    - `System.err` → standard error

---

### ✅ `out`
- A **static field** of the `System` class.
- It is an instance of the `PrintStream` class.
- Used to send **output to the console** (standard output stream).
- `System.out` is what connects your program to the terminal window.

---

### ✅ `println()`
- A **method** of the `PrintStream` class.
- Stands for **“print line”**.
- Prints the given message and **moves the cursor to the next line**.
- Use `print()` instead if you want to print **without** a new line.

---

### 🧠 Summary Table

| Component       | Description                                                       |
|------------------|-------------------------------------------------------------------|
| `System`         | Java class that provides access to system-level resources         |
| `out`            | Static `PrintStream` object for writing output to the console     |
| `println()`      | Method that prints a line of text and moves to the next line      |
