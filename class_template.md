
2025-07-13 18:59
Tags: #cpp #oop
Status:

---
# class_template
- is a template definition to instantiating [[class]] types (class type is struct, class or union)
- they can be defined inside [[tpp]] files
```cpp
#include <iostream>

template <typename T>
struct Pair
{
    T first{};
    T second{};
};

template <typename T>
constexpr T max(Pair<T> p)
{
    return (p.first < p.second ? p.second : p.first);
}

int main()
{
    Pair<int> p1{ 5, 6 };
    std::cout << max<int>(p1) << " is larger\n"; // explicit call to max<int>

    Pair<double> p2{ 1.2, 3.4 };
    std::cout << max(p2) << " is larger\n"; // call to max<double> using template argument deduction (prefer this)

    return 0;
}
```
- do some more reading from reference
- because working with pairs of data is common there's standard [[pair]]
- it makes use of [[CTAD]]
## Compilation
- templates are compileted at instantiation that means that compiler has to see the full definition (defined in [[header_file]] or [[tpp]] file)
---
## References
[Learn Cpp](https://www.learncpp.com/cpp-tutorial/class-templates/)


