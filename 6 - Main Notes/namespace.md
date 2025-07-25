
2025-06-28 11:45
Tags: #cpp
Status:

---
# namespace
- they are used to split code into different logical named parts
- to avoid name conflicts
- they make code more modular
- they can be nested
- names are acced by using [[scope_resolution_operator]] 
## Create namespace
```
namespace my_namespace {
	void foo() {
	
	}
}
int main() {
	my_namespace::foo();
	return 0;
}
```
- i can use **using my_namespace::foo** to use this function  in current scope without retyping name of the namespace
- or **using namespace my_namespace** to automatically use functions from that namespace
- i can "rename namespaces" - **namespace shrt=my_namespace**
## Global namespace
- everything outside any namespace is considered to be part of global namespace
- it can be accesd by **::foo()**
## Extending namespace
- i can extend same way as I was creating it
## Inline namespace
- members are accesible without specifing the namespace name
```
inline namespace inline_space {
	void Dysplay() {
	}
}
```
## Anonymous namespace
- namespaces without name
- ensures that they are limited to current file
---
## References
[Geeks](https://www.geeksforgeeks.org/namespace-in-c/)


