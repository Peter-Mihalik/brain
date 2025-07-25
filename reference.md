
2025-07-07 15:43
Tags: #cpp
Status:

---
# reference
- reference is an alias to an object being refereced
- it can be used to read and modify an object
- check [[retrun_reference]]
## [[lvalue]] reference
- prior to c++11 it was only kind of reference
- it serves as alias to lvalue for example a variable
- they have to be initialized (bound to some object)
- you cant make reference to void
- they are not objects in c++ (they are not required to occupy storage). In most cases the [[compiler]] replaces all references by referants, but it is not allways possible
- when references cant be modified out by compiler than they are implemented as [[pointer]] which are ultimately just copies of addreses (it can be said that in c++ there is only pass by value)
- you cant reference a reference (because creating reference requires identifiable lvalue)
- in case you need reference that can be reseated or referenced [[reference_wrapper]] is used
```cpp
// regular types
int        // a normal int type (not an reference)
int&       // an lvalue reference to an int object
double&    // an lvalue reference to a double object
const int& // an lvalue reference to a const int object
```
- ampersand does not mean "[pointer](pointers) to"  but "lvalue reference to"
```cpp 
#include <iostream>

int main()
{
    int x { 5 };    // x is a normal integer variable
    int& ref { x }; // ref is an lvalue reference variable that can now be used as an alias for variable x

    std::cout << x << '\n';  // print the value of x (5)
    std::cout << ref << '\n'; // print the value of x via ref (5)

    return 0;
}
```
- attach & to the [type](data_type) rather than [[identifiers]] 
```cpp
#include <iostream>

int main()
{
    int x { 5 };
    int y { 6 };

    int& ref { x }; // ref is now an alias for x

    ref = y; // assigns 6 (the value of y) to x (the object being referenced by ref)
    // The above line does NOT change ref into a reference to variable y!

    std::cout << x << '\n'; // user is expecting this to print 5

    return 0;
}
```
- reference can't be reseated (bind to another object)
## References and referants have independent lifetimes
- you can destroy referent (variable that reference is bound to) before reference or vise versa
- when referant is destroyed first it leaves **dangling reference** (using it leads to undefined behaviour)
## Use cases
### Aruments passed by reference
- [[pass_be_reference]]
- [[in_out_parameters]]
- it is done to avoid making expensive copies ([[string]])
- arguments value can be directly modified
- favor passing as const reference (const reference can hadnle more)
- paasing [[string_view]] is prefered in most cases instead of reference (unless you need to call function that needs cstyled string)
```cpp
#include <iostream>
#include <string>

void printValue(const std::string& y) // type changed to std::string&
{
    std::cout << y << '\n';
} // y is destroyed here

int main()
{
    std::string x { "Hello, world!" };

    printValue(x); // x is now passed by reference into reference parameter y (inexpensive)

    return 0;
}
```
![[pass_value_vs_reference.jpg]]


---
## References
[Learn Cpp](https://www.learncpp.com/cpp-tutorial/lvalue-references/)
[More on passing argumets as strings](https://www.learncpp.com/cpp-tutorial/pass-by-const-lvalue-reference/)


