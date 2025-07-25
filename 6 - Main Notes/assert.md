
2025-06-30 18:39
Tags: #cpp
Status:

---
# assert
- assertion is techinique for ensuring conditions (for example in function when we divide with one parameter i should ensure it is not zero)
- assertion is an expresion that evaluates to true, if false program is terminated by [[std::abort]] and message is writen to stderr
- main reason to use them is for debugging and finding bugs quickly
- in C++ they are implemeted as preprocesor directive
- they can also be used for not implemented features
- favor [[static_assert]] when possible
- they should not be present in production build - little less performance
- they do not replace error handling. If there is a way something might cause error in production there should be error handling for that
## Usage
```
#include <cassert> // for assert()
#include <cmath> // for std::sqrt
#include <iostream>

double calculateTimeUntilObjectHitsGround(double initialHeight, double gravity)
{
  assert(gravity > 0.0); // The object won't reach the ground unless there is positive gravity.

  if (initialHeight <= 0.0)
  {
    // The object is already on the ground. Or buried.
    return 0.0;
  }

  return std::sqrt((2.0 * initialHeight) / gravity);
}

int main()
{
  std::cout << "Took " << calculateTimeUntilObjectHitsGround(100.0, -9.8) << " second(s)\n";

  return 0;
}
```
## More descriptive asserts
```
assert(found && "Element wanst found in array")
```
## Disable asserts
- they should not be present in production build
- disable by
```
#define NDEBUG
```
---
## References
[Learn Cpp](https://www.learncpp.com/cpp-tutorial/assert-and-static_assert/)


