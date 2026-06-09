# Unit V: Data Structures - MCQ Bank

Master Arrays, Linked Lists, Stacks, Queues, Trees, Graphs, Hashing, Heaps, Tries, and Disjoint Sets with these 165 solved, high-probability Multiple Choice Questions.

---

## 🔷 Topic 1: Arrays & Linked Lists

#### Q1. Which of the following is the primary advantage of an Array over a Linked List?
- A) Dynamic memory allocation
- B) $O(1)$ random access time
- C) $O(1)$ insertion at any position
- D) Low memory overhead for pointers
- **Answer: ✅ B**
- **Explanation**: Arrays store elements contiguously, allowing direct index calculations ($O(1)$ access). Linked lists require traversing pointers sequentially ($O(N)$ access).

#### Q2. In a Singly Linked List, inserting a new node at the beginning (head) of a list of size $N$ takes how much time?
- A) $O(1)$
- B) $O(N)$
- C) $O(\log N)$
- D) $O(N \log N)$
- **Answer: ✅ A**
- **Explanation**: Inserting at the head requires creating a node, pointing its next pointer to the current head, and updating the head pointer. This takes $O(1)$ constant time regardless of list size.

#### Q3. What is the main characteristic of a Doubly Linked List (DLL)?
- A) The last node points back to the first node
- B) Each node contains two data fields
- C) Each node contains pointers to both the next and the previous nodes, enabling bidirectional traversal
- D) It does not support deletion
- **Answer: ✅ C**
- **Explanation**: DLL nodes store data, a `next` pointer, and a `prev` pointer. Singly linked lists only store data and a `next` pointer.

#### Q4. In a Circular Singly Linked List, the `next` pointer of the last node points to:
- A) NULL
- B) The second node
- C) The head (first) node
- D) A random memory location
- **Answer: ✅ C**
- **Explanation**: In circular lists, the last node points back to the head node, forming a closed loop.

#### Q5. Array insertion at a random index in the worst case takes $O(N)$ time because:
- A) Memory must be reallocated
- B) Elements must be shifted to make room for the new element
- C) Pointers must be updated
- D) The array must be sorted first
- **Answer: ✅ B**
- **Explanation**: Inserting at the beginning or middle of an array requires shifting subsequent elements forward to maintain contiguous storage.

---

## 🔷 Topic 2: Stacks & Queues

#### Q6. A Stack operates on which access principle?
- A) First-In, First-Out (FIFO)
- B) Last-In, First-Out (LIFO)
- C) Highest Priority First
- D) Random Access
- **Answer: ✅ B**
- **Explanation**: Stacks restrict access to a single end (the Top). The last element pushed is the first element popped.

#### Q7. The condition of trying to pop an element from an empty stack is called:
- A) Stack Overflow
- B) Stack Underflow
- C) Null Pointer Exception
- D) Memory Leak
- **Answer: ✅ B**
- **Explanation**: Stack Overflow occurs when pushing onto a full stack. Stack Underflow occurs when popping from an empty stack.

#### Q8. Which of the following is a classic application of a Stack?
- A) Print job spooler queue
- B) CPU round robin scheduling
- C) Recursive function call management
- D) Shortest path routing in networks
- **Answer: ✅ C**
- **Explanation**: The OS uses a call stack to keep track of active function frames, return addresses, and local variables.

#### Q9. A Queue operates on which access principle?
- A) LIFO
- B) FIFO
- C) Random Access
- D) Min-Heap order
- **Answer: ✅ B**
- **Explanation**: Queues insert elements at the Rear and remove them from the Front, ensuring first-in-first-out order.

#### Q10. In a standard linear queue implemented using an array, dequeue operations cause:
- A) Stack Overflow
- B) Unused empty spaces at the front of the array that cannot be reclaimed
- C) Memory leaks
- D) Tree skewing
- **Answer: ✅ B**
- **Explanation**: As elements are dequeued, the front pointer moves forward, leaving unused indices at the front of the array. A **Circular Queue** solves this by wrapping pointers back to index 0.

#### Q11. Which data structure is used to convert an Infix expression (e.g., `A + B * C`) to a Postfix expression (e.g., `A B C * +`)?
- A) Queue
- B) Binary Tree
- C) Stack
- D) Heap
- **Answer: ✅ C**
- **Explanation**: A stack is used to temporarily store operators and enforce precedence rules during conversion.

---

## 🔷 Topic 3: Trees & Binary Search Trees (BST)

#### Q12. In a binary tree, what is the maximum number of nodes possible at level $l$ (where the root is at level 0)?
- A) $l$
- B) $2^l$
- C) $2^{l+1}$
- D) $2^l - 1$
- **Answer: ✅ B**
- **Explanation**: 
  - Level 0 (Root) can have $2^0 = 1$ node.
  - Level 1 can have $2^1 = 2$ nodes.
  - Level 2 can have $2^2 = 4$ nodes.
  - Generalizing, Level $l$ can have a maximum of $2^l$ nodes.

#### Q13. If a binary tree has height $h$ (where the root has height 0), what is the maximum total number of nodes in the tree?
- A) $2^h$
- B) $2^{h+1} - 1$
- C) $2^h + 1$
- D) $2^{h-1}$
- **Answer: ✅ B**
- **Explanation**: A full binary tree of height $h$ contains $\sum_{i=0}^{h} 2^i = 2^{h+1} - 1$ nodes.

#### Q14. In any binary tree, if the number of leaf nodes (nodes with 0 children) is $n_0$, and the number of nodes with exactly 2 children is $n_2$, then:
- A) $n_0 = n_2$
- B) $n_0 = n_2 + 1$
- C) $n_0 = n_2 - 1$
- D) $n_0 = 2 \times n_2$
- **Answer: ✅ B**
- **Explanation**: In a binary tree, the number of leaves is always one more than the number of nodes with two children ($n_0 = n_2 + 1$).

#### Q15. A Binary Search Tree (BST) is characterized by which property?
- A) The root is always the minimum element
- B) Every node's children must have the same height
- C) The left subtree contains values less than the parent node, and the right subtree contains values greater
- D) The tree is always balanced
- **Answer: ✅ C**
- **Explanation**: The left-smaller, right-larger property defines a BST, enabling efficient search, insertion, and deletion.

#### Q16. Traversing a Binary Search Tree (BST) using which traversal method yields values in sorted order?
- A) Preorder
- B) Inorder
- C) Postorder
- D) Level Order
- **Answer: ✅ B**
- **Explanation**: Inorder traversal visits nodes in Left $\to$ Root $\to$ Right order, which matches the sorted order of a BST.

#### Q17. What is the worst-case search complexity in a standard Binary Search Tree of size $N$?
- A) $O(1)$
- B) $O(\log N)$
- C) $O(N)$
- D) $O(N \log N)$
- **Answer: ✅ C**
- **Explanation**: In the worst case (skewed tree where elements are inserted in sorted order), the BST degenerates into a linear list, making search complexity $O(N)$.

#### Q18. What is the balance factor of a node in an AVL tree?
- A) Height(Left Subtree) + Height(Right Subtree)
- B) Height(Left Subtree) - Height(Right Subtree)
- C) Height(Root) - Height(Leaf)
- D) Number of Left Children / Number of Right Children
- **Answer: ✅ B**
- **Explanation**: The balance factor is the difference in height between the left and right subtrees. In an AVL tree, it must be $-1$, $0$, or $+1$.

#### Q19. B+ Trees are preferred over standard binary search trees for database indexing because:
- A) They use less memory
- B) They are simpler to implement
- C) All data records are stored in leaf nodes and leaves are linked, making range queries and disk reads highly efficient
- D) They do not suffer from collisions
- **Answer: ✅ C**
- **Explanation**: B+ trees store all data records in leaf nodes linked in a sequential list. This speeds up range queries and minimizes disk reads.

---

## 🔷 Topic 4: Graphs

#### Q20. In graph representation, what is the space complexity of an Adjacency Matrix for a graph with $V$ vertices?
- A) $O(V)$
- B) $O(V + E)$
- C) $O(V^2)$
- D) $O(E)$
- **Answer: ✅ C**
- **Explanation**: An adjacency matrix is a 2D array of size $V \times V$, requiring $O(V^2)$ space regardless of the number of edges.

#### Q21. Which graph representation is most space-efficient for a sparse graph (a graph with few edges)?
- A) Adjacency Matrix
- B) Adjacency List
- C) Incidence Matrix
- D) Complete Graph Matrix
- **Answer: ✅ B**
- **Explanation**: An adjacency list requires $O(V + E)$ space, making it highly efficient for sparse graphs where $E \ll V^2$.

#### Q22. Breadth-First Search (BFS) on a graph uses which helper data structure?
- A) Stack
- B) Queue
- C) Binary Heap
- D) Hash Table
- **Answer: ✅ B**
- **Explanation**: BFS explores nodes level-by-level using a FIFO queue. DFS uses a LIFO stack or recursion.

#### Q23. Which graph traversal is preferred for cycle detection in a directed graph and generating topological sorts?
- A) BFS
- B) DFS
- C) Kruskal's
- D) Binary Search
- **Answer: ✅ B**
- **Explanation**: DFS's backtracking model enables cycle detection (via back edges) and topological sorting.

