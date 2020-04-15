# Hash Tables

---

- A data structure that implements an associative array abstract data type, a structure that can map keys to values.
- A hash table uses a hash function to compute an index, also called a hash code, into an array of buckets or slots, from which the desired value can be found.
- Ideally, the hash function will assign each key to a unique bucket.
- In many situations, hash tables turn out to be on average more efficient than search trees or any other table lookup structure.
- Lends itself to memoization and caching.

```
Algorithm	 Average  Worst case
Space         O(n)      O(n)
Search        O(1)      O(n)
Insert        O(1)      O(n)
Delete        O(1)      O(n)
```
