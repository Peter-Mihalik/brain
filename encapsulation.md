
2025-07-23 13:49
Tags: #cpp #oop
Status:

---
# encapsulation
- it makes use of data hiding techiniques
- it means that member variables of the [[class]] are private and user iteracts with them with predefined interface (public functions)
- c++ standard acts this way
- prefer using non-member functions (check the reference) - mostly when not modifing the state
## Benefits of data hiding
### Reduced complexity
- reduced complexity for using the class (you dont need to know how things are implemented, you just need to know the interface) - it reduces chaneces for mistakes
### Maintaining invariants
- it allows maintaining of [invariants](invariant)
```cpp
#include <iostream>
#include <string>

struct Employee // members are public by default
{
    std::string name{ "John" };
    char firstInitial{ 'J' }; // should match first initial of name

    void print() const
    {
        std::cout << "Employee " << name << " has first initial " << firstInitial << '\n';
    }
};

int main()
{
    Employee e{}; // defaults to "John" and 'J'
    e.print();

    e.name = "Mark"; // change employee's name to "Mark"
    e.print(); // prints wrong initial

    return 0;
}
```
- because name is public it creates a situation when invariant of first letter of the name is violated
```cpp
#include <iostream>
#include <string>
#include <string_view>

class Employee // members are private by default
{
    std::string m_name{};
    char m_firstInitial{};

public:
    void setName(std::string_view name)
    {
        m_name = name;
        m_firstInitial = name.front(); // use std::string::front() to get first letter of `name`
    }

    void print() const
    {
        std::cout << "Employee " << m_name << " has first initial " << m_firstInitial << '\n';
    }
};

int main()
{
    Employee e{};
    e.setName("John");
    e.print();

    e.setName("Mark");
    e.print();

    return 0;
}
```
### Better error handling
- in above exmaple we can get rid of member variable first_initial and replace it with function that returns first initial (we dont have to update the state whenever name changes). But it has new invariant that name cant be empty string which can lead to undefined behaviour. Good thing is that user must only set the name with member function where we can handle such case acordingly
### Changing implementation doesnt break the programs
 - when i decide to change the implementation but interface stays the same, programs using the classes wont brake
### Ease of debugging
- when variables are public it can results to many places to breakpoint when debuging. But when variables are only change in member functions we can only breakpoint them


---
## References
[Learn Cpp](https://www.learncpp.com/cpp-tutorial/the-benefits-of-data-hiding-encapsulation/)
[Non-member functions improve encapsulation Aritice](https://embeddedartistry.com/fieldatlas/how-non-member-functions-improve-encapsulation/)


