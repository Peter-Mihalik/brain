
2025-07-01 17:03
Tags: #cpp
Status:

---
# type_conversion
- most conversion create new value, they dont modify the old
- i would also like to mention [[type_deduction]] here
## Implicit type conversion
- compiler does this for us
- when asigning int to a double parameter
- it can lose data (converting double to int) - produces warnings
## Explicit conversion
- [[cstyle_conversion]]
- [[static_cast]] ; shuld be used in most cases
- [[dynamic_cast]]
- [[const_cast]]
- [[reinterpret_cast]]


---
## References
[Learn Cpp](https://www.learncpp.com/cpp-tutorial/introduction-to-type-conversion-and-static_cast/)


