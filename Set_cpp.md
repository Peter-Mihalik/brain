
2025-07-29 19:47
Tags: #cpp #data
Status:

---
# Set_cpp
- stores unique elements in order
- updates are not possible

## Different ways to insert element
- one element
	- .insert(element) ; O (log n)
- [iterator](iterators) range
	- set_name.insert(Iterator starting, Iterator ending);
- [initializer list](initialization)
	- set_name.insert({element1,element2,element3,element4});
## Accesing elements
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    set<int> s = {1, 4, 2, 3, 5};

    // Accessing first element
    auto it1 = s.begin();
    
    // Accessing third element
    auto it2 = next(it1, 2);
    
    cout << *it1 << " " << *it2;
    return 0;
}
```
## Finding elements
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    set<int> s = {1, 4, 2, 3, 5};

    // Finding 3
    auto it = s.find(3);
    
    if (it != s.end()) cout << *it;
    else cout << "Element not Found!";
    return 0;
}
```
## Complexity
![[set_complexity.jpg]]

---
## References
[Geeks](https://www.geeksforgeeks.org/cpp/set-in-cpp-stl/)
[Geeks - initializing](https://www.geeksforgeeks.org/cpp/different-ways-to-insert-elements-in-set-in-cpp-stl/)



