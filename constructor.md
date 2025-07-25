
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


---
## References
[Learn Cpp](https://www.learncpp.com/cpp-tutorial/introduction-to-constructors/)

