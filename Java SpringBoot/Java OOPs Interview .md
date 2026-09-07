# Java OOP Interview Questions & Answers

## Section 1: Java Source File Structure - Import and Package Statements (35 Questions)

### Q1. What is a package in Java?
**A:** A package is a namespace that organizes a set of related classes and interfaces. Conceptually, it is similar to a folder in a file system.

### Q2. Why do we use packages in Java?
**A:** Packages are used to:
- Avoid naming conflicts
- Control access with protected and default access levels
- Make searching/locating classes easier
- Provide controlled access and logical grouping of classes

### Q3. What is the syntax to declare a package?
**A:**
java
package com.example.myapp;

### Q4. Where must the package statement be placed in a Java source file?
**A:** The `package` statement must be the **first statement** in a Java source file (only comments can precede it).

### Q5. Can a Java file have more than one package statement?
**A:** No, a Java source file can have **at most one** package statement.

### Q6. What happens if no package statement is specified?
**A:** The class is placed in the **default (unnamed) package**.

### Q7. What is the naming convention for packages?
**A:** Package names are written in **lowercase** and typically follow the reversed domain name convention, e.g., `com.company.project`.

### Q8. What is the import statement used for?
**A:** The `import` statement allows a Java file to use classes and interfaces defined in another package without using their fully qualified names.

### Q9. What is the syntax for importing a single class?
**A:**
java
import java.util.ArrayList;

### Q10. What is the syntax for importing all classes from a package?
**A:**
java
import java.util.*;

### Q11. Does using `import java.util.*;` import sub-packages too?
**A:** No, importing with `*` only imports classes/interfaces in that specific package, **not sub-packages**.

### Q12. What is a fully qualified name?
**A:** A fully qualified name includes the package name along with the class name, e.g., `java.util.ArrayList`.

### Q13. Can you use a fully qualified class name without importing it?
**A:** Yes, you can use the fully qualified name directly in the code without an import statement.

### Q14. What is static import in Java?
**A:** Static import allows accessing static members (fields and methods) of a class directly without class qualification.
java
import static java.lang.Math.PI;

### Q15. Give an example of using static import.
**A:**
java
import static java.lang.Math.sqrt;
public class Test {
    public static void main(String[] args) {
        System.out.println(sqrt(16));
    }
}


### Q16. What package is imported by default in every Java program?
**A:** The `java.lang` package is imported by default.

### Q17. Can two classes with the same name exist in different packages?
**A:** Yes, as long as they are in different packages, class names can be the same.

### Q18. How do you resolve a naming conflict between two classes with the same name from different packages?
**A:** Use the fully qualified name for at least one of the classes.

### Q19. What is a sub-package in Java?
**A:** A sub-package is a package within another package, e.g., `java.util.concurrent` is a sub-package of `java.util`.

### Q20. Is `java.util` and `java.util.concurrent` considered the same package?
**A:** No, they are treated as **completely different packages** in Java.

### Q21. Can you import a class and also use its fully qualified name in the same file?
**A:** Yes, but it's redundant and generally avoided for readability.

### Q22. What is the order of statements in a Java source file?
**A:**
1. Package statement (optional)
2. Import statements (optional)
3. Class/interface declarations

### Q23. Can comments appear before the package statement?
**A:** Yes, comments can appear before the package statement.

### Q24. What happens if you import a class that doesn't exist?
**A:** A **compile-time error** occurs stating the class/package cannot be found.

### Q25. Can multiple classes in a package be declared as public in a single file?
**A:** No, only **one public class** is allowed per Java file, and it must match the file name.

### Q26. What is the purpose of the `CLASSPATH` environment variable?
**A:** `CLASSPATH` tells the JVM and Java compiler where to look for user-defined classes and packages.

### Q27. How does the JVM locate a package physically on disk?
**A:** Packages correspond to directories, so `com.example.util` maps to `com/example/util/` directory structure.

### Q28. Can you rename a class using import?
**A:** No, Java does not support import aliasing like some other languages.

### Q29. What is the difference between `import` and `package` statements?
**A:** `package` declares which package the current class belongs to; `import` brings in classes from other packages for use.

### Q30. Can a class access another class in the same package without import?
**A:** Yes, classes within the **same package** can access each other without explicit import.

### Q31. What access modifiers are affected by packages?
**A:** `default` (package-private) and `protected` access modifiers are directly influenced by package structure.

### Q32. Is it mandatory to match folder structure with package name?
**A:** Yes, the folder structure **must match** the package declaration for successful compilation and execution.

### Q33. Can an import statement be written after a class declaration?
**A:** No, all import statements must appear **before** any class or interface declaration.

### Q34. What happens if two imported packages have classes with the same name and both use wildcard imports?
**A:** A **compile-time ambiguity error** occurs; you must use fully qualified names to resolve it.

