
2025-07-04 22:40
Tags: #cpp
Status:

---
# regex_cpp
- check [[regex]]
- part of the standard library
```
#include <regex>
#include <string>

// replace matches
std::string target {"Hello World!"};
std::string pattern {"Hello"};
std::string replacement {"Hi"};
std::regex reg{pattern}; // initiate regex object
std::regex_replace(target, reg, replacement);

// 

```


---
## References
[Geeks](https://www.geeksforgeeks.org/cpp/replace-text-in-string-using-regex-in-cpp/)