---

## 🔷 Topic 5: Hashing

#### Q24. What is a collision in a hash table?
- A) The hash function returns an index larger than the table size
- B) Two distinct keys map to the same index
- C) A key is deleted from the table
- D) The table runs out of memory
- **Answer: ✅ B**
- **Explanation**: Collisions occur when $h(k_1) = h(k_2)$ for $k_1 \neq k_2$.

#### Q25. In separate chaining collision resolution:
- A) Collisions are resolved by finding the next empty slot in the table
- B) Collisions are stored in a linked list at each table index
- C) The load factor $\alpha$ must remain $\le 1.0$
- D) Deletions are extremely complex
- **Answer: ✅ B**
- **Explanation**: Separate chaining creates a linked list at each index. Because slots can hold multiple nodes, the load factor ($\alpha = N/M$) can exceed $1.0$.

#### Q26. Linear probing resolves collisions by:
- A) Creating a binary tree at each slot
- B) Searching slots sequentially ($h(x), h(x)+1, h(x)+2, \dots$) for the next available position
- C) Re-hashing the key using a second hash function
- D) Throwing a runtime exception
- **Answer: ✅ B**
- **Explanation**: Linear probing scans table slots sequentially. However, it is susceptible to **primary clustering** (long runs of occupied slots).

#### Q27. The load factor $\alpha$ of a hash table with $N$ elements and $M$ slots is defined as:
- A) $M / N$
- B) $N / M$
- C) $N + M$
- D) $N \times M$
- **Answer: ✅ B**
- **Explanation**: The load factor $\alpha = N / M$ measures table fullness.

---

## 🔷 Topic 6: Heaps

#### Q28. A Binary Heap is:
- A) A complete binary tree
- B) A skewed binary search tree
- C) A multi-way search tree
- D) An acyclic graph
- **Answer: ✅ A**
- **Explanation**: Heaps are complete binary trees (filled at all levels except possibly the lowest, which is filled from left to right), allowing them to be represented inside a contiguous array.

#### Q29. In a Max-Heap represented as a 1-indexed array, if a parent node is located at index $i$, where is its right child located?
- A) $2i$
- B) $2i + 1$
- C) $i / 2$
- D) $i + 1$
- **Answer: ✅ B**
- **Explanation**: 
  - Left child = $2i$.
  - Right child = $2i + 1$.
  - Parent = $\lfloor i/2 \rfloor$.

#### Q30. What is the time complexity to insert a new element into a Binary Heap of size $N$?
- A) $O(1)$
- B) $O(N)$
- C) $O(\log N)$
- D) $O(N \log N)$
- **Answer: ✅ C**
- **Explanation**: Insertion appends the element at the end of the array and bubbles it up to restore heap properties, taking at most $O(\log N)$ height swaps.

#### Q31. What is the time complexity of the Heap Sort algorithm in the average and worst cases?
- A) $O(N^2)$
- B) $O(N \log N)$
- C) $O(N)$
- D) $O(\log N)$
- **Answer: ✅ B**
- **Explanation**: Heap sort takes $O(N \log N)$ time in both average and worst cases because it performs $N$ extractions on a heap of height $\log N$.

#### Q32. What is the time complexity to build a binary heap from a raw array of $N$ elements?
- A) $O(N^2)$
- B) $O(N \log N)$
- C) $O(N)$
- D) $O(\log N)$
- **Answer: ✅ C**
- **Explanation**: Building a heap bottom-up using the Floyd's method takes $O(N)$ time.

---

## 🔷 Topic 7: Conceptual Review Questions

#### Q33. A queue where elements can be inserted or deleted at both ends is called:
- A) Priority Queue
- B) Circular Queue
- C) Deque (Double-Ended Queue)
- D) LIFO Queue
- **Answer: ✅ C**
- **Explanation**: Deque allows push/pop operations at both the Front and Rear.

#### Q34. What is the height of a balanced AVL tree containing $N$ nodes?
- A) $O(1)$
- B) $O(\log N)$
- C) $O(N)$
- D) $O(N^2)$
- **Answer: ✅ B**
- **Explanation**: AVL trees remain balanced, guaranteeing $O(\log N)$ height and search times.

#### Q35. If the Inorder traversal of a binary tree is `D B E A F C` and its Preorder traversal is `A B D E C F`, what is the Postorder traversal of the tree?
- A) `D E B F C A`
- B) `D E B F A C`
- C) `D B E F C A`
- D) `A B C D E F`
- **Answer: ✅ A**
- **Explanation**: 
  - Preorder starts with `A` (Root).
  - Split Inorder by `A`: Left subtree is `D B E`, Right subtree is `F C`.
  - Repeat for subtrees. The tree is:
    - Root: `A`
    - Left Child: `B` (with children `D` and `E`)
    - Right Child: `C` (with left child `F`)
  - Postorder (Left $\to$ Right $\to$ Root) is `D E B F C A`.

#### Q36. A binary tree in which every internal node has exactly 0 or 2 children is called a:
- A) Full Binary Tree (Strict Binary Tree)
- B) Complete Binary Tree
- C) Perfect Binary Tree
- D) Skewed Binary Tree
- **Answer: ✅ A**
- **Explanation**: A Full (Strict) binary tree requires that no node has exactly 1 child.

#### Q37. What is the worst-case space complexity of Depth-First Search (DFS) on a tree of height $H$?
- A) $O(1)$
- B) $O(H)$
- C) $O(N)$
- D) $O(2^H)$
- **Answer: ✅ B**
- **Explanation**: DFS uses a recursion stack. The maximum number of stack frames matches the height of the tree ($O(H)$).

#### Q38. Which data structure is best suited for implementing a FIFO printer spooler?
- A) Stack
- B) Binary Search Tree
- C) Queue
- D) Min-Heap
- **Answer: ✅ C**
- **Explanation**: A printer spooler processes print jobs in the order they arrive (FIFO), which is implemented using a queue.

#### Q39. In a hash table using quadratic probing, if a collision occurs at hash index $h(k)$, what is the sequence of probe positions?
- A) $h(k), h(k)+1, h(k)+2$
- B) $h(k), h(k)+1^2, h(k)+2^2, h(k)+3^2$
- C) $h(k), h(k) \times 2, h(k) \times 4$
- D) $h(k), h(k) + h_2(k)$
- **Answer: ✅ B**
- **Explanation**: Quadratic probing resolves collisions by checking slots at quadratic intervals: $(h(k) + i^2) \pmod m$.

#### Q40. Which of the following is true about a B-Tree?
- A) It is a binary search tree
- B) All leaf nodes must be at the same level
- C) It does not allow multiple keys in a node
- D) It has a height of $O(N)$
- **Answer: ✅ B**
- **Explanation**: B-Trees are balanced multi-way search trees where all leaf nodes are at the same level.

#### Q41. In a Min-Heap, the root node contains:
- A) The maximum element
- B) The minimum element
- C) The median element
- D) A random element
- **Answer: ✅ B**
- **Explanation**: A min-heap maintains the property that the parent is less than or equal to its children, placing the minimum value at the root.

#### Q42. Adjacency lists are preferred over adjacency matrices for:
- A) Complete graphs
- B) Sparse graphs
- C) Direct edge lookup speed
- D) Small graphs
- **Answer: ✅ B**
- **Explanation**: Adjacency lists use memory proportional to edges ($O(V+E)$), making them ideal for sparse graphs.

#### Q43. What is the time complexity to search for an element in a Hash Table under the worst-case scenario (e.g., all keys collide)?
- A) $O(1)$
- B) $O(\log N)$
- C) $O(N)$
- D) $O(N \log N)$
- **Answer: ✅ C**
- **Explanation**: In the worst-case scenario where all elements collide at a single index, search time degrades to traversing a linked list of size $N$ ($O(N)$).

#### Q44. The DFS traversal of a graph is equivalent to:
- A) Level order traversal of a tree
- B) Preorder traversal of a tree
- C) Inorder traversal of a tree
- D) Postorder traversal of a tree
- **Answer: ✅ B**
- **Explanation**: DFS visits nodes as deep as possible before backtracking, similar to a preorder traversal.

#### Q45. In a circular queue of size $M$, if the Front is at index 2 and the Rear is at index $M-1$, what happens if we attempt to enqueue a new element?
- A) Queue Underflow
- B) The element is inserted at index 0, and Rear is updated to 0
- C) Queue Overflow
- D) Pointers become invalid
- **Answer: ✅ B**
- **Explanation**: In a circular queue, the Rear pointer wraps around to index 0 if space is available (since Front is at index 2, slots 0 and 1 are empty).

#### Q46. An AVL tree is a:
- A) Multi-way search tree
- B) Self-balancing Binary Search Tree
- C) Complete Binary Tree
- D) Unordered heap
- **Answer: ✅ B**
- **Explanation**: AVL trees are self-balancing BSTs that maintain height balance to ensure $O(\log N)$ operations.

#### Q47. If the balance factor of a node in an AVL tree becomes $+2$ because of an insertion in the left subtree of the left child, what rotation is needed?
- A) Left Rotation (RR)
- B) Right Rotation (LL)
- C) Left-Right Rotation (LR)
- D) Right-Left Rotation (RL)
- **Answer: ✅ B**
- **Explanation**: A left-left (LL) imbalance requires a single Right Rotation to restore balance.

