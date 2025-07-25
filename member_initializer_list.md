
2025-07-25 17:51
Tags: #cpp #oop
Status:

---
# member_initializer_list
- check [[initialization]]
- the order of initialization is the order they are specified in class definiton (not in the order in member initializer list)
- error handling or invariant checking can be done in [[constructor]]
```cpp
#include <iostream>

class Foo
{
private:
    int m_x {};
    int m_y {};

public:
    Foo(int x, int y)
        : m_x { x }, m_y { y } // here's our member initialization list
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
    Foo foo{ 6, 7 };
    foo.print();

    return 0;
}
```


---
## References



