# Data structures (synthesis)

<br>![code image](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/resources/code.jpg)


## Table of Contents

+ [References](#references)
+ [Data structures and algorithms](#data-structures-and-algorithms)
+ [Mathematical preliminaries](#mathematical-preliminaries)
+ [Algorithm analysis](#algorithm-analysis)
+ [Lists, stacks, queues](#lists,-stacks,-queues)
+ [Binary trees](#binary-trees)
+ [Non-binary trees](#non-binary-trees)
+ [Internal sorting](#internal-sorting)
+ [File processing and external sorting](#file-processing-and-external-sorting)
+ [Searching](#searching)
+ [Indexing](#indexing)


## References

- Clifford A. Shaffer (2013) _**Data structures & Algorithm analysis**_. Department of Computer Science, Virginia Tech University. Retrieved from [here](https://people.cs.vt.edu/shaffer/Book/).
- Granville Barnett, Luca Del Tongo (2008) _**Data Structures and Algorithms: Annotated Reference with Examples**_ Dot.NetSlackers. Retrieved from [here](https://archive.org/details/pdfy-A-5D_dQU-sNJJHOB).


## Data Structures and Algorithms

### Introduction

The primary purpose of most computer programs is not to perform calculations, but to store and retrieve information (usually as fast as possible). Data structures and algorithms help with this. Each data structure has costs and benefits (**tradeoffs**), which are described by the amount of space and time required for typical operations. We can evaluate the efficiency of an algorithm with the **asymptotic analysis** method (used for analysing the difficulty of a problem and estimating the time cost of an algorithm).

Ideally, we want to solve a problem with an algorithm that is both readable (easy to understand, code, and debug) and efficient (makes efficient use of computer's resources). Making it readable is for software engineering. Making it efficient is for computer science (data structures and algorithms). Here, we focus on efficiency.

**Data structure** (DS): Any data representations and its associated operations.

A solution is **efficient** if it solves the problem within the required **resource constraints** (like main memory, disk space, time...). The amount of resources that the solution consumes is the **cost** of the solution (often measured in terms of one key resource such as time, and assuming the solution meets the other resource constraints). 

When selecting a data structure to solve a problem:

1. Analyze the problem to determine the basic operations that must be supported.
2. Quantify the resource constraints for each operation.
3. Select the data structure that best meets these requirements

Resource constraints on certain key operations normally drive the data structure selection process. You should ask these questions when choosing a data structure:

- Are all data items inserted into the DS at the beginning, or are insertions interspersed with other operations? Static applications (data is loaded at the beginning and never change) typically require simpler DSs than dynamic applications do.
- Can data items be deleted? If so, probably the implementation will be more complicated.
- Are all data items processed in some well-defined order, or is search for specific data items allowed? “Random access” search generally requires more complex data structures.

Each DS has associated **costs** and **benefits**. A DS requires a certain amount of space for each data item it stores, a certain amount of time to perform a single basic operations, and a certain amount of programming effort. Each problem has constraints on available space and time. Each solution to a problem makes use of the basic operations in some relative proportion, and the DS selection process must account for this.

### Abstract data types and Data structures

**Type**: Collection of values (example: a Boolean type consists of 2 values).

- **Simple type**: Contains no subparts (example: integer).
- **Aggregate/composite type**: Is made of different subparts (example: bank account).

**Data item**: Piece of information or record whose value is drawn from a type. It's a member of a type.

**Data type**: Data type together with a collection of operations to manipulate the type (example: an integer variable is a member of the integer data type). The same data type can be implemented in many different ways. It has a logical (the ADT) and physical (the implementation) form.

- **Abstract data type** (ADT): Realization of a data type as a software component. The ADT interface is defined in terms of a type and a set of operations on that type. An ADT doesn't specify how tht data type is implemented (that's hidden and encapsulated). One ADT might have more than one implementation.

- **Data structure**: Implementation of an ADT. It's data stored in memory.

In object-oriented languages, an ADT and its implementation together make up a **class*. Each ADT operation is implemented by a **member function** (or **method**). The variables defining the space of a data item are **data members**. An **object** is an instance of a class, which is created and takes up storage during program execution.

**File structure**: Data on peripheral storage (like disk drive).

We manage complexity through **abstraction**: assigning a label to an assembly of objects/concepts and then manipulating the label in its place (metaphor). A particular label might be related to other labels, so we can give this collection a label, forming a hierarchy, which allows us to ignore unnecessary details.

### Design patterns

**Design patterns**: Abstractions for describing the design of programs (i.e., the interaction of objects and classes). It's a design concept for a recurring problem. It allows efficient communication between programmers. Each one provides costs and benefits (tradeoffs). Examples:

- __Flyweight__: Consider an application with many objects that are identical in the information they contain and the role they play. Instead of having so much duplication, we can reduce memory usage by using just one of such objects and referencing it wherever it's used. Each reference is a flyweight.

- __Visitor__: Consider a tree and an some operations we want to perform on each node. Instead of writing a separate traversal function for each operation, we can write a generic traversal function and pass in the activity to be performed at each node.

- __Composite__: Consider a hierarchy of classes (base classes and subclasses), and a set of actions to be performed on a collection of such objects. One option is to apply a visitor pattern; however, the visitor function has to contain logic for dealing with each subclass. A better option is to make all classes subclasses of `Component`, including a `Composite` class that can store different `Component` objects. Each subclass implements the required actions. The `Composite` object implement them in a way that they are called for each `Component` it contains. Now, the same action can be executed in a collection of objects (including objects that contain a composition of objects). Individual objects and composition of objects are treated uniformly. This allow the creation of trees.

- __Strategy__: There is an action performed by a function (payment), but there're different ways of doing so (credit card or debit card). Each of these algorithms can be encapsulated into functions and then passed to the main function so it does the action in a certain way. It encapsulates an activity that is part of a larger process, so that different ways of performing that activity can be substituted.

Visitor gives control to the tree. Composite gives control to the nodes. Strategy just encapsulates part of the action.

### Problems, algorithms, and programs

**Problems**: Task to be performed. It should declare the constraints on the resources to consume (like space and time limitations). It's like a mathematical **function**: it's a matching between inputs (domain, parameters) and outputs (range). The same input always gets the same output. Different inputs may get the same output. A problem instance is a specific selection of values for the parameters.

**Algorithms**: Method or process followed to solve a problem. It's like the implementation of the function (problem). A problem can be solved by different algorithms. One algorithm only solves one problem. Properties of an algorithm:

- It must be __correct__: It computes the desired function correctly. It converts each input to the correct output.
- It's composed of __concrete steps__: Each step is understood, doable, and takes a finite amount of time.
- There's __no ambiguity__ as to which step to perform next.
- It's made of a __finite__ number of steps.
- It must __terminate__: It cannot go into an infinite loop.

**Programs**: Instance, or concrete representation, of an algorithm in some programming language.


## Mathematical preliminaries

**Set** (${a,b,c}$): Collection of distinguishable **members** or **elements** with no order. Set ${a,b,c,c}$ is indistinguishable from ${a,b,c}$. Members are typically drawn from a larger population (**base type**: integer, double, bool...). Each set member is a **primitive element** of the base type or a set itself. There're no duplications in a set. Each value from the base type is either in the set or not in the set.

- ${1, 2, 4}$: Set with 3 members
- ${x|x is a positive integer}$: Set of all positive integers
- $x \in P$: x is member of set P
- $x \not\in P$: x is not member of set P
- $\emptyset$: Null/empty set
- $|P|$: Size (number of members in set P)
- $P \subseteq Q, Q \supseteq P$: Set P is subset of Q. Set Q is superset of P.
- $P \cup Q$: Union (all elements in P OR Q)
- $P \cap Q$: Intersection (all elements in P AND Q)
- $P - Q$: Difference (all elements of P NOT in Q)
- **Powerset** of $S={a,b,c}$: ${\emptyset, {a}, {b}, {c}, {a,b}, {b,c}, {a,c}, {a,b,c}}$

**Bag**: Collection of elements with no order, like a set, but with duplicate-valued elements. Bag $[a,b,c,c]$ is distinguishable from $[a,b,c]$, but indistinguishable from $[c,a,b,c]$..

**Sequence** (tuple, vector): Collection of elements with an order, and may contain duplicate-valued elements.
























## Algorithm Analysis
## Lists, Stacks, Queues
## Binary trees
## Non-binary Trees
## Internal Sorting
## File Processing and External sorting
## Searching
## Indexing