#### Q48. What is the space complexity of a complete binary tree stored inside an array?
- A) $O(V^2)$
- B) $O(N)$
- C) $O(2^N)$
- D) $O(N \log N)$
- **Answer: ✅ B**
- **Explanation**: Complete binary trees can be stored compactly in an array of size $N$ without gaps, taking $O(N)$ space.

#### Q49. Which hashing technique uses a second hash function to resolve collisions?
- A) Linear Probing
- B) Double Hashing
- C) Quadratic Probing
- D) Separate Chaining
- **Answer: ✅ B**
- **Explanation**: Double hashing calculates probe indices using: $(h_1(x) + i \cdot h_2(x)) \pmod m$.

#### Q50. In a Max-Heap, where is the second largest element located?
- A) At the root
- B) As a leaf node
- C) At either the left child or the right child of the root node
- D) In the left subtree only
- **Answer: ✅ C**
- **Explanation**: The largest element is at the root. The second largest must be one of its children (index 1 or index 2 in 0-indexed arrays).

---

## 🔷 Topic 3: Advanced Linear Structures & Operations

#### Q51. In a Doubly Linked List, deleting a node at a known position $P$ (not the head or tail) takes:
- A) $O(1)$ time
- B) $O(N)$ time
- C) $O(\log N)$ time
- D) $O(N^2)$ time
- **Answer: ✅ A**
- **Explanation**: Unlike a Singly Linked List (where you must search for the preceding node to update pointers), a DLL node contains pointers to both its previous and next nodes. Thus, deleting a known node requires only pointer adjustments: `node->prev->next = node->next` and `node->next->prev = node->prev` in $O(1)$ constant time.

#### Q52. Floyd's Cycle-Finding Algorithm (Tortoise and Hare) detects a loop in a Linked List by using:
- A) Two pointers moving at the same speed
- B) Two pointers, one moving twice as fast as the other
- C) A hash table to record visited addresses
- D) Reversing the list
- **Answer: ✅ B**
- **Explanation**: The algorithm uses a slow pointer (moves 1 step) and a fast pointer (moves 2 steps). If there is a cycle, the fast pointer will eventually catch up and meet the slow pointer. If there is no cycle, the fast pointer will reach NULL.

#### Q53. What is the time and space complexity of Floyd's Cycle-Finding Algorithm?
- A) $O(N)$ time and $O(N)$ space
- B) $O(N)$ time and $O(1)$ space
- C) $O(N^2)$ time and $O(1)$ space
- D) $O(1)$ time and $O(N)$ space
- **Answer: ✅ B**
- **Explanation**: The algorithm runs in linear time $O(N)$ because the fast pointer catches the slow pointer in at most $N$ steps once inside the loop. It uses only two pointer variables, consuming $O(1)$ extra space.

#### Q54. What is the postfix representation of the infix expression: `A + B * C - D / E`?
- A) `A B C * + D E / -`
- B) `A B C + * D E / -`
- C) `A B + C * D E / -`
- D) `A B C * + D E - /`
- **Answer: ✅ A**
- **Explanation**: Order of operations:
  1. `B * C` becomes `B C *`
  2. `D / E` becomes `D E /`
  3. `A + (B C *)` becomes `A B C * +`
  4. `(A B C * +) - (D E /)` becomes `A B C * + D E / -`

#### Q55. Evaluating the postfix expression `6 2 3 + * 12 -` using a stack yields:
- A) 18
- B) 30
- C) 24
- D) 12
- **Answer: ✅ A**
- **Explanation**: Trace stack actions:
  - Push 6, push 2, push 3 [Stack: 6, 2, 3]
  - Operator `+`: Pop 3, pop 2. Calculate $2 + 3 = 5$. Push 5. [Stack: 6, 5]
  - Operator `*`: Pop 5, pop 6. Calculate $6 \times 5 = 30$. Push 30. [Stack: 30]
  - Push 12 [Stack: 30, 12]
  - Operator `-`: Pop 12, pop 30. Calculate $30 - 12 = 18$. Push 18. [Stack: 18]

#### Q56. How can you implement a Stack such that the `getMin()` operation (retrieving the minimum element) takes $O(1)$ time?
- A) By sorting the stack after every push
- B) By using an auxiliary stack that tracks the minimum element at each level
- C) By using a priority queue
- D) It is impossible to achieve $O(1)$ time
- **Answer: ✅ B**
- **Explanation**: Maintaining a secondary stack (min-stack) that stores the current minimum element matching each push/pop state allows retrieving the minimum value in $O(1)$ time.

#### Q57. In a circular queue implemented using an array of size $N$, how is the number of elements currently in the queue calculated?
- A) `rear - front`
- B) `(rear - front + N) % N`
- C) `(rear + front) % N`
- D) `rear - front + 1`
- **Answer: ✅ B**
- **Explanation**: Because the pointers wrap around, `rear` can be less than `front`. The formula `(rear - front + N) % N` handles wrapping correctly.

#### Q58. A Double-Ended Queue (Deque) allows:
- A) Enqueue at Front, Dequeue at Rear only
- B) Enqueue and Dequeue at both Front and Rear ends
- C) Random access deletion
- D) LIFO operations only
- **Answer: ✅ B**
- **Explanation**: A Deque (pronounced "deck") is a generalized queue that supports insertion and deletion at both ends in $O(1)$ time.

#### Q59. Which data structure is used to handle undo/redo operations in text editors?
- A) Two Stacks (Undo Stack and Redo Stack)
- B) Two Queues
- C) Singly Linked List
- D) Min-Heap
- **Answer: ✅ A**
- **Explanation**: Undo operations pop from the Undo stack and push onto the Redo stack. Redo operations pop from the Redo stack and push back onto the Undo stack.

#### Q60. In an array-based implementation of a binary tree, if a node is at index 12 (0-indexed), what are the indices of its left and right children?
- A) Left: 24, Right: 25
- B) Left: 25, Right: 26
- C) Left: 13, Right: 14
- D) Left: 26, Right: 27
- **Answer: ✅ B**
- **Explanation**: Formulas for 0-indexed trees:
  - Left child = $2i + 1 = 2(12) + 1 = 25$
  - Right child = $2i + 2 = 2(12) + 2 = 26$

---

## 🔷 Topic 4: Hierarchical Structures & Balanced Trees

#### Q61. For a binary tree containing $L$ leaf nodes and $N_2$ nodes with exactly two children, which property always holds?
- A) $L = N_2$
- B) $L = N_2 + 1$
- C) $L = N_2 - 1$
- D) $L = 2 \cdot N_2$
- **Answer: ✅ B**
- **Explanation**: In any binary tree, the number of leaf nodes ($L$) is always exactly one more than the number of nodes with two children ($N_2$).

#### Q62. What is the maximum height of a Full Binary Tree containing $N$ nodes?
- A) $\log_2(N + 1)$
- B) $\frac{N - 1}{2}$
- C) $N$
- D) $\log_2(N)$
- **Answer: ✅ B**
- **Explanation**: A full binary tree is a tree where every node has either 0 or 2 children. The maximum height (worst-case skewed) occurs when each level has exactly 2 nodes (excluding root), yielding a height of $\frac{N - 1}{2}$.

#### Q63. If the Preorder traversal of a binary tree is `A B D E C F` and its Inorder traversal is `D B E A C F`, what is the Postorder traversal of the tree?
- A) `D E B F C A`
- B) `D E B C F A`
- C) `D B E F C A`
- D) `A B D E C F`
- **Answer: ✅ A**
- **Explanation**:
  - Preorder starts with root `A`.
  - In Inorder, `D B E` are in left subtree, `C F` are in right subtree.
  - Reconstructing recursively yields the tree:
    - Root `A`
    - Left Child `B` (with children `D` and `E`)
    - Right Child `C` (with right child `F`)
  - Postorder (L-R-Root): `D E B F C A`.

#### Q64. Inserting the keys `15, 10, 20, 8, 12, 17, 25` into an empty BST results in a tree of height:
- A) 2
- B) 3
- C) 4
- D) 6
- **Answer: ✅ A**
- **Explanation**:
  - Root: 15 (Height 0)
  - Level 1: 10 (left), 20 (right) (Height 1)
  - Level 2: 8 (left of 10), 12 (right of 10), 17 (left of 20), 25 (right of 20) (Height 2)
  - The tree is perfectly balanced, so the max height is 2.

#### Q65. What is the maximum number of rotations required to restore balance in an AVL tree after an insertion?
- A) 1 single or 1 double rotation (max 2 pointer updates)
- B) $O(\log N)$ rotations
- C) $O(N)$ rotations
- D) No rotations are needed for insertion
- **Answer: ✅ A**
- **Explanation**: An insertion in an AVL tree can only increase the height of a single branch by 1. Once a single rotation (LL/RR) or double rotation (LR/RL) is performed at the lowest unbalanced node, the height of that subtree is restored to its pre-insertion state, balancing the entire tree.

