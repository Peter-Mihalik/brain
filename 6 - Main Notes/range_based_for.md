
2025-07-02 23:29
Tags: #cpp
Status:

---
# range_based_for
- special type of c++ loop from c++11
- special kind of [[for_loop]] for iterating through containers ([[array]], [[vector]], [[string]], [[list]])
```
for (declaration : range_expresion) {
	// body of the loop
}
```
## range expresion
- expresion that represents sequece of elemets
- it must be either:
	- something that has either .start() and .end() member functions like [[string]] [[vector]]
	- has non-member std::start() and std::end() functios like c-styled arrys and somem [[iterators]]
	- or is an intializer list
## declaration
- here variable that takes value of each element in iteration is declared
- good practise to use const auto
## Examples
- iterating through directory content
```
using namespace std::filesystem
for (const auto& entry : directory_iterator(directory path)) {
	cout << entry.path() << std::end;
}
```

---
## References