### Q35. Why is package `java.lang` special?
**A:** It contains fundamental classes (`String`, `Math`, `Object`, `System`, etc.) essential to the Java language and is **implicitly imported**.

---

## Section 2: Class and Member Modifiers (35 Questions)

### Q36. What are access modifiers in Java?
**A:** Access modifiers define the visibility/accessibility of classes, methods, and variables. They are: `public`, `private`, `protected`, and default (no modifier).

### Q37. What is the default access modifier?
**A:** When no modifier is specified, it is called **default** or **package-private** access — accessible only within the same package.

### Q38. What is the scope of a `public` member?
**A:** A `public` member is accessible from **anywhere** — any class, any package.

### Q39. What is the scope of a `private` member?
**A:** A `private` member is accessible **only within the same class**.

### Q40. What is the scope of a `protected` member?
**A:** A `protected` member is accessible within the same package and by **subclasses** in different packages.

### Q41. Can a top-level class be declared `private`?
**A:** No, top-level classes can only be `public` or default (package-private).

### Q42. Can a top-level class be declared `protected`?
**A:** No, `protected` is not allowed for top-level classes.

### Q43. What is the `final` modifier used for with variables?
**A:** A `final` variable's value **cannot be changed** once initialized (constant).

### Q44. What is the `final` modifier used for with methods?
**A:** A `final` method **cannot be overridden** by subclasses.

### Q45. What is the `final` modifier used for with classes?
**A:** A `final` class **cannot be extended/inherited**.

### Q46. What is the `static` modifier used for?
**A:** `static` members belong to the **class itself** rather than any instance, shared across all objects.

### Q47. Can static methods access instance (non-static) variables directly?
**A:** No, static methods cannot directly access instance variables since they belong to objects, not the class.

### Q48. Can you override a static method?
**A:** No, static methods are **not overridden**, they are **hidden** (method hiding) if redefined in a subclass.

### Q49. What is a static block used for?
**A:** A static block is used to initialize static variables and runs **once** when the class is loaded into memory.

### Q50. What is the `abstract` modifier used for?
**A:** `abstract` marks a class or method as incomplete, requiring subclasses to provide implementation.

### Q51. Can an abstract class have a constructor?
**A:** Yes, abstract classes can have constructors, called when a subclass object is instantiated.

### Q52. Can you instantiate an abstract class?
**A:** No, abstract classes **cannot be instantiated** directly.

### Q53. Can a class be both `abstract` and `final`?
**A:** No, this is contradictory — `abstract` requires extension, `final` prevents it. This causes a compile-time error.

### Q54. What is the `synchronized` modifier used for?
**A:** `synchronized` ensures that only **one thread** can execute a method/block at a time, used for thread safety.

### Q55. What is the `volatile` modifier used for?
**A:** `volatile` ensures that a variable's value is always read from **main memory**, not cached by threads, ensuring visibility across threads.

### Q56. What is the `transient` modifier used for?
**A:** `transient` marks a variable to be **excluded from serialization**.

### Q57. Can constructors be declared `static`?
**A:** No, constructors cannot be static since they are tied to object instantiation.

### Q58. Can constructors be declared `final`?
**A:** No, constructors cannot be declared final because they are not inherited.

### Q59. What is the difference between `static` and `instance` variables?
**A:** Static variables are shared across all instances; instance variables have a **separate copy per object**.

### Q60. Can an abstract method be `private`?
**A:** No, abstract methods cannot be private since they must be overridden by subclasses.

### Q61. Can an abstract method be `static`?
**A:** No, because static methods cannot be overridden, contradicting the purpose of abstract methods.

### Q62. What happens if a class has an abstract method but is not declared abstract?
**A:** Compile-time error — any class containing an abstract method **must** be declared abstract.

### Q63. Can a `final` variable be a reference type?
**A:** Yes, but the **reference cannot change**; however, the object's internal state (fields) can still be modified.

### Q64. Can we declare an interface method as `final`?
**A:** No, interface methods cannot be `final` since they are meant to be implemented/overridden.

### Q65. What is a blank final variable?
**A:** A `final` variable that is **not initialized at declaration** but must be initialized in the constructor.

### Q66. Can `static` and `final` be used together?
**A:** Yes, `static final` creates a **constant** shared across all instances, e.g., `public static final int MAX = 100;`.

### Q67. What is method hiding in Java?
**A:** When a static method in a subclass has the same signature as a static method in the superclass, it **hides** the parent method rather than overriding it.

### Q68. Can local variables have access modifiers?
**A:** No, local variables (inside methods) **cannot** have access modifiers.

### Q69. What is the difference between `final` and `effectively final`?
**A:** `final` is explicitly declared; **effectively final** means a variable is never reassigned after initialization (used in lambdas without the `final` keyword).

### Q70. Can an abstract class have non-abstract (concrete) methods?
**A:** Yes, abstract classes can have both abstract and fully implemented (concrete) methods.

