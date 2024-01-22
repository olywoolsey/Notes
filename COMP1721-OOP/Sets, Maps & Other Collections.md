#COMP1721
## Stack
- LIFO (ʻLast In, First Outʼ)
- Items are pushed onto the top of the stack
- … then popped oﬀ the top, in the reverse order
## Queue
- FIFO (ʻFirst In, First Outʼ)
- Items are added to tail of the queue
- … and removed from the head

## Implementation
- Stacks & queues are both implemented using a deque (pronounced “deck”) –  ʻdouble-ended queueʼ
- Two implementations of deque provided in Java: ArrayDeque and LinkedList
- Use Deque interface to manipulate a deque as a stack (since this specifies push() & pop() methods)
- Use the more restrictive Queue interface if you want it to act strictly as a queue
### Example
```java
Deque<String> stack = new ArrayDeque<>();
stack.push("Alice");
stack.push("Bob");
stack.push("Charlie");
while (!stack.isEmpty()) {
	System.out.println(stack.pop());
}

Queue<String> queue = new ArrayDeque<>();
queue.add("Alice");
queue.add("Bob");
queue.add("Charlie");
while (!queue.isEmpty()) {
	System.out.println(queue.remove());
}
```
#### Output:
Removing from stack:
Charlie
Bob 
Alice

Removing from queue:
Alice
Bob
Charlie

## Associative Collections
- Not sequences; items are not referenced by position
- Instead, we have the idea of a value being looked up using apiece of associated information: the key
- In eﬀect, we have collections of key-value pairs
- Important point: keys are unique and there is only one value associated with each key (although that value could be a list or some other kind of collection)
- Similar to Pythonʼs dictionaries…
### Maps
- The most useful type of associative collection
- Represented by the Map interface
- … with three standard implementations:
- HashMap: fast, but keys are not ordered
- LinkedHashMap: a bit less eﬀicient than HashMap, but preserves the order of key-value insertion
- TreeMap: keeps keys sorted into their ʻnatural orderʼ, or according to the provided comparator
#### HashMap
- Implemented as an array of N buckets – linked lists of Entry objects
- Each Entry object holds key, value and a hashCode of the key
- N is a power of two, initially 16; when 75% of buckets are non-null, array size is doubled and entries are redistributed, to keep lists small
##### HashCode
- A hashCode is computed for the key and the index into the array of buckets is derived from this hashCode
- Linked list in the indexed bucket is searched for an Entry with the matching key
- If we are fetching from the map and an Entry with the matching key is found, we return the value; otherwise, we return null
- If we are storing in the map and a matching Entry is found, we update it with the value we want to store; otherwise, we created a new Entry at the head of the list
#### LinkedHashMap
- like a HashMap but uses a linked list to store the hash 
#### TreeMap
- Implemented as a self-balancing binary search tree
- Goal is to optimise search by maintaining a tree of keys where keys that come before the parentʼs key are to the left and keys that come after are to the right
- Tree re-balances itself after insertions
- this means that insertions take longer but finding items are faster

### Creating a Map
defined as Map<keyType, valuesType> name = ..
```java
Map<String,Integer> map1 = new HashMap<>();
Map<String,Integer> map2 = new LinkedHashMap<>();
Map<String,Integer> map3 = new TreeMap<>();
```
**Note:** key should be an immutable type
(i.e., class should not have any methods that modify object state)

### Iterating Over a Map
```java
Map<String,Integer> map = new HashMap<>();
map.put("apple", 42);
map.put("orange", 34);
map.put("mango", 100);

for (String key: map.keySet()) {
	int value = map.get(key);
	System.out.printf("%s: %d\n", key, value);
}
```

### Map Methods
| name          | use                                              |
| ------------- | ------------------------------------------------ |
| size          | Returns number of key-value pairs in map         |
| isEmpty       | Returns true if map is empty                     |
| containsKey   | Returns true if map contains given key           |
| containsValue | Returns true if map contains given value         |
| get           | Return value associated with given key,or null   |
| getOrDefault  | Returns value for given key or the given default |
| put           | Inserts a new key-value pair or updates a key    |
| remove        | Removes a key-value pair, given the key          |
| clear         | Removes all key-value pairs from map             | 

## Sets
- Set = collection of items that cannot contain duplicates
	- if you input a item already in the set it will not change the set
- Corresponds to mathematical concept of a set
- Can be thought of as a map containing only keys, no values
- use add instead of put
- Manipulated via the Set interface
- … with similar implementations to those for maps
	- HashSet
	- LinkedHashSet
	- TreeSet
