
2025-07-13 16:36
Tags: #cpp
Status:

---
# scope
- region of visibility of indetifiers
```cpp
int a {5}; // a is global - visible everywhere

int foo(int x) {
	int y = x/2; // y only visible in foo function
	return y;	
}
int main() {
	int z {foo(5)}; // z is visible in main fuction
	std::cout << z + a;
}
```

---
## References