#### Q66. What is the maximum number of rotations required to restore balance in an AVL tree after a deletion?
- A) 1
- B) $O(\log N)$
- C) $O(N)$
- D) No rotations are needed
- **Answer: ✅ B**
- **Explanation**: Deleting a node can cause a cascade of imbalances up the path to the root. Thus, we may need to perform rotations at multiple levels, taking at most $O(\log N)$ rotations.

#### Q67. In a Red-Black Tree, what is the maximum possible height of a tree containing $N$ internal nodes?
- A) $\log_2(N + 1)$
- B) $2 \log_2(N + 1)$
- C) $N$
- D) $1.44 \log_2(N)$
- **Answer: ✅ B**
- **Explanation**: A Red-Black tree is balanced such that its height is guaranteed to be at most $2 \log_2(N + 1)$. This worst-case height occurs when red and black nodes alternate along the longest path.

#### Q68. What is the main structural advantage of a B+ Tree over a B-Tree for database indexing?
- A) B+ Trees are binary, so searches are faster
- B) B+ Trees store all data/records in the leaf nodes, which are linked sequentially, allowing fast range scans and higher internal node fan-out
- C) B+ Trees use less memory
- D) B+ Trees do not require balancing
- **Answer: ✅ B**
- **Explanation**: By storing data pointers only in leaves, B+ Tree internal nodes hold more keys per disk block (high fan-out). The linked list of leaf nodes allows $O(\log N)$ initial search followed by sequential link traversal for range queries, which is much faster than B-Tree tree-traversal range queries.

#### Q69. If a node in an AVL tree has a Balance Factor of $-2$ and its right child has a Balance Factor of $+1$, what rotation is required?
- A) Single Left Rotation (RR)
- B) Double Right-Left Rotation (RL)
- C) Single Right Rotation (LL)
- D) Double Left-Right Rotation (LR)
- **Answer: ✅ B**
- **Explanation**: A node with $BF = -2$ is right-heavy. A child with $BF = +1$ is left-heavy. This is a Right-Left (RL) imbalance, which requires a double RL rotation to balance.

#### Q70. What is the black height of a Red-Black Tree?
- A) The total number of nodes in the tree
- B) The number of black nodes on any path from a node to any of its descendant leaves (excluding the node itself)
- C) The height of the tree
- D) The number of red nodes
- **Answer: ✅ B**
- **Explanation**: Black height is the count of black nodes on the path to a leaf. Rule 5 of Red-Black trees guarantees this count is identical for all paths starting from a given node.

---

## 🔷 Topic 5: Graphs & Traversals

#### Q71. How many edges are in a complete undirected graph containing $V$ vertices?
- A) $V(V-1)$
- B) $\frac{V(V-1)}{2}$
- C) $V^2$
- D) $V + 1$
- **Answer: ✅ B**
- **Explanation**: In a complete graph, every vertex has an edge to every other vertex ($V-1$ edges). Summing these and dividing by 2 (since the graph is undirected and edges are shared) yields $\frac{V(V-1)}{2}$.

#### Q72. Which graph representation is most space-efficient for a sparse graph with $V = 10,000$ and $E = 20,000$?
- A) Adjacency Matrix
- B) Adjacency List
- C) Incidence Matrix
- D) All are equal
- **Answer: ✅ B**
- **Explanation**:
  - Adjacency Matrix space = $V^2 = 100,000,000$ cells.
  - Adjacency List space = $O(V + E) = 10,000 + 20,000 = 30,000$ node pointers.
  - The adjacency list consumes significantly less memory.

#### Q73. What is the time complexity of Breadth-First Search (BFS) using an Adjacency List representation?
- A) $O(V^2)$
- B) $O(V + E)$
- C) $O(V \cdot E)$
- D) $O(\log V)$
- **Answer: ✅ B**
- **Explanation**: BFS visits every vertex once ($O(V)$) and scans the adjacency list of every vertex once, processing all edges ($O(E)$). Thus, the runtime is $O(V + E)$.

#### Q74. What is the time complexity of BFS using an Adjacency Matrix representation?
- A) $O(V + E)$
- B) $O(V^2)$
- C) $O(E^2)$
- D) $O(V \log V)$
- **Answer: ✅ B**
- **Explanation**: For each of the $V$ vertices, we must scan a row of size $V$ in the matrix to find adjacent vertices, resulting in an $O(V^2)$ runtime.

#### Q75. A graph is bipartite if and only if:
- A) It contains no cycles
- B) It can be colored using exactly 2 colors such that no two adjacent vertices share the same color
- C) It is a tree
- D) It has a directed cycle
- **Answer: ✅ B**
- **Explanation**: A bipartite graph can be split into two independent sets $U$ and $V$ such that all edges connect a vertex in $U$ to a vertex in $V$. This is equivalent to 2-coloring. A graph is bipartite if and only if it contains no odd-length cycles.

#### Q76. Topological Sorting can be performed on which type of graph?
- A) Any Directed Graph
- B) Directed Acyclic Graph (DAG)
- C) Complete Undirected Graph
- D) Bipartite Graph
- **Answer: ✅ B**
- **Explanation**: Topological sorting orders vertices linearly. If the graph contains a cycle (e.g. $A \to B \to C \to A$), it is impossible to resolve which comes first, so the graph must be acyclic.

#### Q77. Topological Sort can be solved in $O(V+E)$ time using which algorithm?
- A) Dijkstra's Algorithm
- B) Kahn's Algorithm (indegree-based queue) or DFS-based ordering
- C) Kruskal's Algorithm
- D) Bellman-Ford
- **Answer: ✅ B**
- **Explanation**: Kahn's algorithm calculates the indegree of all vertices, enqueues vertices with indegree 0, and decreases neighbor indegrees as vertices are popped. It runs in $O(V+E)$ time.

#### Q78. Which traversal is used to find the shortest path in an unweighted graph?
- A) DFS
- B) BFS
- C) Inorder Traversal
- D) Dijkstra's
- **Answer: ✅ B**
- **Explanation**: BFS explores vertices in concentric layers. The first time a node is reached, the path taken is guaranteed to be the shortest path in terms of edge count.

#### Q79. What is the maximum number of strongly connected components in a directed graph of $V$ vertices?
- A) 1
- B) $V$
- C) $V - 1$
- D) $2^V$
- **Answer: ✅ B**
- **Explanation**: If a graph has no edges (or no cycles), each vertex forms its own strongly connected component, yielding $V$ components.

#### Q80. DFS traversal uses which underlying data structure implicitly?
- A) Queue
- B) Stack (via Recursion call stack)
- C) Min-Heap
- D) Binary Search Tree
- **Answer: ✅ B**
- **Explanation**: DFS processes nodes deep down a path before backtracking. This LIFO behavior matches a Stack.

---

## 🔷 Topic 6: Hashing & Hashing Mechanics

#### Q81. What is the load factor ($\alpha$) of a hash table?
- A) The size of the hash function code
- B) The ratio of the number of keys stored to the total number of slots in the table ($N / M$)
- C) The count of collisions
- D) The memory consumed by pointers
- **Answer: ✅ B**
- **Explanation**: The load factor $\alpha = N/M$ measures table occupancy. It helps determine when to resize the table.

#### Q82. In a hash table using Open Addressing, what is the maximum value of the load factor ($\alpha$)?
- A) $\infty$
- B) 1.0
- C) 0.5
- D) Table Size
- **Answer: ✅ B**
- **Explanation**: In open addressing, all elements are stored directly within the table array. Because each slot can hold at most one element, the number of keys $N$ cannot exceed slots $M$, meaning $\alpha \le 1.0$.

#### Q83. What is "Primary Clustering" in hashing?
- A) All keys hashing to index 0
- B) The buildup of long runs of adjacent occupied slots in Linear Probing, which increases search times
- C) Deleting elements recursively
- D) Linked list growth in separate chaining
- **Answer: ✅ B**
- **Explanation**: In linear probing, if a collision occurs, we check the next slot. This causes colliding keys to cluster together in contiguous blocks, increasing collision rates and search costs.

#### Q84. How does Quadratic Probing resolve Primary Clustering?
- A) By checking slots at quadratic intervals: $h(x) + i^2 \pmod m$
- B) By using linked lists
- C) By using a second hash function
- D) By resizing the table immediately
- **Answer: ✅ A**
- **Explanation**: Quadratic probing checks slots at increasing intervals, dispersing colliding keys across the table and eliminating primary clustering (though it can still cause *secondary clustering*).

#### Q85. How does Double Hashing eliminate clustering?
- A) By hashing the key twice and adding the results
- B) By calculating probe step sizes using a second hash function: $(h_1(x) + i \cdot h_2(x)) \pmod m$
- C) By using two separate hash tables
- D) By chaining elements in binary trees
- **Answer: ✅ B**
- **Explanation**: Because the step size depends on the key itself ($h_2(x)$), different keys that hash to the same initial slot will follow completely different probe paths, eliminating clustering.

#### Q86. What is a "Tombstone" in Open Addressing hash tables?
- A) A sentinel node at the end of a chain
- B) A special marker placed in a slot when an item is deleted, ensuring that search probes do not stop scanning prematurely
- C) An overflow area
- D) A compile error flag
- **Answer: ✅ B**
- **Explanation**: Setting a deleted slot to empty breaks probe paths. Placing a tombstone marker informs the search algorithm to continue scanning while allowing insertion algorithms to reuse the slot.

