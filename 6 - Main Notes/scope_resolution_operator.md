
2025-06-28 12:11
Tags: #cpp
Status:

---
# scope_resolution_operator
- it is used to access [[identifiers]] from another [[scope]]
- **scope_name :: identifier**
## Accesing [[namespace]]
## Accesing [[global_variables]]
- usefull when global variable has same name as local 
- **::global_var_name**
## Declaring [[iterators]]
## Define [[class]] member functions outside the class
```
#include <iostream>
using namespace std;

// A sample class
class A {
public:
  
    // Only declaration of 
    // member function
    void fun();
};

// Definition outside class by 
// referring to it using ::
void A::fun() {
  	cout << "fun() called";
}

int main() {
    A a;
    a.fun();
    return 0;
}
```

## Accesing [[static_members]] 
- static memebers can be accessed without creating an object
```
#include<iostream>
using namespace std;

class A {
public:
    static int x; 
};

// In C++, static members must 
// be explicitly defined  like this
int A::x = 1;

int main() {
    
  	// Accessing static data member
  	cout << A::x;
    return 0;
}
```

---
## References
[Geeks](https://www.geeksforgeeks.org/cpp/scope-resolution-operator-in-c/)


