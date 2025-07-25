
2025-07-13 18:22
Tags: #cpp
Status:

---
# structure
- is [program_defined_type](program_defined_types) that helps to organize variables tied together in logical way
- it is [[heterogenic]] [[aggregate_types]]
- items ale called members
## Defining struct
```cpp
include <string>
using std
struct Employee {
	string name {}; // memeber of type string which is value initialized
	string email {};
	int age {};
	bool emplyed {true}; // default member initialization
};

int main() {
	Employee e1 {"Peter", "pitu@gmail.com", 22}; // aggregate initialization
	cout << e1.name << " " << e1.email << " " << e1.age << endl;
	return 0;
}
```
- it uses [[aggregate_initialization]]
- it is usefull to [[overload_to_print_struct]]
- allways use default initialization
- in most case we want structs to be owners of their data. It is enusured by not using references, pointers or views
## Designated initializers
- when initializing from value list the order is crucial
- it can lead to problems when adding new members
```cpp
struct Foo
{
    int a{ };
    int b{ };
    int c{ };
};

int main()
{
    Foo f1{ .a{ 1 }, .c{ 3 } }; // ok: f1.a = 1, f1.b = 0 (value initialized), f1.c = 3
    Foo f2{ .a = 1, .c = 3 };   // ok: f2.a = 1, f2.b = 0 (value initialized), f2.c = 3
    Foo f3{ .b{ 2 }, .a{ 1 } }; // error: initialization order does not match order of declaration in struct

    return 0;
}
```

## Size of the struct
- typically the size of struct is sum of members but not allways
- for performance reasons compiler sometimes adds paading [read more](https://en.wikipedia.org/wiki/Data_structure_alignment)
- **you can minimize padding by organizing memebers in decreasing order (largest on top)**

---
## References
[Learn Cpp](https://www.learncpp.com/cpp-tutorial/struct-aggregate-initialization/)
[Sumary](https://www.learncpp.com/cpp-tutorial/alias-templates/)


