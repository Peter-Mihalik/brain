
2025-06-29 03:16
Tags: #cpp
Status:

---
# initialization
- assingnig initial value to a variable/memory
- when initialized value isnt being used it produces warning even error
- it can be supressed by [[meybe_unused]] attribute
- for initializing class objects check [[member_initializer_list]]
- check [[aggregate_initialization]]
## Default initialization
- int a ; no initialization
- in most cases it leaves the value "random" - garbage value
## Copy initialization
- int a = 5 ; right value is copied to the left value
- it was inherited from C
- it has fallen out of favor because it was less performant for comple types
- c++17 has somewhat fixed it and it is accepted now
- more readeable
## Direct initialization
- int a (5)
- created mostly to initialize classes
- was replaced by direct-list initiazation
## List initialization
- int a {5}
- modern way of initialzing
- less readeable
- it was introduced to work in almost all cases, consistancy
- it provides abbility to initiaze from list of values {1, 2,  3}
- **one of the biggest advantages is disallowing [[narrowing_converstions]] - (when assigning float to int it produces error)**
## Value initialization
- int a {}
- for simple types it uses zero or value closest to zero
- for classes it usess default values
- **use when it is temporary, when using the value intialize to zero (int a {0})**



---
## References
[Geeks](https://www.geeksforgeeks.org/computer-science-fundamentals/different-ways-to-initialize-a-variable-in-cpp/)
[Learn Cpp](https://www.learncpp.com/cpp-tutorial/variable-assignment-and-initialization/)
[Redit discusion](https://www.learncpp.com/cpp-tutorial/type-deduction-for-objects-using-the-auto-keyword/)


