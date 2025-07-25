
2025-06-24 21:40
Tags: #cpp
Status:

---
# dynamic_library

## About
- also known as shared libraries
- it has to be installed on every system the program runs
- executable doesn't contain whole library
- they only have references to the functions and other
- when program starts OS dynamic linker preloads used libraries to the memory
- alternative is [[static_library]]
## Pros
- smaller executables
- easier maintanance and updating (you dont have to recompile whole program, just the libraty)
- that implies better modular development
- program can dynamically at run time load new libraries allowing plugins...
## Cons
- runtime dependecies - fail to run if user doesnt have library correctly installed
- more demanding when loading program - overhead (ussualy negligible)
- version compatibility issues

---
## References
[Gemini](https://docs.google.com/document/d/1FvCgiPNN3Umfqs7fl41d46lQ9A2GMLoDtqP5eQeix8w/edit?tab=t.0)
[Geeks](https://www.geeksforgeeks.org/difference-between-static-and-shared-libraries/)