#### Q87. Under separate chaining, what is the average time complexity to search a hash table of size $M$ containing $N$ elements?
- A) $O(1)$
- B) $O(1 + \alpha)$
- C) $O(N)$
- D) $O(\log N)$
- **Answer: ✅ B**
- **Explanation**: The hash function takes $O(1)$ time. The average length of the chain at any slot is the load factor $\alpha = N/M$. Thus, the average search time is $O(1 + \alpha)$.

#### Q88. What is a bad hash function characteristic?
- A) Distributes keys uniformly across the table
- B) Computes indices quickly
- C) Maps consecutive keys to the same index (causes clustering)
- D) Minimizes collisions
- **Answer: ✅ C**
- **Explanation**: A good hash function must distribute keys uniformly to prevent clustering and minimize collisions.

#### Q89. The Mid-Square hashing method works by:
- A) Dividing the key by table size
- B) Squaring the key and extracting the middle digits
- C) Adding the digits of the key
- D) Folding the key
- **Answer: ✅ B**
- **Explanation**: Mid-square squares the key (e.g. $12 \to 144$) and extracts a middle portion as the address index. This utilizes all digits of the key.

#### Q90. What is the main drawback of Separate Chaining?
- A) The load factor cannot exceed 1.0
- B) Pointers consume extra memory, and cache performance is poor due to non-contiguous node storage
- C) Table resizing is mandatory after every collision
- D) It causes primary clustering
- **Answer: ✅ B**
- **Explanation**: Separate chaining uses dynamic nodes for chains. These pointers add memory overhead and cause CPU cache misses during traversal.

---

## 🔷 Topic 7: Heaps & Priority Queues

#### Q91. What is the time complexity of building a Binary Heap of size $N$ from an unsorted array?
- A) $O(N \log N)$
- B) $O(N)$
- C) $O(\log N)$
- D) $O(N^2)$
- **Answer: ✅ B**
- **Explanation**: Building a heap bottom-up runs `Heapify` on nodes starting from the lowest non-leaf level. The sum of heights converges to a constant factor, yielding a linear $O(N)$ runtime.

#### Q92. What is the time complexity to extract the maximum element from a Max-Heap of size $N$?
- A) $O(1)$
- B) $O(\log N)$
- C) $O(N)$
- D) $O(N \log N)$
- **Answer: ✅ B**
- **Explanation**: The max element is at the root ($O(1)$). However, extracting it requires swapping the last element to the root and running `Heapify` to restore properties, taking $O(\log N)$ time.

#### Q93. What is the worst-case space complexity of Heapsort?
- A) $O(N)$
- B) $O(1)$
- C) $O(\log N)$
- D) $O(N \log N)$
- **Answer: ✅ B**
- **Explanation**: Heapsort is an in-place sorting algorithm. It rearranges elements directly within the input array, consuming $O(1)$ auxiliary space.

#### Q94. What is the index of the parent of a node located at index $i$ in a 0-indexed binary heap array?
- A) $2i$
- B) $\lfloor (i - 1) / 2 \rfloor$
- C) $2i + 1$
- D) $i / 2$
- **Answer: ✅ B**
- **Explanation**: For any node $i$, its parent index is $\lfloor (i - 1) / 2 \rfloor$. For example, the parent of node 1 and node 2 is index 0.

#### Q95. Which of the following arrays represents a valid Min-Heap?
- A) `[10, 20, 30, 40, 50]`
- B) `[50, 40, 30, 20, 10]`
- C) `[10, 30, 20, 15, 40]`
- D) `[10, 25, 20, 15, 30]`
- **Answer: ✅ A**
- **Explanation**: For a Min-Heap, the parent value must be less than or equal to its children:
  - `arr[0]=10` $\le$ children `arr[1]=20`, `arr[2]=30` (Valid)
  - `arr[1]=20` $\le$ children `arr[3]=40`, `arr[4]=50` (Valid).
  - In Option D, `arr[1]=25` is greater than its child `arr[3]=15`, which is invalid.

#### Q96. In a Max-Heap with $N$ elements, where are the leaf nodes located in the array representation?
- A) In the first half: indices $0$ to $\lfloor N/2 - 1 \rfloor$
- B) In the second half: indices $\lfloor N/2 \rfloor$ to $N - 1$
- C) At odd indices only
- D) Scattered throughout the array
- **Answer: ✅ B**
- **Explanation**: In a complete binary tree of size $N$, all nodes from index $\lfloor N/2 \rfloor$ to $N-1$ are leaf nodes.

#### Q97. What is the time complexity to insert a new element into a Binary Heap of size $N$?
- A) $O(1)$
- B) $O(\log N)$
- C) $O(N)$
- D) $O(N \log N)$
- **Answer: ✅ B**
- **Explanation**: The element is appended at the end of the array, then swapped up the path to the root (Up-Heap) to restore balance, taking at most $O(\log N)$ swaps.

#### Q98. Heapsort is based on which selection strategy?
- A) Divide and Conquer
- B) Repeated extraction of the root element from a heap
- C) Partitioning around a pivot
- D) Hashing
- **Answer: ✅ B**
- **Explanation**: Heapsort builds a heap and repeatedly extracts the root (max/min element), placing it at the end of the array and rebuilding the heap.

#### Q99. If we perform a `decrease-key` operation on a node in a Min-Heap, we must:
- A) Heapify down (swap with smaller child)
- B) Heapify up (swap with parent)
- C) Rebuild the entire heap
- D) Do nothing
- **Answer: ✅ B**
- **Explanation**: Decreasing a key in a Min-Heap makes it smaller, which may violate the heap property if it is smaller than its parent. Thus, it must be swapped up.

#### Q100. A Priority Queue is best implemented using which data structure for optimal average runtimes?
- A) Unsorted Linked List
- B) Binary Heap
- C) BST
- D) Stack
- **Answer: ✅ B**
- **Explanation**: Binary heaps insert and extract elements in $O(\log N)$ time, outperforming lists ($O(N)$) and keeping a simpler structure than BSTs.

#### Q101. What is the time complexity to find the minimum element in a Max-Heap of size $N$?
- A) $O(1)$
- B) $O(\log N)$
- C) $O(N)$
- D) $O(N \log N)$
- **Answer: ✅ C**
- **Explanation**: In a Max-Heap, the minimum element must be one of the leaf nodes (second half of the array). Because leaf nodes are unsorted, we must search all of them, taking $O(N)$ time.

#### Q102. Can a Binary Heap contain duplicate values?
- A) No, like BSTs, all values must be unique
- B) Yes, heap properties only require parent-child inequalities ($\ge$ or $\le$), allowing duplicate values
- C) Only in Max-Heaps
- D) Only in leaf nodes
- **Answer: ✅ B**
- **Explanation**: Heaps do not enforce sibling order, only parent-child ordering. Duplicate values do not violate these constraints.

#### Q103. If a binary tree is represented by an array, which index represents the right child of the root?
- A) 1
- B) 2
- C) 3
- D) 4
- **Answer: ✅ B**
- **Explanation**: Under 0-indexing, the root is at index 0. Its left child is at $2(0) + 1 = 1$. Its right child is at $2(0) + 2 = 2$.

#### Q104. What is the worst-case time complexity of Heapsort?
- A) $O(N)$
- B) $O(N \log N)$
- C) $O(N^2)$
- D) $O(2^N)$
- **Answer: ✅ B**
- **Explanation**: Heapsort performs $N$ extractions. Each extraction takes $O(\log N)$ heapify time. This guarantees $O(N \log N)$ runtime in all cases (best, average, and worst).

#### Q105. A complete binary tree is a binary tree in which:
- A) Every node has exactly 2 children
- B) Every level, except possibly the last, is completely filled, and all nodes in the last level are as far left as possible
- C) The balance factor of all nodes is 0
- D) All paths to leaves have equal length
- **Answer: ✅ B**
- **Explanation**: Complete binary trees fill levels top-to-bottom and left-to-right. This property allows them to be stored compactly in arrays without gaps.

---

## 🔷 Part 2: Mixed Exam Practice (60 MCQs)

#### Q106. A data structure is:
- A) Programming language
- B) Way of organizing data
- C) Operating System
- D) Compiler
- **Answer: ✅ B**
- **Explanation**: A data structure is a systematic way of organizing, managing, and storing data in a computer so that it can be accessed and modified efficiently.

#### Q107. Which of the following is a linear data structure?
- A) Tree
- B) Graph
- C) Array
- D) Heap
- **Answer: ✅ C**
- **Explanation**: Arrays store elements sequentially in contiguous memory blocks. Trees, graphs, and heaps are non-linear hierarchical or network structures.

#### Q108. Which data structure stores data hierarchically?
- A) Queue
- B) Tree
- C) Array
- D) Stack
- **Answer: ✅ B**
- **Explanation**: A tree is a hierarchical, non-linear data structure consisting of nodes connected by edges, starting from a single root node.

#### Q109. Which is a non-linear data structure?
- A) Linked List
- B) Queue
- C) Graph
- D) Array
- **Answer: ✅ C**
- **Explanation**: Graphs are non-linear because elements can be connected in arbitrary networks rather than sequentially (like arrays, lists, stacks, and queues).