---

## Section 3: Interfaces (30 Questions)

### Q71. What is an interface in Java?
**A:** An interface is a reference type that defines a **contract** — a set of abstract methods (and other members) that implementing classes must fulfill.


Q72. How do you declare an interface?
**A:** To declare an interface in Java, use the interface keyword followed by the interface name. Interfaces are used to achieve abstraction, defining a contract of what a class should do without specifying how it does it


### Q73. Can an interface have a constructor?
**A:** No, interfaces cannot have constructors since they cannot be instantiated.

### Q74. Are interface methods implicitly public and abstract?
**A:** Yes, by default, all methods in an interface (prior to Java 8) are implicitly `public` and `abstract`.

### Q75. Can an interface have variables?
**A:** Yes, but they are implicitly `public`, `static`, and `final` (constants).

### Q76. Can a class implement multiple interfaces?
**A:** Yes, Java supports **multiple inheritance of type** through interfaces — a class can implement multiple interfaces.

### Q77. Can an interface extend another interface?
**A:** Yes, an interface can extend one or more other interfaces using the `extends` keyword.

### Q78. Can an interface extend multiple interfaces?
**A:** Yes, unlike classes, an interface **can extend multiple interfaces**:
java
interface C extends A, B { }

### Q79. What is a default method in an interface (Java 8+)?
**A:** A default method provides a **concrete implementation** within an interface using the `default` keyword, allowing backward compatibility.

### Q80. Give an example of a default method.
**A:**
java
interface Vehicle {
    default void start() {
        System.out.println("Vehicle starting");
    }
}



### Q81. What is a static method in an interface (Java 8+)?
**A:** A static method in an interface is defined with implementation and can be called using the interface name, and it is **not** inherited or overridden by implementing classes.

### Q82. Give an example of a static method in an interface.
**A:**

java
interface MathUtils {
    static int square(int x) {
        return x * x;
    }
}


### Q83. Can a class override a default method from an interface?
**A:** Yes, implementing classes can override default methods to provide their own implementation.

### Q84. What happens when a class implements two interfaces with the same default method signature?
**A:** A **compile-time error** occurs (diamond problem); the class must override the method to resolve the conflict.

### Q85. How do you call a specific interface's default method in case of conflict?
**A:** Using `InterfaceName.super.methodName()`:

java
InterfaceA.super.show();

### Q86. What is a marker interface? Give an example.
**A:** A marker interface has **no methods or fields**; it is used to signal metadata to the JVM/compiler. Examples: `Serializable`, `Cloneable`.

### Q87. What is a functional interface?
**A:** A functional interface has exactly **one abstract method** and can be used with lambda expressions. Examples: `Runnable`, `Comparator`.

### Q88. What annotation is used to declare a functional interface?
**A:** `@FunctionalInterface`

### Q89. Can a functional interface have default and static methods?
**A:** Yes, it can have multiple default/static methods, but it must have **only one** abstract method.

### Q90. Can an interface have private methods (Java 9+)?
**A:** Yes, since Java 9, interfaces can have `private` methods to share code between default methods.

### Q91. Why were private methods introduced in interfaces?
**A:** To allow **code reuse** between default/static methods without exposing helper methods to implementing classes.

### Q92. Can an interface be declared `final`?
**A:** No, interfaces cannot be `final` since they are meant to be implemented.

### Q93. Can an interface implement another interface?
**A:** No, interfaces can only **extend** other interfaces, not implement them.

### Q94. What is the difference between an abstract class and an interface?
**A:**
| Feature | Abstract Class | Interface |
|---|---|---|
| **Methods** | Abstract + concrete | Abstract, default, static, private |
| **Variables** | Any type | `public static final` only |
| **Inheritance** | Single | Multiple |
| **Constructor** | Yes | No |

### Q95. Can an interface variable be reassigned?
**A:** No, since interface variables are implicitly `final`, they cannot be reassigned.

### Q96. What happens if a class doesn't implement all abstract methods of an interface?
**A:** The class must be declared `abstract`, otherwise a **compile-time error** occurs.

### Q97. Can you create an instance of an interface?
**A:** No, but you can create an **anonymous class** that implements the interface:

java
Runnable r = new Runnable() {
    public void run() {
        System.out.println("Running");
    }
};


### Q98. What is the diamond problem, and how does Java handle it with interfaces?
**A:** The diamond problem occurs when a class inherits conflicting default methods from multiple interfaces. Java forces the implementing class to **explicitly override** the method to resolve ambiguity.

### Q99. Can an interface have a main method?
**A:** Yes, since static methods are allowed, an interface can technically have a `main` method and be run directly (Java 8+).

### Q100. Why use interfaces instead of abstract classes?
**A:** Interfaces are preferred when:
- You need **multiple inheritance** of behavior.
- You want to define a **contract** without dictating implementation details.
- You want **loose coupling** between components.
