# Depth-First Search (DFS)

- An algorithm for traversing or searching tree or graph data structures
- Starts at the root node and explores as far as possible along each branch before backtracking.
- It would be implemented like a queue, whereas a breadth-first search would be implemented as a stack.
- Class: **Search algorithm**
- Data structure: **Graph**
- Worst-case performance:
  - O(|V| + |E|) for explicit graphs traversed without repetition
  - O(b^d) for implicit graphs with branching factor b searched to depth d
- Worst-case space complexity:
  - O(|V|) if entire graph is traversed without repetition
  - O(longest path length searched) = {\displaystyle O(bd)}O(bd)for implicit graphs without elimination of duplicate nodes
