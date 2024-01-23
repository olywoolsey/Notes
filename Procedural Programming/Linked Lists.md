#COMP1711 #C
- A linked list is a simple data structure that allows insertion and deletion at any position
- Any item in the list stores some local data values and the location of the next item
- A natural fit for [[Structures]], pointers and functions in C

![[Linked_Lists.png]]
This is simplified but also extends to binary trees or quad trees

## The Data Structures
- top is starting the list
- bottom is creating nodes
```c
// a structure for the data the node stores
typedef struct nodeData {
	int i;
} Data;

// a linked list node structure
typedef struct node {
	Data *data; // the data
	struct node *next; // the link
} Node;
```

## Adding a Node
1. Create the node first
2. adjust the head to point to the node
3. adjust the tail to point to the next node
```c
Node *head = NULL;
```
creating more list:
- Growing our list by adding a node at the head
- Growing our list by adding a node at a given location
- Growing our list by adding a node at the end of the list (the tail)
```c
// creating a node
Node *createNode( Data *data ) {
// allocate memory
	Node *new = (Node *)malloc( sizeof(Node) );
	new->data = data; // assign data to node
	new->next = NULL; // set link to NULL
	
	return new; // the new node
}
```

## De-allocating a Node
```c
// free memory allocated to a node
void freeNode( Node *node ) {
	
	free( node->data ); // deallocate data memory first
	free( node ); // deallocate node memory
	
	return;
}
```

## Adding a node at the Head
```c
// adding a node at the head
Node *addNodeAtHead( Node *head, Node *toAdd ) {
	
	toAdd->next = head; // insert at the head
	
	return toAdd; // the new head node
}
```

## Inserting a Node
- need to know locations of each surrounding nodes to insert and update the links
```c
// adding a node at a location
void addNodeAfter( Node *location, Node *toAdd ) {
	
	toAdd->next = location->next; // link from new node
	location->next = toAdd; // link to new node
	
	return;
}
```

## Deleting a Node
- need to know surrounding nodes to change the links
- make sure to free node from memory
```c
// deleting a node after a location
Node *deleteNextNode( Node *location ) {
	
	Node *removed = location->next; // node to remove
	location->next = removed->next; // link to following node
	
	return removed; // return pointer to removed node
}
```

## Traversal
- visit every node
- perform an operation on every node
- used for:
	- Output contents
	- updating list
	- search for data value
	- deleting list
- 
#### Recursive
```c
// traversing the linked list
void traversal( Node *node ) {
	if( node != NULL ) { // test for tail
		// **your list operation here**
		traversal( node->next ); // next node
	}
	return;
}
```
#### Non-Recursive
```c
// traversing the linked list
void traversal( Node *node ) {
	
	while( node != NULL ) { // the tail link is NULL
		// **your list operation here**
		node = node->next; // next node
	}
	return;
}
```