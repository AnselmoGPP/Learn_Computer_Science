# C++ basics

## Table of Contents
+ [Basics](#basics)
+ [Flow of control](#flow-of-control)
+ [Return](#return)
+ [Variables](#variables)
+ [Keywords, operators and punctuators](#keywords,-operators-and-punctuators)<<<
+ [Keywords](#keywords)<<<
+ [Identifiers](#identifiers)<<<
+ [Preprocessor directives](#preprocessor-directives)<<<
+ [References](#references)


## Basics

C++ provides a set of built-in types, operators to manipulate those types, a few statements for program flow control, and mechanisms that allow to define new data structures.

C++ provides a rich set of operators and defines what they do when applied to operands of built-in type. It also allows us to define the meaning of most of the operators when applied to operands of class types.

### Main terms

- **Expression**: Smallest unit of computation. One or more operands and usually one or more operators. It is evaluated to produce a result (i + j, assuming i and j are ints). Simplest for: single literal or variable.

- **Compound expression**: Expression with 2 or more operators.

- **Statement**: Composed of one or more operands and (usually) an operator. Yields a result.

- **Variable**: Named object.

- **Declaration**: Asserts the existence of a variable, function, or type defined elsewhere. Names may not be used until they are defined or declared.

- **Definition**: Allocates storage for a variable of a specified type and optionally initializes the variable. Names may not be used until they are defined or declared.

- **Preprocessor**: Program that runs before the compiler and changes the source text of our programs. Example of preprocessor facilities: `#include`, header guards, namespaces, etc.

- **C++ Standard library**: Collection of classes and functions. Provides generic containers, functions to utilize and manipulate these containers, function objects, generic strings and streams (including interactive and file I/O), support for some language features, and functions for everyday tasks. Also incorporates the **C library**. Headers in C have names ending in **.h**. C++ versions of these C headers are named **cname**, without .h. Names from the C++ library (not C library) are declared within the **std** namespace. Use the C++ versions of C library headers. They have similar contents, but in a form appropriate for C++ programs

- **Template**: Instructions to the compiler for generating classes or functions. When we use a template, we specify what kind of class or function we want the compiler to instantiate by supplying additional information, which nature depends on the template (supply it inside angle brackets, following the template’s name.

- **Instantiation**: Process the compiler uses to create a class or function from a template.

- **Undefined behaviour**: Results from error that the compiler is not required or not able to detect. Programs with these problem can appear to execute correctly in some circumstances and/or on some compilers.

- **Implementation-defined behaviour**: Programs with this problem are nonportable. Such as assuming that the size of an int is a fixed and known value.

- **Compilation**: 

  - **Preprocessing**: The preprocessor takes a C++ _source code_ file and deals with the preprocessor directive (`#include`, `#define`, …). Outputs a C++ file without preprocessor directives.
  - **Compilation**: Compiler takes the preprocessor’s output and produces an _object file_.
  - **Linking**: The linker takes these object files and produces either a _library_ or an _executable file_.

### Compiling

We write the source code in `hpp` (headers) and `cpp` (translation units) files. Compiler translates the source code into machine code that the computer can understand and run. Header files (`hpp`) are not compiled, they are just copied into `cpp` files. Only `cpp` files are compiled, which results in a bunch of `obj` files, one per `cpp` file.

In `VS` the `Compile` button compiles. The compiler can output its own error messages (like `C2143: Syntax error`).

1. We write simple **text files** (`hpp` and `cpp` files) using C++ programming language.

2. **Preprocessing**: Compiler substitutes all the preprocessor statements that are in our code with whatever are the contents they refer (`include`, `define`, `if`, `ifdef`, …).
  - `include`: Copies whatever is the content of the header in your code.
  - `define`: Substitutes a given sequence of letters by another sequence of letters.
  - `if`, `endif`: Include or exclude code based on a given condition.
  - etc.

3. **Abstract syntax tree**: Sort the code (by tokenizing and parsing) to a format compiler understands.

4. **Object files (`obj`)**: Compiler creates it from our C++ preprocessed code (one `obj` per `cpp` file). It contains the machine code (assembly instructions and constants) the CPU will actually execute when running our program. 

  - **Optimization**: Compiler may optimize your code to improve its performance (example: it may get rid of useless instructions)
  - **Debug mode**: Code is not optimized, is made verbose, and is made easier to debug.
  - **Constant folding**: Compiler works out anything that is constant (example: `5 * 2` becomes `10`).

### Linking

The **linker** links all the `obj` files into one executable that contains all the machine code that we need to run.

In `VS`, the `Build` button compiles and links. The linker can output its own error messages (like `LNK1561: Entry point must be defined`).












## Flow of control

Statements usually execute sequentially. Some flow-of-control statements allow for more complicated execution paths. Types:

- **Iteration (loop)**: Repeats execution until a condition is true.
  - While
  - Do while
  - For
  - Range for
- **Selection (condition)**: Executes if a condition is true.
  - If
  - Switch
  - Ternary <<<
- **Jump**
  - Break
  - Continue
  - Return <<<
  - Goto

### Iteration

#### While

Repeatedly executes a section of code so long as a given condition is true (bool). Tests condition before executing the body. Useful for iterating indefinitly or for accessing to the value of the control variable after the loop finishes.

Tests the condition > If true, executes the statement > Repeats until condition is false

```
while (condition)
    statement
```

**Condition**: Expression or initialized variable declaration. It may not be empty. Ordinarily, the condition or the loop body must change this expression; otherwise, the loop might never terminate.

Variables defined in a while condition or while body are created and destroyed on each iteration.

```
while (val <= 0) {
    sum += val;
    ++val;
}
```

```
while (cin >> value) ...
```

The while tests the stream until it encounters **end-of-file** or an **input error**. Different operating systems use different conventions to enter end-of-file. Usually:

- __Windows__: Ctrl-z + Enter or Return.
- __UNIX, Mac OS X__: Ctrl-d.

#### Do While

Executes the body and then tests its condition. Like a while, but condition is tested after the statement body completes. Ends with a semicolon.

```
do
    statement
while (condition);
```

- **Statement**: Executed before condition is evaluated.
- **Condition**: Cannot be empty. Cannot contain variable definitions. Variables used here must be defined outside the body.

```
string str;
do {
    cout << "Enter 2 values: ";
    int a = 0, b = 0;
    cin >> a >> b;
    cout >> "For more, enter yes or no: ";
    cin >> str;
} while (!str.empty() && str[0] != 'n');
```

#### For

Control how often the body is executed. Test condition before executing the body. The header has 3 parts:

```
for(init-statement; condition; expression)
    statement
```

- **Init-statement**: Executed only once. Must be declaration statement, expression statement, or null statement. Usually initialize or assign a starting value modified during the loop. Can define several objects (use comma) but can only be a single declaration statement, so all variables must have same base type.
- **Condition**: Tested each time through the loop (loop continues until condition fails). If false, statement is not executed.
- **Expression**
- **Statement**: Single or compound statement.

```
for (int i = 0; i < 10; ++i) {...}
```

Execution flow: init-statement/expression > Condition > Statement

Any object **defined** within the for header is limited to the body of the for loop.

A for header can **omit** any or all of init-statement, condition, expression or statement by using a null statement (single semicolon). Omitting condition is equivalent to writing true as the condition.

#### Range for

Iterates through the elements in a given sequence and performs some operation on each value. Execution ends when all the elements have been processed.

```
for (declaration : expression)
    statement
```

- **Expression**: Represent a sequence: braced initialized list, array, or an object that has begin and end members that returns iterators (such as vector or string).
- **Declaration**: Defines a variable. It must be possible to convert each element of the sequence to the variable’s type.

To modify the value of the elements in a sequence, you must define the loop variable as a reference type:

```
for (auto &c : str)
    c = toupper(c);
```

The body of a **range for** must not change size of the sequence over which it is iterating (example: It cannot add elements to a vector).

To avoid copying the sequence, you can define the loop variable as const reference:

```
for(const auto &s : text) { ... }
```

### Selection

#### If

A conditional execution like while, but without loop. Executes an statement based on whether a specified condition is true.

```
if (condition)
    statement_1
else
    statement_2
```

```
if (std::cin >> val) {...}   // These statements can be blocks
else {...}
```

Both, “=” (assignment) and “==” (equality) operators can appear inside a condition.

**Condition** must be enclosed by parentheses. It can be an expression or an initialized variable declaration. Must have a type convertible to bool.

```
if (condition_2)        // Nested ifs
    statement_1
else if (condition_2)
    statement_2
else ...
```

**Dangling else**: When we nest an _if_ inside another _if_, it’s possible that there will be more _if_ branches than _else_ branches. How do we know to which _if_ a given _else_ belongs? Each _else_ is matched with the closest preceding unmatched if.

```
if(grade % 10 ≻= 3)
    if(grade % 10 ≻ 7)
        grade += '+';
    else
        grade += '-';
```

We can make the else part of the outer _if_ by enclosing the inner _if_ in a block.

```
if(grade % 10 ≻= 3) {
    if(grade % 10 ≻ 7)
        grade += '+';
} else 
    grade += '-';
```

#### Switch

Way of selecting among a number of fixeed alternatives. Evaluates an integral expression and chooses one of several execution paths.

```
switch (ch) {
    case 'a':
        ++counter;
        break;
    case 'b':
        ++counter;
        break;
    case 'c':
        ++counter;
        break;
    default:
        --counter;
        break;
}
```

Evaluates the parenthesized expression. That expression may be an initialized variable declaration. It is converted to integral type. If it matches the value of a case label, execution begins from there until the end of the switch or until a **break**.

- **case**: This keyword and the associated value is the **case label**. It must be __integral constant expression__. Can only have a single value.
- **break**: Interrupts the current control flow. If you omit a break, explain the logic.
- **default**: Special label executed when no case label matches the value of the switch expression. An empty default (must be followed by null statement or empty block) indicates that the case was considered.

```
char ch = get_val();
int val = 32;
switch(ch) {
    case 3.14:     // error (non-integer)
    case val:      // error (non-constant)
    ...
```

Any code inside the switch before the activated label is ignored. What happens if the skipped code includes a variable definition? It’s illegal to jump from a place where a variable with an initializer is out of scope to a place where it is in scope. You can only declare it previously, but not initialize it previously.

```
switch (x) {
    case true:
        string file_name;     // error (implicitly initialized)
        int val_1 = 0;        // error (explicitly initialized)
        int val_2;            // ok (not initialized)
        break;
    case false:
        val_2 = next_num();         // ok
        if(file_name.empty()) ...   // error (file_name is in scope but wasn't initialized
        break;
}
```

It’s illegal to jump over an initialization if the initialized variable is in scope at the point to which control transfers. If we need to define and initialize a variable for a particular case, we can define the variable inside a block.

```
case true:
    {
        string file_name = get_file_name();
    }
```

#### Ternary

```
int a = 5, b = 10;
int largestumber;
largestNumber = (a > b) ? a : b;
```

### Jump

#### Break

Interrupts the current control flow. It can only affect the nearest enclosing loop or switch. Terminates the nearest enclosing while, do while, for or switch.

#### Continue

Terminates the current iteration of the nearest enclosing loop and begins the next iteration. Can only appear inside a for, while or do while, including inside statements or blocks nested inside these loops. May appear inside a switch only if it’s embedded inside an iterative statement.

#### Return

The return statement terminates the function that is currenty executing and returns control to the point from which the function was called.  Learn more [**here**](#return).

#### Goto

Unconditional jump from the goto to another statement in the same function. Programs should not use goto (harder to understand and to modify). Allows jumping backwards.

```
goto label_A;
...
label_A: return;          // labeled statement
```

- **Label**: Identifier that identifies a statement.
- **Labeled statement**: Any statement preceded by an identifier followed by a colon. Independent of names used for variables and other identifiers.

It cannot transfer control from a point where an initialized variable is out of scope to a point where that variable is in scope.

```
goto end;
int a = 5;
end:
    a = 42;    // error (code uses a but bypassed its declaration)
```

Jumping back to a point before a variable is defined destroys the variable and constructs it again:

```
begin:
int b = get_size();
if (b ≺= 0)
    goto begin;
```


## Return

The return statement terminates the function that is currenty executing and returns control to the point from which the function was called. Two forms: `return;` and `return expression;`.

### Functions with no return value

A return with no value may be used only in a function that returns `void`, although it doesn’t require to contain a return. It’s usually used to exit the function in an intermediate point. It may return the result of another function that returns void.

### Functions that return a value

Every return in a function with a return type other than void must return a value, and it must be the same type as the function return type or a type that can be implicitly converted.

Values are returned in exactly the same way as variables and parameters are initialized: The return value (result of the function call) is used to initialize a temporary at the call site.

Remember the initialization rules in functions that return local variables. Examples of return types:

- `string` > The returned value is copied to the call site
- `const string &` > The returned value is not copied

Never return local objects or pointer to local objects

#### Functions that return class types

The call operator () has associativity and precedence (same precedence as dot and arrow operators and left associative like them). If a function returns a pointer, reference of object of class type, we can use the result of a call to call a member of the resulting object.

```
auto sz = shorterString(s1,s2).size();
```

Calls to functions that return references are **Lvalues**. Other return types yield **rvalues**. A call to a function that returns a reference can be used in the same way as any other lvalue. Example: We can assign to the result of a function that returns a reference to nonconst.

```
char &getVal();

void func() {
    getVal() = 'A';   // Return value is a reference, so the call is an lvalue
}
```

If the return type is a reference to const, we may not assign to the result of the call.

#### List initializing the return value

Functions can return a braced list of values. If the list is empty, that temporary is value initialized. Otherwise, the value of the return depends on the function’s return type.

```
vector<string> process() {
    // ... expected and actual are strings
    if(expected.empty()) return {};                         // return empty vector
    else if(expected == actual) return {"hello", "okay"};   // return list-initialized vector
    else return {"hello", expected, actual};
}
```

In a function that returns a built-in type, a braced list may contain at most one value, and that value must not require a narrowing conversion. If the function returns a class type, that class defines how the initializers are used.

#### Return from main

A function with a return type other than void must return a value. However, main() is an exception because when control reaches the end of main() and there is no return, then the compiler implicitly inserts a return of 0.

A value returned from main() is trated as a status indicator (0 is success, other values are failure). A nonzero value has machine dependent meaning. To make return values machine independent, <cstdlib> defines 2 preprocessor variables that can be used to indicate success or failure:

```
int main() {
    if(some_failure) return EXIT_FAILURE;
    else return EXIT_SUCCESS;
}
```

#### Recursion

A recursive functions calls itself, either directly or indirectly.

```
int factorial(int val) {
    if(val > 1) 
        return factorial(val-1) * val;
    return 1
}
```

There must always be a path through a recursive function that doesn’t involve a recursive call; otherwise, the function will recurse forever (until the program stack is exhausted). Main() may not call itself.

#### Returning a pointer to an array

Because we cannot copy an array, a function cannot return an array, but it can return a pointer or reference to an array. The most straightforward way is to use a type alias.

```
typedef int arrT[10];     // arrT is a synonym for the type array of 10 ints
using arrT = int[10];     // equivalent to the previous
arrT* func(int i);        // function that returns a pointer to an array of 10 ints
```

#### Declaring a function that returns a pointer to an array

Remember that, without using a type alias, we must remember that the dimension of an array follows the name being defined.

```
int arr[10];       // array of 10 int
int * p1[10];      // array of 10 pointers
int (*p2)[10];     // pointer to an array of 10 ints
```

```
type (*function(parameter_list))[dimension]
```

The parentheses are necessary for the same reason as with p2. Without them, we would be defining a function that returns an array of pointers.

Declaration of func without using type alias:

```
int (*func(int i))[10];
     // func(int) -> We call this function.
     // (*func(int)) -> We dereference the result of that call.
     // int (*func(int))[10]) -> Dereferencing the result of func yields an array of type int and size 10.
```

#### Using a Trailing return

Can be defined for any function, but is most useful for functions with complicated returns (such as pointers or references to arrays). It’s another way to simplify the declaration of func.

```
auto func(int i) -> int(*)[10];        // func returns a pointer to an array of 10 ints
```

#### Using decltype

An alternative is to use decltype to declare the return type. decltype doesn’t automatically convert an array to its corresponding pointer type, we must add a *.

```
int odd[] = {1,3,5,7,9};
int even[] = {0,2,4,6,8};
decltype(odd) *arrPtr(int i) {
    return (i % 2) ? &odd :: &even;    // returns a pointer to the array
}
````


## Variables

**Variable/object**: Named storage that our programs can manipulate. It has a type that determines the size and layout of the variable’s memory, range of values that can be stored there, and set of operations that can be applied on it.

**Object**: Generally, it’s a region of memory that can contain data and has a type. However, sometimes is used with different meanings:

- Variables or values of class types
- Named objects
- Data that can be changed by the program (consider value as data that is read-only)

### Initialization

**Initialization**: A value is given to a variable when it is created.

**Assignment**: Obliterates an object’s current value and replaces that with a new one.

Several forms of initialization:

```
int item = 0;
int item = {0};
int item{0};
int item(0);
```

**List initialization**: When curly braces are used for initialization. Compiler will not let list initialize variables of built-in type if the initializer leads to loss of information.

```
long double val = 2,71828;
int a{val}, b = {val};          // errors
int c(val), d = val;            // ok, but truncated
```

**Default initialization**: It’s when you define a variable without an initializer. Variables defined outside any function body are initialized to zero (with one exception), but inside a function are uninitialized, so its value is undefined (so, it’s recommended to initialize every object of built-in type). Each class controls how we initialize objects of that class type.

**Declaration**: Makes a name known to the program. Specify type and name. Allocates storage and may provide an initial value. Variables must be defined only once but can be declared many times.

**Definition**: Creates the associated entity.

### Identifier

Name of a variable.

- Can be composed of letters, digits and the underscore character
- No length limits
- Case-sensitive
- Must begin with letter or underscore (identifiers defined outside a function cannot begin with underscore)
- Cannot begin with underscore followed immediately by uppercase letter
- Cannot contain 2 consecutive underscores
- You cannot use names of keywords, alternative operators or reserved names from the standard library

Conventions for naming variables:

- Identifier should have some meaning
- Variable names > Usually lowercase
- Classes names > Usually begin with uppercase
- Identifiers with multiple words should distinguish each (deep_blue, deepBlue)

### Scope

Part of the program where a name has a particular meaning. Most scopes are delimited by **curly braces**. The same name can refer to different objects in different scopes. Names are visible from the point where they are declared until the end of the scope in which the declaration appears.

Names declared at the **global scope** are accessible throughout the program. Names declared inside a block have **block scope**.

**Nested scopes**: Scopes can contain other scopes (**inner scope**, **outer scope**). A name declared in one scope can be used in inner scopes. Names declared in a scope can also be redefine in an inner scope.

```
int test = 5;
int main() {
    int test = 8; // new local test hides the global test
    std::cout << ::test; // outputs the global test
}
```

The global scope has no name, so the **scope operator** with empty left side is a request to the global scope.


## Keywords, operators and punctuators

















## Keywords

**Reference**: [Keywords](https://en.cppreference.com/w/cpp/keyword)

**Flow of control**:

- `for`: Declares a for-loop or range-based for-loop.
- `do`: Declares a do-while loop
- `while`: Declares a while loop or do-while loop.
- `if`: Conditionally executes another statement.
  - `else`: Declaration of an alternative branch in an if-statement.
- `switch`: Transfers control to one of several statements, depending on the value of a condition.
  - `case`: Label where control can be transferred.
  - `default`: Label where control can be transferred if no previous _case_ label received it.
- `continue`: Skips the remaining portion of the enclosing _for_, _range-for_, _while_, or _do-while_ loop body.
- `break`: Terminates the enclosing _for_, _range-for_, _while_ or _do-while_ loop or _switch_ statement to terminate.
- `goto`: Transfers control unconditionally to another location.
- `return`: Terminates the current function and returns the specified value (if any) to the caller.

**Error handling**: Exceptions and asserts.

- `try`: Specifies a try block.
- `catch`: Catches an exception.
- `throw`: Throws an exception.
- `static_assert`: Performs compile-time assertion checking.

**Types**:

- `auto`: Placeholder type specifier. And other uses.
- `void`: Type with an empty set of values. Objects of type void are disallowed, but pointers to void and functions returning void are permitted.
- `signed`: Target type will have signed representation (this is the default if omitted).
- `unsigned`: Target type will have unsigned representation.
- `int`: Fundamental types. Can be signed (default) or unsigned.
- `short`: Target type will be optimized for space and will have at least 16 bits.
- `long`: Target type will have at least 32 bits.
- `long long`: Target type will have at least 64 bits.
- `float`: Single preision floating-point type (usually, [IEEE-754 binary32](https://en.wikipedia.org/wiki/Single-precision_floating-point_format) format).
- `double`: Double precision floating-point type (usually, [IEEE-754 binary64](https://en.wikipedia.org/wiki/Double-precision_floating-point_format) format).
- `long double`: Extended precision floating-point type (doesn't necessarily map to types mandated by IEEE-754).
- `char`: Character representation. Can be signed or unsigned (the default is implementation defined).
- `wchar_t`: Wide character representation. It holds UTF-32 (32 bits) on Linux and many other systems, but holds UTF-16 (16 bits) on Windows.
- `char8_t`: Unsigned character representing UTF-8 (8 bits).
- `char16_t`: Unsigned character representing UTF-16 (16 bits).
- `char32_t`: Unsigned character representing UTF-32 (32 bits).

**OOP**:

- __Custom types__:
  - `enum`: Declaration of an enumeration type.
  - `struct`: Declaration of a struct type (class public by default).
  - `union`: Declaration of a union type (class that can hold only one of its non-static data members at a time).
  - `class`: Declaration of a class (class private by default), scoped enumeration type, type template parameter, or template template.
  - `template`: Declaration of a template class or function.
- `this`: Used in a member function. Pointer (prvalue) to the object on which the member function is called.
- __Access specifiers__: In a member-specification of a class (a), defines accessibility of subsequent members. In a derived class declaration (b), defines the accessibility of inherited members of the subsequent base class (however, base class private members are always inaccessible to the derived class).
  - `private`: In a, it grants public member access. In b, base class public and protected members keep their member access in the derived class.
  - `protected`: In a, it grants protected member access. In b, base class public and protected members are protected members of the derived class.
  - `public`: In a, it grants public member access. In b, base class public and protected members are private members of the derived class.
- `virtual`: As a function specifier, it specifies that a non-static member function is virtual and supports dynamic dispatch. As a base class specifier, it uses virtual inheritance: in a complex inheritance hierarchy, only one instance of the virtual inherited class is created (example: if both X and Y virtually inherit from A, and another class inherits from both X and Y, only one instance of A will be created).
- `volatile`:
  - As a type qualifier, it indicates that a variable's value can changed at any time by something outside the control of the program (hardware, thread...), preventing the compiler from optimizing code by assuming that the variable's value remains unchanged (prevents caching and disables optimization), ensuring its value is always read from memory (and not cached in a register).
  - As a member function qualifier, it ensures a function is safe to call when the object is volatile. A non-volatile member function cannot be called on a volatile object (compilation error), since the function might assume the object's state won't change and could perform optimizations that aren't safe.
- `typename`: Alternative to class used for declaring type template parameters in a template parameter list of a template declaration.
- `friend`: Declared in a class body for granting a function/class access to private and protected members of that class.
- `operator`: Name of an overloaded operator function, user-defined conversion function, allocation function, deallocation function, or literal operator function.

**Type management**:

- `typedef`: Creates type aliases. Type-safe. Scoped. Doesn't support templates. Less flexible than __using__.
- `using`: Creates type aliases. Type-safe. Scoped. Supports template. More flexible than __typedef__.
- `typeid`: Queries information of a type. Used where the dynamic type of a polymorphic object must be known and for static type identification.
- `decltype`: Type specifier that inspects the type of an expression at compile time and yields that type. 
- `namespace`: Declares or uses a namespace block (prevents name conflicts in large projects), or defines a namespace alias (define an alternate name for a namespace).
- `extern`: Declares a variable/function that is defined in another file (hpp) or translation unit (cpp). It tells the compiler that the definition exists elsewhere and it will be linked during the linking stage of the build process. It also links program units written in different programming languages.
- `inline`: Used to suggest the compiler to replace the function call with the function's body to avoid the overhead of a function call (useful for small, frequently used function). If you define a function inside a header file (which gets included in multiple source files), marking it _inline_ ensures that there won't be multiple definition errors at link time.
- `static`:
  - A static variable declared in a function is initialized once and retains its value across multiple function calls.
  - A static global variable has a scope limited to the file (hpp) or translation unit (cpp) in which it is defined. It's not visible to other files, even if they include that header file.
  - A static data member of a class is shared among all objects of the class. There's only one instance of the static variable regardless of the number of class objects.
  - A static member function of a class can be called without creating an object of the class. It has no access to non-static data members or functions of the class.
- `sizeof`: Queries the size (bytes) of an object or type, or the number of elements in a parameter pack. 
- `alignas`: Explicitly specifies the alignment requirement of a type or an object (so it is stored at a specific byte boundary in memory). 
- `alignof`: Queries alignment requirements of a type or object (number of bytes between successive addresses where the type/object can be stored in memory).

**Constants**:

- `const`:
- `constexpr`:
- `constinit`:
- `consteval`:
- `mutable`:

**Pointers**:

- `new`:
- `delete`:
- `nullptr`:

**Casting**:

- `dynamic_cast`:
- `reinterpret_cast`:
- `static_cast`:
- `const_cast`:

**Comparison**:

- `bool`: Integer type that stores one of two values (true, false).
- `true`: prvalue of type bool.
- `false`: prvalue of type bool.
- `!` (`not`):
- `!=` (`not_eq`):
- `&&` (`and`): 
- `&=` (`and_eq`): 
- `||` (`or`):
- `|=` (`or_eq`):
- `^` (`xor`): 
- `^=` (`xor_eq`): 
- `&` (`bitand`): 
- `|` (`bitor`): 

**Others**:

- `~` (`compl`):
- `concept`:
- `co_await`:
- `co_return`:
- `co_yield`:
- `explicit`:
- `export`:
- `noexcept`:
- `register`:
- `requires`:
- `thread_local`:
- `asm`: Used to declare an inline assembly block.

**Other technical specifications**: TM TS (Transactional Memory Technical Specification) and Reflection TS:

- `atomic_cancel` (TM TS): Atomic block that rolls back on exceptions.
- `atomic_commit` (TM TS): Atomic block that commits on exceptions.
- `atomic_noexcept` (TM TS): Atomic block that aborts on exceptions.
- `synchronized` (TM TS): Synchronized block, executed in single total order with all synchronized blocks.
- `reflexpr` (reflection TS): Get certain data from an enum, a class, or its members.


## Identifiers

They are arbitrarily long sequence of digits, underscores, lowercase and uppercase Latin letters, and most Unicode characters. They can be used to name objects, references, functions, enumerators, types, class members, namespaces, templates, template specializations, parameter packs, goto labels, and other entities. Those containing a double underscore (`__`) in any position, or beginning with an underscore followed by an uppercase letter, are always reserved. Those beginning with an underscore are reserved for use as names in the global namespace. 

**Identifiers** with special meaning:

- `final`: 
- `override`: 
- `transaction_safe`: 
- `transaction_safe_dynamic`: 
- `import`: 
- `module`: 


## Preprocessor directives

- `if`:
- `elif`:
- `else`:
- `endif`:
- `ifdef`:
- `ifndef`:
- `elifdef`:
- `elifndef`:
- `define`: Performs global textual substitution before the code is compiled. Since it's not type-safe, for type aliases prefer __using__ or __typedef__.
- `undef`:
- `include`:
- `line`:
- `error`:
- `warning`:
- `pragma`:
- `defined`:
- `__has_include`:
- `__has_cpp_attribute`:
- `export`:
- `import`:
- `module`:
- `_Pragma`: 


## References

- [Keywords](https://en.cppreference.com/w/cpp/keyword)