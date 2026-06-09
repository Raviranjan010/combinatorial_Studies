# Unit V: DS Revision Cheat Sheet

A comprehensive study card covering data structure operations, time/space complexities, tree properties, and traversal techniques.

---

## ⚡ 1. Complexity & Formulas Card

### Time & Space Complexity Matrix
| Data Structure | Access (Avg/Worst) | Search (Avg/Worst) | Insert (Avg/Worst) | Delete (Avg/Worst)| Space Complexity |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Array** | $O(1) / O(1)$ | $O(N) / O(N)$ | $O(N) / O(N)$ | $O(N) / O(N)$ | $O(N)$ |
| **Singly LL** | $O(N) / O(N)$ | $O(N) / O(N)$ | $O(1) / O(1)$ | $O(1) / O(1)$ | $O(N)$ |
| **Stack (Array)**| $O(N) / O(N)$ | $O(N) / O(N)$ | $O(1) / O(1)$ | $O(1) / O(1)$ | $O(N)$ |
| **Queue (Array)**| $O(N) / O(N)$ | $O(N) / O(N)$ | $O(1) / O(1)$ | $O(1) / O(1)$ | $O(N)$ |
| **BST** | $O(\log N)/O(N)$ | $O(\log N)/O(N)$ | $O(\log N)/O(N)$ | $O(\log N)/O(N)$ | $O(N)$ |
| **AVL Tree** | $O(\log N)/O(\log N)$| $O(\log N)/O(\log N)$| $O(\log N)/O(\log N)$| $O(\log N)/O(\log N)$| $O(N)$ |
| **Hash Table** | N/A | $O(1) / O(N)$ | $O(1) / O(N)$ | $O(1) / O(N)$ | $O(N)$ |
| **Binary Heap** | N/A | $O(N) / O(N)$ | $O(\log N)/O(\log N)$| $O(\log N)/O(\log N)$| $O(N)$ |

### Binary Tree Properties Formulas
Let $h$ be the height of the tree (where a single root node has height 0):
*   **Max Nodes at Level $l$** = $2^l$.
*   **Max Total Nodes in a Binary Tree** = $2^{h+1} - 1$.
*   **Min Total Nodes in a Binary Tree** = $h + 1$ (skewed tree).
*   **Leaf Nodes vs. Degree-2 Nodes**: In any binary tree, let $n_0$ be the number of leaf nodes and $n_2$ be the number of nodes with exactly 2 children:
    $$n_0 = n_2 + 1$$

---

## 📊 2. High-Yield Summary Tables

### Graph Traversals Comparison
| Feature | Breadth-First Search (BFS) | Depth-First Search (DFS) |
| :--- | :--- | :--- |
| **Data Structure** | **Queue** (FIFO). | **Stack** (LIFO) or **Recursion**. |
| **Execution Path** | Visits all neighbor nodes first before moving deeper.| Explores deep down a branch before backtracking. |
| **Time Complexity** | $O(V + E)$ | $O(V + E)$ |
| **Space Complexity** | $O(V)$ (for Queue storage). | $O(V)$ (for recursion call stack). |
| **Key Use Case** | Finding the shortest path in an unweighted graph. | Cycle detection, Topological sort. |

### Heap Array Indirection Formulas (1-Indexed Array)
*   **Parent Node Index** of node $i$ = $\lfloor i / 2 \rfloor$.
*   **Left Child Index** of node $i$ = $2 \times i$.
*   **Right Child Index** of node $i$ = $2 \times i + 1$.
*   *(Note: For 0-indexed arrays: Parent = $\lfloor (i-1)/2 \rfloor$, Left Child = $2i+1$, Right Child = $2i+2$)*.

---

## 🧠 3. Memory Tricks & Mnemonics

*   **Tree Traversals**:
    *   **In**order: Left $\to$ **Root** $\to$ Right (Root is **in** the middle).
    *   **Pre**order: **Root** $\to$ Left $\to$ Right (Root is **pre**/before).
    *   **Post**order: Left $\to$ Right $\to$ **Root** (Root is **post**/after).
