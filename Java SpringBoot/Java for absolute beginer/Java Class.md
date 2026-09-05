# Java Classes - Complete Detailed Study Guide

> Classes are the foundation of Object-Oriented Programming (OOP) in Java. Everything in Enterprise Java, Spring Boot, Microservices, Hibernate, and backend development revolves around classes and objects. Understanding classes deeply is essential for becoming a professional Java developer.

---

# Table of Contents

1. What is a Class?
2. Why Classes are Needed
3. Real World Analogy
4. Class Syntax
5. Components of a Class
6. Creating a Class
7. Creating Objects
8. Class vs Object
9. Instance Variables
10. Local Variables
11. Static Variables
12. Constructors
13. Default Constructor
14. Parameterized Constructor
15. Constructor Overloading
16. this Keyword
17. Methods Inside Class
18. Access Modifiers
19. Instance Methods
20. Static Methods
21. Nested Classes
22. Inner Classes
23. Anonymous Classes
24. Static Nested Classes
25. Final Classes
26. Abstract Classes
27. Sealed Classes
28. Immutable Classes
29. Utility Classes
30. POJO Classes
31. JavaBean Classes
32. DTO Classes
33. Entity Classes
34. Singleton Class
35. Object Class
36. Class Loading
37. Memory Allocation
38. Class Lifecycle
39. Best Practices
40. Interview Questions

---

# 1. What is a Class?

A class is a blueprint or template used to create objects.

A class defines:

- Properties (Variables)
- Behaviors (Methods)

Example:

```java
class Employee {

    String name;
    int age;

    void work() {
        System.out.println("Employee is working");
    }
}
```

---

# 2. Why Classes are Needed

Without Classes

```java
String employee1Name = "Pawan";
int employee1Age = 25;

String employee2Name = "Rahul";
int employee2Age = 26;
```

As the application grows:

```text
More Data
More Complexity
Hard Maintenance
```

Using Classes:

```java
Employee emp1 = new Employee();
Employee emp2 = new Employee();
```

Advantages:

- Reusability
- Scalability
- Maintainability
- Modularity

---

# 3. Real World Analogy

Consider:

```text
Car
```

A Car has:

Properties:

```text
color
brand
speed
model
```

Behaviors:

```text
start()
stop()
accelerate()
```

Class:

```java
class Car
```

Objects:

```java
BMW
Audi
Mercedes
```

---

# 4. Class Syntax

```java
class ClassName {

    // variables

    // methods

}
```

Example:

```java
class Student {

    String name;

    void study() {
        System.out.println("Studying");
    }

}
```

---

# 5. Components of a Class

A class may contain:

```text
Variables
Methods
Constructors
Blocks
Nested Classes
```

Structure:

```java
class Employee {

    String name;

    Employee() {

    }

    void work() {

    }

}
```

---

# 6. Creating a Class

```java
class Student {

    String name;
    int age;

}
```

This only creates the blueprint.

No memory is allocated yet.

---

# 7. Creating Objects

Object creation:

```java
Student s1 = new Student();
```

Explanation:

```java
Student
```

Reference Type

```java
s1
```

Reference Variable

```java
new Student()
```

Object Creation

---

# 8. Class vs Object

## Class

Blueprint

Example:

```java
class Car
```

No memory for instance variables allocated until object creation.

---

## Object

Instance of Class

```java
Car car1 = new Car();
```

Memory allocated in Heap.

---

# 9. Instance Variables

Declared inside class but outside methods.

```java
class Employee {

    String name;
    int age;

}
```

Characteristics:

- Belong to object
- Stored in Heap
- Default values assigned

---

Example:

```java
class Employee{

    String name;
}
```

Default value:

```text
null
```

---

# 10. Local Variables

Declared inside methods.

```java
void display() {

    int age = 25;

}
```

Characteristics:

- Stored in Stack
- No default value
- Accessible only inside method

---

# 11. Static Variables

Shared among all objects.

```java
class Employee {

    static String company = "Sopra Steria";

}
```

Memory created once.

---

Example:

```java
Employee e1 = new Employee();
Employee e2 = new Employee();
```

Both use:

```text
company
```

same memory.

---

# 12. Constructors

Special method used to initialize objects.

Characteristics:

- Same name as class
- No return type
- Automatically called

Example:

```java
class Student {

    Student() {

        System.out.println("Constructor Called");

    }

}
```

---

# 13. Default Constructor

Compiler generates one if not provided.

Example:

```java
class Employee {

}
```

Compiler adds:

```java
Employee() {

}
```

internally.

---

# 14. Parameterized Constructor

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
Employee e =
    new Employee("Pawan");
```

---

# 15. Constructor Overloading

Multiple constructors.

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

---

# 16. this Keyword

Represents current object.

Example:

```java
class Employee {

    String name;

    Employee(String name){

        this.name = name;

    }

}
```

Without this:

```java
name = name;
```

Creates ambiguity.

---

# 17. Methods Inside Class

Behaviors of objects.

```java
class Employee {

    void work() {

        System.out.println("Working");

    }

}
```

Object:

```java
Employee e =
      new Employee();

e.work();
```

---

# 18. Access Modifiers

Control visibility.

---

## public

Accessible everywhere.

```java
public class Employee
```

---

## private

Accessible only inside class.

```java
private String password;
```

---

## protected

Accessible within package and subclasses.

```java
protected String name;
```

---

## default

Accessible within package.

```java
String city;
```

---

# 19. Instance Methods

Need object.

```java
class Employee {

    void show() {

        System.out.println("Show");

    }

}
```

Call:

```java
Employee e = new Employee();

e.show();
```

---

# 20. Static Methods

Belong to class.

```java
class MathUtil {

