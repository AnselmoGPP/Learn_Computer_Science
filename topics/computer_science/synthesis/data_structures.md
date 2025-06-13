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
+ [Graphs](#graphs)


## References

- Clifford A. Shaffer (2013) _**Data structures & Algorithm analysis**_. Department of Computer Science, Virginia Tech University. Retrieved from [here](https://people.cs.vt.edu/shaffer/Book/).
- Granville Barnett, Luca Del Tongo (2008) _**Data Structures and Algorithms: Annotated Reference with Examples**_ Dot.NetSlackers. Retrieved from [here](https://archive.org/details/pdfy-A-5D_dQU-sNJJHOB).
- [How to do problems](https://www.quora.com/When-should-I-start-doing-LeetCode-problems-I-haven-t-learned-data-structures-and-algorithms)

Symbols used: ≤, ≥, ≠, ≈, √, ∑, →, ↔, ∨, ∧, ~, ¬, ∀, ∃, ⌊⌋, ⌈⌉, <sub>i</sub>, <sup>i</sup>, ∞, Ω, Θ


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

### Sets and relations

**Set** (${a,b,c}$): Collection of distinguishable **members** or **elements** with no order. Set ${a,b,c,c}$ is indistinguishable from ${a,b,c}$. Members are typically drawn from a larger population (**base type**: integer, double, bool...). Each set member is a **primitive element** of the base type or a set itself. There're no duplications in a set. Each value from the base type is either in the set or not in the set.

- $\{1, 2, 4\}$: Set with 3 members
- $\{x|x is a positive integer\}$: Set of all positive integers
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

**Sequence** (tuple, vector): Collection of elements with an order, and may contain duplicate-valued elements. Each element has a position (0th, 1st, 2nd...). Sequence $\<3,4,5,4\>$ is distinct from $\<3,5,4,4\>$.

**Relation** over a set S: Set of ordered pairs from S. Each pair is a sequence. Given set $\<a,b,c\>$, one relation is $\{\<a,c\>,\<b,c\>,\<c,c\>\}$. Infix notation: $xRy$ means that tuple $\<x,y\>$ is in relation R. Properties of relations (given a binary relation R over set S):

- R is __reflexive__ if $aRa$ for all $a \in S$.
- R is __symmetric__ if whenever $aRb$, then $bRa$, for all $a,b \in S$.
- R is __antisymmetric__ if whenever $aRb$ and $bRa$, then $a = b$, for all $a,b \in S$.
- R is __transitive__ if whenever $aRb$ and $bRc$, then $aRc$, for all $a,b,c \in S$.

**Equivalence relation** of S: Relation that is reflexive, symmetric, and transitive. If 2 elements a and b are equivalent, we write $a &equiv; b$.

**Partition** of set S: Collection of subsets disjoint from each other and whose union is S. An equivalence relation on set S partitions the set into subsets whose elements are equivalent.

**Partial order**: Binary relation that is antisymmetric and transitive. The set on which it's defined is called a **partially ordered set** (or poset). Elements x and y of a set are **comparable** under a given relation if either $xRy$ or $yRx$. If every pair of distinct elements in a partial order are comparable, then the order is called **total order** or **linear order**.

### Notations

**Units of measure**:

- b: bits
- B: bytes
- KB: kilobytes (2<sup>10</sup> = 1024 bytes)
- MB: megabytes (2<sup>20</sup> bytes)
- GB: gigabytes (2<sup>30</sup> bytes)
- ms: milliseconds (1/1000 seconds)

Spaces between the number and the unit abbreviation are:

- __not placed__ when a power of 2 is intended (25GB when a gigabyte is intended as 2<sup>30</sup> bytes).
- __placed__ when a decimal value is intended (2000 bits would be written "2 Kb" while "2Kb" represents 2048 bits) (2000 milliseconds is written as 2000 ms).

**Factorial function** ($n!$): Product of the integers between 1 and n, inclusive ($5! = 1·2·3·4·5 = 120$). Special case: $0! = 1$. It grows quickly as n becomes larger, slower than n<sup>n</sup>, but faster than c<sup>n</sup> (where c is any positive integer constant). Stirling's approximation states that √(2πn)(n/e)<sup>n</sup> (where $e ≈ 2.71828$).

**Permutation** of a sequence S: Members of S arranged in some order. A sequence containing n distinct members have n! different permutations.

**Boolean** variable: Variable that takes one of two values: `true` or `false` (often associated with values `1` and `0`).

**Logic notation**:

- A→B: A implies B (or if A then B)
- A↔B: A if and only if B (or A is equivalent to B)
- A∨B: A or B
- A∧B: A and B
- ~A (or ¬A): not A (where A is boolean)
- ∀: for all (universal quantifier) (`∀x P(x)`)
- ∃: there exists (existential quantifier) (`∃x P(x)`)

**Floor and ceiling**:

- **Floor** (⌊x⌋): Greatest integer ≤ x (`⌊3.4⌋ = 3`) (`⌊-3.4⌋ = -4`)
- **Ceiling** (⌈x⌉): Least integer ≥ x (`⌈3.4⌉ = 4`) (`⌈-3.4⌉ = -3`)

**Modulus operator** (mod, %): Returns the remainder of an integers division. The result of $n mod m$ is in the range [0, m-1]. Examples: `5 mod 3 = 2`, `-3 mod 5 = 2`.

**Logarithm** of base b for value y (log<sub>b</sub>y=x): Power to which b is raised to get y (b<sup>x</sup> = y = b<sup>log<sub>b</sub>y</sup>). In computer science, most logarithms have base 2 (data structures and algorithms most often divide things in half, or store codes with binary bits). Here, "log n" means either "log<sub>2</sub>n" or it's used asymptotically (so base doesn't matter).

Logarithm properties (for positive values m, n, r, and positive integers a, b):

- log(nm) = log n + log m
- log(n/m) = log n - log m
- log(n<sup>r</sup>) = r log n
- log<sub>a</sub>n = log<sub>b</sub>n/log<sub>b</sub>a

Additional logarithm representations:

- Square of a logarithm: (log n)<sup>2</sup> or log<sup>2</sup>n.
- Logarithm of a logarithm: log log n.
- Times we have to take the log of a number before reaching a value ≤ 1: log* n (example: log* 1024 = 4, because log 1024 = 10, log 10 ≈ 3.33, log 3.33 ≈ 1.74, log 1.74 < 1)

### Summations and Recurrences

**Summation**: Sum of costs for some function applied to a range of parameter values (∑<sup>n</sup><sub>i=1</sub> f(i) = f(1) + f(2) + ... + f(n)). Solving the summation results in a closed-form solution (algebraic equation with the same value as the summation). Examples (summations and closed-form solutions):

- ∑<sup>n</sup><sub>i=1</sub> i = (n(n+1)) / 2
- ∑<sup>n</sup><sub>i=1</sub> i<sup>2</sup> = (2n<sup>3</sup> + 3n<sup>2</sup> + n) / 6 = (n(2n+1)(n+1)) / 6
- ∑<sup>log n</sup><sub>i=1</sub> n = n log n
- ∑<sup>∞</sup><sub>i=0</sub> a<sup>i</sup> = 1 / (1-a) for 0<a<1
- ∑<sup>n</sup><sub>i=0</sub> a<sup>i</sup> = (a<sup>n+1</sup>-1) / (a-1) for a≠1
- ∑<sup>n</sup><sub>i=1</sub> 1 / 2<sup>i</sup> = 1 - 1 / 2<sup>n</sup>
- ∑<sup>n</sup><sub>i=0</sub> 2<sup>i</sup> = 2<sup>n+1</sup> - 1
- ∑<sup>log n</sup><sub>i=0</sub> 2<sup>i</sup> = 2<sup>log n+1</sup> - 1 = 2n - 1
- ∑<sup>n</sup><sub>i=1</sub> i / 2<sup>i</sup> = 2 - (n+2) / 2<sup>n</sup>

**Recurrence relation**: Expression that includes one or more (smaller) instances of itself. Examples:

- Factorial function: n! = (n-1)!·n   for n>1;   1!=0!=1
- Fibonacci sequence: Fib(n) = Fib(n-1) + Fib(n-2)   for n>2;   Fib(1) = Fib(2) = 1   (1, 1, 3, 3, 5, 8, 13...)

### Recursion

An algorithm is **recursive** if it calls itself to do part of its work. It has 2 parts: **base case** (simple input that can be solved without a recursive call) and recursive part (one or more recursive calls where, the more calls, the "closer" the parameters are to the base case). The base case prevents recursion from going on forever.

Start by writing the base cases, and then solve the problem by combining the results of one or more smaller subproblems. Don't worry about how the recursive call solves the subproblem, but simply accept that it will solve it correctly, and use this result to in turn correctly solve the original problem. Train yourself to stop analysing the recursive process beyond the recursive call. Just worry about base cases and how to recombine subproblems.

- __Factorial__:

```
long fact(int n) {
  if(n <= 1) return 1;
  return n * fact(n-1);
}
```

- __Towers of Hanoi puzzle__: There're 3 poles and n rings. All rings start on pole 1. Each ring has a different size, and are stacked in decreasing size order (largest ring at the bottom). The problem is to move the rings from pole 1 to pole 3 in a series of steps. At each step the top ring on a pole is moved to another pole. A ring can never be moved on top of a smaller ring. How to solve this?

  - We first need to move the largest (bottom) ring to pole 3, which requires all the other rings (n-1) to be stacked up in order on pole 2.
  - Don't worry about how subproblem is solved. Rely on the algorithm to do this work for you.
  - Provide a base case: what to do if there's only one ring.
  - The recursive call can only be used to solve a smaller problem, and then only one of the proper form.

```
void TOH(int n, Pole start, Pole goal, Pole temp)
{
  if(n == 0) return;
  TOH(n-1, start, temp, goal);      // 1. Move n-1 disks from start to temp
  move(start, goal);      // 2. Move largest disk to goal
  TOH(n-1, temp, goal, start);      // 2. Move n-1 disks from temp to goal
}
```

Recursive algorithms usually don't yield the most efficient solution (function calls are more expensive than other alternatives such as a while-loop). Many data structures are naturally recursive (they have self-similar parts, like in tree structures). Many searching and sorting algorithms are based on a divide-and-conquer strategy (break a problem into smaller similar subproblems, solve them, and combine the solutions), often implemented using recursion.

### Mathematical proof techniques

Solving a **problem** has 2 parts: **investigation** (engaging the problem and working through until you find a solution) and **argument** (describe the solution clearly and succinctly). Three commonly used proof techniques are: direct proof (deduction), proof by contradiction, and proof by mathematical induction.

#### Direct proof

It's a logical explanation, a deduction, an argument in terms of logic (P → Q). Example: if we want to prove that P and Q are equivalent, we can first prove P → Q and then Q → P. In some domain, proofs are a series of state changes from a start state to an end state (like symbolic manipulations to solve integration problems, or some geometry proofs).

#### Proof by contradiction

We assume that the theorem is false. Then we find a logical contradiction stemming from this assumption. If there's a contradiction, we have to recognize that theorem is not false, i.e. it's true.

Example: _There is no largest integer_. We assume that B is the largest integer. However, if we consider C = B + 1, where C is an integer, we find a contradiction because C > B, so B is not the largest integer. Thus, the theorem is correct.

A related proof technique is proving the contrapositive. We can prove that P→Q by proving (not Q)→(not P).

#### Proof by mathematical induction

We assume that a theorem holds for certain parameter values (induction hypothesis). If this is demonstrated, then it must hold for any other value.

Let T be a theorem to prove, and express it in terms of a positive integer parameter n. Mathematical induction states that T is true for any value of parameter n (for n ≥ c, where c is some constant) if the following 2 conditions are true:

1. **Base case**: T holds for n = c.
2. **Induction step**: Two options:
  - __Induction step__: If T holds for n-1, the T holds for n.
  - __Strong induction step__: If T holds for all k, c ≤ k ≤ n, then T holds for n.

Recursion and induction have similarities. Both are anchored on one or more base cases. Recursive function rely on calling itself to solve subproblems, while induction proofs rely on the induction hypothesis to prove the theorem. The induction hypothesis is true if and only if the theorem itself is true. Using the induction hypothesis to do work is exactly the same as using a recursive call to do work.

### Estimation

Estimation is no substitute for rigorous, detailed analysis of a problem, but it can serve to indicate when a rigorous analysis is warranted: If the initial estimate indicates that the solution is unworkable, then further analysis is probably unnecessary. Estimation steps:

1. Determine major parameters that affect the problem.
2. Derive an equation that relates the parameters to the problem.
3. Select values for the parameters and apply the equation to yield an estimated solution.

A good way to reassure yourself that the estimate is reasonable is to do it in 2 different ways. If both approaches (independently) give similar answers, then this should build confidence in the estimate.

When calculating, ensure that your units match (don't add feet and pounds). The output of a calculation is only as good as its input. Before calculating, you should decide on acceptable error bounds (one order of magnitude, a factor of two, 25%...) and not try to get a more precise estimate than necessary for your purpose.


## Algorithm Analysis

### Introduction

Comparing two algorithms empirically (implementing them as computer programs, running them on a range of inputs, and measuring how much resources each uses) is often unsatisfactory because:

- Programming and testing two algorithms when you want to keep only one involve additional effort.
- One algorithm could be "better written" than the other, representing badly the relative quality of the underlying algorithms.
- The choice of test cases might unfairly favour one algorithm.
- Even the better algorithm could not fall within your resource budget, forcing to begin the entire process again. Or maybe no implementation can possibly be within budget.

**Asymptotic analysis**: Estimating technique that measures the efficiency of an algorithm, or its implementation, as the input size becomes large. This analysis is useful for determining if a particular algorithm is worth considering for implementation.

The main resources for a program are its running **time** and the **space** required (main memory and disk space). Typically you analyse the time required for an algorithm, and the space required for a data structure.

Many factors affect the running time of a program such as CPU speed, bus speed, peripheral hardware speed, users competition for computer or network resources, programming language, compiler, coding efficiency, etc. Yet, none of these factors address the differences between two algorithms or data structures. When estimating an algorithm's performance, we have to consider the number of **basic operations** required to process an input of a certain **size**. The time to complete such operations must not depend on the particular values of its operands (correct: adding or comparing 2 integers) (wrong: summing contents of an array containing n integers).

**Growth rate**: Rate at which the cost of the algorithm grows as the size of its input grows. It can be __linear__ (as n grows, the running time of the algorithm grows in the same proportion), __quadratic__ (the running time equation has a highest-order term containing a factor of n<sup>2</sup>), __exponential__ (like 2<sup>n</sup>, because n appears in the exponent) (n! also grows exponentially), etc.

<br>![growth rates](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/topics/computer_science/synthesis/growth_rates_1.png)

<br>![growth rates](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/topics/computer_science/synthesis/growth_rates_2.png)

### Best, worst, and average cases

For some algorithms, different inputs of a given size require different amounts of time. Consider the problem of searching an array containing n elements to find one with value K:

- A **sequential search** algorithm begins at the first position and looks at each value in turn until K is found, and it stops when K is found.
  - __Best case__: The first integer in the array is K. Running time is short because only one element is examined.
  - __Worst case__: The last position in the array is K. Running time is relatively long because n elements are examined.
  - __Average case__: We expect the algorithm to examine ~n/2 values on average (if it runs many times for different n-size arrays or search for different K values).
- A **largest-value sequential search** algorithm however examines every array value.
  - __Best case__ = __Worst case__ = __Average case__ = n (all elements are always examined)

The **best case** is normally not interesting because it rarely happens and it too optimistic. It's not representative of the behavior of the algorithm, unless the best case has high probability of occurring.

The **worst case** is interesting because the algorithm must perform at least that well. It's especially important for real-time applications.  

The **average case** shows the typical behavior of the algorithm in inputs of size n. It's useful when we wish to aggregate the cost of running the program many times on many different inputs. However, average-case analysis is not always possible: it requires to understand how the inputs and their costs are distributed with respect to the set of all possible inputs to the program (example: the sequential search algorithm on average doesn't examine n/2 array values if K is not equally likely to appear in any position in the array). Data distribution have significant effect on many search algorithm (search based on hashing, search trees...). Unusual data distributions can also be used to advantage.

### Faster computer or faster algorithm

If an algorithm has a too long running time, getting a faster computer could make the algorithm run faster. However, most people who get a faster computer don't run the same problem faster, but they run a bigger problem.

If your algorithm's growth rate is linear, then you can use a 10 times faster machine to solve a 10 times bigger problem (example: to examine 10.000 records in the old machine would take the same time as 100.000 records in the new one). Algorithms with bigger growth rate (example: n<sup>2</sup>) get less improvement. The bigger the algorithm's growth rate, the less relative improvement (speedup) it can get from a faster machine. Thus, as computers get faster, the disparity in problem sizes becomes ever greater. Also, the slower growth rate of an algorithm, the greater benefit it gets from a new computer in terms of larger problem size that it can run in a certain time. 

<br>![growth rates](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/topics/computer_science/synthesis/improvements.png)

Operations that an algorithm can do in a 10 times faster machine:

- Linear (cn): n·10
- Logarithmic (log n): More than quadratic algorithms, but less than linear ones.
- Quadratic (n<sup>2</sup>): n·√10 ≈ n·3.16
- Exponential (2<sup>n</sup>): n + log<sub>2</sub>10 = n + 3

Note that constant factors never affect the relative improvement in problem size gained by a faster computer.

For an input of size n = 1023, an algorithm with running time T(n) = n<sup>2</sup> requires 1.048.576 (1024 x 1024) time steps, but a running time T(n) = n log n only requires 10.240 (1024 x 10).

### Asymptotic analysis

The time curve 10n is crossed by 2n<sup>2</sup> at n=5. For 20n, it's crossed at n=10. Changing the constant factor only shift where the 2 curves cross, but the two curves always cross at some point despite the constant factor. That's why we usually ignore the constants when estimating the growth rate for the running time or other resource requirement of an algorithm (asymptotic analysis). 

**Asymptotic algorithm analysis**: Study of an algorithm as the input size gets big or reaches a limit (Calculus limit). It provides a simplified model (estimation) of the algorithm resource consumption (running time or other resource). It helps understand the behaviour of an algorithm.

It's not always reasonable to ignore constants. The constant can have a significant effect when comparing algorithms meant to run on small values of n, or when the constants between the two algorithms differ by a factor of 1000 or more.

**Upper bounds** (O): __Highest growth rate that the algorithm can have__. It's represented with **big-Oh** notation. Measure of an algorithm's growth rate. It works for any resource (usually time) of some particular class (best, average, or worst inputs). Example: if the upper bound for an algorithm's growth rate for, say, the worst case, is f(n), then this algorithm is in O(f(n)) in the worst case (example: n<sup>2</sup> is in O(n<sup>2</sup> in the worst case). 

- Mathematical definition: Consider an algorithm, its true running time (T(n), a non-negatively valued function) and some expression for the upper bound (f(n)). T(n) is in set O(f(n)) if there exist 2 possible constants c and n<sub>0</sub> such that T(n) ≤ cf(n) for all n > n<sub>0</sub>. Constant n<sub>0</sub> (it's usually small) is the smallest value of n for which the claim of an upper bound holds true. The value of c is irrelevant.
- Another definition: For all inputs of the type in question (such as the worst case for all inputs of size n) that are large enough (i.e., n > n<sub>0</sub>), the algorithm always executes in less than cf(n) steps for some constant c.

Example 1: Consider the sequential search algorithm for finding a specified value in an array of integers. Visiting and examining one value in the array requires c<sub>s</sub> steps. 

- If the value we search for has equal probability to appearing in any position in the array, then in the **average case** **T(n) = c<sub>s</sub>n/2**. 
- For all values n > 1, c<sub>s</sub>n/2 ≤ c<sub>s</sub>n. 
- Thus, T(n) is in **O(n)** for n<sub>0</sub>=1 and c=c<sub>s</sub>.

Example 2: For a particular algorithm, **T(n) = c<sub>1</sub>n<sup>2</sup> + c<sub>2</sub>n** in the average case (c<sub>1</sub> and c<sub>2</sub> are positive numbers). 

- Then, c<sub>1</sub>n<sup>2</sup> + c<sub>2</sub>n ≤ c<sub>1</sub>n<sup>2</sup> + c<sub>2</sub>n<sup>2</sup> ≤ (c<sub>1</sub> + c<sub>2</sub>)n<sup>2</sup> for all n > 1. 
- So, T(n) ≤ cn<sup>2</sup> for c = c<sub>1</sub> + c<sub>2</sub>, and n<sub>0</sub>=1. 
- Therefore, T(n) is in **O(n<sup>2</sup>)** by the second definition.

Example 3: Assume **T(n) = c** for best, worst, and average cases.

- We can say that T(n) is in O(c). 
- However, it's traditional to say that an algorithm whose running time has a constant upper bound is in **O(1)**.

An algorithm has a growth rate for each case (best, average, worst). Any statement about the upper bound of an algorithm must be in the context of some class of inputs of size n. We say that "this algorithm has an upper bound to its growth rate of n<sup>2</sup> in the average case".

Saying only that something is in O(f(n)) only says how bad things can be. But perhaps things are not nearly so bad. Because sequential search is in O(n) in the worst case, it's also true that it is in O(n<sup>2</sup>). O(n) is in O(n<sup>2</sup>), but O(n<sup>2</sup>) is not it O(n). However, we always seek to define the running time of an algorithm with the tightest (lowest) possible upper bound. So we prefer to say that sequential search is in O(n).

Big-Oh notation describes an upper bound (greatest amount of a resource, usually time, required by an algorithm for some class of inputs of size n, typically the worst, average, or best such inputs).

**Lower bounds** (Ω): __Least amount of a resource (usually time) that an algorithm needs for some class of input__. It's represented with **big-Omega** notation. Measure of an algorithm's growth rate. It works for any resource (usually time) of some particular class (best, average, or worst inputs).

- Mathematical definition: For T(n) a non-negatively valued function, T(n) is in set Ω(g(n)) if there exist 2 positive constants c and n<sub>0</sub> such that T(n) ≥ cg(n) for all n > n<sub>0</sub>.

Example 1: Assume T(n) = c<sub>1</sub>n<sup>2</sup> + c<sub>2</sub>n for c<sub>1</sub> and c<sub>2</sub> > 0.

- Then, c<sub>1</sub>n<sup>2</sup> + c<sub>2</sub>n ≥ c<sub>1</sub>n<sup>2</sup> for all n > 1
- So, T(n) ≥ cn<sup>2</sup> for c = c<sub>1</sub> and n<sub>0</sub> = 1
- Therefore, T(n) is Ω(n<sup>2</sup>) by the definition
- Note that it's also in Ω(n), but wish to get the tightest (largest) bound possible, so we prefer Ω(n<sup>2</sup>)

Example 2: Recall the sequential search algorithm to find a value K in an array of integers.

- Both in the average and worst case we must examine at least cn values (c=1/2 in the average case, c=1 in the worst case)
- Thus, in both cases this algorithm is Ω(n)

**Big-Theta** notation (Θ): Used to indicate that the upper and lower bounds are the same within a constant factor. An algorithm is in Θ(h(n)) if it's in O(h(n)) and Ω(h(n)). Given an algebraic equation describing the time requirement for an algorithm, the upper and lower bounds always meet, because an equation represents a perfect analysis for the algorithm. Almost always we can give a Θ analysis, but not always. Though big-Oh notation is used very often, it's generally better to use Θ notation instead if we have enough knowledge about an algorithm.

Example: The sequential search algorithm is both O(n) and Ω(n) in the average case, so it's Θ(n) in the average case.

**Simplifying rules**: Once you determine the running-time equation for an algorithm, it's really simple to derive the big-Oh, Ω, and Θ expressions. Just follow these rules (appliable to O, Ω, and Θ):

1. If f(n) is in O(g(n)) and g(n) is in O(h(n)), then f(n) is in O(h(n)).
2. If f(n) is in O(kg(n)) for any constant k > 0, then f(n) is in O(g(n)).
3. If f<sub>1</sub>(n) is in O(g<sub>1</sub>(n)) and f<sub>2</sub>(n) is in O(g<sub>2</sub>(n)):
  - Then f<sub>1</sub>(n) + f<sub>2</sub>(n) is in O(max(g<sub>1</sub>(n), g<sub>2</sub>(n))).
  - Then f<sub>1</sub>(n)f<sub>2</sub>(n) is in O(g<sub>1</sub>(n)g<sub>2</sub>(n)).

That is to say:

1. If g(n) is an upper bound for the cost function, then any upper bound for g(n) is also an upper bound for the cost function.
2. Multiplicative constants can be ignored.
3. Given 2 parts of a program:
  3.1. If run in sequence, consider only the more expensive part.
  3.2. If some action is repeated a number of times (simple loop), each repetition having the same cost, then [total cost] = [cost of the action] x [number of times the action takes place].

Thus, to determine the asymptotic growth rate for a cost function, we can ignore all constants and all lower-order terms. Higher-order terms soon swamp the lower-order terms in their contribution to the total cost as n becomes larger.

Example: For T(n) = 3n<sup>4</sup> + 5n<sup>2</sup>, then T(n) is in O(n<sup>4</sup>).

**Classifying functions**: Given functions f(n) and g(n) whose growth rates are expressed as algebraic equations, we can determine which one grows faster by taking the limit of both functions as n grows towards infinity: **lim<sub>n→∞</sub>(f(n)/g(n))**. If the limit goes to

- **∞**, then f(n) is in Ω(g(n)) because f(n) grows faster.
- **0**, then f(n) is in O(g(n)) because g(n) grows faster.
- **some constant ≠ 0**, then f(n) = Θ(g(n)) because both grow at the same rate.

### Calculating running time of a program

```
a = b
```

It's **Θ(1)** because it takes constant time (c).

```
sum = 0;
for(i=1; i<=n; i++)
  sum += n;
```

Θ(c<sub>1</sub> + n·c<sub>2</sub>) → **Θ(n)**

```
sum = 0;
for (i=1; i<=n; i++)
  for(j=1; j<=i; j++)
    sum++;

for(k=0; k<n; k++)
  A[k] = k;
```

Θ(c<sub>1</sub> + c<sub>2</sub>n<sup>2</sup> + c<sub>3</sub>n = n<sup>2</sup>) → **Θ(n<sup>2</sup>)**

- The first loop runs n·i times, where i changes each time (1, 2, 3...). We know this is equal to ∑<sup>n</sup><sub>i=1</sub> = n(n+1)/2, which is Θ(n<sup>2</sup>).

```
sum1 = 0;
for(i=1; i<=n; i++)
  for(j=1; j<=n; j++)
    sum1++;

sum2 = 0;
for(i=1; i<=n; i++)
  for(j=1; j<=i; j++)
    sum2++;
```

Θ(c<sub>1</sub> + n<sup>2</sup>c<sub>2</sub> + c<sub>3</sub> + n<sup>2</sup>c<sub>4</sub>) → **Θ(n<sup>2</sup>)**

```
sum1 = 0;
for(k=1; k<=n; k*=2)
  for(j=1; j<=n; j++)
    sum1++;

sum2 = 0;
for(k=1; k<=n; k*=2)
  for(j=1; j<=k; j++)
    sum2++;
```

Θ(c<sub>1</sub> + (log n + 1)nc<sub>2</sub> + c<sub>3</sub> + (log n + 1)kn<sup>2</sup>c<sub>4</sub>) → Θ(n log n + n) → **Θ(n log n)**

- k = 2<sup>i</sup> (k doubles each time)
- First loop total cost  = ∑<sup>log n</sup><sub>i=0</sub>n → Θ(n log n)
- Second loop total cost = ∑<sup>log n</sup><sub>i=0</sub>2<sup>i</sup> → Θ(n)

```
while {…}
```

`while` loops are analysed similarly to a `for` loop.

```
if(…) {…}
else {…}
```

The cost of an `if` statement in the worst case is the greater of the costs for the `then` and `else` clauses. This is also true for the average case, assuming that the size of n does not affect the probability of executing one of the clauses (which is rare).

```
switch(a)
{
case 0:
  break;
case 2:
  break;
default:
  break;
}
```

The cost of a `switch` statement in the worst-case is that of the most expensive branch.

In rare situations the probability for executing the various branches of an `if` or `switch` statement are functions of the input size (example: given an input n, the `then` clause of an `if` statement might be executed with probability 1/n, like when executing it only for the smallest of n values). In these cases the cost has to be calculated using the **amortized analysis** technique.

```
myFunction(a, b);
```

For **subroutines**, simply add the cost of executing the subroutine.

```
int fact(int n)
{
    if (n == 0 || n == 1) return 1;
    return n * fact(n - 1);
}
```

For a **recursive** subroutine, it's complicated to determine its running-time. It's best expressed by a **recurrence relation**. Example: The running-time for the recursive factorial function `fact` can be expressed as: $T(n) = T(n-1) + 1$ for $n > 1; (1) = 0$. The closed-form solution for this relation is Θ(n).

```
int find(char* array, int size, char target)
{
  for(int i=0; i<size; i++)
    if(*array ==  target)
      return i;
  return size;
}
```

For **sequential search** on an array (sorted or not) where the value to search is equally likely to appear in any location, it's Θ(n) in both average and worst cases.

```
int binary(int A[], int n, int K)
{
  int l = -1, r = n, m;
  while(l+1 != r)
  {
    m = (l+r)/2;
    if(K < A[m]) r = m;
    if(K == A[m]) return m;
    if(K > A[m]) l = m;
  }
  return n;
}
```

For **binary search** on an sorted array, we can model the running-time as a recurrence relation and then find the closed-form solution (worst-case):

- $T(n) = T(n/2) + 1   for n > 1;   T(1) = 1$
- $T(n) = log n$ → Θ(log n)

**Binary search**: Given a sorted array (values are stored in order from lowest to highest), we want to find the value K. We start examining the middle position (`mid`) which has value k<sub>mid</sub>. If k<sub>mid</sub> = K, we found it. If k<sub>mid</sub> > K, then K is before `mid`. If k<sub>mid</sub> < K, then K is after `mid`. This way we can eliminate half of the positions from further consideration. Next, we look at the middle position in the part of the array where K may exist and repeat the process, eliminating half of the remaining positions. This process repeats until either the desired value is found, or there are no positions remaining that might contain K.

The constant factor of a binary search is greater than the one of a sequential search (calculating the next position is more expensive than just incrementing the current position). And the requirement of the array values to be ordered increase the cost of inserting new elements. 

### Problem analysis

Algorithm analysis techniques can be used not only to analyse algorithms but also to analyse the cost of a problem.

The **upper bound for a problem** cannot be worse than the upper bound for the best algorithm that we know for that problem. A problem is in O(f(n)) if the best known algorithm that solves it is in O(f(n)).

The **lower bound for a problem** is more complicated. A problem is in Ω(f(n)) if every algorithm that solves the problem is in Ω(f(n)), even algorithms we haven't thought of.

Example:

- What is the least possible cost for any sorting algorithm in the worst case? Since it must at least look at every element in the input (just to determine that the input is truly sorted), then any sorting algorithm must take at least $cn$ time, which leads to Ω(n) lower bound.
- Some sorting algorithms (Bubble sort, Insertion sort...) have a running-time in O(n<sup>2</sup>) in the worst case. So we can say that the problem of sorting has an upper bound in O(n<sup>2</sup>). How do we close the gap between Ω(n) and O(n<sup>2</sup>)?
- There're some sorting algorithms with O(n log n) running time for the worst case, which narrows the gap. Now we have a lower bound in Ω(n) and upper bound in O(n log n).
- Is there a faster algorithm? No. There's a proof that any sorting algorithm must have running time in Ω(n log n) in the worst case. It means that no sorting algorithm can possibly run faster than $cn log n$ for the worst-case input of size n. Thus, the problem of sorting is Θ(n log n) in the worst case, because upper and lower bounds have met.

knowing the lower bound for a problem doesn't give you a good algorithm, but it helps to know when to stop looking. If the lower bound for the problem matches the upper bound for the algorithm (within a constant factor), then we know that we can find an algorithm that is better only by a constant factor.

### Common misunderstandings

For most algorithms, it's easy to recognize its true growth rate. Given complete knowledge about a cost function, the **upper and lower bound** for it are always the same (indicated with Θ-notation), which is usually the case for simple algorithms. Distinguishing upper and a lower bound is only worthwhile when we have incomplete knowledge about the thing being measured. 

The **best, worst, or average cases** each give us a concrete input instance (or set of instances) that we can apply to an algorithm description to get a cost measure. The **upper and lower bounds** describe our understanding of the growth rate for that cost measure. To define the **growth rate** for an algorithm or problem, we need to determine what we are measuring (best, worst, or average case) and our description for what we know about the growth rate of that cost measure (big-Oh, Ω, or Θ).

The upper bound for an algorithm is not the same as the worst case for that algorithm for a given input of size n. What is being bounded is not the cost, but rather the growth rate for the cost. The growth rate applies to the change in cost as a change in input size occurs.

It's incorrect to think that the best case for an algorithm occurs when the input size is as small as possible, or that the worst case occurs when the input size is as large as possible. The best- and worse-case instances exist for each possible size of input. That is, for all inputs of a given size, say i, one or more of the inputs of size i is the best and one or more of the inputs of size i is the worst. Often, but not always, we can characterize the best input case for an arbitrary size, and we can characterize the worst input case for an arbitrary size. Ideally, we can determine the growth rate for the characterized best, worst, and average cases as the input size grows.

Example 1: What is the growth rate of the best case for sequential search? The best case occurs when the value we look for appears in the first position in the array, regardless of the array size (n), and its cost is 1.

Example 2:

- Imagine a graph showing the cost (y axis) of finding the maximum value among n values (x axis), as n grows. It would be an increasing diagonal line.
- Imagine the graph showing the cost for each instance of the problem of finding the maximum value among 20 elements. The first x axis position correspond to having the maximum value in the first array position, the second x axis position correspond to having it in the second array position, and so on. The cost is always 20, so the graph is a horizontal line with value 20.
- For the problem of finding a value doing sequential search, imagine the graph showing all the problem instances of size 20. The first problem instance has the searched value in first position (cost 1), the second problem instance has it in second position (cost 2), and so on. The graph is an increasing diagonal line.
- Consider the cost of sequential search as the array size n gets bigger. The graph's shape will depend on whether we are considering the best case cost (horizontal line with value 1), worst case cost (diagonal with value i for x=i), or average cost (diagonal with value i/2 for x=i). We must always say that a function f(n) is in O(g(n)) in the best, average, or worst case. 

### Multiple parameters

Sometimes the analysis of an algorithm requires multiple parameters to describe the cost. Consider an image (two-dimensional array), where each pixel has a value in the range 0 to C-1. Get the number of pixels of each colour, and then sort the resulting list of number of pixels (C is the number of colours, P is the number of pixels).

```
int count[C];
for(i=0; i<C; i++)  // initialize count
  count[i] = 0;
for(i=0; i<P; i++)  // count pixel values
  count[value(i)]++;
sort(count, C);
```

The time is Θ(C + P + C log C) → **Θ(P + C log C)**

### Space bounds

Beside time, space is another resource commonly considered. The amount of available disk space or main memory can be significant constraints. The analysis techniques used to measure space requirements are similar to those to measure time requirements. However, while time requirements are normally measured for an algorithm that manipulates a particular data structure, space requirements are normally determined for the data structure itself. The concepts of asymptotic analysis for growth rates on input size apply completely to measuring space requirements. 

Example 1: Consider an array of n integers. Each integer requires c bytes, so the array requires cn bytes. Thus, the space requirement is Θ(n).

Example 2: Consider an array of size n x n. Each row represents the friends of an individual. Each column represent an individual with friends. Total size: Θ(n<sup>2</sup>)

A data structure’s primary purpose is to store data in a way that allows efficient access to those data. Providing efficient access may require to add some **overhead** (information stored in addition to the actual data values), such as a pointer to the next node in a linked list. Overhead should be kept to a minimum while allowing maximum access. 

**Space/time tradeoff principle**: One can often achieve a reduction in time if one is willing to sacrifice space or vice versa. Typically, these changes in space and time are both by a constant factor. Example: We can reduce storage requirements by encoding information (packing), but decoding it (unpacking) will require additional time. Or we can include pre-store results to allow faster running time at the expense of greater storage requirements.

- **Lookup table**: It pre-stores the value of a function that would otherwise be computed each time it's needed.

**Disk-based space/time tradeoff**: Generally, the smaller you make your disk storage requirements, the faster your program will run. The time to read information from disk is enormous compared to computation time. 

### Speeding up your programs

**Algorithm changing**: Try to change algorithms to reduce its growth rate. It's not unusual that a problem whose obvious solution requires Θ(n<sup>2</sup>) time also has a solution requiring Θ(n log n) time (sorting, searching...).

**Code tuning**: Art of hand-optimizing a program to run faster or require less storage. While not nearly so important as "algorithm changing", it can also lead to dramatic improvements in running time. For many programs, it can reduce running time by a factor of 10, or storage requirements by 2 or more. Some recommendations:

- Most statements in a program don't have much effect on the running time of the program. Normally, just a few key subroutines, possibly even key lines of code within them, account for most of the running time. Focus on those parts that have the most impact (there's little point to cutting in half the running time of a subroutine that accounts for only 1% of total running time).

- Gather good timing statistics so you can tell where to invest your effort. Many compilers and OSs include profilers and other tools for gathering information about space and time use.

- Some work can be avoided. Example: maybe testing for a condition let us skip some work (check that the cost of the test doesn't exceed the amount of work saved). 

- Avoid tricks that make the program unreadable. Most code tuning is simply cleaning up a carelessly written program, not taking a clear program and adding tricks. Modern compilers can make extremely good __optimizations of expressions__ (rearrangement of arithmetic or logical expressions to run more efficiently), so don't make them difficult to do so. It's hard to do better than the compiler. Always check that your "optimizations" really do improve the program by running the program before and after the change on a suitable benchmark set of input.

- The greatest time and space improvements come from a better data structure or algorithm. First tune the algorithm, then tune the code.

### Empirical analysis

**Asymptotic analysis** is an analytic tool for modelling the key aspects of an algorithm to determine its growth rate as the input size grows. It has limitations:

- Effects at small problem size
- Determining finer distinctions between algorithms with same growth rate
- Difficulty of doing mathematical modelling for more complex problems

**Empirical analysis**: Alternative to asymptotic analysis. Different approaches:

- Run two competitors and see which performs better. However, comparative timing is difficult since often it's subject to experimental errors arising from uncontrolled factors (system load, language, compiler, ...). You can also be biased in favour of one program (one may receive more code-tuning effort...). If the running time for 2 programs differ by a constant factor regardless of input size (same growth rates), then different code tuning might account the any run-time difference.

**Simulation**: Model the problem with a computer program and then run it to get a result. Its purpose it to perform analysis that might otherwise be too difficult (example: analysing the space cost in order to balance time cost versus space size).


## Lists, Stacks, Queues

### Lists

#### Abstract list

**Sequence** types:
- **List**
  - **Array**: Static, Dynamic
  - **Linked-list**: Single, Double, Xor
- **Stack**
- **Queue**

**List** (or sequence): Finite, ordered sequence of data items (<a<sub>0</sub>, a<sub>1</sub>, ... a<sub>n-1</sub>>). Each data item is an **element**. "Ordered" here means that each element has a **position** in the list (first, second...), not that it's sorted by value. Each element has a data type. Usually, the same for all elements. The operations defined as part of the list ADT don't depend on the elemental data type. An **empty** list contains no elements (<>). The **length** of the list is the number of elements currently stored. The beginning is the **head**, the end is the **tail**. **Sorted lists** have their elements positioned in ascending order of value, **unsorted lists** have no particular relationship between element values and their positions. Standard approaches to implementing a list: **Array-based list** and **Linked list**.

**Abstract class**: Class whose member functions are pure virtual (`=0`). It doesn't define operations, just declare them. 

Steps for implementing a list:

1. Select the base operations it must support (random access, access next/previous, random remove/insert, resize after remove/insert, clear...).
2. Define the ADT for a list object in terms of a set of operations on that object (abstract class).

```
template <typename E> class List
{
public:
  List();
  List(const List&);   // copy constructor
  virtual ~List();

  virtual T& operator[](size_t i) const = 0;   // Subscript
  //void operator=(const List&);   // Copy-assignment (cannot be virtual, define it in subclasses)

  virtual void append(const E& item) = 0;
  virtual void insert(const E& item) = 0;
  virtual E remove() = 0;
  virtual void clear() = 0;

  virtual int length() const = 0;

  virtual int currPos() const = 0;
  virtual const E& getValue() const = 0;
  virtual void moveToStart() = 0;
  virtual void moveToEnd() = 0;
  virtual void moveToPos(int pos) = 0;
  virtual void prev() = 0;
  virtual void next() = 0;
};
```

Supported features:

- **Copy constructor**
- Operators: **Subscript operator** (`[]`) and **overloaded assignment operator** (`=` cannot be virtual, so it's directly defined by each subclass).
- **`append`**: Insert element at the end of the list.
- **`clear`**: Remove all elements from the list.
- **Current position** (`curr`): It's where any action takes place (`insert`, `remove`, `getValue`, `currPos`). It can be modified (`moveToStart`, `moveToEnd`, `moveToPos`, `next`, `prev`). Method `currPos` returns current position (range [0, n]), `getValue` returns the element (error/exception at n), `insert` introduces a new element, `remove` removes an element (error/exception at n).
- **`length`**: Number of active elements.

```
// Return true if K is in the list, false otherwise
bool find(List<int>& L, int K)
{
  int it;
  for(L.moveToStart(); L.currPos() < L.length(); L.next()) // iterate the list
  {
    it = L.getValue();
    if(K == it) return true;
  }
  return false;
}
```

#### Array-based list

Elements are stored in contiguous cells of an array. Random access and inserting/removing elements at the tail take Θ(1) time. However, inserting at position i (n-1 elements are shifted) and removing at position i (n-i-1 elements are shifted) take Θ(n) time. In the average case, insertion/removal requires moving half of the elements, which is Θ(n).

General member variables: `array` (elements storage), `size` (number of active elements), `capacity` (max. size), `curr` (current position).

Note: System free-store operations (`new`, `delete`) can be expensive. The cost of allocating/deleting an array depends on the element's type, which determines wether the `new`/`delete` operator must call a constructor/destructor on each one.

- **Static array** (SA): The maximum size (capacity) cannot change. Construction, assignment (`=`), and operations `insert` and `remove` take O(n) time.

- **Dynamic array** (like `std::vector`) (DA): Array-based list with dynamic size, not fixed size. The size can grow and shrink (resizing) depending on the number of elements stored (requires to copy contents). One resizing method is: double the size when full, cut in half when one quarter full. Operations have same time cost as in SA, but sometimes they are more expensive (when resizing) by a constant factor. To analyse the overall time cost of an operation we need the __amortized analysis technique__.

#### Linked list

Set of nodes linked to one another one-by-one. Traditionally implemented using pointers. New elements are allocated dynamically (dynamic memory allocation). Nodes are objects containing one element and a pointer to the next node (for singly linked list), and maybe another pointer to the previous node (for double linked list). Whether the list implementation is single or double should be hidden from the user. The node class should be a private class of the class using it (linked list, stack, queue...), not visible to the rest of the program.

General member variables: `head` (first node), `tail` (last node), `curr` (node preceding the current node), `count` (number of nodes), `freelist` (object pool for unused nodes).

- **Singly linked list** (one-way list) (SLL):  Each node has a single pointer to the next node. `curr` points to the element preceding the current element (required for inserting a new element after `curr`). It uses an additional header node (pointed by `head`), which is not considered an element of the list so its value is ignored (avoids special cases for `insert` and `remove`). Construction, assignment (`=`), random access (`[]`), and operations `insert`, `remove`, `currPos`, `moveToPos`, and `prev` take O(n) time.

- **Double linked-list** (DLL): Each node has a pointer to the previous and the next node. Easier to implement and debug. It has twice the overhead of a SLL. It uses a header node (`head`) and tailer node (`tail`), which are not elements of the list, so their values are ignored (avoids special cases for `insert`, `append`, and `remove` when the list is empty, or when we insert at the head or tail of the list). `tail` node cannot be `curr`. For convention, `curr` points to the element preceding the current element (though it could now point directly to the node containing the current element, since we now have access to previous node). Operations have same time cost as in SLL, except `prev` now takes O(1).

- **XOR linked-list** (XLL): Like a DLL, but using the same space as a SLL, though complicates implementation and is slower by constant time (space-time tradeoff). Member `currPrev` is the node preceding `curr` (allows access `curr.next` in O(1) time). Operations have same time cost as in DLL, but more expensive by a constant time. Space-saving technique: if `c=a+b`, then `b = c-a` and `a=c-b`. Alternatively: if `npx = prev XOR next`, then `prev = npx XOR next` and `next = npx XOR prev`. Thus, knowing one link node let us get the other. And knowing the pointer to the first node and one of its link fields, allows access to all of the remaining nodes.

**Nodes**: Generally contains `element` and link node/s (pointer/s to other nodes).

- **Singly nodes**: For SLL. Contains pointer `next`.
- **Double nodes**: For DLL. Contains pointers `next` and `prev`.
- **XOR nodes**: For XLL. Contains `npx` (= `prev` XOR `next`). Getting one link node requires knowing the other (`next` = `npx` XOR `prev`) (`prev` = `npx` XOR `next`).

**Freelists**: Free-store management operators `new` and `delete` are relatively expensive and inefficient. A freelist helps by holding the nodes that aren't currently being used. When a node is deleted from a linked list, it's placed at the head of the freelist. When a new node has to be added to a linked list, the freelist is checked for an available node to use. If freelist is empty, the `new` operator is called. It will never grow larger than the largest size yet reached by the linked list.

- You can overload `new` and `delete` operators (however, they are implicitly static) or implement two new operators.
- Instead of creating nodes one by one with `new`, it's faster to create many of them at the same time and load them onto the freelist at once.
- The freelist can be declared `static`, so we will have a single freelist for all `Link` nodes of a given type. However, I prefer that each list has its own freelist (otherwise, freelist can contain too many nodes if some lists are destroyed, and there's no easy way to know when to delete its content).
- Regular freelists can grow to the largest size yet reached by the linked list, which can lead to too big freelists with many unused nodes. Maybe a regular size adjustment could reduce overhead while still having a helpful freelist.

#### Lists comparison

- **Static array**:
  - Random access: Fast (Θ(1) time).
  - Insertion/removal: Slow (Θ(n) time in average and worst cases).
  - Size: Fixed.
  - Size overhead: If array is not fully filled, there's an amount of space reserved but not used. It requires Ω(n) space or more. Generally it's more space efficient when the array is close to full, and when the user knows in advance approximately how large the list will become.
  - Element overhead: No wasted space for an individual element.

- **Dynamic array**: Similar to SA, but with dynamic size.

- **Singly/Double/XOR linked-list**:
  - Random access: Slow (Θ(n) time in average and worst cases).
  - Insertion/removal: Fast (Θ(1) time).
  - Size: Dynamic.
  - Size overhead:
    - Without freelist: Only needs space for the objects actually on the list. It requires Θ(n) space. Generally it's more space efficient when few elements are in the list, and when the number of elements vary widely or is unknown.
    - With freelist: Similar to SA.
  - Element overhead: Each element requires an extra pointer/s in each node.

**Formula** for determining which list implementation is more space efficient.

- Given:
  - `n`: Number of elements in the list
  - `P`: Size of a pointer (bytes)
  - `E`: Size of a data element (bytes)
  - `D`: Maximum number of list elements that can be stored in the array

- The smaller of the following expressions for a given value n determines the more space-efficient implementation for n elements:
  - `D·E`: Amount of space required for the array-based list
  - `n(P+E)`: Amount of space required for the linked list

- Solving for n we can determine the break-even point beyond which the array-based list is more space efficient in any particular situation: `n > D·E/(P+E)`

**Element implementations**:

- **Store pointers**: In general, the larger the elements and the more they are duplicated, the more likely that storing pointers to the objects instead of copies is a better approach. This saves space, allows for multiple lists to point to the same object, and modification of a value is automatically reflected at all locations where it's referenced. However, storing a pointer requires space, which adds unnecessary overhead if elements are never duplicated.
- **Store elements of different type** (homogeneity in a DS): This can be done using a `void*` pointer, with the user performing the necessary casting to and from the actual object type for each element. This approach requires that the user do his own type checking. Since lists are implemented using templates, this approach prevents the compiler from creating a new class for each data type.
- **Besides templates**, there are other techniques to ensure that the element type for a given list remains fixed, while still permitting different lists to store different element types. One approach is to store an object of the appropriate type in the header node of the list (perhaps supplied as a parameter to the list constructor), and then check that all insert operations on that list use the same element type.
- **Automatic garbage collection**: C++ doesn't have it. Deleting the list or calling `clear` may cause memory problems if the element has not a simple type. If the elements are pointers to objects, the list doesn't know if it should be deleted or not (the object may be pointed to elsewhere). Thus, the user of the list must be responsible for deleting the objects when appropriate.

### Stacks

#### Abstract stack

It's a list-like structure where elements can only be inserted or removed from one end. It's less flexible than lists, but efficient and easy to implement. It follows a **LIFO** (Last-In, First-Out) policy: Elements are removed in rever order of their arrival. We can both **push** (insert) an element onto the stack, and **pop** (remove) the **top** element (accessible element) from the stack. Standard approaches to implementing a stack: **array stack** and **linked stack**.

```
// Stack ADT
template<typename T> class Stack
{
public:
  Stack();
  Stack(const Stack& obj);   // copy constructor
  virtual ~Stack();

  //void operator=(const Stack& obj);   // Copy-assignment (cannot be virtual, define it in subclasses)

  virtual void clear() = 0;
  virtual void push(const T& it) = 0;
  virtual T pop() = 0;
  virtual const T& topValue() const = 0;
  virtual int length() const = 0;
}
```

Main operations: Their running-time complexity is O(1).

- `clear`: Remove all elements. It's O(n) in linked stacks.
- `push`: Insert element at top.
- `pop`: Remove element from top.
- `topValue`: Value of element at top.
- `length`: Number of active elements.

#### Array stack

Member variables: `array` (container), `capacity` (max. size), `top` (array index of first free position. Range [0, n]).

**Static-array stack** (SAS): Fixed size. Simplified static array-based list. The `top` position is at the tail (otherwise, insertion/removal might require shifting elements). `push` inserts an element at the array's `top` position and increments `top`. `pop` decrements `top` and removes an element from the array's `top` position. All operations take constant time.

**Double static-array stack**: Static-array stack that stores 2 stacks. A single array can be used to store both, where each one grows inward from each end. This only works well when the space requirements of both stacks are inversely correlated (example: when elements taken from one stack are given to the other).

#### Linked stack

Member variables: `top` (pointer to first element), `size` (number of elements).

**Linked list stack** (LLS): Dynamic size. Elements are inserted and removed from the head (`top`). There's no need for a header node (no special-case code is needed for 0 or 1 elements). A freelist is a linked stack. `push` sets the `next` field of the new link node to point `top` and sets `top` to point the new node. `pop` sets `top` to point to the next link in the stack and returns the element of the old node is returned. All operations take constant time.

#### Comparison

- **Array stack**:
  - All operations take constant time.
  - Fixed size. Some space is wasted when the stack is not full.
  - Allows storing 2 stacks in a single array (double static array stack).

- **Linked stack**:
  - All operations take constant time.
  - Dynamic size. Requires overhead of a link for every element.

#### Recursion

A **subroutine call** is normally implemented by placing necessary information about the subroutine (return address, parameters, local variables...) onto a stack. This information is called **activation record** (or stack frame). Further subroutine calls add to the stack. Each return from a subroutine pops the top activation record off the stack.

Example: <<<

1. Calling to `fact(4)` places an activation record (AR<sub>1</sub>) onto the stack, which contains the program address to the instruction from which `fact` is called (a<sub>1</sub>). 
2. Next, 4 is passed to `fact` and then `fact(3)` is called (recursive call), so AR<sub>2</sub> is placed onto the stack, which includes a<sub>2</sub> and current n value (4).
3. Next, 3 is passed to `fact` and then `fact(2)` is called, so AR<sub>3</sub> is stacked (includes a<sub>3</sub> and 3).
4. Next, 2 is passed to `fact` and then `fact(1)` is called, so AR<sub>4</sub> is stacked (includes a<sub>4</sub> and 2).
5. Next, 1 is passed to `fact` and the base case is reached, so recursion begins to unwind. Each return from `fact` involves popping from the stack the stored n value and the return address from the function call. The return value for `fact` is multiplied by the restored value for n, and the result is returned.

[AR1] [AR2, 4] [AR3, 3] [AR4, 2]  (1 returned)
[AR1] [AR2, 4] [AR3, 3]  (1*2= 2 returned)
[AR1] [AR2, 4] (2*3 = 6 returned)
[AR1] (6*4 = 24 returned)

1. When we call `fact(4)`, the stack stores the program address to the program instruction from which `fact` is called (A<sub>1</sub>). Then, 4 is passed to `fact`.
2. Next, the recursive call `fact(3)` is made, so A<sub>2</sub> and the current value for n (4) is saved on the stack. Then, 3 is passed to `fact`.
3. Next, the recursive call `fact(2)` is made, so A<sub>3</sub> and the current value for n (3) is saved on the stack. Then, 2 is passed to `fact`.
4. Next, the recursive call `fact(1)` is made, so A<sub>4</sub> and the current value for n (2) is saved on the stack. Then, 1 is passed to `fact`.
5. Base case for `fact` is reached, so recursion begins to unwind. Each return from `fact` involves popping the stored value for n from the stack, along with the return address from the function call. The return value for `fact` is multiplied by the restored value for n, and the result is returned.

Because an activation record must be created and placed onto the stack for each subroutine call, making subroutine calls is relatively expensive. While recursion makes implementation easy and clear, sometimes you might want to eliminate this overhead by replacing recursion by **iteration**. 

```
// Non-recursive factorial
long fact(int n, Stack<int>& S)
{
  if(n < 0 || n > 12) throw std::out_of_range("Input out of range");

  while(n > 1) S.push(n--);
  long result = 1;
  while(S.length() > 0) result *= S.pop();
  return result;
}
```

An iterative `fact` is both simpler and faster than this **recursion imitation**.

- **Recursion**: A function calls to itself. Relatively expensive.
- **Iteration** (loops): Iteration could replace recursion, but it's not always possible. Usually simpler and faster.
- **Recursion imitation** (stack): Recursion can always be imitated with a stack. 

Recursion or some imitation is necessary (iteration is not possible) when implementing algorithms that require multiple branching (Towers of Hanoi algorithm, traversing a binary tree, Mergesort, Quicksort...).

Recursive algorithms can be efficiently implemented with a stack when the amount of information to describe a sub-problem is small (like in Quicksort).

```
// Operations
enum TOHop { DOMOVE, DOTOH };

// Operation object
class TOHobj
{
public:
  TOHop op;   // operation type
  int num;   // disks count
  Pole start, goal, tmp;

  TOHobj(int n, Pole s, Pole g, Pole t)
    : op(DOTOH), num(n), start(s), goal(g), tmp(t) { }

  TOHobj(Pole s, Pole g)
    : op(DOMOVE), start(s), goal(g) { }
}

// Non-recursive Towers of Hanoi algorithm
void TOH(int n, Pole start, Pole goal, Pole temp, Stack<TOHobj*>& S)
{
  S.push(new TOHobj(n, start, goal, tmp));
  TOHobj* t;
  while(S.length() > 0)   // Grab next task
  {
    t = S.pop();
    if(t->op == DOMOVE)   // Do a move
      move(t->start, t->goal);
    else if(t->num > 0)   // Store in reverse 3 recursive statements
    {
      int num = t->num;
      Pole tmp = t->tmp;
      Pole goal = t->goal;
      Pole start = t->start;
      S.push(new TOHobj(num-1, tmp, goal, start));
      S.push(new TOHobj(start, goal));
      S.push(new TOHobj(num-1, start, tmp, goal));
    }
    delete t;
  }
}
```

<<< UNDERSTAND THIS

### Queues

#### Abstract queue

It's a list-like structure where elements can only be inserted at the back (**enqueue**) and removed from the front (**dequeue**). It follows a **FIFO** (Firt-In, First-Out) policy. Elements are released in order of arrival. Standard approaches to implementing a queue: **array queue** and **linked queue**.

```
// Queue ADT
template<typename T>
class Queue
{
public:
  Queue() { }
  virtual ~Queue() { }

  //void operator=(const Queue&) { }   // Copy-assignment (cannot be virtual, define it in subclasses)

  virtual void clear() = 0;
  virtual void enqueue(const T&) = 0;
  virtual T dequeue() = 0;
  virtual const T& frontValue() const = 0;
  virtual int length() const = 0;
}
```

Main operations: Their running-time complexity is O(1).

- `clear`: Remove all elements. It's O(n) in linked queues.
- `enqueue`: Insert element at rear.
- `dequeue`: Remove element from front.
- `topValue`: Value of element at top.
- `length`: Number of active elements.

#### Array queue

Consider an array of size n that stores n elements. Considering position n-1 to be the rear, then enqueue requires Θ(1) time (equivalent to append), and dequeue requires Θ(n) (all elements are shifted down one position). Considering position 0 to be the rear, then enqueue requires Θ(n) time and dequeue requires Θ(1). A more efficient implementation allows the content of the queue to drift within the array, so enqueue and deque operations can be performed in Θ(1) time.

- Removing elements from the queue increases the front index, eventually causing the queue to run out of space despite having free positions at the array's low end. This can be solved by pretending the array to be circular, easily implemented through the use of the modulus operator (`%`).
- A full queue is indistinguishable from the empty queue (a queue of n elements has n+1 possible states). Two possible solutions: keep an explicit counter of elements, or make the array have size n+1 but only allow n elements.
- `enqueue` increments the rear pointer, and `dequeue` increments the front pointer (modulus size).

Member variables: `capacity` (max. size, and base for the modulus operator), `front` (front element position), `rear` (rear element position), `array` (elements storage).

#### Linked queue

Straightforward adaptation of the linked list. Including a header node simplifies implementation of `enqueue` (avoids special cases when queue is empty). `front` points to header node. `rear` points to last link node. `enqueue` places a new element at the end of the list and advances the `rear` pointer. `dequeue` removes and returns the first element.

Member variables: `front` (front element pointer), `rear` (rear element pointer), `count` (number of elements).

#### Comparison

All operations from both array queue and linked queue require constant time. The space comparison issues are the same as for the equivalent stack implementations. Unlike the array stack, there's no convenient way to store 2 queues in the same array.

### Dictionaries

#### Abstract dictionary

A **dictionary** stores objects where each object is associated to a **search key**, which is used for searching records. It provides lookup, insert, and remove operations. Each key is unique, and each key maps to a value.

```
template <typename K, typename E>
class Dictionary
{
public:
  Dictionary() { }
  Dictionary(const Dictionary&) { }
  virtual ~Dictionary() { }

  //virtual List& operator=(const List& obj) = 0;   // Copy-assignment (cannot be virtual)
  virtual T& operator[](size_t i) const = 0;   // Subscript

  virtual void clear() = 0;
  virtual void insert(const K& k, const E& e) = 0;
  virtual E remove(const K& k) = 0;
  virtual E removeAny() = 0;
  virtual E find(const K& k) const = 0;
  virtual int size() = 0;
};
```

Main operations:

- `insert`: Insert a record.
- `find`: Given a key, return the associated record. Returns `nullptr` if none exists. If multiple records match the key, returns an arbitrary one.
- `clear`: Reinitialization.
- `remove`: Given a key, delete and return a record. If multiple records match the key, an arbitrary one is removed. Returns `nullptr` if no record with that key exists.
- `removeAny`: Remove and return an arbitrary record, if one exists. If none exists, returns `nullptr`.
- `size`: Number of elements.

`removeAny` provides a generic access to all elements. It's useful for iterating over all elements and removing them. Otherwise, a user could not get at a record that he didn't know the key value for. Other approaches can use a `first` and `next` function, but not all data structures used for implementing a dictionary can do `first` efficiently (like a hash table).

```
while(dict.size() > 0)
{
  it = dict.removeAny();
  doSomething(it);
}
```

**Key extraction** methods:

- __Record returns key__: Require all record types to support a method that returns the key value. However, this doesn't work when the same record type is meant to be stored in multiple dictionaries, each keyed by a different field of the record (like in databases).
- __External gets key from record__: Supply a class whose job is to extract the key from the record. However, there're record types for which it's not possible to write a key extraction method (example: consider records that describe books, where one of its fields stores a few keywords. Our dictionary might list records sorted by keyword. If a book contains 3 keywords, it will appear 3 times on the list, once per keyword. But, given the record, there's no simple way to determine which keyword triggered the appearance of the record, so we cannot write a function that extracts the key from such record).
- __Key-value pairs__ (most general and preferred option): Consider the key for a record not an intrinsic property of the record, but of the context in which the record is used. Store the key as a separate field in the dictionary. Each entry in the dictionary will contain both a record and its key (key-value pair). Such entry can be implemented as a container class containing both fields (`KVpair<K,E>`).

**Keys comparison** methods:

- Using operators `==`, `<=`, `>=`. Depending on the type, the user may need to overload them.
- Using a **comparator** (most general and preferred option). It's a class provided by the user that does comparison and makes those operations be template parameters (strategy pattern). In some cases, it makes sense for the comparator to extract the key from the record type (alternative to storing key-value pairs).

#### Unsorted array dictionary

It internally uses an unsorted array. Operations costs:

- `insert` is Θ(1) (constant-time) because it inserts a new record at the end of the list.
- `find` and `remove` require Θ(n) time in the average and worst cases, because a sequential search is necessary. `remove` must touch every record in the list (to find and to shift).
- `removeAny` is Θ(1) (it removes the last record).

#### Sorted array dictionary

It internally uses a sorted array. Operations costs:

- `insert` and `remove` are Θ(n) (binary search can be used, but all subsequent elements still have to be shifted next).
- `find` is Θ(log n) (binary search is used).
- `removeAny` is Θ(1).

Whether a sorted list is more or less efficient than an unsorted list depends on the relative number of `insert` and `find` operations.

A sorted list is different than an unsorted list since it cannot permit the user to control where the elements get inserted (`insert`, `append`). Thus, a sorted list cannot be implemented with simple inheritance from the `List` ADT. Solution: We can create a `SortedList` that inherits from `protected List`, so all `List` members are hidden from the user. Then, we can expose all `List` members except `insert` and `append`, and redefine `insert` (so it stores elements in sorted order).

#### Linked dictionary

It internally uses a linked list. The operations costs should be asymptotically the same as those of an unsorted array dictionary.

Operations costs: `insert` is Θ(1), `find` is Θ(n), `remove` is Θ(n), `removeAny` is Θ(1).



TODO: sorted list must accept a single type. Comparater is passed too.


// copy constructors > use object slicing, if necessary
// copyFrom > use pointer arguments


<<< Complexity
<<< Particular member variables

<<< Make DLL::curr point to current element
<<< Implement algorithms: TOH_recursive, TOH_stack, fact_recursive, fact_iterative, fact_stack

Symbols used: ≤, ≥, ≠, ≈, √, ∑, →, ↔, ∨, ∧, ~, ¬, ∀, ∃, ⌊⌋, ⌈⌉, <sub>i</sub>, <sup>i</sup>, ∞, Ω, Θ

## Binary trees
## Non-binary Trees
## Internal Sorting
## File Processing and External sorting
## Searching
## Indexing
## Graphs

## R
