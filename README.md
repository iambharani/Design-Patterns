# Design-Patterns

Design patterns are reusable solutions to common software design problems. They offer templates for solving issues related to software architecture in a flexible and scalable way. There are several categories of design patterns, each serving different purposes. Here’s a brief overview of the main types:

### 1. **Creational Patterns**
   These patterns deal with object creation mechanisms, ensuring that objects are created in a manner suited to the situation.

   - **Singleton**: Ensures a class has only one instance and provides a global point of access to it.
   - **Factory Method**: Defines an interface for creating an object, but lets subclasses alter the type of objects that will be created.
   - **Abstract Factory**: Provides an interface for creating families of related or dependent objects without specifying their concrete classes.
   - **Builder**: Separates the construction of a complex object from its representation, allowing the same construction process to create different representations.
   - **Prototype**: Creates new objects by copying an existing object, known as the prototype.

### 2. **Structural Patterns**
   These patterns deal with object composition, simplifying the structure by identifying relationships.

   - **Adapter**: Allows incompatible interfaces to work together by wrapping an interface around an existing class.
   - **Bridge**: Separates an object’s abstraction from its implementation, allowing the two to vary independently.
   - **Composite**: Composes objects into tree structures to represent part-whole hierarchies, allowing individual objects and compositions to be treated uniformly.
   - **Decorator**: Adds behavior or responsibilities to objects dynamically without modifying their code.
   - **Facade**: Provides a simplified interface to a complex subsystem, hiding its complexities.
   - **Flyweight**: Reduces the cost of creating and manipulating a large number of similar objects.
   - **Proxy**: Provides a surrogate or placeholder for another object to control access to it.

### 3. **Behavioral Patterns**
   These patterns are concerned with object interaction and communication.

   - **Chain of Responsibility**: Passes a request along a chain of handlers, where each handler decides whether to handle the request or pass it to the next.
   - **Command**: Encapsulates a request as an object, thereby allowing parameterization of clients with different requests and queuing or logging requests.
   - **Interpreter**: Defines a grammatical representation for a language and provides an interpreter to deal with this grammar.
   - **Iterator**: Provides a way to access the elements of an aggregate object sequentially without exposing its underlying structure.
   - **Mediator**: Defines an object that encapsulates how a set of objects interact, promoting loose coupling.
   - **Memento**: Captures and externalizes an object’s internal state so that it can be restored later without violating encapsulation.
   - **Observer**: Defines a one-to-many dependency between objects so that when one object changes state, all its dependents are notified.
   - **State**: Allows an object to alter its behavior when its internal state changes, appearing to change its class.
   - **Strategy**: Defines a family of algorithms, encapsulates each one, and makes them interchangeable.
   - **Template Method**: Defines the skeleton of an algorithm, with certain steps being redefined by subclasses.
   - **Visitor**: Represents an operation to be performed on elements of an object structure, allowing new operations without changing the classes of the elements.

### 4. **Concurrency Patterns**
   These deal with multi-threaded programming and optimizing the use of shared resources.

   - **Thread Pool**: Reuses a fixed number of threads to execute tasks, managing them efficiently to improve performance.
   - **Lock Object**: Manages mutual exclusion for access to shared resources.
   - **Read-Write Lock**: Allows multiple threads to read a resource but gives exclusive access when writing is required.

### Example in JavaScript (Observer Pattern)
In React, for example, the **Observer** pattern is often seen with state management tools like Redux, where components observe changes in the state.

```javascript
class Subject {
  constructor() {
    this.observers = [];
  }

  subscribe(observer) {
    this.observers.push(observer);
  }

  unsubscribe(observer) {
    this.observers = this.observers.filter((obs) => obs !== observer);
  }

  notify(data) {
    this.observers.forEach((observer) => observer.update(data));
  }
}

class Observer {
  update(data) {
    console.log('Observer received data:', data);
  }
}

const subject = new Subject();
const observer1 = new Observer();
const observer2 = new Observer();

subject.subscribe(observer1);
subject.subscribe(observer2);

subject.notify('Notification message!');
```

Design patterns are an essential tool in software engineering, helping solve architectural challenges in scalable and maintainable ways.
