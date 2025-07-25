
2025-07-05 22:41
Tags: #cpp
Status:

---
# lvalue
- check [[expresions]] (it is a value category/property of an expresion)
- in short - it evaluets to indentifiable object
- is an expresion that evaluates to indentifiable object (**can be accesed with identifier, reference or poiter and typically have longer life span than one expresion or statement**)
- lvalue is implicitly converted to rvalue (it can be used everywhere where rvalue is expected)
```cpp
int main()
{
    int x { 5 };
    int y { x }; // x is an lvalue expression

    return 0;
}
```
- can be modifiable or non-modifiable lvalue (it's value is const or constexpr)
- check [[rvalue]]


---
## References
[Learn Cpp](https://www.learncpp.com/cpp-tutorial/value-categories-lvalues-and-rvalues/)


