
2025-07-08 20:29
Tags: #cpp
Status:

---
# retrun_reference
- when returning by reference it is needed to ensure that the object bound to reference isnt destroyed before reference is still in used. It can create [dangling reference](reference)
```cpp
#include <iostream>
#include <string>

const std::string& getProgramName() // returns a const reference
{
    static const std::string s_programName { "Calculator" }; // has static duration, destroyed at end of program

    return s_programName;
}

int main()
{
    std::cout << "This program is named " << getProgramName();

    return 0;
}
```
- in this example [[static]] keyword ensures that s_programName is destroyed at the end of the program
## Avoid returning non-const non-static variables by reference
- problematic program
```cpp
#include <iostream>
#include <string>

const int& getNextId()
{
    static int s_x{ 0 }; // note: variable is non-const
    ++s_x; // generate the next id
    return s_x; // and return a reference to it
}

int main()
{
    const int& id1 { getNextId() }; // id1 is a reference
    const int& id2 { getNextId() }; // id2 is a reference

    std::cout << id1 << id2 << '\n';

    return 0;
}
```
- it prints 22 because both function calls are tied to the same reference
## Returning parameters by reference
- it is okay
```cpp
#include <iostream>
#include <string>

// Takes two std::string objects, returns the one that comes first alphabetically
const std::string& firstAlphabetical(const std::string& a, const std::string& b)
{
	return (a < b) ? a : b; // We can use operator< on std::string to determine which comes first alphabetically
}

int main()
{
	std::string hello { "Hello" };
	std::string world { "World" };

	std::cout << firstAlphabetical(hello, world) << '\n';

	return 0;
}
```


---
## References
[Learn Cpp](https://www.learncpp.com/cpp-tutorial/return-by-reference-and-return-by-address/)


