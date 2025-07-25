
2025-06-23 02:06
Tags:  #cpp
Status:

---
# pragma once

## Usage
- Used for including file only once to avoid conficts at compilation
- Alternative to [[Header Guards]]
- Inside header file
		# pagma once
		typedef struct {int number} age;

## Cons
- I think it is not part of the standard
- It has some  issues:
	- It is not easy to idetify identical files (because of links and so on)
## USE HEADER GUARDS


---
## References
[Good wikipedia about pros and cons](https://en.wikipedia.org/wiki/Pragma_once)