*   **DFS vs. BFS**:
    *   **D**FS $\to$ **D**eep (Stack/Recursion).
    *   **B**FS $\to$ **B**readth/Wide (Queue).
*   **Stack vs Queue**:
    *   Stack = **LIFO** (Last In, First Out).
    *   Queue = **FIFO** (First In, First Out).

---

## 🚨 4. High-Risk Confusion Zones

### 1. Inorder Traversal Sort Property
*   **Confusion**: Does Inorder traversal print all binary trees in sorted order?
*   **Reality**: **No**. Inorder traversal prints elements in sorted order **only** if the tree is a Binary Search Tree (BST). For general binary trees, it does not print values in sorted order.

### 2. Heap vs. Binary Search Tree (BST)
*   **Confusion**: Are Heaps and BSTs ordered the same way?
*   **Reality**: **No**. In a BST, the left child is smaller than the parent, and the right child is larger. In a Max-Heap, **both** children must be smaller than the parent (no left-to-right ordering). Consequently, you cannot search a Heap in $O(\log N)$ time; searching a Heap takes $O(N)$ time.

### 3. Hashing: Chaining vs. Open Addressing
*   **Chaining**: Collisions are placed in separate, dynamic linked lists. The Load Factor $\alpha = N / M$ can exceed $1.0$.
*   **Open Addressing**: Collisions must be resolved inside the pre-allocated table cells. The Load Factor $\alpha$ must be $\le 1.0$.

---

## ⚠️ 5. Traps & Mistakes to Avoid in Exams

*   **BST Skewed Tree Trap**: Do not assume BST operations are always $O(\log N)$. If keys are inserted in sorted order (e.g., $1, 2, 3, 4$), the BST degenerates into a skewed line, and search times degrade to $O(N)$. Self-balancing AVL trees are needed to guarantee $O(\log N)$.
*   **Heap Sort Array Bounds**: When performing heap calculations, double-check whether the problem assumes 1-based indexing or 0-based indexing for the array representation, as this changes child-parent index calculations.
*   **Recursion space overhead**: Even though DFS and tree traversals have $O(1)$ auxiliary space excluding the system stack, their actual runtime space complexity is $O(H)$ (where $H$ is the tree height) due to recursion stack frames.

---

## ⚡ 6. Masterclass Revision Kits

### 📋 6.1 5-Minute Quick Reference Sheets

#### Linked Lists
*   **Core definition:** Nodes connected dynamically using address pointers.
*   **Types:** Singly Linked List (SLL), Doubly Linked List (DLL), Circular Linked List (CLL), Circular Doubly Linked List (CDLL).
*   **Operations:** Insert/Delete at Beginning ($O(1)$), End ($O(N)$ or $O(1)$ with tail pointer), Middle ($O(N)$ traversal + $O(1)$ pointer shift).
*   **Key Advantage:** Dynamic size allocation, fast insertion and deletion without memory shifting.
*   **Key Disadvantage:** Slow sequential random access ($O(N)$), extra pointer memory overhead.

#### Stacks & Queues
*   **Stack:** LIFO (Last In First Out) principle. Operations: `push()`, `pop()`, `peek()` ($O(1)$). Used for Undos, parentheses matching, recursion call stack.
*   **Queue:** FIFO (First In First Out) principle. Operations: `enqueue()`, `dequeue()`, `peek()` ($O(1)$). Used for job queues, CPU scheduling, networking buffers.
*   **Key Variants:** Circular Queue (avoids space leaks), Priority Queue (processed by importance rating), Deque (insert/delete from both Front and Rear).

#### Trees
*   **Core structure:** Hierarchical, acyclic node structure containing a Root, internal nodes, and Leaves.
*   **Binary Tree:** Each node can have at most 2 children.
*   **Binary Search Tree (BST):** Left Subtree $<$ Root $<$ Right Subtree ordering. Inorder traversal yields sorted ascending values.
*   **Balanced Trees:** Height is kept to $O(\log N)$ via rotations (AVL) or color flags (Red-Black) to prevent linear degeneration.

