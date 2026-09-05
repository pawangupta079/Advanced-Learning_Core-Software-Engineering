# Java Methods - Complete Detailed Study Guide

> Methods are one of the most important concepts in Java. Every Java application, Spring Boot project, Microservice, REST API, and Enterprise Application is built using methods. A strong understanding of methods is essential before learning OOP, Collections, Streams, and Spring Boot.

---

# Table of Contents

1. What is a Method?
2. Why Methods are Needed
3. Method Syntax
4. Components of a Method
5. How Methods Work Internally
6. Types of Methods
7. Parameterized vs Non-Parameterized Methods
8. Return Type vs Void Methods
9. Method Calling
10. Method Overloading
11. Variable Arguments (Varargs)
12. Pass by Value
13. Recursive Methods
14. Static Methods
15. Instance Methods
16. Final Methods
17. Abstract Methods
18. Default Methods
19. Private Methods in Interfaces
20. Method Hiding
21. Method Overriding
22. Access Modifiers with Methods
23. Method Memory Management
24. Best Practices
25. Interview Questions

---

# 1. What is a Method?

A method is a block of code that performs a specific task.

Instead of writing the same code repeatedly, we create a method and reuse it whenever needed.

Example:

```java
public class Main {

    static void greet() {
        System.out.println("Welcome to Java");
    }

    public static void main(String[] args) {

        greet();
        greet();

    }
}
```

Output:

```text
Welcome to Java
Welcome to Java
```

---

# 2. Why Methods are Needed

Without Methods

```java
System.out.println("Welcome");
System.out.println("Welcome");
System.out.println("Welcome");
System.out.println("Welcome");
```

With Methods

```java
greet();
greet();
greet();
greet();
```

Benefits:

- Reusability
- Readability
- Maintainability
- Modularity
- Easier Testing
- Less Code Duplication

---

# 3. Method Syntax

General Syntax:

```java
accessModifier returnType methodName(parameters) {

    // code

}
```

Example:

```java
public int add(int a, int b) {

    return a + b;

}
```

---

# 4. Components of a Method

Example:

```java
public int add(int a, int b) {

    return a + b;

}
```

### Access Modifier

```java
public
```

Controls access.

---

### Return Type

```java
int
```

Specifies what method returns.

---

### Method Name

```java
add
```

Should clearly indicate purpose.

---

### Parameters

```java
int a, int b
```

Inputs provided to method.

---

### Method Body

```java
{
   return a + b;
}
```

Contains logic.

---

# 5. How Methods Work Internally

Example:

```java
public static void greet() {

    System.out.println("Hello");

}
```

Execution:

```text
main()
 ↓
greet()
 ↓
Execute Code
 ↓
Return To main()
```

Every method call creates a stack frame in JVM Stack Memory.

---

# 6. Types of Methods

Java methods can be classified as:

```text
1. Predefined Methods
2. User Defined Methods
```

---

## Predefined Methods

Already provided by Java.

Examples:

```java
Math.sqrt()
Math.max()
String.length()
```

Example:

```java
System.out.println(Math.sqrt(25));
```

Output:

```text
5.0
```

---

## User Defined Methods

Created by developers.

Example:

```java
static void greet() {

    System.out.println("Hello");

}
```

---

# 7. Non-Parameterized Method

Method without inputs.

```java
static void greet() {

    System.out.println("Welcome");

}
```

Call:

```java
greet();
```

Output:

```text
Welcome
```

---

# 8. Parameterized Method

Method accepts inputs.

```java
static void greet(String name) {

    System.out.println(name);

}
```

Call:

```java
greet("Pawan");
```

Output:

```text
Pawan
```

---

# 9. Void Method

Returns nothing.

```java
static void printMessage() {

    System.out.println("Hello");

}
```

Call:

```java
printMessage();
```

---

# 10. Return Type Method

Returns a value.

```java
static int add(int a,int b){

    return a+b;

}
```

Call:

```java
int result = add(10,20);

System.out.println(result);
```

Output:

```text
30
```

---

# 11. Method Calling

Methods can be called from:

- main()
- Other Methods
- Objects

Example:

```java
static void methodB(){

    System.out.println("B");

}

static void methodA(){

    methodB();

}
```

---

# 12. Multiple Parameters

```java
static int multiply(int a,int b){

    return a*b;

}
```

Call:

```java
multiply(10,5);
```

Output:

```text
50
```

---

