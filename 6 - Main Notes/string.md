
2025-07-01 01:38
Tags: #cpp
Status:

---
# string
- you can use c-styled strings, but they are not dynamic, input is tricky because of overflow
- you should use std::string 
- you can access member functions
- but making copy is expensive, thats why you should use [[string_view]]
- use std::get_line(std::cin >> std::ws, string) to get input
- std::ws is [[input_manipulator]]
- string manipulation with [[regex]] chech [[regex_cpp]]
  


---
## References
[Learn Cpp](https://www.learncpp.com/cpp-tutorial/introduction-to-stdstring/)


