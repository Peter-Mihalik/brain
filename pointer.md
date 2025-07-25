
2025-07-08 19:29
Tags: #cpp
Status:

# pointer
- is an object (variable) that holds memory address of another [[object]]
- in modern cpp clasical c styled pointers are called raw pointers (dumb pointers)
- they should be allways initialized but dont have to be like [[reference]]
- references should be favored over pointers whenever possible even passing by reference
```
int n {5};
int* n_p {&n};
```
 - size of a pointer is fixed on current machine (based on architecture it has been compiled to) 32/64bit mostly
## Null pointer
```cpp
int* n_p {}; // null pointer created by value initialization
```
- [value initialization](initialization)
- it can be also done using nullptr keyword
- nullptr implicitly converts to false
- 0 or macro from cstddef NULL can be used as well (favor nullptr)
## Constant pointers
```cpp
const int* ptr {&x}; // pointer to const (value of x cant be changed)
int* const ptr {&x}; // const pointer (value of pointer cant be changed, reseated)
const int* const ptr {&x}; // const pointer to const value
```
## Pass by address
- when passing by address  the copy of address is passed
- pass by address should be favored whenever possible
## Optionall arguments
```cpp
void printId(int* id_p = nullptr) {
	if (id_p) {
		std::cout << "Your ID is: " << *id_p;	
	}
	else {
		std::cout << "No ID was provided";	
	}
}
```
- [[function_overloading]] is better alternative
## Reference a pointer
- when you pass a pointer to a function and that function modifies value of the poiter (address it holds, not a value of that address) it does not affect original pointer passed to a function because copy of the pointer is created
- but you can do something like this
```cpp
#include <iostream>

void nullify(int*& refptr) // refptr is now a reference to a pointer
{
    refptr = nullptr; // Make the function parameter a null pointer
}

int main()
{
    int x{ 5 };
    int* ptr{ &x }; // ptr points to x

    std::cout << "ptr is " << (ptr ? "non-null\n" : "null\n");

    nullify(ptr);

    std::cout << "ptr is " << (ptr ? "non-null\n" : "null\n");
    return 0;
}
```
## nullptr
- is of the type std::nullptr_t defined in cstddef and it can only hold nullptr
---
## References
[Learn Cpp](https://www.learncpp.com/cpp-tutorial/introduction-to-pointers/)


