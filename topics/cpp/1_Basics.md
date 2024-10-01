# C++ basics

## Table of Contents
+ [Keywords](#keywords)
+ [Identifiers](#identifiers)
+ [Preprocessor directives](#preprocessor-directives)
+ [References](#references)


## Keywords

Flow of control:
- `for`:
- `do`:
- `while`:
- `if`:
- `else`:
- `switch`:
- `case`:
- `default`:
- `continue`:
- `break`:
- `goto`:
- `return`:

Exceptions:
- `try`:
- `catch`:
- `throw`:
- `static_assert`:

Types:
- `auto`:
- `void`:
- `int`:
- `signed`:
- `unsigned`:
- `short`:
- `long`:
- `float`:
- `double`:
- `char`:
- `wchar_t`:
- `char8_t`:
- `char16_t`:
- `char32_t`:

OOP:
- `enum`:
- `struct`:
- `union`:
- `class`:
- `template`:
- `this`:
- `private`:
- `protected`:
- `public`:
- `virtual`:
- `volatile`:
- `typename`:
- `friend`:
- `operator`:

Type management:
- `typedef`: Creates type aliases. Type-safe. Scoped. Doesn't support templates. Less flexible than __using__.
- `using`: Creates type aliases. Type-safe. Scoped. Supports template. More flexible than __typedef__.
- `typeid`:
- `decltype`:
- `namespace`:
- `extern`:
- `inline`:
- `static`:
- `sizeof`:
- `alignas`: 
- `alignof`: 

Constants:
- `const`:
- `constexpr`:
- `constinit`:
- `consteval`:
- `mutable`:

Pointers:
- `new`:
- `delete`:
- `nullptr`:

Casting:
- `dynamic_cast`:
- `reinterpret_cast`:
- `static_cast`:
- `const_cast`:

Comparison:
- `bool`: 
- `true`:
- `false`:
- `not` (``):
- `not_eq` (``):
- `and` (``): 
- `and_eq` (``): 
- `or` (``):
- `or_eq` (``):
- `xor` (``): 
- `xor_eq` (``): 
- `bitand` (``): 
- `bitor` (``): 

Others:
- `compl`:
- `concept`:
- `co_await`:
- `co_return`:
- `co_yield`:
- `explicit`:
- `export`:
- `noexcept`:
- `reflexpr`:
- `register`:
- `requires`:
- `synchronized`:
- `thread_local`:
- `asm`: 
- `atomic_cancel`: 
- `atomic_commit`: 
- `atomic_noexcept`: 


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
- `define`: Performs global textual substitution before the code is compiled. Since it's not type-safe, prefer __using__ or __typedef__ for type aliases.
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