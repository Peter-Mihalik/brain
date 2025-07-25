
2025-07-04 22:39
Tags: #cpp #linux
Status:

---
# regex
- regular expresion are sequences of characters that help create search paterns for text/string manipulation
- check [[regex_cpp]]
## Metacharacters
### Anchors (mathes positions not a charracters)
- ^(caret) ; matches the beggining of the line
- $ ; matches the end of the line
- \b ; word boudary when you want to match cat but not catterpilar
- \B ; non word boudary matches any character that is not a wordboudary
### Quantifiers (specify how many times characters can match)
- \* ; matches zero or more times (b\*a = a, ba, bba)
- + ; matches one or more of preceding character
- ? ; matches zero of none (optional)
- {n} ; matches exactly n times
- {n,} ; n or more accurancies
- {n, m} ; matches from range
### Character classes (sets)
- \[abc] ; matches a or b or c
- \[a-z] ; matches any lowercase latter a-z
- \[0-9] ; digits
- `[a-zA-Z0-9]` : Matches any alphanumeric character.
- \[\^] ; negation (except)
## Shorthand character classes
- \d ; digits
- \D ; any non digit
- \w ; any word character (alphanumeric + underscore)
- \W ; any non word character
- \s ; whitespace character
- \S ; any non withespace character
- . ; any single character
### Grouping
- () ; grouping (ab)+ = ab,abab,ababab...
- | ; or 
## Back references
- ones i created a group I and reference to it by \1, \2...
- 


---
## References
[Geeks](https://www.geeksforgeeks.org/cpp/replace-text-in-string-using-regex-in-cpp/)
[Gemini](https://docs.google.com/document/d/1LdGClxS2hyunCmYdcfyAh9_KFYov4BHVNSbuDjTTIzQ/edit?tab=t.0)
[Online tester](https://regex101.com/)


