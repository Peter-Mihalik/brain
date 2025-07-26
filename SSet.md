
2025-07-26 12:58
Tags: #data
Status:

---
# SSet
- it stores element in order
- ordering is done by compare method
![[sset_compare.jpg]]
- it has the same [[ADT]] as [[USet]] with one difference in find method
	- find the smallest element $y$ such that $y>=x$. Return $y$ if such element exists or null
	- this is called succesor search (returns meaningfull result even if x doesnt exastly match y)
	- it is slower (logarithmic complexity compared to konstant time of the USet.find(x)) and it has more complex implementation
- [[Uset]] should be preffered over SSet unless extra functionality provided by find (succesor search) is needed


---
## References
[Open data  structures](https://opendatastructures.org/ods-cpp/1_2_Interfaces.html)


