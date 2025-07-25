
2025-07-06 18:28
Tags: #cpp
Status:

---
# increment_operator
```cpp
#include <iostream>
#include <string>

// T& is an lvalue reference, so this overload will be preferred for lvalues
template <typename T>
constexpr bool is_lvalue(T&)
{
    return true;
}

// T&& is an rvalue reference, so this overload will be preferred for rvalues
template <typename T>
constexpr bool is_lvalue(T&&)
{
    return false;
}

// A helper macro (#expr prints whatever is passed in for expr as text)
#define PRINTVCAT(expr) { std::cout << #expr << " is an " << (is_lvalue(expr) ? "lvalue\n" : "rvalue\n"); }

int getint() { return 5; }

int main()
{
    PRINTVCAT(++x);      // lvalue
    PRINTVCAT(x++);      // rvalue
}
```
- ++x is an lvalue
- x++ is an rvalue

---
## References
[Learn Cpp](https://www.learncpp.com/cpp-tutorial/value-categories-lvalues-and-rvalues/)


