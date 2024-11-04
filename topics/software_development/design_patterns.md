# Design patterns

## Table of Contents
+ [References](#references)
+ [Diagrams](#diagrams)
+ [Introduction](#introduction)


## References
- Erich Gamma, Richard Helm, Ralph Johnson, John Vlissides (1994) _**Design patterns. Elements of object-oriented software**_. Addison-Wesley. Retrieved from [link1](http://www.uml.org.cn/c++/pdf/designpatterns.pdf), [link2](http://www.grch.com.ar/docs/unlu.poo/Gamma-DesignPatternsIntro.pdf), [link3](https://github.com/TushaarGVS/Design-Patterns-Mentorship/blob/master/Erich%20Gamma%2C%20Richard%20Helm%2C%20Ralph%20Johnson%2C%20John%20M.%20Vlissides-Design%20Patterns_%20Elements%20of%20Reusable%20Object-Oriented%20Software%20%20-Addison-Wesley%20Professional%20(1994).pdf).
- [Sourcemaking](https://sourcemaking.com/design_patterns)
- [MVC design pattern](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller)


## Diagrams

## Class diagrams

It depicts classes, their strructure, and the static relationships between them.

<br>![class_diagram_2](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/topics/software_development/resources/class_diagrams_2.png)

<br>![class_diagram_1](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/topics/software_development/resources/class_diagram_1.png)

### Object diagrams

It depicts a particular object structrue at run-time.

<br>![object_diagram_1](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/topics/software_development/resources/object_diagram_1.png)

<br>![object_diagram_2](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/topics/software_development/resources/object_diagrams_2.png)

### Interaction diagrams

It shows the flow of requests between objects.

<br>![interaction_diagram_1](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/topics/software_development/resources/interaction_diagrams_2.png)

<br>![interaction_diagram_2](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/topics/software_development/resources/interaction_diagram_1.png)


## Introduction

Designing reusable object-oriented software is hard. You have to:

- Find pertinent objects
- Factor them into classes at the right granularity
- Define class interfaces
- Define inheritance hierarchies
- Establish key relationships among them

The design should be specific to the problem at hand but also general enough to address future problems and requirements. Furthermore, you want to avoid redesign, or at least minimize it. A flexible and reusable design is difficult to get.

Experienced designers discovered that certain patterns of classes and communicating objects were very useful for solving specific design problems and make object-oriented designs more flexible, elegant and reusable. They can apply this patterns immediately to solve design problems without having to rediscover them.

### Types

A **pattern** describes a problem that happens very often in our environment, and then describes the core of the solution to it in such a way that you can use this solution a million times over without ever doing it the same way twice. A pattern has 4 elements:

- **Name**: Describes a design problem, its solutions, and consequences in one/two words.
- **Problem**: Describes when to apply a pattern.
- **Solution**: Elements that make up the design, their relationships, responsabilities and collaborations.
- **Consequences**: Results and trade-offs of applying the pattern.

**Design patterns**: Descriptions of communicating objects and classes that are customized to solve a general design problem in a particular context.

<br>![design patterns table](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/topics/software_development/resources/design_patterns_table.png)

**Purpose**: What a pattern does.

- **Creational**: Relative to object creation.
- **Structural**: Deals with the composition of classes or objects.
- **Behavioral**: Characterizes the ways in which classes or objects interact and distribute responsibility.

**Scope**: Specifies whether the pattern applies primarily to classes or objects

- **Class**: Deals with relationships between classes and their sub-classes (inheritance). They are static-fixed at compile-time.
- **Object**: Deals with object relationships, which can be changed at run-time.

**Creational class patterns** defer some part of object creation to subclasses. **Creational object patterns** defer it to another object.

**Structural class patterns** use inheritance to compose classes. **Structural object patterns** describe ways to assemble objects.

**Behavioral class patterns** use inheritance to describe algorithms and flow of control. **Behavioral object patterns** describe how a group of objects cooperate to perform a task that no single object can carry out alone.

### Relationships

Some patterns are often used **together** (e.g.: Composite + Iterator/Visitor). Some are **alternatives** (Prototype, Abstract factory). Some result in **similar designs** (Composite, Decorator).

<br>![relationships](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/topics/software_development/resources/relationships.png)

### Solving design problems

- **Finding appropriate objects**

Design patterns help you identify less-obvious abstractions and the objects that can capture them.

- **Determining object granularity**

Objects can vary tremendously in size and number (from everything down to the hardware, to all the way up to entire applications).

- **Specifying object interfaces**

Objects are only known through their interfaces, and interfaces say nothing about the object’s implementation. The interface is the set of operations allowed by the object, wich are defined by their **signatures** (operation’s name, parameters and return values). A **type** is a name used to denote a particular interface. A type is a sub-type of another if its interface contains the interface of its super-type (sub-type **inherits** from its super-type).

**Dynamic binding**: It’s the run-time association of a request to an object and one of its operations. So, issuing a request doesn’t commit you to a particular implementation until run-time. Then, you can write programs that expect an object with a particular interface, knowing that any object that has the correct interface will accept the request. Moreover, dynamic binding lets you substitute objects that have identical interfaces for each other at run-time (**polymorphism**).

**Polymorphism**: It lets a client object make few assumptions about other objects beyond supporting a particular interface. It simplifies the definitions of clients, decouples objects from each other and lets them vary their relationships to each other at run-time.

Design patterns help you define interfaces by identifying their key elements and the kinds of data that get sent across an interface. They might also tell you what not to put in the interface (Memento). They also specify relationships between interfaces (Decorator, Proxy, Visitor).

- **Specifying object implementations**

An object implementation is defined by its class. The class defines the object’s internal _data_ and representation, and defines the _operations_ the object can perform. Objects are created by instantiating a class (the object is an instance of the class), and then some storage is allocated for the object’s internal data (instance variables) and associates the operations with these data.

**Class inheritance**: New classes can be defined in terms of existing classes. When a sub-class inherits from a parent class, it includes the definitions of all the data and operations that the parent class defines. Objects that are instances of the subclass will contain all data defined by the subclass and its parent classes, and they’ll be able to perform all operations defined by both.

**Classes**:

- **Abstract class**: It defines a common interface for its sub-classes. I defers some or all of its implementation to operations defined in sub-classes, hence it cannot be instantiated. The operations that it declares but doesn’t implement are **abstract operations**.
- **Concrete class**: A class that is not an abstract class.

A sub-class may **override** an operation defined by its parent class, which gives it a chance to handle requests instead of their parent classes. Class inheritance lets you define classes simply by extending other classes, making it easy to define families of objects having related functionality.

**Mixin class**: It’s intended to provide an optional interface or functionality to other classes. It’s similar to an abstract class in that it’s not intended to be instantiated. I requires multiple inheritance (the mixin in one of many classes that are inherited by a certain class).

**Object**:

- **Object’s class**: Defines how the object is implemented. The internal state and the implementation of its operations.
- **Object’s type**: The object’s interface (set of requests to which it can respond). An object can have many types, and objects of different classes can have the same type.

**Inheritance**:

- **Class inheritance**: Defines an object’s implementation in terms of another object’s implementation. Useful for extending an application’s functionality by reusing functionality in parent classes. It lets you define a new kind of object rapidly in terms of an old one.
- **Interface inheritance**: Defines when an object can be used in place of another. Polymorphism depends on this inheritance.

In C++, inheritance means both interface and implementation inheritance. The standard way to _inherit an interface_ in C++ is to inherit publicly from a class that has (pure) virtual member functions. Pure interface inheritance can be approximated in C++ by inheriting publicly from pure abstract classes. Pure implementation or _class inheritance_ can be approximated with private inheritance.

When inheritance is used carefully, all classes derived from an abstract class will share its interface. This implies that a subclass merely adds or overrides operations and doesn’t hide operations of the parent class. All subclasses can then respond to the requests in the interface of this abstract class, making them all subtypes of the abstract class. Benefits from manipulating objects solely in terms of the interface defined by abstract classes:

- Clients remain unaware of the specific types of objects they use, as long as the objects adhere to the interface that clients expect.
- Clients remain unaware of the classes that implement these objects. Clients only know about the abstract class/es defining the interface.

**Program to an interface, not an implementation**. Don’t declare variables to be instances of particular concrete classes. Instead, commit only to an interface defined by an abstract class. You have to instantiate concrete classes (i.e. specify a particular implementation) somewhere in your system, and the creational patterns let you do just that. By abstracting the process of object creation, these patterns give you different ways to associate an interface with its implementation transparently at instantiation. Creational patterns ensure that your system is written in terms of interfaces, not implementations.

### Reuse mechanisms

#### Most common techniques:

- **Class inheritance**: You define the implementation of one class in terms of another’s. With inheritance, the internals of parent classes are often visible to subclasses (white-box reuse). Defined **statically** at compile-time.

  - Advantages:

    - Straightforward to use because it’s supported directly by the programming language.
    - Easier to modify the implementation being reused.

  - Disadvantages:

    - You can’t change the implementations inherited from parent classes at run-time, because inheritance is defined at compile-time.
    - Inheritance exposes a subclass to details of its parent’s implementation (it’s often said that “inheritance breaks encapsulation”). The implementation of a subclass becomes so bound up with the implementation of its parent class that any change in the parent’s implementation will force the subclass to change.
    - If any aspect of the inherited implementation is not appropriate for new problems, the parent class must be rewritten/replaced. One solution: Inherit from abstract classes (they have little or no implementation)

- **Object composition**: New functionality is obtained by assembling (composing) objects to get more complex functionality (it requires well-defined interfaces). No internal details of objects are visible (black-box reuse). It requires objects to respect each others’ interfaces (objects are accessed solely through their interfaces). Defined **dynamically** at run-time through objects acquiring references to objects.

  - Advantages:

    - It’s easy to compose behaviors at run-time by changing how they’re composed.
    - Any object can be replaced at run-time by another as long as it has same type.
    - Fewer implementation dependencies (since an object’s implementations is written in terms of objects interfaces).
    - Keeps each class encapsulated and focused on one task.
    - It has more objects (if fewer classes), and its behavior depends on their relationships instead of being defined in one class.

- **Parameterized types** (Templates): It lets define types without specifying all the other types it uses. Unspecified types are supplied as parameters at the point of use(e.g.: a List class can be parameterized by the types of elements it contains).

**Favor object composition over class inheritance**: However, the set of available components is never quite rich enough in practice, so both mechanisms should work together. Inheritance makes it easier to make new components that can be composed with old ones. Object composition makes designs more reusable and simpler.

#### Delegation

It is a type of object composition that makes composition as powerful for reuse as inheritance. Two objects are involved in handling a request: a receiving object delegates operations to its **delegate** (analogous to subclasses deferring requests to parent classes). To let the delegated operation refer to the receiver, the receiver passes itself to the delegate. Delegation shows that inheritance can always be replaced with object composition.

Example: Instead of making class Window a subclass of Rectangle, Window class might keep a rectangle member variable and delegate Rectangle-specific behavior to it.

<br>![window object](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/topics/software_development/resources/titan1.png)

Advantages:

- It’s easy to compose behaviors at run-time and change the way they’re composed. Replacing Rectangle instance with a Circle instance (assuming they have same type) our window can become circular at run-time.

Disadvantages:

- Dynamic, highly parameterized software is harder to understand than more static software.
- Run-time inefficiencies (though human inefficiencies are more important in the long run).

Delegation is a good choice only when it simplifies more than it complicates. It works best when used in highly stylized ways (i.e., in standard patterns). Several design patterns use delegation (State, Strategy, Visitor, Mediator, Chain of Responsability, Bridge).

22
