# Data Structures
---
- **compound data** is data items that are grouped together.
- **Big O Notation** is basically a measure of how well an operation scales.

---
## Linked Lists
- A **node** is the atomic unit of linked list which contains a value and a pointer.
- The **pointer** connects you to the next node in the linked list change.
- The **head** is the first node in the list.
- The **tail** is the last node in the list. It does not have a pointer.

### Pros of Linked Lists
- Really good at adding new nodes and deleting nodes.
  - We just change where the next pointer is pointing
  - 
### Cons of Linked Lists
- Not good at retrieving nodes or searching.
  - This is because each node is only aware of the node next to it.

---
## Array
- A continuous block of cells in the computer memory.
- By keeping track of the memory locations it can instantly locate any item inside of it.

### Pros of Arrays
- Really good at retrieving items.
  
### Cons of Arrays
- Adding items is not always efficient because we might have to move the array to a new place so it fits.
  - Luckily this happens under the hood in high level languages.

---
## Hash Table
- This is known as an **object** in JavaScript or a **dictionary** in Python.
- You give the hash table a word (or key) and it will return the value.
- The key is run through a hashing function that spits out a memory location for you.
- Under the hood it works a lot like an array but the memory locations don't have to be next to each other.

### Pros of Hash Tables
- Really good at removing, deleting and retrieving items.

### Cons of Hash Tables
- **Collisions** - depending on the hashing algorithm you use, two keys could hash to the same location.

---
## Stack
- Last in first out.
- Kind of like arrays with a few additonal features.
- **push** is when you add an item on the top of the stack.
- **pop** is when you take an item off the top of the stack.
- **call stack** is how every language keeps track of the functions that have been called.
- Really important for an algorithm known as **Depth-first search**.

### Pros of Stacks
- Really efficient add and remove

### Cons of Stacks
- Limited use cases

---
## Queue
- Last in last out.
- Kind of like arrays with a few additonal features.
- **enqueue** is when you add an item to the end of the queue.
- **dequeue** is when you remove an item from the front of the queue.
- Really important for an algorithm known as **Breadth-first search**.

### Pros of Stacks
- Really efficient add and remove

### Cons of Stacks
- Limited use cases

---
## Graphs
- Similar to linked lists where nodes are point to other nodes but the pointers are called **edges**
- **Edges** can have weights (or numbers) inside of them.
- Social media networks are stored as graphs.

---
## Trees
- A special kind of hierarchical graph where the data expands out in one direction.
- These can be used to represent things like a family tree or an HTML tree with nested elements.
- A **binary search tree** has really specific rules that allow us to do things like search really efficiently.
  - Each node can only have up to two children (left and right)
  - The **left** has to be less than the node and the **right** has to be more.

### Cons of Trees
- If you add elenents in a weird order the tree can become very unbalanced and you lose some of the optimization advantages.