# 13. Method Overloading

Same method name.

Different parameters.

Example:

```java
class Calculator {

    int add(int a,int b){

        return a+b;

    }

    int add(int a,int b,int c){

        return a+b+c;

    }
}
```

Call:

```java
add(10,20);

add(10,20,30);
```

This is called:

```text
Compile Time Polymorphism
```

---

# 14. Varargs Method

Accepts multiple values.

Syntax:

```java
datatype... variableName
```

Example:

```java
static int sum(int... nums){

    int total = 0;

    for(int num : nums){

        total += num;

    }

    return total;
}
```

Call:

```java
sum(10,20);
sum(10,20,30);
sum(10,20,30,40);
```

---

# 15. Method Returning Different Data Types

## Returning int

```java
static int getAge(){

    return 25;
}
```

---

## Returning String

```java
static String getName(){

    return "Pawan";

}
```

---

## Returning Boolean

```java
static boolean isActive(){

    return true;

}
```

---

# 16. Pass By Value

Java supports only:

```text
Pass By Value
```

Example:

```java
static void change(int x){

    x = 100;

}
```

```java
int num = 10;

change(num);

System.out.println(num);
```

Output:

```text
10
```

Original variable remains unchanged.

---

# 17. Recursive Methods

Method calls itself.

Example:

```java
static void print(int n){

    if(n==0)
        return;

    System.out.println(n);

    print(n-1);

}
```

Call:

```java
print(5);
```

Output:

```text
5
4
3
2
1
```

---

# 18. Static Methods

Belong to class.

No object required.

Example:

```java
class Demo {

    static void display(){

        System.out.println("Java");

    }

}
```

Call:

```java
Demo.display();
```

---

# 19. Instance Methods

Require object creation.

Example:

```java
class Employee {

    void show(){

        System.out.println("Employee");

    }

}
```

Call:

```java
Employee e = new Employee();

e.show();
```

---

# 20. Static vs Instance Methods

### Static Method

```java
static void display()
```

Characteristics:

- Belongs to class
- No object required
- Memory efficient

---

### Instance Method

```java
void display()
```

Characteristics:

- Belongs to object
- Requires object
- Can access instance variables

---

# 21. Final Methods

Cannot be overridden.

```java
class Parent {

    final void show(){

        System.out.println("Show");

    }

}
```

Child class cannot override.

---

# 22. Abstract Methods

Method without implementation.

```java
abstract class Animal {

    abstract void sound();

}
```

Child must implement.

```java
class Dog extends Animal {

    void sound(){

        System.out.println("Bark");

    }

}
```

---

# 23. Default Methods (Java 8)

Methods with implementation inside interfaces.

```java
interface Vehicle {

    default void start(){

        System.out.println("Starting");

    }

}
```

---

# 24. Private Methods in Interfaces (Java 9)

Used internally within interfaces.

```java
interface Demo {

    private void helper(){

        System.out.println("Helper");

    }

}
```

---

# 25. Method Overriding

Child provides its own implementation.

Parent:

```java
class Animal {

    void sound(){

        System.out.println("Animal Sound");

    }

}
```

Child:

```java
class Dog extends Animal {

    @Override
    void sound(){

        System.out.println("Bark");

    }

}
```

Output:

```text
Bark
```

---

# 26. Method Hiding

Static methods are hidden, not overridden.

```java
class Parent {

    static void show(){

        System.out.println("Parent");

    }

}
```

```java
class Child extends Parent {

    static void show(){

        System.out.println("Child");

    }

}
```

This is Method Hiding.

---

# 27. Access Modifiers and Methods

## public

Accessible everywhere.

```java
public void display()
```

---

## protected

Accessible within package and subclasses.

```java
protected void display()
```

---

## default

Accessible within package.

```java
void display()
```

---

## private

Accessible only within class.

```java
private void display()
```

---

# 28. Method Memory Management

When Method Executes:

```text
main()
  |
  |-- add()
  |
  |-- display()
```

JVM Stack:

```text
Stack
----------------
display()
----------------
add()
----------------
main()
----------------
```

After completion:

```text
display() removed
add() removed
main() removed
```

This is called:

```text
Stack Frame Management
```

---

# 29. Method Best Practices

### Good Names

✅

```java
calculateSalary()
getEmployeeById()
sendEmail()
```

❌

```java
a()
abc()
test()
```

---

### Single Responsibility

One method should perform one task.