    static int square(int n) {

        return n*n;

    }

}
```

Call:

```java
MathUtil.square(5);
```

---

# 21. Nested Classes

Class inside another class.

```java
class Outer {

    class Inner {

    }

}
```

Used for logical grouping.

---

# 22. Inner Class

Non-static class inside outer class.

```java
class Outer {

    class Inner {

    }

}
```

Inner class can access all members of outer class.

---

# 23. Anonymous Class

Class without explicit name.

Example:

```java
Runnable r = new Runnable() {

    @Override
    public void run() {

        System.out.println("Running");

    }

};
```

Used before Lambda Expressions.

---

# 24. Static Nested Class

```java
class Outer {

    static class Inner {

    }

}
```

Usage:

```java
Outer.Inner obj =
      new Outer.Inner();
```

---

# 25. Final Class

Cannot be inherited.

```java
final class Utility {

}
```

Example:

```java
String
```

is a final class.

---

# 26. Abstract Class

Cannot create object directly.

```java
abstract class Animal {

    abstract void sound();

}
```

Child must implement.

---

Example:

```java
class Dog extends Animal {

    void sound() {

        System.out.println("Bark");

    }

}
```

---

# 27. Sealed Classes (Java 17+)

Restrict inheritance.

```java
public sealed class Vehicle
permits Car, Bike {

}
```

Only:

```java
Car
Bike
```

can extend it.

---

# 28. Immutable Class

Object state cannot change after creation.

Example:

```java
public final class Employee {

    private final String name;

    public Employee(String name) {

        this.name = name;

    }

    public String getName() {

        return name;

    }

}
```

Benefits:

- Thread Safe
- Secure
- Predictable

---

# 29. Utility Class

Contains only static methods.

Example:

```java
class MathUtil {

    static int add(int a,int b){

        return a+b;

    }

}
```

Usage:

```java
MathUtil.add(10,20);
```

---

# 30. POJO Class

POJO:

```text
Plain Old Java Object
```

Simple class.

```java
class Employee {

    private int id;
    private String name;

}
```

---

# 31. JavaBean Class

Special POJO.

Contains:

- Private Variables
- Getter
- Setter
- No-Arg Constructor

```java
public class Employee {

    private int id;

    public Employee() {

    }

    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id=id;
    }

}
```

---

# 32. DTO Class

Data Transfer Object.

Used in APIs.

```java
public class EmployeeDTO {

    private String name;
    private String email;

}
```

Transfers data.

---

# 33. Entity Class

Represents Database Table.

Spring Boot Example:

```java
@Entity
public class Employee {

    @Id
    private Long id;

    private String name;

}
```

Maps to table.

---

# 34. Singleton Class

Only one object allowed.

```java
class Singleton {

    private static Singleton instance =
            new Singleton();

    private Singleton() {

    }

    public static Singleton getInstance() {

        return instance;

    }

}
```

Usage:

```java
Singleton obj =
        Singleton.getInstance();
```

---

# 35. Object Class

Parent of all Java classes.

```java
class Employee {

}
```

Actually:

```java
class Employee extends Object {

}
```

Common methods:

```java
toString()
equals()
hashCode()
getClass()
clone()
```

---

# 36. Class Loading Process

When JVM starts:

```text
Load
Link
Initialize
```

---

### Loading

Class Loader loads class.

---

### Linking

Verification performed.

---

### Initialization

Static variables initialized.

---

# 37. Memory Allocation

Object Creation:

```java
Employee e =
        new Employee();
```

Memory:

```text
Stack
-----
e

Heap
-----
Employee Object
```

Reference stored in Stack.

Object stored in Heap.

---

# 38. Class Lifecycle

```text
Write Class
      ↓
Compile
      ↓
.class File
      ↓
Class Loader
      ↓
Memory Allocation
      ↓
Object Creation
      ↓
Method Execution
      ↓
Garbage Collection
```

---

# 39. Class Design Best Practices

✅ Follow Single Responsibility Principle

✅ Use Encapsulation

✅ Keep Variables Private

✅ Use Getters/Setters

✅ Meaningful Class Names

✅ Favour Composition Over Inheritance

✅ Make Utility Classes Static

✅ Use Immutable Objects When Possible

✅ Avoid God Classes

✅ Follow SOLID Principles

---

# 40. Interview Questions

## What is a Class?

A class is a blueprint used to create objects.

---

## What is an Object?

An object is an instance of a class.

---

## Difference Between Class and Object?

Class:

```text
Blueprint
```

Object:

```text
Actual Instance
```

---

## What is a Constructor?

A special method used to initialize objects.

---

## Difference Between Instance and Static Variables?

Instance:

```text
Per Object
```

Static:

```text
Shared Across All Objects
```

---

## What is an Immutable Class?

A class whose state cannot be changed after object creation.

---

## What is a POJO?

Plain Old Java Object with minimal restrictions.

---

## What is a JavaBean?

POJO with:

- Private Fields
- Getters
- Setters
- No-Arg Constructor

---

## What is a Singleton Class?

A class that allows only one object throughout the application.

---

# Must Master Before Moving Forward

✅ Class Structure  
✅ Objects  
✅ Constructors  
✅ this Keyword  
✅ Variables (Instance, Local, Static)  
✅ Methods  
✅ Access Modifiers  
✅ Nested Classes  
✅ Static Classes  
✅ Anonymous Classes  
✅ Abstract Classes  
✅ Final Classes  
✅ Sealed Classes  
✅ POJO  
✅ JavaBean  
✅ DTO  
✅ Entity Classes  
✅ Singleton Pattern  
✅ Memory Allocation  
✅ Class Loading Process

---