#### Q110. Which data structure provides LIFO access?
- A) Queue
- B) Stack
- C) Array
- D) Tree
- **Answer: ✅ B**
- **Explanation**: Stacks follow the LIFO (Last-In, First-Out) access principle where the last element inserted is the first one removed.

#### Q111. Array elements are stored in:
- A) Random locations
- B) Contiguous memory locations
- C) Heap memory only
- D) Linked memory
- **Answer: ✅ B**
- **Explanation**: Arrays allocate contiguous (side-by-side) memory blocks, which enables direct index address calculations.

#### Q112. Accessing the 10th element of an array requires:
- A) $O(1)$
- B) $O(\log N)$
- C) $O(N)$
- D) $O(N^2)$
- **Answer: ✅ A**
- **Explanation**: Contiguous memory allows the CPU to calculate the exact address of any index in $O(1)$ constant time.

#### Q113. Which operation is costly in arrays?
- A) Access
- B) Traversal
- C) Insertion at middle
- D) Reading
- **Answer: ✅ C**
- **Explanation**: Inserting in the middle of an array requires shifting all subsequent elements forward to maintain contiguity, which takes $O(N)$ time.

#### Q114. Linked Lists use:
- A) Contiguous memory
- B) Hashing
- C) Pointers
- D) Recursion
- **Answer: ✅ C**
- **Explanation**: Linked lists allocate memory dynamically and link non-contiguous nodes using address pointers.

#### Q115. Which structure is best when frequent insertions and deletions are required?
- A) Array
- B) Linked List
- C) Heap
- D) Trie
- **Answer: ✅ B**
- **Explanation**: Linked lists insert/delete elements in $O(1)$ time by adjusting neighbor node pointers without shifting elements.

#### Q116. In a singly linked list, each node contains:
- A) Data only
- B) Pointer only
- C) Data and next pointer
- D) Data and two pointers
- **Answer: ✅ C**
- **Explanation**: Singly linked list nodes contain a data field and a single reference pointer pointing to the next node.

#### Q117. Random access is difficult in:
- A) Array
- B) Linked List
- C) Matrix
- D) String
- **Answer: ✅ B**
- **Explanation**: Since linked list nodes are scattered in memory, accessing a random node requires sequential traversal from the head node.

#### Q118. Stack follows:
- A) FIFO
- B) LIFO
- C) Priority Order
- D) Random Order
- **Answer: ✅ B**
- **Explanation**: Stacks restrict all operations to the Top end, enforcing Last-In, First-Out (LIFO) access.

#### Q119. Queue follows:
- A) LIFO
- B) FIFO
- C) Circular Order
- D) Sorted Order
- **Answer: ✅ B**
- **Explanation**: Queues insert at the rear and delete from the front, enforcing First-In, First-Out (FIFO) access.

#### Q120. Which stack operation inserts an element?
- A) Pop
- B) Push
- C) Peek
- D) Front
- **Answer: ✅ B**
- **Explanation**: The `push(x)` operation inserts a new element `x` onto the top of the stack.

#### Q121. Removing an element from a stack is called:
- A) Delete
- B) Pop
- C) Push
- D) Enqueue
- **Answer: ✅ B**
- **Explanation**: The `pop()` operation removes and returns the topmost element of the stack.

#### Q122. Which data structure is used for recursion?
- A) Queue
- B) Graph
- C) Stack
- D) Tree
- **Answer: ✅ C**
- **Explanation**: The operating system manages nested recursive function calls using an activation record stack.

#### Q123. Which operation returns the top element without removing it?
- A) Pop
- B) Push
- C) Peek
- D) Delete
- **Answer: ✅ C**
- **Explanation**: The `peek()` (or `top()`) operation inspects the top element without popping it off the stack.

#### Q124. Insertion in a queue is called:
- A) Push
- B) Pop
- C) Enqueue
- D) Peek
- **Answer: ✅ C**
- **Explanation**: The `enqueue(x)` operation appends a new element `x` to the rear of the queue.

#### Q125. Deletion in a queue is called:
- A) Pop
- B) Enqueue
- C) Dequeue
- D) Traverse
- **Answer: ✅ C**
- **Explanation**: The `dequeue()` operation removes and returns the element at the front of the queue.

#### Q126. A tree with $N$ nodes has:
- A) $N$ edges
- B) $N+1$ edges
- C) $N-1$ edges
- D) $N^2$ edges
- **Answer: ✅ C**
- **Explanation**: A connected acyclic graph (tree) with $N$ nodes always contains exactly $N-1$ edges.

#### Q127. Root -> Left -> Right is:
- A) Inorder
- B) Postorder
- C) Preorder
- D) Level Order
- **Answer: ✅ C**
- **Explanation**: Preorder tree traversal visits nodes in the sequence: Root, Left subtree, then Right subtree.

#### Q128. Left -> Root -> Right is:
- A) Preorder
- B) Inorder
- C) Postorder
- D) DFS
- **Answer: ✅ B**
- **Explanation**: Inorder tree traversal visits nodes in the sequence: Left subtree, Root, then Right subtree.

#### Q129. In a BST:
- A) Left > Root
- B) Right < Root
- C) Left < Root < Right
- D) Root always maximum
- **Answer: ✅ C**
- **Explanation**: Binary Search Trees (BSTs) enforce that all left child keys are smaller than the parent node, and all right child keys are larger.

#### Q130. Which traversal of BST gives sorted output?
- A) Preorder
- B) Postorder
- C) Inorder
- D) Level Order
- **Answer: ✅ C**
- **Explanation**: Visually traversing a BST from left to right (Inorder traversal) visits keys in sorted, ascending order.

#### Q131. BFS uses:
- A) Stack
- B) Queue
- C) Heap
- D) Array
- **Answer: ✅ B**
- **Explanation**: Breadth-First Search (BFS) processes nodes level-by-level using a FIFO queue.

#### Q132. DFS uses:
- A) Queue
- B) Linked List
- C) Stack
- D) Heap
- **Answer: ✅ C**
- **Explanation**: Depth-First Search (DFS) explores paths as deep as possible before backtracking using a LIFO stack (or recursion stack).

#### Q133. A graph consists of:
- A) Vertices only
- B) Edges only
- C) Vertices and edges
- D) Trees only
- **Answer: ✅ C**
- **Explanation**: A graph $G = (V, E)$ is mathematically defined by a set of vertices $V$ (nodes) connected by edges $E$ (links).

#### Q134. Which structure is best for representing social networks?
- A) Array
- B) Graph
- C) Queue
- D) Stack
- **Answer: ✅ B**
- **Explanation**: Social networks represent entities (people) as vertices and their connections (friendships) as edges, which is modeled as a Graph.

#### Q135. Complexity of BFS is:
- A) $O(N^2)$
- B) $O(\log N)$
- C) $O(V+E)$
- D) $O(1)$
- **Answer: ✅ C**
- **Explanation**: Breadth-First Search visits all vertices $V$ and scans neighbor lists to trace all edges $E$ once, running in $O(V+E)$ time.

#### Q136. Hashing is mainly used for:
- A) Sorting
- B) Fast searching
- C) Traversal
- D) Recursion
- **Answer: ✅ B**
- **Explanation**: Hashing maps search keys directly to index slots using a hash function, enabling $O(1)$ average search times.

#### Q137. A collision occurs when:
- A) Table is empty
- B) Search fails
- C) Two keys map to same index
- D) Table is full
- **Answer: ✅ C**
- **Explanation**: A collision happens when the hash function generates the identical index for two distinct keys: $h(K_1) = h(K_2)$ for $K_1 \neq K_2$.

#### Q138. Which collision technique uses linked lists?
- A) Linear Probing
- B) Double Hashing
- C) Chaining
- D) Quadratic Probing
- **Answer: ✅ C**
- **Explanation**: Separate chaining resolves collisions by building a linked list at each index slot of the hash table.

#### Q139. Which probing method suffers from primary clustering?
- A) Chaining
- B) Double Hashing
- C) Linear Probing
- D) Trie
- **Answer: ✅ C**
- **Explanation**: Linear probing scans slots sequentially, causing adjacent filled slots to cluster together and increasing search steps.

#### Q140. Average search complexity in hashing:
- A) $O(N^2)$
- B) $O(\log N)$
- C) $O(N)$
- D) $O(1)$
- **Answer: ✅ D**
- **Explanation**: If values are distributed uniformly, hashing retrieves keys in $O(1)$ constant time on average.

#### Q141. Load Factor is:
- A) $N \times M$
- B) $N + M$
- C) $N / M$
- D) $M / N$
- **Answer: ✅ C**
- **Explanation**: The load factor ($\alpha$) is the ratio of keys stored ($N$) to total hash table capacity ($M$): $\alpha = N/M$.

#### Q142. Hash function commonly used:
- A) $k + m$
- B) $k \pmod m$
- C) $k^2$
- D) $\log(k)$
- **Answer: ✅ B**
- **Explanation**: Division hashing ($h(k) = k \pmod m$) is the simplest and most common hash function.

#### Q143. Which collision technique generally gives best distribution?
- A) Linear Probing
- B) Chaining
- C) Double Hashing
- D) Queue
- **Answer: ✅ C**
- **Explanation**: Double hashing uses a second hash function to calculate custom step sizes, resolving primary and secondary clustering to distribute keys evenly.

