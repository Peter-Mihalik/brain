
2025-06-28 12:57
Tags: #cpp
Status:

---
# array_decay
- usually accurs when passing array as a parameter to a function
- sizeof(array) changes because it is treated as simple pointer to the first element
```
// C++ code to demonstrate prevention of
// decay of array
#include<iostream>
using namespace std;

// A function that prevents Array decay
// by passing array by reference
void fun(int (&p)[7])
{
    // Printing size of array
    cout << "Modified size of array by "
            "passing by reference: ";
    cout << sizeof(p) << endl;
}

int main()
{
    int a[7] = {1, 2, 3, 4, 5, 6, 7,};

    // Printing original size of array
    cout << "Actual size of array is: ";
    cout << sizeof(a) <<endl;

    // Calling function by reference
    fun(a);

    return 0;
}
```
Output:
```
Actual size of array is: 28
Modified size of array is by  passing by value: 8
```

---
## References
[Geeks](https://www.geeksforgeeks.org/what-is-array-decay-in-c-how-can-it-be-prevented/)


