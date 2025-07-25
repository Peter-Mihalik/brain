
2025-07-05 22:53
Tags: #cpp
Status:

---
# rvalue
- check [[expresions]] (it is a value category/property of an expresion)
- in short - it evaluets to a value
- expresion that is not a lvalue
- typically literalls (excluding [c-styled string](string)) and return values of functions or operators that return value
- they are not identifiable (have to be used immediately) and have life span of current expresion 
```cpp
int return5()
{
    return 5;
}

int main()
{
    int x{ 5 }; // 5 is an rvalue expression
    const double d{ 1.2 }; // 1.2 is an rvalue expression

    int y { x }; // x is a modifiable lvalue expression
    const double e { d }; // d is a non-modifiable lvalue expression
    int z { return5() }; // return5() is an rvalue expression (since the result is returned by value)

    int w { x + 1 }; // x + 1 is an rvalue expression
    int q { static_cast<int>(d) }; // the result of static casting d to an int is an rvalue expression

    return 0;
}
```
- 
---
## References



