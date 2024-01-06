#COMP2711 #DataStructures 
*(Special type of [List](Lists.md))*
A data structure which has front end and rear end and supports only two operations:
- Enqueue: add to the rear of the queue
- Dequeue: delete from the from of the queue
- This type of queue is a **FIFO**
***Example:** Managing requests on a shared resource (e.g., CPU)*
## Properties
- Easy to implement
- For both implementations (array or linked-list), enqueue/dequeue operations are fast: O(1)
- Often used in:
	- Search algorithms
	- Time-driven simulation
	- Scheduling
## Implementations
### Arrays
1. Q[0] is the front of the queue
	- Enqueue adds to the end so takes O(1) time
	- Dequeue will need to shuffle down all the items so will take O(n) time
2. Q[0] is allowed to drift
	- Every-time enqueue is called the array moves towards max-length and will never shrink
	- Enqueue and Dequeue are O(1) time
3. Drifts but is wraps around (circular array implementation):
	-  Enqueue and Dequeue are O(1) time
	- As long as $n < maxlength$ this will work
### Linked List
- To maintain efficiency for enqueue there will be links from front-to-rear and rear-to-front
- Enqueue and Dequeue are O(1) time

## Comparison
| Circular Array Implementation | Linked List Implementation |
| --- | --- |
| An array implementation uses statically allocated memory. It prevents the enqueue operation from adding an item if the size limit has been reached. | A linked list implementation requires additional memory for references |
All operations take constant time O(1)