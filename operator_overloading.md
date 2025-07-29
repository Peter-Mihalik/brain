
2025-07-13 17:20
Tags: #cpp
Status:

---
# operator_overloading
- it allows to redefine behaviour of operators when working with custom type
- form of [[polymorphism]]
- when overloading an operator, you are difining special function that is called by the compiler when overloaded operator is used
- there is difference between overloading member function and non-member function (member functions take one less argument because there is explicit *this) 
```cpp
struct MyStringLengthCompare
{
    bool operator () (const std::string & p_lhs, const std::string & p_rhs)
    {
        const size_t lhsLength = p_lhs.length() ;
        const size_t rhsLength = p_rhs.length() ;

        if(lhsLength == rhsLength)
        {
            return (p_lhs < p_rhs) ; // when two strings have the same
                                     // length, defaults to the normal
                                     // string comparison
        }

        return (lhsLength < rhsLength) ; // compares with the length
    }
} ;
```

---
## References
[Gemini](https://docs.google.com/document/d/1BgyKlmCTakNgLHTH2wu7KhxGZftCdOJnz474WaGK8io/edit?tab=t.0)


