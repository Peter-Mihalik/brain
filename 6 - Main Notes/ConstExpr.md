
2025-06-22 21:41
Tags:  #cpp
Status:

---
# ConstExpr
![[constexpr.jpg]]
- they must be evaluated at compile time
- they are used for [[compile_time_optimalization]]
- in case when constant expresion is not required compiler can choose whether it will be evaluated at compile time
- only integral values can be used as contant expresion initializers
```
const int x { 3 + 4 }; // constant expression 3 + 4 must be evaluated at compile-time
int y { 3 + 4 };       // constant expression 3 + 4 may be evaluated at compile-time or runtime
```
- x is const that means it can be used in const expresion so it has to be evaluated at compile time, otherwise it would be unkown hence not usable in const expresion
## const vs constexpr
- **const** means that object value cant be changed after initialization. Value might be know at compile time, but can be evaluated at runtime 
- `constexpr` means that the object can be used in a constant expression. The value of the initializer must be known at compile-time. The constexpr object can be evaluated at runtime or compile-time
- **BEST PRACTISE** any constant value that can be initialized with constant expresion initializer - to ensure evaluation at compile tim`e
## Examples of constant and nonconstant expresions
```
#include <iostream>

int getNumber()
{
    std::cout << "Enter a number: ";
    int y{};
    std::cin >> y; // can only execute at runtime

    return y;      // this return expression is a runtime expression
}

// The return value of a non-constexpr function is a runtime expression
// even when the return expression is a constant expression
int five()
{
    return 5;      // this return expression is a constant expression
}

int main()
{
    // Literals can be used in constant expressions
    5;                           // constant expression
    1.2;                         // constant expression
    "Hello world!";              // constant expression

    // Most operators that have constant expression operands can be used in constant expressions
    5 + 6;                       // constant expression
    1.2 * 3.4;                   // constant expression
    8 - 5.6;                     // constant expression (even though operands have different types)
    sizeof(int) + 1;             // constant expression (sizeof can be determined at compile-time)

    // The return values of non-constexpr functions can only be used in runtime expressions
    getNumber();                 // runtime expression
    five();                      // runtime expression (even though the return expression is a constant expression)

    // Operators without constant expression operands can only be used in runtime expressions
    std::cout << 5;              // runtime expression (std::cout isn't a constant expression operand)

    return 0;
}
```
```
// Const integral variables with a constant expression initializer can be used in constant expressions:
const int a { 5 };           // a is usable in constant expressions
const int b { a };           // b is usable in constant expressions (a is a constant expression per the prior statement)
const long c { a + 2 };      // c is usable in constant expressions (operator+ has constant expression operands)

// Other variables cannot be used in constant expressions (even when they have a constant expression initializer):
int d { 5 };                 // d is not usable in constant expressions (d is non-const)
const int e { d };           // e is not usable in constant expressions (initializer is not a constant expression)
const double f { 1.2 };      // f is not usable in constant expressions (not a const integral variable)
```
## constexpr varibles
- when using const to initialize variables it might not always be clear whether it is actually a constant expresion and hence whether it will be evaluated at compile time
- and it also does not produce error when initializing const variable with non constant expresion initializer
```
const int d { someVar };    // not obvious whether d is usable in a constant expression or not
const int e { getValue() }; // not obvious whether e is usable in a constant expression or not
```
- to ensure all of that constexpr keyword can be used
- constexpr int a {5}
- producing error
- it works with non integral types
- non constexpr function return is not constant expresion
## constexpr functions
- it is a function that can be called in constant expresion
- to be eligible for compile time execution all parameters must be constant expresions
```
#include <iostream>

int max(int x, int y) // this is a non-constexpr function
{
    if (x > y)
        return x;
    else
        return y;
}

constexpr int cmax(int x, int y) // this is a constexpr function
{
    if (x > y)
        return x;
    else
        return y;
}

int main()
{
    int m1 { max(5, 6) };            // ok
    const int m2 { max(5, 6) };      // ok
    constexpr int m3 { max(5, 6) };  // compile error: max(5, 6) not a constant expression

    int m4 { cmax(5, 6) };           // ok: may evaluate at compile-time or runtime
    const int m5 { cmax(5, 6) };     // ok: may evaluate at compile-time or runtime
    constexpr int m6 { cmax(5, 6) }; // okay: must evaluate at compile-time

    return 0;
}
```
---

## References
[Learn Cpp constant expresions](https://www.learncpp.com/cpp-tutorial/constant-expressions/#whywecare)
[Learn cpp constexpr variables](https://www.learncpp.com/cpp-tutorial/constexpr-variables/)