#### Graphs
*   **Formal Math:** $G = (V, E)$. Network representation of many-to-many relationships.
*   **Representations:** Adjacency Matrix ($O(V^2)$ space, $O(1)$ edge checking) vs. Adjacency List ($O(V+E)$ space, $O(\text{degree})$ edge checking).
*   **Traversals:** BFS (Queue helper, level-by-level, finds shortest path on unweighted edges) vs. DFS (Stack helper/recursion, deep explorer, cycle detection).

---

### ⏱ 6.2 2-Minute Memory Maps
*   **Linked List:** Node = Data + Pointer Address. Traversed sequentially.
*   **Stack:** Pile of Plates $\to$ LIFO order. Insertion/Deletion at `Top`.
*   **Queue:** Ticket counter line $\to$ FIFO order. Insertion at `Rear`, deletion at `Front`.
*   **Tree:** Family tree hierarchy $\to$ Root at top, Leaves at bottom. Max 2 kids for Binary.
*   **Graph:** Cities (vertices) and roads (edges). DFS = Deep explorer; BFS = Ripple expander.

---

### 📑 6.3 Last-Night Study summaries

#### Singly vs. Doubly Linked Lists
*   *SLL:* Single `next` pointer. Traverses forward only. Low memory.
*   *DLL:* `next` and `prev` pointers. Traverses bidirectionally. Easy deletion but higher memory cost.

#### Stacks vs. Queues
*   *Stack (LIFO):* Push $\to$ insert, Pop $\to$ delete. Access limited to `top`.
*   *Queue (FIFO):* Enqueue $\to$ insert (Rear), Dequeue $\to$ delete (Front). Access limited to `front`.

#### BST vs. AVL Tree
*   *BST:* Basic ordered tree. Can become skewed ($O(N)$ time) if keys arrive sorted.
*   *AVL:* Always balanced. Balance factor is Height(Left) - Height(Right) $\in \{-1,0,1\}$. Guaranteed $O(\log N)$ search time.

#### Graph traversals
*   *BFS:* Uses a Queue. Explores neighbors first. Finds shortest unweighted paths.
*   *DFS:* Uses a Stack (implicit call stack). Explores branch paths to the bottom before backtracking.

---

## ⏱ 7. The 60-Second Exam Hall Recall Cards

If you have only 60 seconds before entering the exam, memorize these core data structure rules:

1.  **Linked List = Pointers + Nodes:** Memory is non-contiguous. Head stores address of first node. Tail points to NULL.
2.  **LIFO vs FIFO:** Stack is Last-In-First-Out (plates). Queue is First-In-First-Out (checkout line).
3.  **Push/Pop vs Enqueue/Dequeue:** Stacks push/pop at Top. Queues enqueue at Rear and dequeue at Front.
4.  **Recursion uses Stack:** Call stacks process nested returns in LIFO order.
5.  **Tree is Acyclic Graph:** Trees have exactly one root, no cycles, and exactly $N-1$ edges for $N$ nodes.
6.  **BST Rule:** Left Child $<$ Root $<$ Right Child. BST Inorder traversal prints values in sorted order.
7.  **AVL = Balanced BST:** BF = Height(Left) - Height(Right) must be $-1$, $0$, or $+1$. restorers use single (LL/RR) or double (LR/RL) rotations.
8.  **BST vs AVL Worst Case:** BST search takes $O(N)$ worst-case. AVL search takes $O(\log N)$ worst-case.
9.  **Matrix vs List:** Adjacency matrix is $O(V^2)$ space (good for dense). Adjacency list is $O(V+E)$ space (good for sparse).
10. **BFS vs DFS:** BFS explores wide using a Queue. DFS explores deep using a Stack/Recursion.
11. **Circular Queue Modulo:** $\text{rear} = (\text{rear} + 1) \mathbin{\%} \text{capacity}$. Prevents empty space leaks.
12. **Heaps are Array Trees:** Root is min/max. Left child is $2i+1$; Right child is $2i+2$ (for 0-indexed arrays).

