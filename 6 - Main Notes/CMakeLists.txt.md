
2025-06-23 02:28
Tags: #cpp
Status:

---
# CMakeLists.txt
## About
- To configure cmake
- platform independent
## Simple Example
```
cmake_minimum_required(VERSION 2.8.11)
# Name of the project
set(NAME test)
project(${NAME})

set(SOURCES main.cpp error.h erroe.cpp external.cpp)
add_executable(${NAME} ${SOURCES})
```
## Options
- -D ; define (example -DCMAKE_TOOLCHAIN_FILE=/path/ - for linking libraries)
## Comands
- project(/name/) ; name the project
- set(CMAKE_CXX_STANDARD 17) ; set cpp standard
- find_package(/package_name/ CONFIG REQUIRED) ; search for package
- add_executable(/name/ /source_files/) ; create executable
- target_link_libraries(/lib_name/ PRIVATE /fmt::fmt-header-only) ; add libraries last option is for header only
## Linking_libraries
```
if(NOT DEFINED CMAKE_TOOLCHAIN_FILE AND DEFINED ENV{CMAKE_TOOLCHAIN_FILE})
   set(CMAKE_TOOLCHAIN_FILE $ENV{CMAKE_TOOLCHAIN_FILE})
endif()
```


---
## References
[Source from redit](https://cliutils.gitlab.io/modern-cmake/chapters/basics.html)
[Book on cmake](https://crascit.com/professional-cmake/)

