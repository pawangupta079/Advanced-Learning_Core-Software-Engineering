# Java Packages - Complete Detailed Study Guide

> Packages are one of the most important concepts in Java. They help organize code, avoid naming conflicts, improve maintainability, provide access control, and form the foundation of large-scale applications like Spring Boot, Hibernate, Microservices, and Enterprise Systems.

---

# Table of Contents

1. What is a Package?
2. Why Packages are Needed
3. Real World Analogy
4. Package Syntax
5. Types of Packages
6. Built-in Packages
7. User Defined Packages
8. Creating Packages
9. Compiling Packages
10. Running Packaged Programs
11. Import Statement
12. Types of Import
13. Static Import
14. Package Naming Conventions
15. Package and Access Modifiers
16. Sub-Packages
17. Classpath
18. Package Structure
19. JAR Files and Packages
20. Package Best Practices
21. Enterprise Project Structure
22. Interview Questions

---

# 1. What is a Package?

A Package is a namespace used to organize related classes, interfaces, enums, and annotations.

Think of packages as folders in your operating system.

Example:

```text
Documents
├── Resume
├── Notes
├── Projects
```

Similarly in Java:

```text
com.company.project
├── Employee.java
├── Department.java
├── Address.java
```

Package helps organize code logically.

---

# 2. Why Packages are Needed

Without Packages:

```text
Employee.java
Employee.java
Employee.java
Employee.java
```

Different developers may create classes with the same name.

This causes:

```text
Name Collision
Confusion
Maintenance Problems
```

Packages solve these issues.

Benefits:

✅ Better Code Organization

✅ Avoid Class Name Conflicts

✅ Reusability

✅ Security

✅ Access Control

✅ Easier Maintenance

✅ Enterprise-Level Structure

---

# 3. Real World Analogy

Consider a company:

```text
Company
│
├── HR Department
│
├── Finance Department
│
├── Sales Department
│
└── Technology Department
```

Every department contains its own employees.

Similarly:

```text
com.company
│
├── hr
│
├── finance
│
├── sales
│
└── technology
```

Each package contains related classes.

---

# 4. Package Syntax

Package declaration must be the first statement.

Example:

```java
package com.company.employee;

public class Employee {

}
```

---

# 5. General Package Structure

```java
package package_name;
```

Example:

```java
package com.pawan.java;
```

Class:

```java
package com.pawan.java;

public class Student {

}
```

---

# 6. Types of Packages

Java provides two categories:

```text
1. Built-in Packages
2. User Defined Packages
```

---

# 7. Built-in Packages

Provided by Java.

Examples:

```text
java.lang
java.util
java.io
java.sql
java.net
java.time
java.math
java.nio
```

---

# 8. java.lang Package

Most frequently used package.

Automatically imported.

Contains:

```text
String
System
Object
Math
Exception
Thread
Integer
Double
```

Example:

```java
String name = "Java";

System.out.println(name);
```

No import required.

---

# 9. java.util Package

Contains utility classes.

Examples:

```java
ArrayList
HashMap
Scanner
Date
Collections
Optional
```

Import:

```java
import java.util.Scanner;
```

Example:

```java
Scanner sc =
    new Scanner(System.in);
```

---

# 10. java.io Package

Used for Input/Output Operations.

Examples:

```java
File
BufferedReader
FileReader
InputStream
OutputStream
```

---

# 11. java.sql Package

Used for database communication.

Examples:

```java
Connection
PreparedStatement
ResultSet
Statement
```

Common in JDBC Applications.

---

# 12. User Defined Packages

Packages created by developers.

Example:

```java
package com.pawan.employee;
```

Class:

```java
package com.pawan.employee;

public class Employee {

}
```

---

# 13. Creating a User Defined Package

Directory Structure:

```text
src
└── com
    └── pawan
        └── employee
            └── Employee.java
```

Employee.java

```java
package com.pawan.employee;

public class Employee {

    public void display() {

        System.out.println("Employee Class");

    }
}
```

---

# 14. Compiling Packages

Compile:

```bash
javac -d . Employee.java
```

Explanation:

```text
-d
```

Creates package directory structure automatically.

Output:

```text
com
└── pawan
    └── employee
        └── Employee.class
```

---

# 15. Running Packaged Program

Run:

```bash
java com.pawan.employee.Employee
```

Use fully qualified class name.

---

# 16. Import Statement

Import allows a class to use another package's classes.

Example:

```java
import java.util.Scanner;
```

Now Scanner can be used directly.

---

# Without Import

```java
java.util.Scanner sc =
    new java.util.Scanner(System.in);
```

---

# With Import

```java
import java.util.Scanner;

Scanner sc =
    new Scanner(System.in);
```

Cleaner and shorter.

---

# 17. Types of Import

---

## Single Class Import

```java
import java.util.Scanner;
```

Imports only Scanner.

---

## Package Import

```java
import java.util.*;
```

Imports all public classes.

Example:

```java
ArrayList
HashMap
Scanner
Collections
```

---

# 18. Fully Qualified Class Name

Using complete package path.

Example:

```java
java.util.Scanner sc =
        new java.util.Scanner(System.in);
```

No import needed.

---

# 19. Static Import

Allows direct access to static members.

Without Static Import:

```java
System.out.println(Math.PI);
```

