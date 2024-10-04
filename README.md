# Gang-of-Four

The **Gang of Four (GoF)** patterns refer to 23 classic design patterns introduced in the book _"Design Patterns: Elements of Reusable Object-Oriented Software"_ by Erich Gamma, Richard Helm, Ralph Johnson, and John Vlissides. These patterns are divided into three categories: **Creational**, **Structural**, and **Behavioral**. They provide solutions to common design problems in object-oriented programming.

### 1. **Creational Patterns**

Creational patterns deal with object creation mechanisms, trying to create objects in a manner suitable to the situation.

-   **[Factory Method](/1.1%20Factory%20Method.md)**: Defines an interface for creating objects but allows subclasses to alter the type of objects that will be created.
-   **[Abstract Factory](1.2%20Abstract%20Factory.md)**: Provides an interface for creating families of related or dependent objects without specifying their concrete classes.
-   **Builder**: Separates the construction of a complex object from its representation so that the same construction process can create different representations.
-   **Prototype**: Creates new objects by copying an existing object, known as the prototype.
-   **Singleton**: Ensures a class has only one instance and provides a global point of access to it.

### 2. **Structural Patterns**

Structural patterns concern class and object composition. They help ensure that if one part of a system changes, the entire structure does not need to do so.

-   **Adapter**: Allows incompatible interfaces to work together. It acts as a bridge between two incompatible interfaces.
-   **Bridge**: Decouples an abstraction from its implementation, allowing both to vary independently.
-   **Composite**: Composes objects into tree structures to represent part-whole hierarchies. Allows clients to treat individual objects and compositions of objects uniformly.
-   **Decorator**: Adds additional responsibilities to an object dynamically. It’s more flexible than subclassing for extending functionality.
-   **Facade**: Provides a simplified interface to a complex subsystem or a group of interfaces.
-   **Flyweight**: Reduces the cost of creating and manipulating a large number of similar objects by sharing them.
-   **Proxy**: Provides a surrogate or placeholder for another object to control access to it.

### 3. **Behavioral Patterns**

Behavioral patterns deal with algorithms and the assignment of responsibilities between objects.

-   **Chain of Responsibility**: Passes a request along a chain of handlers, where each handler decides whether to process the request or pass it along to the next handler.
-   **Command**: Encapsulates a request as an object, allowing for parameterization of clients with queues, requests, and operations.
-   **Interpreter**: Defines a grammar for interpreting expressions and builds an interpreter to evaluate sentences in that language.
-   **Iterator**: Provides a way to access elements of a collection sequentially without exposing the underlying representation.
-   **Mediator**: Defines an object that encapsulates how a set of objects interact, promoting loose coupling by keeping objects from referring to each other explicitly.
-   **Memento**: Captures an object’s internal state to be restored later without violating encapsulation.
-   **Observer**: Defines a one-to-many dependency, where if one object changes state, all its dependents are notified.
-   **State**: Allows an object to change its behavior when its internal state changes.
-   **Strategy**: Defines a family of algorithms, encapsulates each one, and makes them interchangeable.
-   **Template Method**: Defines the skeleton of an algorithm in a superclass but lets subclasses override specific steps without changing the algorithm’s structure.
-   **Visitor**: Represents an operation to be performed on the elements of an object structure. It allows defining new operations without changing the classes of the elements on which it operates.

These patterns are widely used in object-oriented design to solve recurring design problems and create more flexible, maintainable, and scalable software.
