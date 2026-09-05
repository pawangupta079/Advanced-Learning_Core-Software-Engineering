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

# Types of Java Methods: Static Methods, Instance Methods, Constructors, Getters & Setters, and Instance Variables

> This module provides a complete understanding of some of the most important Java class components. These concepts are heavily used in Core Java, OOP, Spring Boot, Hibernate, Microservices, and Enterprise Application Development.

---

# Table of Contents

1. Introduction
2. Static Methods
3. Instance Methods
4. Static vs Instance Methods
5. Constructor Methods
6. Types of Constructors
7. Constructor Chaining
8. this Keyword
9. Getters and Setters
10. Instance Variables
11. Memory Allocation
12. Real-World Spring Boot Examples
13. Best Practices
14. Interview Questions

---

# Introduction

A Java class can contain:

```text
1. Variables
2. Methods
3. Constructors
4. Nested Classes
5. Blocks
```

Example:

```java
public class Employee {

    private String name;      // Instance Variable

    public Employee() {       // Constructor

    }

    public void work() {      // Instance Method

    }

    public static void companyPolicy() { // Static Method

    }
}
```

---

# 1. Static Methods

## What is a Static Method?

A static method belongs to the class itself rather than an object.

Because it belongs to the class, we can call it without creating an object.

Syntax:

```java
class Demo {

    static void display() {

        System.out.println("Static Method");

    }
}
```

Calling:

```java
Demo.display();
```

Output:

```text
Static Method
```

---

# Why Static Methods Exist

Suppose a method does not require object-specific data.

Example:

```java
calculateCircleArea()
calculateTax()
calculateInterest()
```

Creating objects would be unnecessary.

Static methods solve this problem.

---

# Static Method Memory

```text
Method Area
    |
    ---> Static Methods
```

Static methods are loaded when the class is loaded.

Only one copy exists.

---

# Example

```java
public class Calculator {

    static int add(int a, int b) {

        return a + b;

    }

    public static void main(String[] args) {

        int result = Calculator.add(10, 20);

        System.out.println(result);

    }
}
```

Output:

```text
30
```

---

# Rules of Static Methods

## Static Methods Can Access

✅ Static Variables

✅ Other Static Methods

Example:

```java
class Demo {

    static int count = 100;

    static void display() {

        System.out.println(count);

    }
}
```

---

## Static Methods Cannot Directly Access Instance Variables

Wrong:

```java
class Employee {

    String name = "Pawan";

    static void display() {

        System.out.println(name);

    }
}
```

Error:

```text
Cannot access non-static field from static context
```

Reason:

Static methods execute without object creation.

---

# Real Examples of Static Methods

```java
Math.sqrt()
Math.max()
Math.min()
Integer.parseInt()
Collections.sort()
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

# Advantages of Static Methods

✅ Faster access

✅ Shared logic

✅ Memory efficient

✅ No object required

✅ Ideal for utility classes

---

# 2. Instance Methods

## What is an Instance Method?

An instance method belongs to an object, not the class.

Object creation is mandatory.

Example:

```java
class Employee {

    void work() {

        System.out.println("Working");

    }

}
```

Call:

```java
Employee emp = new Employee();

emp.work();
```

Output:

```text
Working
```

---

# Instance Method Memory

```text
Heap
 |
 ---> Object
          |
          ---> Instance Methods Access Object State
```

---

# Example

```java
class Student {

    String name = "Pawan";

    void display() {

        System.out.println(name);

    }

}
```

Call:

```java
Student s = new Student();

s.display();
```

Output:

```text
Pawan
```

---

# Why Instance Methods Are Important

Instance methods can access:

```text
Object Variables
Object State
Object Behavior
```

This is the foundation of OOP.

---

# Real Example

```java
class BankAccount {

    String accountHolder;
    double balance;

    void deposit(double amount) {

        balance += amount;

    }
}
```

Each account has different balance values.

Therefore object-specific methods are required.

---

# Static vs Instance Methods

## Static Method

```java
static void display()
```

Characteristics:

```text
Belongs to Class
No Object Required
Loaded Once
Memory Efficient
```

---

## Instance Method

```java
void display()
```

Characteristics:

```text
Belongs To Object
Requires Object
Uses Instance Variables
Supports OOP
```

---

# 3. Constructor Method

## What is Constructor?

A constructor is a special method used to initialize an object.

Constructor executes automatically when object is created.

---

# Constructor Syntax

```java
class Student {

    Student() {

        System.out.println("Constructor Called");

    }

}
```

Object Creation:

```java
Student s = new Student();
```

Output:

```text
Constructor Called
```

---

# Characteristics of Constructors

✅ Same name as class

✅ No return type

✅ Automatically called

✅ Used for initialization

✅ Can be overloaded

---

# Constructor vs Method

Constructor:

```java
Student() {

}
```

Method:

```java
void Student() {

}
```

Major Difference:

```text
Constructor executes automatically.

Method must be called explicitly.
```

---

# Types of Constructors

## 1. Default Constructor

Provided by compiler automatically.

Example:

```java
class Employee {

}
```

Compiler internally creates:

```java
Employee() {

}
```

---

## 2. No-Argument Constructor

Created by programmer.

```java
class Employee {

    Employee() {

        System.out.println("Employee Created");

    }

}
```

---

## 3. Parameterized Constructor

Accepts values.

```java
class Employee {

    String name;

    Employee(String name) {

        this.name = name;

    }

}
```

Usage:

```java
Employee emp =
        new Employee("Pawan");