---

With Static Import:

```java
import static java.lang.Math.PI;

System.out.println(PI);
```

Output:

```text
3.141592653589793
```

---

# Static Method Import

```java
import static java.lang.Math.sqrt;
```

Usage:

```java
System.out.println(sqrt(25));
```

Output:

```text
5.0
```

---

# 20. Package Naming Conventions

Industry Standard Format:

```text
com.company.project.module
```

Example:

```text
com.amazon.order
com.amazon.payment
com.amazon.user
```

---

# Naming Rules

Use:

```text
lowercase letters
```

Good:

```text
com.pawan.java
```

Bad:

```text
Com.Pawan.Java
```

---

# Domain-Based Naming

Company Domain:

```text
google.com
```

Package:

```text
com.google
```

Company:

```text
amazon.com
```

Package:

```text
com.amazon
```

---

# 21. Sub-Packages

Java supports nested packages.

Example:

```text
com
└── company
    ├── employee
    ├── service
    ├── controller
    └── repository
```

Each is treated as a separate package.

---

# Example

```java
package com.company.service;
```

```java
package com.company.repository;
```

Independent packages.

---

# 22. Package and Access Modifiers

Package directly affects visibility.

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
private int age;
```

---

## protected

Same package + subclasses.

```java
protected void show()
```

---

## Default Access

No modifier.

```java
class Employee
```

Accessible only within same package.

---

# Example

Package:

```java
package employee;
```

Class:

```java
class Employee {

}
```

Cannot be accessed outside package.

---

# 23. Package Access Example

Package:

```java
com.company.hr
```

Class:

```java
class Employee {

}
```

Only classes in:

```java
com.company.hr
```

can access it.

---

# 24. Package Structure in Large Projects

Example:

```text
src
│
├── model
│
├── service
│
├── repository
│
├── controller
│
├── exception
│
└── config
```

---

# 25. Spring Boot Package Structure

```text
com.company.project
│
├── controller
│
├── service
│
├── repository
│
├── entity
│
├── dto
│
├── config
│
├── exception
│
└── util
```

This is the industry standard structure.

---

# 26. package-info.java

Used for package-level documentation.

Example:

```java
/**
 * Employee package
 */

package com.company.employee;
```

Useful in Enterprise Projects.

---

# 27. Classpath

Classpath tells JVM:

```text
Where classes are located
```

Example:

```bash
java -cp . Main
```

Current directory added to classpath.

---

# 28. JAR Files and Packages

Java packages are generally distributed as:

```text
JAR Files
```

Example:

```text
spring-core.jar
hibernate-core.jar
mysql-connector.jar
```

JAR contains package structure and compiled classes.

---

# 29. Common Java Packages

---

## java.lang

```text
String
System
Math
Object
```

---

## java.util

```text
List
Set
Map
ArrayList
HashMap
Scanner
```

---

## java.time

```text
LocalDate
LocalTime
LocalDateTime
Duration
Period
```

---

## java.io

```text
File
InputStream
OutputStream
```

---

## java.sql

```text
Connection
PreparedStatement
ResultSet
```

---

# 30. Best Practices

✅ Follow Reverse Domain Convention

```text
com.company.project
```

✅ Keep Package Names Lowercase

✅ Group Related Classes Together

✅ Create Separate Layers

```text
controller
service
repository
```

✅ Avoid Very Deep Package Structures

✅ Use Meaningful Names

✅ Maintain Consistent Organization

---

# Real Enterprise Project Structure

```text
com.soprasteria.employee
│
├── controller
│   └── EmployeeController
│
├── service
│   └── EmployeeService
│
├── repository
│   └── EmployeeRepository
│
├── entity
│   └── Employee
│
├── dto
│   └── EmployeeDTO
│
├── exception
│   └── ResourceNotFoundException
│
└── config
    └── SecurityConfig
```

This structure is commonly used in Spring Boot applications.

---

# Interview Questions

## What is a Package?

A package is a namespace used to organize related classes and interfaces.

---

## Why Use Packages?

To:

- Organize code
- Avoid naming conflicts
- Provide access control
- Improve maintainability

---

## What are Built-in Packages?

Packages provided by Java.

Examples:

```text
java.lang
java.util
java.io
java.sql
```

---

## What is Import Statement?

Import allows usage of classes from another package.

Example:

```java
import java.util.Scanner;
```

---

## What is Static Import?

Static import allows direct access to static members without class name.

Example:

```java
import static java.lang.Math.PI;
```

---

## What is a Sub-Package?

A package inside another package.

Example:

```text
com.company.employee
```

---

## What is Classpath?

Classpath is the location where JVM searches for classes and packages.

---

# Mastery Checklist

✅ Package Basics

✅ Package Syntax

✅ Built-in Packages

✅ User Defined Packages

✅ Import Statement

✅ Package Import

✅ Static Import

✅ Fully Qualified Names

✅ Package Naming Conventions

✅ Access Modifiers and Packages

✅ Sub-Packages

✅ Classpath

✅ JAR Files

✅ Spring Boot Package Structure

✅ Enterprise Project Structure

After mastering Packages, the next topic should be **Access Modifiers + Encapsulation + OOP**, because package visibility and access control become much easier to understand when combined with Object-Oriented Programming concepts.
