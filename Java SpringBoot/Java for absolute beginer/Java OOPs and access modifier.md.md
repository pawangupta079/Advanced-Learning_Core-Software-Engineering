# Java OOP (Object-Oriented Programming) - Complete Industry Ready Study Guide

> This document covers Encapsulation, Inheritance, Polymorphism, Overriding, Overloading, Abstract Classes, and Interfaces in complete detail. These concepts are the foundation of Spring Boot, Hibernate, Microservices, Design Patterns, and Enterprise Java Applications.

---

# Table of Contents

1. OOP Overview
2. Encapsulation
3. Inheritance
4. Types of Inheritance
5. Polymorphism
6. Method Overloading
7. Method Overriding
8. Abstract Classes
9. Interfaces
10. Abstract Class vs Interface
11. OOP Relationships
12. Industry Best Practices
13. Interview Questions

---

# What is OOP?

Object-Oriented Programming (OOP) is a programming paradigm that organizes software around objects rather than functions.

An Object contains:

```text
State  -> Variables
Behavior -> Methods
```

Example:

```java
class Employee {

    String name;

    void work() {

        System.out.println("Working");

    }
}
```

---

# Four Pillars of OOP

```text
1. Encapsulation
2. Inheritance
3. Polymorphism
4. Abstraction
```
<img width="1353" height="1001" alt="image" src="https://github.com/user-attachments/assets/898db10c-e8f6-4b9c-98cd-8886c66f97c5" />

These are asked in almost every Java interview.

---

# 1. Encapsulation
<img width="1528" height="1016" alt="image" src="https://github.com/user-attachments/assets/8ac497fa-c7cf-4ce0-ac32-d4ce91697b9c" />

# What is Encapsulation?

Encapsulation means wrapping data and methods together into a single unit and restricting direct access to data.

Definition:

```text
Data Hiding + Controlled Access
```

---

# Why Encapsulation?

Without Encapsulation:

```java
class Employee {

    public double salary = -1000;

}
```

Anyone can modify:

```java
employee.salary = -50000;
```

This can corrupt application data.

---

# With Encapsulation

```java
class Employee {

    private double salary;

    public void setSalary(double salary) {

        if(salary > 0) {
            this.salary = salary;
        }

    }

    public double getSalary() {

        return salary;

    }

}
```

---

# Advantages

✅ Data Security

✅ Data Validation

✅ Loose Coupling

✅ Maintainability

✅ Better Control

✅ Supports OOP Design

---

# Real Spring Boot Example

```java
@Entity
public class Employee {

    private String name;

    public String getName() {

        return name;

    }

    public void setName(String name) {

        this.name = name;

    }
}
```

Every entity follows encapsulation.

---

# 2. Inheritance

# What is Inheritance?

Inheritance allows one class to acquire properties and methods of another class.

Definition:

```text
IS-A Relationship
```

Example:

```text
Dog IS-A Animal
Car IS-A Vehicle
Manager IS-A Employee
```

---

# Parent Class

```java
class Animal {

    void eat() {

        System.out.println("Eating");

    }

}
```

---

# Child Class

```java
class Dog extends Animal {

}
```

Usage:

```java
Dog d = new Dog();

d.eat();
```

Output:

```text
Eating
```

---

# Why Inheritance?

Without Inheritance:

```java
class Dog {

}

class Cat {

}

class Tiger {

}
```

Repeated code everywhere.

---

# With Inheritance

```java
class Animal {

}

class Dog extends Animal {

}

class Cat extends Animal {

}
```

Common code stays in Animal.

---

# Benefits

✅ Code Reuse

✅ Maintainability

✅ Extensibility

✅ Polymorphism Support

---

# Types of Inheritance

---

## Single Inheritance

```text
Animal
   |
   ↓
 Dog
```

```java
class Animal {
}

class Dog extends Animal {
}
```

---

## Multilevel Inheritance

```text
Animal
   |
 Mammal
   |
  Dog
```

```java
class Animal {
}

class Mammal extends Animal {
}

class Dog extends Mammal {
}
```

---

## Hierarchical Inheritance

```text
      Animal
     /   |   \
  Dog  Cat Tiger
```

---

## Multiple Inheritance

Not supported by classes.

❌

```java
class A {
}

class B {
}

class C extends A,B {
}
```

