
2025-06-27 19:44
Tags: #cpp
Status:

---
# header_only_libraries
## About
- at compilation there s option to include library in heade only fromat
- it means that i dont have to use -L flag to locate library
- i only have to use -I to specify source of the library
## Drawback
- noticably slower compilation
## Example
- gcc -DFMT_HEADER_ONLY -I /home/pitu/github/vcpkg/installed/x64-linux/include/ fmt.cpp -o fmt


---
## References



