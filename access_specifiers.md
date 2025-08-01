
2025-07-23 12:26
Tags: #cpp #oop
Status:

---
# access_specifiers
- they are used to explicitly set [[access_level]] of members 
```cpp
class Date
{
// Any members defined here would default to private

public: // here's our public access specifier

    void print() const // public due to above public: specifier
    {
        // members can access other private members
        std::cout << m_year << '/' << m_month << '/' << m_day;
    }

private: // here's our private access specifier

    int m_year { 2020 };  // private due to above private: specifier
    int m_month { 14 }; // private due to above private: specifier
    int m_day { 10 };   // private due to above private: specifier
};

int main()
{
    Date d{};
    d.print();  // okay, main() allowed to access public members

    return 0;
}
```
![[access_specifiers.jpg]]

---
## References
[Learn Cpp](https://www.learncpp.com/cpp-tutorial/public-and-private-members-and-access-specifiers/)


