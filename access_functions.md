
2025-07-23 12:54
Tags: #cpp #oop
Status:

---
# access_functions
- simple fuctions whos job is to get or modify value of [private](access_level) member variable
## getters
- functions that return value of private member variable
- ussually const (they can be called on const and non const members)
- they should return non modifiable value (return by value if non expensive or retrun by [[const]] [[lvalue]] [[reference]])
```cpp
#include <iostream>
#include <string>

class Employee
{
	std::string m_name{};

public:
	void setName(std::string_view name) { m_name = name; }
	const auto& getName() const { return m_name; } // uses `auto` to deduce return type from m_name
};

int main()
{
	Employee joe{}; // joe exists until end of function
	joe.setName("Joe");

	std::cout << joe.getName(); // returns joe.m_name by reference

	return 0;
}
```
## setters
- function that modifies private member variable
- also called [[muttator]]
## Discusion about using them
- if class has no [invariants](invariant) and has lot of member variables (requires a lot of access functions) consider using struct
- prefer implementing behavioues or acctions. For example on class Person prefer implementing Revive and Kill functions instead of simple setters
- implement access functions only when theres good reason for public to access those values
## naming convention
- using set and get prefixes (easy to read, maybe to much typing)
- using same name and relly on [[function_overloading]] (standart library uses this convention)
- **prefixing only setters** (this I like the most)
```cpp
#include <iostream>

class Date
{
private:
    int m_year { 2020 };
    int m_month { 10 };
    int m_day { 14 };

public:
    void print()
    {
        std::cout << m_year << '/' << m_month << '/' << m_day << '\n';
    }

    int getYear() const { return m_year; }        // getter for year
    void setYear(int year) { m_year = year; }     // setter for year

    int getMonth() const  { return m_month; }     // getter for month
    void setMonth(int month) { m_month = month; } // setter for month

    int getDay() const { return m_day; }          // getter for day
    void setDay(int day) { m_day = day; }         // setter for day
};

int main()
{
    Date d{};
    d.setYear(2021);
    std::cout << "The year is: " << d.getYear() << '\n';

    return 0;
}
```


---
## References
[Learn Cpp](https://www.learncpp.com/cpp-tutorial/access-functions/)


