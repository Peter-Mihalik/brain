
2025-06-23 02:20
Tags: #cpp
Status:

---
# cmake
# About
- To manage building system of cpp projects
- It basically generates [[Makefile]]
- Configureted by [[CMakeLists.txt]] file
- It can also use other tools not only makefile e.g [[Ninja]]
- it creates platform specific makefiles (on Windows [[MSBuild]])
## Example of simple CMakeLists.txt
```
cmake_minimum_required(VERSION 2.8.11)
# Name of the project
set(NAME test)
project(${NAME})

set(SOURCES main.cpp error.h erroe.cpp external.cpp)
add_executable(${NAME} ${SOURCES})
```
- More details about [[CMakeLists.txt]]
## Usage
- make build directory
-  call cmake


---
## References



