# Design Pattern - Gang of Four (GoF)

The **Gang of Four (GoF)** refers to four authors (Erich Gamma, Richard Helm, Ralph Johnson, John Vlissides) who wrote the famous book _“Design Patterns: Elements of Reusable Object-Oriented Software”_.

They introduced **23 design patterns** that solve common software design problems.  
These are grouped into **three categories**: **Creational, Structural, Behavioral**.

## 1\. **Creational Patterns - (How objects are created)**

Help you **create objects in flexible ways** instead of directly using `new`.

1.  [**Factory Method**](/1.1%20Factory%20Method.md) → Let subclasses decide which object to create.
2.  [**Abstract Factory**](1.2%20Abstract%20Factory.md): Create families of related objects without knowing their concrete classes.
    1.  Difference between [Abstract Factory vs Factory method](1.2.1%20Abstract%20Factory%20vs%20Factory%20method.md)
3.  **Builder→** Build complex objects step by step.
4.  **Prototype→** Clone existing objects instead of creating new ones.
5.  **Singleton** → Only one instance of a class.

## 2\. **Structural Patterns - (How objects/classes are composed)**

Structural patterns concern class and object composition. They help ensure that if one part of a system changes, the entire structure does not need to do so. Help you **organize and connect classes/objects** for easier maintenance.

1.  **Adapter** → Make incompatible classes work together (like a plug adapter).
2.  **Bridge** → Separate abstraction from implementation so both can vary.
3.  **Composite** → Tree structures where individual & groups are treated the same.
4.  **Decorator** → Add new behavior to objects without modifying them.
5.  **Facade** → Provide a simple interface to a complex system.
6.  **Flyweight** → Reuse shared objects to save memory.
7.  **Proxy** → A placeholder that controls access to another object.

## 3\. **Behavioral Patterns - (How objects interact)**

Behavioral patterns deal with algorithms and the assignment of responsibilities between objects.

*   **Chain of Responsibility**: Passes a request along a chain of handlers, where each handler decides whether to process the request or pass it along to the next handler.
*   **Command**: Encapsulates a request as an object, allowing for parameterization of clients with queues, requests, and operations.
*   **Interpreter**: Defines a grammar for interpreting expressions and builds an interpreter to evaluate sentences in that language.
*   **Iterator**: Provides a way to access elements of a collection sequentially without exposing the underlying representation.
*   **Mediator**: Defines an object that encapsulates how a set of objects interact, promoting loose coupling by keeping objects from referring to each other explicitly.
*   **Memento**: Captures an object’s internal state to be restored later without violating encapsulation.
*   **Observer**: Defines a one-to-many dependency, where if one object changes state, all its dependents are notified.
*   **State**: Allows an object to change its behavior when its internal state changes.
*   **Strategy**: Defines a family of algorithms, encapsulates each one, and makes them interchangeable.
*   **Template Method**: Defines the skeleton of an algorithm in a superclass but lets subclasses override specific steps without changing the algorithm’s structure.
*   **Visitor**: Represents an operation to be performed on the elements of an object structure. It allows defining new operations without changing the classes of the elements on which it operates.

These patterns are widely used in object-oriented design to solve recurring design problems and create more flexible, maintainable, and scalable software.
