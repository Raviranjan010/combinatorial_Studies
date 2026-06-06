# Unit V: Data Structures - MCQ Bank

Master Arrays, Linked Lists, Stacks, Queues, Trees, Graphs, Hashing, and Heaps with these 50 solved, high-probability Multiple Choice Questions.

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
