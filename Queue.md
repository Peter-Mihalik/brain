
2025-07-25 16:08
Tags: #data
Status:

---
# Queue
- [[data_structure]] that we can add and remove elements
- it's [[ADT]] is
```
Queue {
	add(Element) - adds element based on type of queue (FIFO/LIFO/PRIORITY)
	remove() - remove value and return it
}
```
## FIFO Queue
- is the most basic form of Queue (queueing dicipline) it acts as FIFO (first in first out) queue. Element which is added first is removed (served) first as well
- FIFO is often emmited
- add and remove are also called enqueue and dequeue
![[fifo_q.jpg]]
## Priority Queue
- elements are removed based on some criteria (for example smallest number)
- much like patients in  hospital emergency room
![[priority_q.jpg]]
## LIFO (Stack)
- last in first out
- new elements are added on top of the stack and are removed first
- add and remove are called push and pop the stack
![[stack.png]]
##  Dequeue
- it is the mix of fifo queue and stack
- elements can be added and removed from front and the back of the Queue
- operations it supports are addFirst(x), addLast(x), removeFirst(), removeLast()

---
## References
[Open book of data structures](https://opendatastructures.org/ods-cpp/1_2_Interfaces.html)


