
2025-07-23 12:30
Tags: #cpp #oop
Status:

---
# access_level
- it determines who can access the member
- [[structure]] should only have public members to be able to [[aggregate_initialization]]
## public
- default of [[structure]]
- members can be accessed by other members and public (outside of the class type)
## private
- defualt of [[class]]
- members can be accessed only by other members
- class with private members cant be initialized by [[aggregate_initialization]] 
- to set or get private member [[access_functions]] are used
## protected
- 
## Access level on per-class basis
- member function has access to private member variables. This is also true for other instances of the same class when passed to member function
```cpp
#include <iostream>
#include <string>
#include <string_view>

class Person
{
private:
    std::string m_name{};

public:
    void kisses(const Person& p) const
    {
        std::cout << m_name << " kisses " << p.m_name << '\n';
    }

    void setName(std::string_view name)
    {
        m_name = name;
    }
};

int main()
{
    Person joe;
    joe.setName("Joe");

    Person kate;
    kate.setName("Kate");

    joe.kisses(kate);

    return 0;
}
```

---
## References



