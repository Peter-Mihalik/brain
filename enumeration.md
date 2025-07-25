
2025-07-13 16:18
Tags: #cpp
Status:

---
# enumeration
- is [[coumpound_types]] whos values are restricted to set of symbolic constants called enumerators
- each enumerator is [[integer]] based on order of definition
- they implicitly convert to integer (when used in cout it prints integer value)
## Unscoped enumerations
- used for better readability when buch of related constants is needed
- help to avoid [[magic_numbers]]
- they dont have to be named but they should be
- interesting use case is to use them as flags/masks when working with [bits](bit) 
```cpp
enum Color {
	red,
	green,
	blue,
};

int main() {
	Color carColor {red};
	return 0;
}
```
- they are named unscoped because they put defined enumerators into same [[scope]] they are defined in (as a result you cant use same enumerator name twice in the same scope)
```cpp
enum Color // this enum is defined in the global namespace
{
    red, // so red is put into the global namespace
    green,
    blue,
};

int main()
{
    Color apple { red }; // my apple is red

    return 0;
}
```
- you can use [[scope_resolution_operator]] but dont have to
- it is good practice to put enumerations to named scope regenios ([[namespace]] or [[class]]) to avoid polluting [global](global_variables) namespace 
## Specify base type
```cpp
enum Color : std::int8_t { // Each enumerator will be 8 bit integer
	black,
	red,
	green,
}
```
## Scoped enumerations
- unscped enumerations can pollute namespaces and can behave sematically incorect as in example bellow
- favor scoped enumerations when you dont need a lot of conversions to int (using enumerators as indeces to arrays)
- there is a usefull [[hack_to_convert_static_enums]]
```cpp
enum Color {
	red, 
	gree,
}
enum Fruit {
	apple,
	bannana,
}
int main() {
	Color color {red};
	Fruit fruit {apple};
	if (color == fruit) {// Compiler implicitly converts enums to integers
		std::cout << "They are the same\n";
	}
}
```
- to prevent these problems scoped (class) enums were introduced
- they wont implicitly convert to integers and enumerators will be placed in enum scope not in the scope where enum was defined

```cpp
#include <iostream>
int main()
{
    enum class Color // "enum class" defines this as a scoped enumeration rather than an unscoped enumeration
    {
        red, // red is considered part of Color's scope region
        blue,
    };

    enum class Fruit
    {
        banana, // banana is considered part of Fruit's scope region
        apple,
    };

    Color color { Color::red }; // note: red is not directly accessible, we have to use Color::red
    Fruit fruit { Fruit::banana }; // note: banana is not directly accessible, we have to use Fruit::banana

    if (color == fruit) // compile error: the compiler doesn't know how to compare different types Color and Fruit
        std::cout << "color and fruit are equal\n";
    else
        std::cout << "color and fruit are not equal\n";

    return 0;
}
```
- comparison will throw an error
- class is one of the most [overloaded](overloading) keyword in c++ (can have different meaning) it doesnt mean that enum class is of type [[class]]
- enum struct can be also used but it is not prefered
- you can use [[static_cast]]  or [[to_underlying]] to convert to integer when needed
- you can import enumerators by:
```cpp 
using enum Color
```


---
## References
[Learn Cpp](https://www.learncpp.com/cpp-tutorial/unscoped-enumerations/)


