# 📈 Data Structures — Unit V: Comprehensive Lecture Notes

> **Target Audience:** Students and candidates preparing for technical interviews. This unit covers linear structures, hierarchical trees, graph models, hashing, and priority queues with step-by-step algorithms, ASCII graphics, and "Mistakes to Avoid" sections.

---

## 📌 Table of Contents

1. [Introduction to Data Structures & Memory Layout](#1-introduction-to-data-structures--memory-layout)
2. [Linked Lists: Singly, Doubly, and Circular](#2-linked-lists-singly-doubly-and-circular)
3. [Stacks & Queues: Constraints & Implementations](#3-stacks--queues-constraints--implementations)
4. [Trees: Binary Trees, BST, and Self-Balancing Trees (AVL, Red-Black, B/B+)](#4-trees-binary-trees-bst-and-self-balancing-trees)
5. [Graphs: Representations (Matrix vs. List) & Traversals (BFS & DFS)](#5-graphs-representations--traversals)
6. [Hashing: Hash Functions, Collisions, and Resolution Strategies](#6-hashing-hash-functions-collisions-and-resolution-strategies)
7. [Heaps: Priority Queues, Binary Heaps & Heapify Mechanics](#7-heaps-priority-queues-binary-heaps--heapify-mechanics)
8. [Common Pitfalls & Mistakes to Avoid](#8-common-pitfalls--mistakes-to-avoid)

---

## 1. Introduction to Data Structures & Memory Layout

A **Data Structure** is a systematic way of organizing, managing, and storing data in a computer so that operations (such as search, insertion, deletion, and updates) can be performed efficiently.

### 🧠 Cache Locality & Memory Layout
How data structures reside in physical RAM directly impacts their CPU performance:
*   **Contiguous Layout (Arrays):** Elements are stored side-by-side in memory blocks.
    *   *Hardware Benefit:* Excellent cache spatial locality. When the CPU accesses `arr[0]`, the hardware pre-fetches the entire block (`arr[1]`, `arr[2]`, etc.) into the L1/L2 cache.
*   **Non-Contiguous Layout (Linked Lists, Trees):** Elements (nodes) are allocated dynamically at arbitrary memory locations and linked via address pointers.
    *   *Hardware Drawback:* Poor cache locality. Traversing a linked list causes multiple CPU cache misses because nodes are scattered across RAM.

---

## 2. Linked Lists: Singly, Doubly, and Circular

A **Linked List** is a dynamic linear data structure composed of nodes, where each node contains data and a reference (pointer) to the next node.

```
Singly Linked List:
┌──────────────┐      ┌──────────────┐      ┌──────────────┐
│ Head: Data10 ├───►  │ Data20       ├───►  │ Data30       ├───► NULL
│ Next: 0x500  │      │ Next: 0x800  │      │ Next: NULL   │
└──────────────┘      └──────────────┘      └──────────────┘
Address: 0x100        Address: 0x500        Address: 0x800
```

### 2.1 Linked List Variants
1.  **Singly Linked List (SLL):** One pointer per node (`next`). Unidirectional traversal.
2.  **Doubly Linked List (DLL):** Two pointers per node (`next` and `prev`). Bidirectional traversal.
3.  **Circular Linked List (CLL):** The last node's `next` pointer references the head node, forming a closed ring.

---

### 2.2 Trace: Inserting a Node in the Middle of an SLL
Let's insert a node with value `15` between `Node(10)` and `Node(20)`:

```
Step 1: Create new node N(15).
        N(15)->next = NULL

Step 2: Traverse to the node before insertion point: Current = Node(10)
        Current->next points to Node(20)

Step 3: Bind new node to next node first:
        N(15)->next = Current->next   (N(15)->next now points to Node(20))

Step 4: Update preceding node pointer:
        Current->next = N(15)         (Node(10)->next now points to N(15))
```
If you perform Step 4 before Step 3, you lose the reference to `Node(20)`, orphanizing the rest of the list and causing a memory leak!

---

## 3. Stacks & Queues: Constraints & Implementations

Both are restricted linear data structures where insertion and deletion occur at defined boundaries.

### 3.1 Stack (LIFO - Last In First Out)
*   **Analogy:** A vertical stack of books. You add to the top and remove from the top.
*   **Operations:** `push(x)` ($O(1)$), `pop()` ($O(1)$), `peek()` ($O(1)$).
*   **C++ Array Implementation Variables:**
    *   `top`: Stores the array index of the topmost element. Initialized to `-1`.
    *   *Overflow Condition:* `top == MAX_SIZE - 1`
    *   *Underflow Condition:* `top == -1`

---

### 3.2 Queue (FIFO - First In First Out)
*   **Analogy:** A queue line at a bank. You join the line at the rear and leave at the front.
*   **Operations:** `enqueue(x)` ($O(1)$), `dequeue()` ($O(1)$).
*   **Linear Queue Issue:** As elements are dequeued, the front pointer moves forward, leaving unused empty spaces at the front of the array that cannot be reused.

#### The Solution: Circular Queue
Use modulo arithmetic to wrap array pointers around back to index 0:

```
        0      1      2      3
      [ 40 ] [ 10 ] [ 20 ] [ 30 ]
        ▲                   ▲
        Front               Rear
```
*   **Enqueue index calculation:**
    $$\text{rear} = (\text{rear} + 1) \mathbin{\%} \text{capacity}$$
*   **Dequeue index calculation:**
    $$\text{front} = (\text{front} + 1) \mathbin{\%} \text{capacity}$$
*   **Queue Full Condition:**
    $$(\text{rear} + 1) \mathbin{\%} \text{capacity} == \text{front}$$
*   **Queue Empty Condition:**
    $$\text{front} == -1$$

---

## 4. Trees: Binary Trees, BST, and Self-Balancing Trees

A **Tree** is a hierarchical, non-linear structure of nodes connected by edges, containing no cycles.

### 4.1 Binary Search Tree (BST) Ordering
For every node $X$ in a BST:
*   All keys in the **left subtree** of $X$ must be less than $X$.
*   All keys in the **right subtree** of $X$ must be greater than $X$.

```
              ( 50 )
             /      \
          ( 30 )  ( 70 )
          /    \      \
       ( 20 ) ( 40 ) ( 80 )
```
*   **Inorder Traversal (L-Root-R) of a BST always yields sorted keys:** `20 30 40 50 70 80`
*   **Preorder Traversal (Root-L-R):** `50 30 20 40 70 80`
*   **Postorder Traversal (L-R-Root):** `20 40 30 80 70 50`

---

### 4.2 Balanced Trees

#### A) AVL Tree (Height-Balanced)
An AVL tree is a BST where the height difference (**Balance Factor**) between the left and right subtrees of any node is at most $\pm 1$:
$$\text{Balance Factor (BF)} = \text{Height}(Left) - \text{Height}(Right) \quad \text{where } BF \in \{-1, 0, 1\}$$

If an insertion or deletion causes $BF = \pm 2$, balance is restored using rotations:
1.  **Single LL Rotation:** Parent node is rotated right when a node is added to the left child's left subtree.
2.  **Single RR Rotation:** Parent node is rotated left when a node is added to the right child's right subtree.
3.  **Double LR Rotation:** Left-Right rotation. Perform left rotation on child, then right rotation on parent.
4.  **Double RL Rotation:** Right-Left rotation. Perform right rotation on child, then left rotation on parent.

```
   LL Imbalance (BF = +2):           RR Rotation (Right Rotate Node 30):
         ( 30 )  BF = +2                       ( 20 )
        /                                     /      \
     ( 20 )  BF = +1                       ( 10 )  ( 30 )
    /
 ( 10 )  BF = 0
```

#### B) Red-Black Tree
A self-balancing BST that uses a color flag (Red/Black) to maintain balance.
*   **Rules:**
    1.  Every node is either Red or Black.
    2.  The root is always Black.
    3.  Every leaf (NULL pointer) is Black.
    4.  If a node is Red, both its children must be Black (no adjacent Red nodes).
    5.  For each node, all paths from the node to descendant leaves contain the same number of Black nodes.

#### C) B-Trees and B+ Trees
Multi-way search trees designed for external storage systems (hard drives, SSDs).
*   **B-Tree:** Keys and data pointers are stored in both internal and leaf nodes.
*   **B+ Tree:** All data pointers are stored **only in leaf nodes**, and leaf nodes are linked sequentially. Internal nodes store only search keys. This maximizes fan-out and facilitates fast range queries.

---

## 5. Graphs: Representations & Traversals

A **Graph** $G = (V, E)$ consists of a set of vertices $V$ connected by edges $E$.

### 5.1 Graph Representation

#### 1. Adjacency Matrix
A 2D array of size $V \times V$, where `matrix[i][j] = 1` indicates an edge between node $i$ and node $j$.
*   *Pros:* $O(1)$ check for edge existence.
*   *Cons:* Always consumes $O(V^2)$ memory space, making it inefficient for sparse graphs.

#### 2. Adjacency List
An array of lists of size $V$, where slot $i$ contains a linked list of all neighbors of node $i$.
*   *Pros:* Space-efficient ($O(V + E)$), ideal for sparse graphs.
*   *Cons:* Checking edge existence takes $O(\text{degree}(v))$ time.

---

### 5.2 Graph Traversals

#### Breadth-First Search (BFS)
Explores neighbors level-by-level using a **Queue** data structure.
*   *Trace Table (Start Node A):*
```
Graph: A-B, A-C, B-D, C-D
Queue Initial: [A]
Step 1: Dequeue A. Visit A. Enqueue unvisited neighbors of A: [B, C]. Mark Visited = {A, B, C}
Step 2: Dequeue B. Visit B. Enqueue unvisited neighbors of B: [C, D]. Mark Visited = {A, B, C, D}
Step 3: Dequeue C. Visit C. Neighbors are already visited.
Step 4: Dequeue D. Visit D.
Final Order: A, B, C, D
```

#### Depth-First Search (DFS)
Explores deep along branches before backtracking. Uses **Recursion (System Stack)**.
*   *Order:* A, B, D, C (using same graph).

---

## 6. Hashing: Hash Functions, Collisions, and Resolution Strategies

**Hashing** maps keys of arbitrary size to fixed-size array indices using a **Hash Function**:
$$index = h(key) \mathbin{\%} \text{Table\_Size}$$

### 6.1 Collisions
A **Collision** occurs when two distinct keys produce the identical hash index: $h(K_1) == h(K_2)$.

```
                     COLLISION RESOLUTION
                               │
            ┌──────────────────┴──────────────────┐
            ▼                                     ▼
   [Separate Chaining]                   [Open Addressing]
   LinkedList at each slot               Find empty slot in array
                                                  │
                            ┌─────────────────────┼─────────────────────┐
                            ▼                     ▼                     ▼
                    [Linear Probing]     [Quadratic Probing]    [Double Hashing]
                     Index: h(x) + i      Index: h(x) + i^2     h(x) + i * h2(x)
```

#### 1. Separate Chaining (Open Hashing)
Each slot in the hash table points to a linked list. Colliding items are simply appended to the list at that slot.
*   *Load Factor ($\alpha$):* $\alpha = \frac{N}{M}$ (where $N$ is keys, $M$ is table slots). Here, $\alpha$ can exceed 1.0.

#### 2. Open Addressing (Closed Hashing)
All keys are stored within the table array itself. Thus, $\alpha \le 1.0$. If a collision occurs, we probe other slots:
*   **Linear Probing:** Check indices sequentially: $h(x), \ h(x)+1, \ h(x)+2, \ \dots$
    *   *Issue:* **Primary Clustering** — long contiguous blocks of occupied slots build up, slowing down search times.
*   **Quadratic Probing:** Check slots at quadratic offsets: $h(x) + i^2 \pmod{M}$.
*   **Double Hashing:** Check slots using a step size calculated from a second hash function:
    $$Index = (h_1(key) + i \times h_2(key)) \mathbin{\%} M$$
    This eliminates primary and secondary clustering.

---

## 7. Heaps: Priority Queues, Binary Heaps & Heapify Mechanics

A **Binary Heap** is a complete binary tree stored inside a contiguous array.

```
       Max-Heap:                     Array representation:
         ( 90 )                       Index: [0]  [1]  [2]  [3]  [4]  [5]
        /      \                      Value: [90] [80] [70] [30] [40] [10]
     ( 80 )  ( 70 )
     /    \  /
  ( 30 ) (40)(10)
```

### 7.1 Array Mappings (0-Indexed)
For any node at index $i$:
*   **Left Child Index:** $2i + 1$
*   **Right Child Index:** $2i + 2$
*   **Parent Index:** $\lfloor (i - 1) / 2 \rfloor$

### 7.2 Heap Operations
*   **Heapify (Down-Heap):** Corrects a single imbalance at index $i$ by swapping it with its largest child (for Max-Heap) and recursing down ($O(\log N)$ time).
*   **Build Heap:** Converts an unsorted array into a heap. We run `Heapify` starting from the last non-leaf node ($\lfloor N/2 - 1 \rfloor$) up to the root (index 0).
    *   *Time Complexity:* Provably **$O(N)$** because most nodes reside near the bottom of the tree, requiring short swap paths.
*   **Insertion:** Append new item at the end of the array, then swap up (Up-Heap) to restore properties ($O(\log N)$ time).

---

## 8. Common Pitfalls & Mistakes to Avoid

> [!WARNING]
> ### 1. Pointer Loss during Linked List Insertions
> *   **The Mistake:** Reassigning the preceding node's pointer before binding the new node's next pointer.
> *   **The Reality:**
>     ```cpp
>     // ❌ INCORRECT (loss of reference to temp->next)
>     temp->next = new_node;
>     new_node->next = temp->next;
>     
>     // ✅ CORRECT
>     new_node->next = temp->next;
>     temp->next = new_node;
>     ```

> [!WARNING]
> ### 2. Mismatched AVL Balance Factor Signs
> *   **The Mistake:** Thinking a right-heavy tree has a positive balance factor.
> *   **The Reality:** Standard AVL definition is $BF = \text{Height}(Left) - \text{Height}(Right)$.
>     *   If a node is **Left-Heavy**, $BF > 0$.
>     *   If a node is **Right-Heavy**, $BF < 0$.
>     *   If $|BF| \ge 2$, rotations are triggered.

> [!WARNING]
> ### 3. Confusing Heapify and Build-Heap Complexities
> *   **The Mistake:** Stating that building a heap from an array of size $N$ takes $O(N \log N)$ time.
> *   **The Reality:**
>     - A single `Heapify` call on a node takes $O(\log N)$ time.
>     - However, **Build-Heap** runs `Heapify` bottom-up. The mathematical sum of node heights converges, yielding a tight time bound of **$O(N)$**.

> [!WARNING]
> ### 4. Linear Probing Deletion Orphanization
> *   **The Mistake:** Deleting an element in a linear probed hash table by simply setting the array slot to `NULL` / Empty.
> *   **The Reality:** If you set a slot to empty, future searches for elements probed *past* that slot will stop scanning when they hit the empty cell, returning false (not found). You must mark deleted slots with a special **Tombstone** flag (e.g. `DELETED`) so searches know to keep scanning.
