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
- [How to do problems](https://www.quora.com/When-should-I-start-doing-LeetCode-problems-I-haven-t-learned-data-structures-and-algorithms)


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

Symbols used: ≤, ≥, ≠, ≈, √, →, ↔, ∨, ∧, ~, ¬, ∀, ∃, ⌊⌋, ⌈⌉, <sub>i</sub>, <sup>i</sup>, ∞

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

<br>![growth rates](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/topics/computer_science/synthesis/growth_rates_1.png)

<br>![growth rates](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/topics/computer_science/synthesis/growth_rates_2.png)

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

<br>![growth rates](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/topics/computer_science/synthesis/improvements.png)

Operations that an algorithm can do in a 10 times faster machine:

- Linear (`cn`): n·10
- Logarithmic (`log n`): More than quadratic algorithms, but less than linear ones.
- Quadratic (`n<sup>2</sup>`): n·√10 ≈ n·3.16
- Exponential (`2<sup>n</sup>`): n + log<sub>2</sub>10 = n + 3

Note that constant factors never affect the relative improvement in problem size gained by a faster computer.

For an input of size n = 1023, an algorithm with running time T(n) = n<sup>2</sup> requires 1.048.576 (1024 x 1024) time steps, but a running time T(n) = n log n only requires 10.240 (1024 x 10).

### Asymptotic analysis

The curve $10n$ is crossed by $2n<sup>2</sup>$ at $n=5$. For $20n$, it's crossed at $n=10$. The two curves always cross at some point. Changing the constant factor only shift where the 2 curves cross. For a faster computer or compiler, the new problem size that can be run in a given amount of time for a given growth rate is larger by the same factor, regardless of the constant. The time curves for two algorithms with different growth rates still cross, regardless of their running-time equation constants. That's why we usually ignore the constants when estimating the growth rate for the running time or other resource requirement of an algorithm (asymptotic analysis). 

**Asymptotic algorithm analysis**: Study of an algorithm as the input size gets big or reaches a limit (Calculus limit). It provides a simplified model (estimation) of the algorithm resource consumption (running time or other resource). It helps understand the behaviour of an algorithm.

However, it's not always reasonable to ignore constants. When comparing algorithms meant to run on small values of n, the constant can have a large effect. Or when the constants between the two algorithms differ by a factor of 1000 or more.

**Upper bounds**: Highest growth rate that the algorithm can have. It's represented with **big-Oh** notation. Example: if the upper bound for an algorithm's growth rate (for, say, the worst case), is $f(n)$, then this algorithm is in O(f(n)) in the worst case ($n<sup>2</sup>$ is in $O(n<sup>2</sup>)$ in the worst case. 

- Mathematical definition: Given an algorithm, its true running time (T(n)) and some expression for the upper bound (f(n)), for T(n) a non-negatively valued function, T(n) is in set O(f(n)) if there exist 2 possible constants c and n<sub>0</sub> such that T(n) ≤ cf(n) for all n > n<sub>0</sub>. Constant n<sub>0</sub> (it's usually small) is the smallest value of n for which the claim of an upper bound holds true. The value of c is irrelevant.
- Another definition: For all inputs of the type in question (such as the worst case for all inputs of size n) that are large enough (i.e., n > n<sub>0</sub>, the algorithm always executes in less than cf(n) steps for some constant c.

Example: Consider the sequential search algorithm for finding a specified value in an array of integers. Visiting an examining one value in the array requires c<sub>s</sub> steps. If the value we search for has equal probability to appearing in any position in the array, then in the average case T(n) = c<sub>s</sub>n/2. For all values n > 1, c<sub>s</sub>n/2 ≤ c<sub>s</sub>n. Thus, T(n) is in O(n) for n<sub>0</sub>=1 and c=c<sub>s</sub>.

An algorithm has a growth rate for each case (best, average, worst). Any statement about the upper bound of an algorithm must be in the context of some class of inputs of size n. We say that "this algorithm has an upper bound to its growth rate of n<sup>2</sup> in the average case". Saying only that something is in O(f(n)) only says how bad things can be. But perhaps things are not nearly so bad.

Because sequential search is in O(n) in the worst case, it's also true that it is in O(n<sup>2</sup>). O(n) is in O(n<sup>2</sup>), but O(n<sup>2</sup>) is not it O(n). However, we always seek to define the running time of an algorithm with the tightest (lowest) possible upper bound. So we prefer to say that sequential search is in O(n)



Symbols used: ≤, ≥, ≠, ≈, √, →, ↔, ∨, ∧, ~, ¬, ∀, ∃, ⌊⌋, ⌈⌉, <sub>i</sub>, <sup>i</sup>, ∞

## Lists, Stacks, Queues
## Binary trees
## Non-binary Trees
## Internal Sorting
## File Processing and External sorting
## Searching
## Indexing

## R