Causes Diamond Problem.

---

# 3. Polymorphism
<img width="1482" height="1000" alt="image" src="https://github.com/user-attachments/assets/5fb15c81-fa9f-486c-aaa4-036c3f81daed" />

# What is Polymorphism?

Definition:

```text
One Interface
Multiple Forms
```

Same action behaves differently.

---

# Real Example

```text
Payment
|
├── Credit Card
├── UPI
├── Net Banking
```

Same operation:

```java
pay()
```

Different behavior.

<img width="1390" height="898" alt="image" src="https://github.com/user-attachments/assets/2ab6c546-a1fd-4b45-bf1b-18b9e4787af5" />


---

# Types of Polymorphism

```text
1. Compile Time
2. Runtime
```

---

# Compile Time Polymorphism

Achieved using:

```text
Method Overloading
```

---

# Runtime Polymorphism

Achieved using:

```text
Method Overriding
```

---

# Benefits

✅ Flexibility

✅ Scalability

✅ Reusability

✅ Extensibility

---

# 4. Method Overloading

# What is Method Overloading?

Methods having:

```text
Same Name
Different Parameters
```

inside same class.

---

# Example

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

---

Usage

```java
Calculator c =
        new Calculator();

System.out.println(c.add(10,20));

System.out.println(c.add(10,20,30));
```

Output:

```text
30
60
```

---

# Rules of Overloading

Can change:

✅ Number of Parameters

✅ Data Types

✅ Order of Parameters

---

Example

```java
void show(int a)

void show(String a)

void show(int a,String b)
```

---

# Overloading is

```text
Compile Time Polymorphism
Static Binding
Early Binding
```

---

# Real Example

```java
System.out.println()
```

has many overloaded versions.

---

# 5. Method Overriding

# What is Overriding?

Child class provides a new implementation of parent method.

---

Parent:

```java
class Animal {

    void sound() {

        System.out.println("Animal Sound");

    }

}
```

Child:

```java
class Dog extends Animal {

    @Override
    void sound() {

        System.out.println("Bark");

    }

}
```

---

Usage:

```java
Dog d = new Dog();

d.sound();
```

Output:

```text
Bark
```

---

# Rules of Overriding

Method Name:

✅ Same

Parameters:

✅ Same

Return Type:

✅ Same or Covariant

Access Modifier:

✅ Cannot Reduce Visibility

---

# Runtime Polymorphism Example

```java
Animal a = new Dog();

a.sound();
```

Output:

```text
Bark
```

JVM decides method at runtime.

---

# Overriding Uses

✅ Dynamic Behavior

✅ Custom Logic

✅ Extensibility

✅ Framework Development

---

# Spring Boot Example

```java
class UserService {

    void save() {

    }

}
```

Specialized service:

```java
class EmployeeService extends UserService {

    @Override
    void save() {

        System.out.println("Employee Saved");

    }

}
```

---

# Overloading vs Overriding

## Overloading

```text
Same Class
Different Parameters
Compile Time
```

---

## Overriding

```text
Parent & Child Class
Same Signature
Runtime
```

---

# 6. Abstract Class

# What is Abstract Class?

A class that cannot be instantiated.

```java
abstract class Animal {

}
```

Wrong:

```java
Animal a = new Animal();
```

❌

---

# Why Abstract Class?

Sometimes parent class is incomplete.

Example:

```text
Animal
```

Every animal has different sound.

Parent cannot define exact sound.

---

# Abstract Method

```java
abstract void sound();
```

No implementation.

---

Example

```java
abstract class Animal {

    abstract void sound();

}
```

---

Child Implementation

```java
class Dog extends Animal {

    void sound() {

        System.out.println("Bark");

    }

}
```

---

# Abstract Class Can Have

✅ Variables

✅ Methods

✅ Constructors

✅ Static Methods

✅ Abstract Methods

---

# Example

```java
abstract class Vehicle {

    String company;

    Vehicle() {

    }

    abstract void start();

    void stop() {

        System.out.println("Stopped");

    }
}
```

---

# Real Usage

Template classes

Framework development

Base implementations

---

# 7. Interface

# What is Interface?

Interface defines a contract.

It tells:

```text
WHAT to do
```

not

```text
HOW to do
```

---

Example

```java
interface Payment {

    void pay();

}
```

---

Implementation

