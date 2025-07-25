
2025-07-02 02:15
Tags: #cpp
Status:

---
# type_deduction
- there is little redundacy when initializing variables that can be overcome by type deduction with auto keyword
- you can use [[type_suffixes]] to infuence deduction
- type deduction must have something to deduct from
- it drops const specifier, if you want it you must specify it (drops [[reference]] as well)
- for [strings](string) it will default to c strings, if you want std::string or [[string_view]] you have to use suffixes s or sv
- it can be used for return type of the function, but types in all paths must be the same and [[forward_declaration]] doesnt work - it should be probably avoided but sometimes is better (check [[trailing_return_type_syntax]])
```
int main()
{
    auto d { 5.0 }; // 5.0 is a double literal, so d will be deduced as a double
    auto i { 1 + 2 }; // 1 + 2 evaluates to an int, so i will be deduced as an int
    auto x { i }; // i is an int, so x will be deduced as an int

    return 0;
}
```
## Best practise
- use deduction when type doesnt really matter
- use explicit where it is usefull or needed
## Pros
- alignment of multiple initialization helps readeability
- avoiding uninitialized variables
- **avoiding bad performance conversions**
```
std::string_view getString();   // some function that returns a std::string_view

std::string s1 { getString() }; // bad: expensive conversion from std::string_view to std::string (assuming you didn't want this)
auto s2 { getString() };        // good: no conversion required
```
## Cons
- it can be less intuitive to know what type is the variable
- deduced type may change unexpectedly 
```
auto sum { add(5, 6) + gravity };
```


---
## References
[Learn Cpp](https://www.learncpp.com/cpp-tutorial/type-deduction-for-objects-using-the-auto-keyword/)



