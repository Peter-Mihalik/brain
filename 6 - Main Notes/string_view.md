
2025-07-01 01:40
Tags: #cpp
Status:

---
# string_view
- it provides read only access to existing [[string]]
- you should use it for passing strings as arguments
- prefer when writing is not nedded
- it accepts all kinds of strings that will be implicitly converted to string_view
- while the string that is tied to string_view is changed the string_view is changed also
- when string is modified the string_view is invalidated
## Modify the view
- it is possible to modify the view without changing the original string
- .remove_prefix(1) and remove_suffix(1)
- to reverse it you have to reasign the view
- at may remove null-termination
- 
## Miss use of string_view
```cpp
#include <iostream>
#include <string>
#include <string_view>

int main()
{
    std::string_view sv{};

    { // create a nested block
        std::string s{ "Hello, world!" }; // create a std::string local to this nested block
        sv = s; // sv is now viewing s
    } // s is destroyed here, so sv is now viewing an invalid string

    std::cout << sv << '\n'; // undefined behavior

    return 0;
}
```
- another example
```
#include <iostream>
#include <string>
#include <string_view>

std::string getName()
{
    std::string s { "Alex" };
    return s;
}

int main()
{
  std::string_view name { getName() }; // name initialized with return value of function
  std::cout << name << '\n'; // undefined behavior

  return 0;
}
```

---
## References
[Learn Cpp](https://www.learncpp.com/cpp-tutorial/introduction-to-stdstring_view/)


