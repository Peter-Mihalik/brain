
2025-06-24 21:27
Tags: #cpp
Status:

---
# static_library
## About
- practically it's an archive of object files
- at COMPILE time the linker links it to the program (it is the part of the program)
- they produce so called self-contained programs
- alternative is [[dynamic_library]]
##  Pros and cons
### Pros
- self contained
- potentially faster - no overhead of loading and resolving symbols at runtime
- compiler might optimize them heavilly
### Cons
- larger executables
- wasting space if one library is used across many programs
- need recompilation to fix bug or update
- on older system they used to be less memory efficient (multiple programs loading the same code)

---
## References
[Gemini](https://docs.google.com/document/d/1FvCgiPNN3Umfqs7fl41d46lQ9A2GMLoDtqP5eQeix8w/edit?tab=t.0)
[Geeks](https://www.geeksforgeeks.org/difference-between-static-and-shared-libraries/)


