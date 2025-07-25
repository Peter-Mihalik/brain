
2025-07-13 22:44
Tags: #cpp
Status:

---
# CTAD (Class Template Argument Deduction)
- from c++17 when instatiating from [[class_template]] you dont have to specify argument types, they will be deducted from litterals
- defaults can be set when defining template
```cpp
template <typename T=int, typename U=int>
struct Pair {
	T first {};
	U second {};
};
pair p1 {1, 3.4} // Types will be deducted 
```
- [[literal_suffixes]] can be used
## Deductions guide
- sometimes compiler cant deduce types for custom types (in c++17, c++20 provides functionality for compiler to deduce types for aggregates)
- deduction guide is neede
```cpp
// templated definition
template <typename T, typename U>
struct Pair {
	T first {};
	T second {};
};
// deduction guide
template <typename T, typename U>
Pair(T, U) -> Pair<T, U>;
```
## Alias template
- we can create type alias for class templates
```cpp
#include <iostream>

template <typename T>
struct Pair
{
    T first{};
    T second{};
};

// Here's our alias template
// Alias templates must be defined in global scope
template <typename T>
using Coord = Pair<T>; // Coord is an alias for Pair<T>

// Our print function template needs to know that Coord's template parameter T is a type template parameter
template <typename T>
void print(const Coord<T>& c)
{
    std::cout << c.first << ' ' << c.second << '\n';
}

int main()
{
    Coord<int> p1 { 1, 2 }; // Pre C++-20: We must explicitly specify all type template argument
    Coord p2 { 1, 2 };      // In C++20, we can use alias template deduction to deduce the template arguments in cases where CTAD works

    std::cout << p1.first << ' ' << p1.second << '\n';
    print(p2);

    return 0;
}
```

---
## References
[Learn Cpp](https://www.learncpp.com/cpp-tutorial/alias-templates/)


