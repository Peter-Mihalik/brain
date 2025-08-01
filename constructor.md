
2025-07-25 17:41
Tags: #cpp #oop
Status:

---
# constructor
- it is special kind of function which is automatically called upon object creation
- it does not create the object (compiler does that before calling constructor)
- constructor can initialize member variables via [[member_initializer_list]] and perform other setup functions
- when constuctor is done we can say that object is consturcted and should be in valid state
```cpp
#include <iostream>

class Foo
{
private:
    int m_x {};
    int m_y {};

public:
    Foo(int x, int y) // here's our constructor function that takes two initializers
    {
        std::cout << "Foo(" << x << ", " << y << ") constructed\n";
    }

    void print() const
    {
        std::cout << "Foo(" << m_x << ", " << m_y << ")\n";
    }
};

int main()
{
    Foo foo{ 6, 7 }; // calls Foo(int, int) constructor
    foo.print();

    return 0;
}
```
## Overloading constructor
- it is possible to overload a constructor, but it should have only one default constructor
```cpp
#include <iostream>

class Foo
{
private:
    int m_x {};
    int m_y {};

public:
    Foo() // default constructor
    {
        std::cout << "Foo constructed\n";
    }

    Foo(int x=1, int y=2) // default constructor
        : m_x { x }, m_y { y }
    {
        std::cout << "Foo(" << m_x << ", " << m_y << ") constructed\n";
    }
};

int main()
{
    Foo foo{}; // compile error: ambiguous constructor function call

    return 0;
}
```

## Explicit defualt constructor
- when we do not provide constructor to a class compiler will auto generate implicit defualt constuctor (with no parameters, no member initializer list and no statemetns)
- when we want to have explicit defualt constructor along with others we can use defualt keyword
```cpp
Foo() = defualt;
```

## Delegating constructor
- when we need overloaded constructors their code can be redundant whick violates [[DRY]]
```cpp
#include <iostream>
#include <string>
#include <string_view>

class Employee
{
private:
    std::string m_name { "???" };
    int m_id { 0 };

public:
    Employee(std::string_view name)
        : Employee{ name, 0 } // delegate initialization to Employee(std::string_view, int) constructor
    {
    }

    Employee(std::string_view name, int id)
        : m_name{ name }, m_id { id } // actually initializes the members
    {
        std::cout << "Employee " << m_name << " created\n";
    }

};

int main()
{
    Employee e1{ "James" };
    Employee e2{ "Dave", 42 };
}
```
- first constructo is not allowed to the any member list initialization
- 


---
## References
[Learn Cpp](https://www.learncpp.com/cpp-tutorial/introduction-to-constructors/)

