
2025-07-05 22:43
Tags: #cpp
Status:

---
# expresions
- combination of literals, variables, operators and function calls that can be executed to produce single value
## Side effects
```cpp
int {x};
x++; // this expresion has sideeffect of inceremnting and it outlives the
expresion
```
## Type category of the expresion
```cpp
int main()
{
    auto v1 { 12 / 4 }; // int / int => int
    auto v2 { 12.0 / 4 }; // double / int => double

    return 0;
}
```

# Value category of the expresion
```cpp
int main()
{
    int x{};

    x = 5; // valid: we can assign 5 to x
    5 = x; // error: can not assign value of x to literal value 5

    return 0;
}
```
- value category of an expresion idicates wheter expresion resolves to a value, function or an object
- prior to c++11 there where only two value categories [[lvalue]] and [[rvalue]]
---
## References
[Learn cpp](https://www.learncpp.com/cpp-tutorial/value-categories-lvalues-and-rvalues/)