```java
class UPIPayment implements Payment {

    public void pay() {

        System.out.println("Paid Using UPI");

    }

}
```

---

Usage

```java
Payment p =
        new UPIPayment();

p.pay();
```

Output:

```text
Paid Using UPI
```

---

# Why Interface?

Supports:

✅ Multiple Inheritance

✅ Loose Coupling

✅ Extensibility

✅ Testability

✅ Dependency Injection

---

# Multiple Interface Example

```java
interface Flyable {

}

interface Swimmable {

}

class Duck implements Flyable, Swimmable {

}
```

---

# Java 8 Enhancements

Interface can contain:

✅ Default Methods

✅ Static Methods

---

Default Method

```java
default void show() {

    System.out.println("Default");

}
```

---

Static Method

```java
static void display() {

}
```

---

# Java 9 Enhancements

Private methods allowed.

```java
private void helper() {

}
```

---

# Real Spring Boot Example

Repository Layer

```java
public interface EmployeeRepository
        extends JpaRepository<Employee, Long> {

}
```

Most Spring components use interfaces.

---

# Abstract Class vs Interface
<img width="1244" height="432" alt="image" src="https://github.com/user-attachments/assets/51baba96-a1e3-462b-902e-8deccbb9819e" />

## Abstract Class

```java
abstract class Animal {

}
```

Purpose:

```text
Common Implementation
```

---

## Interface

```java
interface Flyable {

}
```

Purpose:

```text
Contract
```

---

# Feature Comparison

| Feature | Abstract Class | Interface |
|-----------|-----------|-----------|
| Constructor | ✅ | ❌ |
| Instance Variables | ✅ | ❌ |
| Multiple Inheritance | ❌ | ✅ |
| Abstract Methods | ✅ | ✅ |
| Concrete Methods | ✅ | ✅ (default/static) |

---

# OOP Relationships

# IS-A Relationship

Inheritance

```text
Dog IS-A Animal
```

---

# HAS-A Relationship

Composition

```java
class Engine {

}

class Car {

    Engine engine =
            new Engine();

}
```

Car HAS-A Engine

---

# Interview Questions

## What is Encapsulation?

Wrapping data and methods together and controlling access using private variables and public methods.

---

## What is Inheritance?

Acquiring properties and behaviors of a parent class.

---

## Why Multiple Inheritance Not Supported?

To avoid Diamond Problem.

---

## What is Polymorphism?

One interface, multiple forms.

---

## Difference Between Overloading and Overriding?

Overloading:

```text
Compile Time
```

Overriding:

```text
Runtime
```

---

## What is Abstract Class?

A class that cannot be instantiated and may contain abstract methods.

---

## What is Interface?

A contract that defines what a class must implement.

---

## Why Interfaces Are Important in Spring Boot?

Because Spring Framework heavily uses:

```text
Dependency Injection
Loose Coupling
Proxy Objects
AOP
```

which are built around interfaces.

---

# Enterprise Java Mastery Checklist

✅ Encapsulation

✅ Getters & Setters

✅ Data Hiding

✅ Inheritance

✅ Single Inheritance

✅ Multilevel Inheritance

✅ Hierarchical Inheritance

✅ Polymorphism

✅ Compile Time Polymorphism

✅ Runtime Polymorphism

✅ Method Overloading

✅ Method Overriding

✅ Abstract Classes

✅ Abstract Methods

✅ Interfaces

✅ Default Methods

✅ Static Methods in Interface

✅ OOP Relationships

✅ IS-A Relationship

✅ HAS-A Relationship

✅ Spring Boot OOP Design

---

# Next Learning Path

```text
01. Collections Framework
    ├── ArrayList
    ├── LinkedList
    ├── Vector
    ├── Stack
    ├── Queue
    ├── PriorityQueue

02. Set Framework
    ├── HashSet
    ├── LinkedHashSet
    ├── TreeSet

03. Map Framework
    ├── HashMap
    ├── LinkedHashMap
    ├── TreeMap
    ├── ConcurrentHashMap

04. Exception Handling

05. Generics

06. Multithreading

07. Java 8 Features

08. Streams API

09. JDBC

10. Spring Boot
```

This OOP module is one of the most important topics in Core Java. Nearly every Spring Boot application, design pattern, framework, and enterprise backend system depends heavily on these concepts.