```

---

# Constructor Overloading

Multiple constructors inside same class.

```java
class Employee {

    Employee() {

    }

    Employee(String name) {

    }

    Employee(String name,int age) {

    }
}
```

This is:

```text
Constructor Overloading
```

---

# Constructor Chaining

One constructor calls another constructor.

Syntax:

```java
this();
```

Example:

```java
class Employee {

    Employee() {

        System.out.println("Default");

    }

    Employee(String name) {

        this();

        System.out.println(name);

    }

}
```

Output:

```text
Default
Pawan
```

---

# this Keyword

Represents current object.

Example:

```java
class Employee {

    String name;

    Employee(String name) {

        this.name = name;

    }

}
```

---

# Without this

```java
name = name;
```

Problem:

```text
Local Variable shadows Instance Variable.
```

---

# With this

```java
this.name = name;
```

Correctly assigns value.

---

# Constructor Execution Flow

```text
Object Creation
      |
      ▼
Memory Reserved
      |
      ▼
Constructor Executed
      |
      ▼
Object Fully Initialized
```

---

# 4. Getters and Setters

## What are Getters and Setters?

Methods used to read and modify private variables.

They are part of:

```text
Encapsulation
```

---

# Why They Are Needed

Bad Practice:

```java
class Employee {

    public String name;

}
```

Anyone can update value.

---

Good Practice:

```java
class Employee {

    private String name;

}
```

Now direct access is blocked.

---

# Getter Method

Returns value.

Example:

```java
public String getName() {

    return name;

}
```

---

# Setter Method

Updates value.

Example:

```java
public void setName(String name) {

    this.name = name;

}
```

---

# Complete Example

```java
class Employee {

    private String name;

    public String getName() {

        return name;

    }

    public void setName(String name) {

        this.name = name;

    }
}
```

Usage:

```java
Employee emp = new Employee();

emp.setName("Pawan");

System.out.println(emp.getName());
```

Output:

```text
Pawan
```

---

# Getter & Setter Benefits

✅ Data Hiding

✅ Validation

✅ Security

✅ Controlled Access

✅ Encapsulation

---

# Validation Example

```java
public void setAge(int age) {

    if(age > 0) {

        this.age = age;

    }

}
```

Invalid values can be blocked.

---

# 5. Instance Variables

## What are Instance Variables?

Variables declared inside a class but outside methods.

Example:

```java
class Employee {

    String name;
    int age;

}
```

---

# Characteristics

✅ Belong to object

✅ Stored in Heap

✅ Get default values

✅ Accessible through object

---

# Example

```java
class Employee {

    String name = "Pawan";

}
```

Object:

```java
Employee e = new Employee();
```

Object receives:

```text
name = Pawan
```

---

# Default Values

## Numeric

```java
int age;
```

Default:

```text
0
```

---

## double

```java
double salary;
```

Default:

```text
0.0
```

---

## boolean

```java
boolean active;
```

Default:

```text
false
```

---

## String

```java
String name;
```

Default:

```text
null
```

---

# Instance Variable Memory

Example:

```java
class Employee {

    String name;
}
```

Object Creation:

```java
Employee emp =
        new Employee();
```

Memory:

```text
STACK
-----
emp

HEAP
-----
Employee Object
    |
    ---> name
```

Reference:

```java
emp
```

stored in Stack.

Object stored in Heap.

---

# Real Spring Boot Example

Entity Class

```java
@Entity
public class Employee {

    @Id
    private Long id;

    private String name;

    private Double salary;

    public String getName() {

        return name;

    }

    public void setName(String name) {

        this.name = name;

    }
}
```

Here:

```text
id
name
salary
```

are Instance Variables.

```text
getName()
setName()
```

are Instance Methods.

Constructor initializes object.

---

# Best Practices

## Variables

✅ Keep private

```java
private String name;
```

---

## Use Constructor Initialization

```java
Employee(String name) {

    this.name = name;

}
```

---

## Use Getters and Setters

```java
getName()

setName()
```

---

## Keep Utility Methods Static

```java
MathUtil.add()
```

---

## Follow Java Naming Conventions

Class:

```java
EmployeeService
```

Variable:

```java
employeeName
```

Method:

```java
calculateSalary()
```

---

# Interview Questions

## What is a Static Method?

A method that belongs to the class and can be called without creating an object.

---

## What is an Instance Method?

A method that belongs to an object and requires an object for execution.

---

## What is a Constructor?

A special method used to initialize objects.

---

## Can Constructors Be Overloaded?

Yes.

Multiple constructors with different parameters are allowed.

---

## Why Use Getters and Setters?

To implement encapsulation and controlled access.

---

## What are Instance Variables?

Variables declared inside a class but outside methods.

---

## Where are Instance Variables Stored?

Inside Heap Memory as part of the object.

---

## Difference Between Static and Instance Methods?

Static:

```text
Belongs To Class
```

Instance:

```text
Belongs To Object
```

---

# Mastery Checklist

✅ Static Methods

✅ Instance Methods

✅ Constructor Fundamentals

✅ Constructor Overloading

✅ Constructor Chaining

✅ this Keyword

✅ Getters

✅ Setters

✅ Encapsulation

✅ Instance Variables

✅ Heap Memory

✅ Stack Memory

✅ JVM Object Creation

✅ Real Enterprise Code Structure

These concepts are fundamental building blocks for OOP, Hibernate, Spring Framework, Spring Boot, JPA, and Microservices.

