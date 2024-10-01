# Container basics

## Table of Contents
+ [Container library](#container-library)
+ [Operations](#operations)
+ [Definition and initialization](#definition-and-initialization)
+ [Iterators](#iterators)


## Container library

**Container**: Holds a collection of objects of a specified type. Two types:

**Sequential (non-linked or linked)**: Holds elements whose position corresponds to the positions in which the elements are added to the container.

**Associative (ordered or unordered)**: Holds elements whose positions depend on a key associated with each element.

The library provides 3 **adaptors**, which adapt a container type by defining a different interface to the container’s operations.

The container classes share a common interface, which each container extends in its own way. Each kind of container offers different set of performance and functionality trade-offs.

In general, each container is defined in a header file with the same name as the type (`<deque>`, `<list>`, etc.). The containers are **class templates**. We must supply additional information to generate a particular container type (usually, the element type).

Almost any type can be used as the element type of a **sequential container** (even another container).

```
list‹Sales_data› a;
deque‹double› b;
vector‹vector‹string›› c;
```

Some container operations require certain element types. We can define a container for a type that doesn’t support an operation-specific requirement, but won’t be able to use that operation.

Example: The sequential container constructor that takes a size argument uses the element type’s default constructor. If the element type has no default constructor, we won’t be able to construct a container using only an element count.

```
vector<noDefault> v1(10, init);
vector<noDefault> v2(10);          // error: No element initializer supplied
```


## Operations

Some operations are provided by all container types, others only by one type of container (sequential, associative, unordered associative), others are specific to a smaller subset of containers. The operations below are provided by all container types (unless declared otherwise).

**Type aliases**

- **Iterators**
  - `iterator`: Type of iterator for this container type
  - `const_iterator`: Iterator that can read but not change its elements
- **Sizes**
  - `size_type`: Unsigned int big enough to hold the size of the largest possible container of this type
  - `difference_type`: Signed type big enough to hold the distance between two iterators
- **Types**
  - `value_type`: Element type alias.
  - `reference`: Element’s lvalue type (i.e., `value_type&`)
  - `const_reference`: Element’s const lvalue type (i.e., `const value_type&`)
- **Construction**
  - `C c`: Default constructor, empty container
  - `C c1(c2)`: Construct c1 as a copy of c2
  - `C c(b, e)`: Copy elements from the range denoted by iterators b and e (not valid for `std::array`)
  - `C c{a,b,c...}`: List initialize c
- **Assignment and swap**
  - `c1 = c2`: Replace elements in c1  with those in c2
  - `c1 = {a,b,c...}`: Replace elements in c1 with those in the list (not valid for array)
  - `a.swap(b)` or `swap(a, b)` (preferred): Interchange contents of two containers in constant time (excepting arrays, element’s are not swapped, internal structures are). Since elements aren’t moved, iterators, references, and pointers aren’t invalidated.
- **Size**
  - `c.size()`: Number of elements in c (not valid for forward_list)
  - `c.max.size()`: Maximum number (or bigger) of elements c can hold
  - `c.empty()`: false if c has any elements, true otherwise
- **Add/Remove elements** (not valid for std::array) (these operations’ interfaces varies by container type)
  - `c.insert(args)`: Copy element/s into c
  - `c.emplace(inits)`: Construct an element in c
  - `c.erase(args)`: Remove element/s
  - `c.clear()`: Remove all elements from c. Returns void
 - **Equality**
  - `==`,  `!=`: Equality operators
- **Relational operators**: Performs a pairwise comparison of elements.
  - `‹`,  `‹=`,  `›`,  `›=`: Relational operators (not supported by unordered associative containers)
- **Get iterators**
  - `c.begin()`,  `c.end()`: Return iterator to the first, one past the last element
  - `c.cbegin()`,  `c.cend()`: Return `const_iterator`
- **Reversible containers** (not valid for std::forward_list)
  - `reverse_iterator` (provided by most containers): Iterator that addresses elements in reverse order (inverts operators meaning).
  - `const_reverse_iterator`: Reverse iterator that cannot write the elements
  - `c.rbegin()`,  `c.rend()`: Return iterator to the last, one past the first element in c
  - `c.crbegin()`,  `c.crend()`: Return `const_reverse_iterator`

Examples:

```
list<string>::iterator iter;
vector<int>::difference_type count;
```

## Definition and initialization

Every container type defines a default **constructor**. It creates (except array) an empty container of the specified type. The other constructors take arguments that specify (except array) the size of the container and initial values of the elements.

**Initializing a container as a copy of another**

```
list<string> authors = {"John", "Steve", "Austen"}
vector<const char*> articles = {"a", "an", "the"}
```

Two ways:

- **Directly copy the container**: The container and element types must match (`list<string> list1(authors)`).

```
list<string> list2(authors);
deque<string> list3(authors);    // error: container type doesn't match
vector<string> words(articles);  // error: elements type doesn't match
```

**Copy a range of elements using 2 iterators** (array can’t): The container and element types can differ, as long as the elements can be converted (`deque<string> list2(authors.begin()+3, authors.end())`).

**List initialization**

```
list<string> authors = {"Milton", "Cervantes", "Austen"};
vector<const char*> articles = {"a", "an", "the"};
```

The initializer list implicitly specifies the size of the container (except the `array`).