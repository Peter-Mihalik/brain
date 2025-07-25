
2025-07-13 18:32
Tags: #cpp
Status:

---
# overload_to_print_struct
- cout cant print struct by default
- that's why it is usefull to [overload](overloading) << operator
```cpp
#include <iostream>

struct Employee
{
    int id {};
    int age {};
    double wage {};
};

std::ostream& operator<<(std::ostream& out, const Employee& e)
{
    out << e.id << ' ' << e.age << ' ' << e.wage;
    return out;
}

int main()
{
    Employee joe { 2, 28 }; // joe.wage will be value-initialized to 0.0
    std::cout << joe << '\n';

    return 0;
}
```


---
## References
[Learn Cpp](https://www.learncpp.com/cpp-tutorial/struct-aggregate-initialization/)


