
2025-06-28 12:45
Tags: #cpp
Status:

---
# static_arrays
- the size has to be know at compile time
- you cant make them bigger
- biggest advatage is [[ConstExpr]], otherwise consideer [[dynamic_arrays]]
## C like arrays
- the name of the array can be treated as constant pointer
- accessing outside bounds results in compilation errror
- int my_array[5] = {1, 2, 3, 4, 5} ; declaration of static array of 5 ints and initialization
- int my_array[5] = {0} ; zero initialization
- int elem = my_array[1] ; accesing elements using index
- when passing them as parameters to functions they are treated as [[pointers]] because of [[array_decay]]
## std::array
- include array
- std::array<int, 5> a = {} ; declaration 
- lenght must be [[ConstExpr]] or numeric litteral
- lenght can be zero (.empty() member fuction to test it)
- it uses [[aggregate_initializations]]
- generally should be at least value initialized
- it can be const and elements are treated that way
- define as [[ConstExpr]] whenever possible othewise consider using [[dynamic_arrays]]
- [[class_template_argument_deduction]] possible and use whenever possible (c++17 above)
```
constexpr std::array a1 = {1, 2, 3, 4}
constexpr std::array a1 = {1.3, 2.4, 3.8, 4.9}
```


---
## References
[Learn Cpp](https://www.learncpp.com/cpp-tutorial/introduction-to-stdarray/)