#### Q144. Heap is a:
- A) Linked List
- B) Complete Binary Tree
- C) Graph
- D) Queue
- **Answer: ✅ B**
- **Explanation**: A Binary Heap is a complete binary tree (filled top-to-bottom and left-to-right), allowing contiguous array storage.

#### Q145. In Max Heap, root contains:
- A) Smallest element
- B) Median element
- C) Largest element
- D) Any element
- **Answer: ✅ C**
- **Explanation**: Max-heaps enforce that parents are $\ge$ children, placing the maximum value at the root node.

#### Q146. In Min Heap, root contains:
- A) Largest element
- B) Smallest element
- C) Random element
- D) Average element
- **Answer: ✅ B**
- **Explanation**: Min-heaps enforce that parents are $\le$ children, placing the minimum value at the root node.

#### Q147. Heap Sort complexity:
- A) $O(N^2)$
- B) $O(\log N)$
- C) $O(N \log N)$
- D) $O(N)$
- **Answer: ✅ C**
- **Explanation**: Heapsort performs $N$ extractions, taking $O(\log N)$ heapify time for each, which bounds sorting time to $O(N \log N)$ in all cases.

#### Q148. Which operation restores heap property after insertion?
- A) Heapify Down
- B) Heapify Up
- C) DFS
- D) BFS
- **Answer: ✅ B**
- **Explanation**: Inserting places elements at the leaf. The node must bubble up the path to the root (Heapify Up) to restore parent constraints.

#### Q149. Priority Queue is commonly implemented using:
- A) Array
- B) Stack
- C) Heap
- D) Graph
- **Answer: ✅ C**
- **Explanation**: Binary heaps insert and extract min/max elements in optimal $O(\log N)$ times, making them ideal for priority queue schedules.

#### Q150. For node at index $i$, left child index is:
- A) $i+1$
- B) $2i$
- C) $2i+1$
- D) $2i+2$
- **Answer: ✅ C**
- **Explanation**: Under 0-indexed arrays, the left child of node $i$ is calculated using $2i + 1$.

#### Q151. For node at index $i$, right child index is:
- A) $2i+2$
- B) $i+1$
- C) $2i$
- D) $i-1$
- **Answer: ✅ A**
- **Explanation**: Under 0-indexed arrays, the right child of node $i$ is calculated using $2i + 2$.

#### Q152. Main operations of Disjoint Set are:
- A) Push and Pop
- B) Union and Find
- C) Insert and Delete
- D) BFS and DFS
- **Answer: ✅ B**
- **Explanation**: Disjoint sets partition elements and support `Union` (merge groups) and `Find` (determine group representative).

#### Q153. Find operation returns:
- A) Child node
- B) Representative element
- C) Leaf node
- D) Edge
- **Answer: ✅ B**
- **Explanation**: `Find(x)` traverses pointers up to locate the root representative of the set containing `x`.

#### Q154. Path Compression is used to:
- A) Increase height
- B) Reduce height
- C) Delete nodes
- D) Sort elements
- **Answer: ✅ B**
- **Explanation**: Path compression points traversed nodes directly to the root, flattening the tree height to speed up future searches.

#### Q155. Union by Rank attaches:
- A) Larger tree below smaller tree
- B) Smaller tree below larger tree
- C) Random tree
- D) Equal tree only
- **Answer: ✅ B**
- **Explanation**: Union by Rank attaches the root of the shorter tree to the root of the taller tree to minimize height growth.

#### Q156. Which algorithm heavily uses Disjoint Set?
- A) DFS
- B) BFS
- C) Kruskal's Algorithm
- D) Binary Search
- **Answer: ✅ C**
- **Explanation**: Kruskal's minimum spanning tree algorithm uses Disjoint Sets to check if adding a candidate edge creates a cycle in the spanning forest.

#### Q157. Trie is also called:
- A) Heap Tree
- B) Prefix Tree
- C) AVL Tree
- D) Binary Tree
- **Answer: ✅ B**
- **Explanation**: Tries are called Prefix Trees because all descendant nodes share the string prefix character associated with their ancestor nodes.

#### Q158. Trie is mainly used to store:
- A) Graphs
- B) Integers
- C) Strings
- D) Arrays
- **Answer: ✅ C**
- **Explanation**: Tries store and search keys representing text strings over a character alphabet.

#### Q159. Search complexity in Trie depends on:
- A) Number of words
- B) Height of graph
- C) Length of word
- D) Number of nodes
- **Answer: ✅ C**
- **Explanation**: Searching a Trie requires traversing characters of the query string, running in $O(L)$ time where $L$ is the string length.

#### Q160. Autocomplete systems commonly use:
- A) Heap
- B) Trie
- C) Queue
- D) Stack
- **Answer: ✅ B**
- **Explanation**: Autocomplete systems traverse character prefixes using Tries to locate matching vocabulary.

#### Q161. AVL Tree is:
- A) Queue
- B) Stack
- C) Self-balancing BST
- D) Graph
- **Answer: ✅ C**
- **Explanation**: An AVL Tree is a height-balanced Binary Search Tree that enforces height differences between subtrees of at most $\pm 1$.

#### Q162. B-Tree is commonly used in:
- A) Networking
- B) Databases
- C) Graphics
- D) Operating Systems
- **Answer: ✅ B**
- **Explanation**: Databases use balanced multi-way B-Trees to index tables because their high fan-out minimizes disk block reads.

#### Q163. Best structure for fast random access:
- A) Linked List
- B) Queue
- C) Array
- D) Trie
- **Answer: ✅ C**
- **Explanation**: Contiguous memory slots allow arrays to access elements by index in $O(1)$ constant time.

#### Q164. Best structure for connectivity checking:
- A) Heap
- B) Graph
- C) Disjoint Set
- D) Queue
- **Answer: ✅ C**
- **Explanation**: Disjoint Sets (Union-Find) check connection connectivity between sets of nodes in near-$O(1)$ time.

#### Q165. Best structure for priority scheduling:
- A) Linked List
- B) Heap
- C) Stack
- D) Trie
- **Answer: ✅ B**
- **Explanation**: Heaps keep the root node key sorted in min/max priority order, making insertions and extractions highly efficient ($O(\log N)$).

---

## 🔷 Topic 8: Masterclass Core & Trap MCQs

#### Q166. A Linked List is composed of which elements?
- A) Variables
- B) Nodes
- C) Arrays
- D) Functions
- **Answer: ✅ B**
- **Explanation**: A Linked List consists of individual structures called **nodes**, where each node contains a data field and a reference (pointer) to the next node.
- **Why Other Options Are Wrong**:
  - *A*: Variables are basic primitives; nodes are structured custom types.
  - *C*: Arrays are separate, contiguous data structures.
  - *D*: Functions contain executable logic, not data organization blocks.

#### Q167. In a standard Linked List, what address value is stored in the `next` pointer of the last node?
- A) Address of the head node
- B) Integer 0
- C) NULL
- D) Address of the tail node
- **Answer: ✅ C**
- **Explanation**: In linear linked lists, the last node's `next` pointer is set to `NULL` to signify the boundary/end of the list.
- **Why Other Options Are Wrong**:
  - *A*: Circular linked lists point back to the head; standard lists do not.
  - *B*: NULL is a pointer constant, not a raw integer data value.
  - *D*: Pointing to itself would create a circular self-reference loop.

#### Q168. Which physical memory arrangement does a Linked List use to store its elements?
- A) Continuous / Contiguous
- B) Non-continuous / Non-contiguous
- C) Fixed static blocks
- D) Virtual mapping only
- **Answer: ✅ B**
- **Explanation**: Unlike arrays, linked list nodes are dynamically allocated at scattered (non-continuous) addresses in memory. They are stitched together using pointer links.
- **Why Other Options Are Wrong**:
  - *A*: Arrays use contiguous memory, enabling random indexing.
  - *C*: Nodes are created on demand, not in pre-allocated static blocks.
  - *D*: It resides in real memory space, not just virtual maps.

#### Q169. Why is inserting a node at the beginning of a Linked List highly efficient compared to an Array?
- A) No shifting of elements is required
- B) Pointers are stored in cache memory
- C) The list is sorted automatically
- D) Less memory is allocated for the head node
- **Answer: ✅ A**
- **Explanation**: Inserting at the head of a linked list only requires updating pointers ($O(1)$ time). In contrast, arrays require shifting all existing elements in memory to clear slot 0 ($O(N)$ time).
- **Why Other Options Are Wrong**:
  - *B*: Pointers are stored in standard RAM, not specifically forced into cache.
  - *C*: Insertion does not sort the list.
  - *D*: Nodes consume identical memory size regardless of insertion position.

#### Q170. What does the `Head` pointer of a Linked List store?
- A) The actual data of the first node
- B) The size of the linked list
- C) The memory address of the first node
- D) A pointer to NULL
- **Answer: ✅ C**
- **Explanation**: The `Head` pointer is a reference variable that holds the memory address of the first node. It does not store raw data.
- **Why Other Options Are Wrong**:
  - *A*: The data is stored in the data field of the node, which is accessed via the head pointer (`head->data`).
  - *B*: The size is tracked separately or by traversing nodes.
  - *D*: Head only points to NULL if the list is empty.

#### Q171. Which access principle does a Stack follow?
- A) First-In, First-Out (FIFO)
- B) Last-In, First-Out (LIFO)
- C) Random Access Order
- D) Highest Priority First
- **Answer: ✅ B**
- **Explanation**: Stacks restrict all operations to the Top, meaning the element pushed last is the first one popped.
- **Why Other Options Are Wrong**:
  - *A*: FIFO is the access principle for queues.
  - *C*: Random access is supported by arrays, not stacks.
  - *D*: Priority queues process items by priority weight.

#### Q172. Which access principle does a Queue follow?
- A) Last-In, First-Out (LIFO)
- B) First-In, First-Out (FIFO)
- C) Sorted Order Access
- D) Depth-First Order
- **Answer: ✅ B**
- **Explanation**: Queues insert elements at the Rear and delete from the Front, ensuring the first element entered is the first one removed.
- **Why Other Options Are Wrong**:
  - *A*: LIFO is stack ordering.
  - *C*: Elements are retrieved by arrival order, not value sorting.
  - *D*: Depth-First is a traversal strategy for trees/graphs.

#### Q173. The operation of adding a new item to the top of a Stack is formally called:
- A) Pop
- B) Push
- C) Enqueue
- D) Peak
- **Answer: ✅ B**
- **Explanation**: Pushing is the standard term for inserting an item into a stack.
- **Why Other Options Are Wrong**:
  - *A*: Pop is the term for deleting an item from a stack.
  - *C*: Enqueue is for queues.
  - *D*: Peek/Peak is for viewing the top without deletion.

#### Q174. The operation of deleting an item from a Queue is called:
- A) Pop
- B) Push
- C) Enqueue
- D) Dequeue
- **Answer: ✅ D**
- **Explanation**: Dequeue is the operation that removes the front element of a queue.
- **Why Other Options Are Wrong**:
  - *A*: Pop deletes from a stack.
  - *B*: Push inserts into a stack.
  - *C*: Enqueue inserts into a queue.

#### Q175. Why is a Stack the ideal data structure for managing Undo operations in software?
- A) Undo operations require the oldest action to be reversed first
- B) Stacks consume less memory than queues
- C) Undo operations require the most recent action to be reversed first (LIFO)
- D) Stacks allow random modifications
- **Answer: ✅ C**
- **Explanation**: When a user selects "Undo", they expect their most recent (last) action to be undone first. This matches LIFO ordering, which is implemented using a stack.
- **Why Other Options Are Wrong**:
  - *A*: Reversing the oldest action first is FIFO, which would break natural undo flow.
  - *B*: Stacks and queues have identical memory complexity.
  - *D*: Stacks restrict access to the top node only.

#### Q176. Deleting the oldest element from a Queue occurs at which boundary?
- A) Top
- B) Front
- C) Rear
- D) Leaf
- **Answer: ✅ B**
- **Explanation**: In queues, insertions happen at the Rear, and deletions happen at the Front (representing the oldest element).
- **Why Other Options Are Wrong**:
  - *A*: Top is stack terminology.
  - *C*: Rear is where new elements are enqueued.
  - *D*: Leaf is tree terminology.

#### Q177. In a Binary Tree, what is the maximum number of child nodes any individual node can have?
- A) 1
- B) 2
- C) 3
- D) Unlimited
- **Answer: ✅ B**
- **Explanation**: By definition, a binary tree node is restricted to a maximum of 2 children: a left child and a right child.
- **Why Other Options Are Wrong**:
  - *A*: Skewed trees have 1 child per node, but the maximum allowed in binary trees is 2.
  - *C & D*: Multi-way trees can have more than 2 children, but binary trees cannot.

#### Q178. What ordering property characterizes a Binary Search Tree (BST)?
- A) Left child > Root > Right child
- B) Right child < Root < Left child
- C) Left subtree keys < Root key < Right subtree keys
- D) Parent nodes are always smaller than children nodes
- **Answer: ✅ C**
- **Explanation**: A BST arranges keys such that all descendants in a node's left subtree are smaller than the node's key, and all descendants in the right subtree are larger.
- **Why Other Options Are Wrong**:
  - *A & B*: Inverts sorting properties.
  - *D*: This defines a min-heap structure, not a BST.

#### Q179. A leaf node in a tree is characterized by having how many children?
- A) Exactly two children
- B) One child
- C) Zero children
- D) A parent only
- **Answer: ✅ C**
- **Explanation**: A leaf node (external node) resides at the boundary of a tree and has no children (degree = 0).
- **Why Other Options Are Wrong**:
  - *A*: This represents internal nodes in binary trees.
  - *B*: This represents single-child internal nodes.
  - *D*: While leaves do have a parent, they are characterized by their lack of child nodes.

#### Q180. Which tree structure guarantees logarithmic time complexity $O(\log N)$ for search, insertion, and deletion operations in the worst case?
- A) Unbalanced Binary Search Tree (BST)
- B) Self-balancing AVL Tree
- C) Skewed Binary Tree
- D) General Tree
- **Answer: ✅ B**
- **Explanation**: AVL trees dynamically balance themselves using rotations, keeping height bound to $O(\log N)$ and preventing skewing.
- **Why Other Options Are Wrong**:
  - *A*: Standard BSTs degrade to $O(N)$ when skewed.
  - *C*: Skewed trees run in linear $O(N)$ time.
  - *D*: General trees do not enforce binary search rules.

#### Q181. Which statement correctly describes the relationship between a Binary Search Tree (BST) and a Binary Tree?
- A) Every Binary Tree is a BST
- B) Every BST is a Binary Tree
- C) BSTs and Binary Trees are completely disjoint concepts
- D) A BST is a special type of Graph, not a Binary Tree
- **Answer: ✅ B**
- **Explanation**: A BST is a binary tree that satisfies a sorting property. Therefore, every BST is structurally a binary tree.
- **Why Other Options Are Wrong**:
  - *A*: Many binary trees do not satisfy the sorted ordering rules of a BST.
  - *C*: They are directly related (BST is a subset of Binary Tree).
  - *D*: A tree is a subset of graph structures, but a BST is classified under binary trees.

#### Q182. Graph Theory originated from the resolution of which historical mathematical problem?
- A) Four Color Problem
- B) Traveling Salesman Problem
- C) Seven Bridges of Königsberg
- D) Tower of Hanoi
- **Answer: ✅ C**
- **Explanation**: Leonhard Euler's 1736 analysis of whether one could walk through the city of Königsberg crossing its seven bridges exactly once led to the invention of graph structures.
- **Why Other Options Are Wrong**:
  - *A*: The Four Color Problem was solved much later in the 19th-20th century.
  - *B*: The Traveling Salesman Problem is an optimization challenge.
  - *D*: The Tower of Hanoi is a puzzle solved using recursive logic.

#### Q183. A Tree can be defined as which type of Graph?
- A) Directed cyclic graph
- B) Connected acyclic graph
- C) Disconnected undirected graph
- D) Complete weighted graph
- **Answer: ✅ B**
- **Explanation**: A tree is mathematically defined as a graph that is connected (every node reachable) and acyclic (contains no loops).
- **Why Other Options Are Wrong**:
  - *A*: Trees cannot have cycles.
  - *C*: Trees must be connected.
  - *D*: Trees do not have to be complete or weighted.

#### Q184. Which graph representation is most space-efficient for sparse graphs?
- A) Adjacency Matrix
- B) Adjacency List
- C) Incidence Matrix
- D) Complete Grid Map
- **Answer: ✅ B**
- **Explanation**: Adjacency lists only allocate memory for actual connections, consuming $O(V + E)$ space, which is optimal for sparse graphs.
- **Why Other Options Are Wrong**:
  - *A*: Matrices consume $O(V^2)$ space regardless of edge count, wasting memory for sparse graphs.
  - *C*: Incidence matrices consume $O(V \cdot E)$ space, which is less optimal than adjacency lists.

#### Q185. Which graph traversal algorithm is guaranteed to find the shortest path between two nodes in an unweighted graph?
- A) Depth-First Search (DFS)
- B) Breadth-First Search (BFS)
- C) Kruskal's Algorithm
- D) Topological Sorting
- **Answer: ✅ B**
- **Explanation**: BFS searches layer-by-layer. Since edges are unweighted, the first time BFS reaches a target node, it does so using the minimum number of edge steps.
- **Why Other Options Are Wrong**:
  - *A*: DFS goes deep along branches and may find a much longer path before finding the target.
  - *C*: Kruskal's finds a Minimum Spanning Tree.
  - *D*: Topological Sort yields a linear schedule order for directed acyclic graphs.

#### Q186. In a directed graph, the number of incoming edges pointing directly into a vertex is defined as its:
- A) Outdegree
- B) Indegree
- C) Sibling count
- D) Vertex connectivity
- **Answer: ✅ B**
- **Explanation**: Indegree measures how many edge arrows point towards a node.
- **Why Other Options Are Wrong**:
  - *A*: Outdegree measures outgoing edges.
  - *C*: Sibling counts are tree node terms.
  - *D*: Connectivity is a global graph property.

