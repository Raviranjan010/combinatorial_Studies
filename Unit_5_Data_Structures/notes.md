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
8. [Disjoint Set Data Structures (Union-Find)](#8-disjoint-set-data-structures-union-find)
9. [Trie & Advanced Data Structures](#9-trie--advanced-data-structures)
10. [Choosing the Right Data Structure](#10-choosing-the-right-data-structure)
11. [Important Formulas and Concepts](#11-important-formulas-and-concepts)
12. [Top 25 Last-Minute Exam Facts](#12-top-25-last-minute-exam-facts)
13. [Common Pitfalls & Mistakes to Avoid](#13-common-pitfalls--mistakes-to-avoid)

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

### 🎓 2.1 Foundation & Historical Context
*   **Formal Definition:** A Linked List is a linear data structure consisting of a sequence of nodes, where each node contains its data and a reference (pointer) to the next node. Unlike arrays, elements are not stored in contiguous memory locations.
*   **Simple Analogy (The Treasure Hunt):** Imagine a treasure hunt where each clue contains information (data) and the physical location of the next clue (pointer):
    $$\text{Clue 1} \longrightarrow \text{Clue 2} \longrightarrow \text{Clue 3} \longrightarrow \text{Clue 4}$$
*   **History & Motivation (1955–1960):** Developed by Allen Newell, Cliff Shaw, and Herbert Simon at RAND Corporation as the primary data structure for their Information Processing Language (IPL). They wanted to overcome array limitations such as fixed size, dynamic allocation overhead, and expensive elements shifting.

#### Why Linked Lists Exist
Linked Lists solve key limitations of Arrays:
1.  **Fixed Size:** Standard arrays need pre-allocated contiguous memory. Linked Lists grow dynamically.
2.  **Expensive Insertion:** Inserting at the beginning/middle of an array requires shifting all subsequent elements ($O(N)$).
3.  **Expensive Deletion:** Deleting elements requires shifting elements to fill the gap ($O(N)$).

| Problem | Array Limitation | Linked List Solution |
| :--- | :--- | :--- |
| **Size Constraint** | Fixed-size pre-allocation | Dynamic memory allocation |
| **Insert Cost** | $O(N)$ due to shifting | $O(1)$ pointer update |
| **Delete Cost** | $O(N)$ due to shifting | $O(1)$ pointer update |
| **Memory Waste** | Unused allocated slots | Allocates memory per node on demand |

*   **Real-World Applications:**
    *   *Music Playlists:* Song 1 $\to$ Song 2 $\to$ Song 3 (circular play loop).
    *   *Browser History:* Back and Forward buttons navigate nodes (Doubly Linked List).
    *   *OS Process Scheduling & Memory Management:* The OS tracks free RAM blocks using a free linked list.
    *   *Hash Tables:* Chaining collision handling uses linked lists.

---

### 📖 2.2 Terminology
*   **Node:** The basic building block of a linked list containing data and pointer fields.
*   **Data:** The actual value (integer, character, object) stored in the node.
*   **Pointer (Next/Prev):** A reference variable storing the memory address of the next/previous node.
*   **Head:** A pointer variable pointing to the first node of the list (if NULL, list is empty).
*   **Tail:** The last node in the linked list, which points to `NULL` (in a circular list, it points to `Head`).
*   **NULL:** A special marker indicating the end of the list.
*   **Traversal:** Visiting each node sequentially from the Head to the end.

---

### ⚙️ 2.3 Internal Structure & Memory Layout
Unlike contiguous arrays, linked list nodes are scattered across RAM. Pointers bridge these memory gaps:

```
Memory Allocation Layout:
Address 0x100                Address 0x500                Address 0x800
┌──────────────┐             ┌──────────────┐             ┌──────────────┐
│ Data: 10     │             │ Data: 20     │             │ Data: 30     │
│ Next: 0x500  ├────────────►│ Next: 0x800  ├────────────►│ Next: NULL   │
└──────────────┘             └──────────────┘             └──────────────┘
```
**In C++, a node structure is defined as:**
```cpp
struct Node {
    int data;
    Node* next;
    Node(int val) : data(val), next(nullptr) {}
};
```

---

### 🔄 2.4 Linked List Variants & ASCII Diagrams

#### 1. Singly Linked List (SLL)
Each node has one pointer (`next`) pointing forward:
$$\text{Head} \longrightarrow [10 \mid \bullet] \longrightarrow [20 \mid \bullet] \longrightarrow [30 \mid \text{NULL}]$$

#### 2. Doubly Linked List (DLL)
Each node has two pointers (`next` and `prev`), allowing bidirectional traversal:
$$\text{NULL} \longleftarrow [ \text{prev} \mid 10 \mid \text{next} ] \rightleftharpoons [ \text{prev} \mid 20 \mid \text{next} ] \rightleftharpoons [ \text{prev} \mid 30 \mid \text{next} ] \longrightarrow \text{NULL}$$

#### 3. Circular Linked List (CLL)
The last node points back to the first node, forming a closed ring:
```
      ┌─────────────────────────────────────────┐
      ▼                                         │
Head ─► [10 | •] ──► [20 | •] ──► [30 | •] ──►──┘
```

#### 4. Circular Doubly Linked List (CDLL)
Both forward and backward paths form a closed circle:
```
     ┌──────────────────────────────────────────────────┐
     ▼                                                  │
   [prev| 10 |next] ⇄ [prev| 20 |next] ⇄ [prev| 30 |next]
     │                                                  ▲
     └──────────────────────────────────────────────────┘
```

---

### 🔨 2.5 Insertion & Deletion Mechanics

#### A) Insertion at the Beginning
1.  Create a new node $N$.
2.  Set $N\to\text{next} = \text{Head}$.
3.  Update $\text{Head} = N$.

#### B) Deletion at the Beginning
1.  Verify list is not empty ($\text{Head} \ne \text{NULL}$).
2.  Store the node to delete in a temporary pointer: $\text{Temp} = \text{Head}$.
3.  Move the Head pointer forward: $\text{Head} = \text{Head}\to\text{next}$.
4.  Deallocate the old node memory: $\text{free}(\text{Temp})$ or $\text{delete Temp}$.

#### C) Trace: Inserting a Node in the Middle of an SLL
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

---

### 📊 2.6 Comparison Tables & Relationships

#### Array vs. Linked List
| Feature | Array | Linked List |
| :--- | :--- | :--- |
| **Memory Allocation** | Contiguous (static/dynamic) | Scattered/Non-contiguous (dynamic) |
| **Size** | Fixed at declaration | Dynamic (grows & shrinks) |
| **Access Time** | $O(1)$ random access | $O(N)$ sequential traversal |
| **Insertion/Deletion** | $O(N)$ (requires shifting) | $O(1)$ (if node position is known) |
| **Memory Overhead** | Nil (no pointers) | Extra memory for storing pointer fields |

#### Singly vs. Doubly Linked List
| Feature | Singly Linked List | Doubly Linked List |
| :--- | :--- | :--- |
| **Next Pointer** | Yes | Yes |
| **Previous Pointer**| No | Yes |
| **Traversal** | Forward traversal only | Forward & Backward traversal |
| **Memory Space** | Less memory (1 pointer/node) | More memory (2 pointers/node) |
| **Deletion Ease** | $O(N)$ (must find preceding node)| $O(1)$ (directly access preceding node) |

#### Connection Map
$$\text{Memory / RAM} \longrightarrow \text{Pointers} \longrightarrow \text{Structures} \longrightarrow \mathbf{Linked\ List} \longrightarrow \begin{cases} \text{Stack} \\ \text{Queue} \\ \text{Hashing} \\ \text{Graphs} \end{cases}$$

---

### 🧠 2.7 Memory System & Visual Tricks
*   **Mnemonic: N.P.D:** Every node consists of **N**ode, **P**ointer, **D**ata.
*   **The Train Trick:** Imagine a train. Each coach represents a node. You can't reach coach 4 from the engine without walking through coaches 2 and 3 because each coach only connects to the immediate next one.
*   **Quick Recall:**
    *   *Array* = Labeled boxes in a shelf (contiguous, fast index access).
    *   *Linked List* = Treasure hunt clues (scattered, pointer traversal).

---


---

## 3. Stacks & Queues: Constraints & Implementations

### 🎓 3.1 Foundation & Historical Context
*   **Formal Definition:** Stacks and Queues are linear data structures that enforce structural constraints on how elements are inserted and retrieved, answering the question: *"When multiple items are stored, which item should be removed first?"*
*   **Historical Motivation (1950s–1960s):** As early computing systems struggled to manage function execution pathways and operating system jobs, computer scientists realized they needed two distinct processing models:
    *   *Function Calls:* Last function called must return first (LIFO $\to$ Stack).
    *   *Task Schedules:* First job arrived must run first (FIFO $\to$ Queue).

#### Why Stacks and Queues Exist
They enforce structural integrity. By restricting access to designated boundaries (Top for Stacks, Front/Rear for Queues), they prevent arbitrary modifications and guarantee predictable ordering.

| Data Structure | Principle | Action | Real-Life Analogy | Classic Applications |
| :--- | :--- | :--- | :--- | :--- |
| **Stack** | **LIFO** (Last In First Out) | Add/Remove at the Top | A stack of dinner plates (🍽) | Undo operations, Browser Back button, Recursion management |
| **Queue** | **FIFO** (First In First Out) | Insert at Rear, Delete at Front | People waiting in a ticket line (🙂$\to$🙂$\to$🙂) | Printer jobs spooling, CPU Scheduling, Web server request handling |

---

### 📖 3.2 Terminology
*   **Stack:** A linear structure restricting insertions and deletions to one end (the top).
*   **Queue:** A linear structure allowing insertion at one end (rear) and deletion at the other (front).
*   **LIFO (Last In First Out):** The element added most recently is the first to be removed.
*   **FIFO (First In First Out):** The element added first is the first to be removed.
*   **Push:** The operation of inserting an element into a stack.
*   **Pop:** The operation of removing the top element from a stack.
*   **Peek (or Top):** Inspects the top element without removing it.
*   **Enqueue:** Inserts an element at the rear of a queue.
*   **Dequeue:** Removes the element at the front of a queue.
*   **Front:** The boundary index pointing to the first/oldest element in a queue.
*   **Rear:** The boundary index pointing to the last/newest element in a queue.
*   **Overflow:** Trying to insert an element into a full stack/queue.
*   **Underflow:** Trying to delete an element from an empty stack/queue.

---

### ⚙️ 3.3 Complete Theory & Implementation Models

#### A) Stacks
A Stack is a vertically oriented linear structure:

```
STACK Architecture:
  TOP
   │
   ▼
┌───────┐
│  40   │  (Last element inserted)
├───────┤
│  30   │
├───────┤
│  20   │
├───────┤
│  10   │  (First element inserted)
└───────┘
```

*   **Stack Using Array (C++):**
    We track the stack top using an index integer `top` (initially `-1`):
    *   *Push:* `top++`, then `arr[top] = value`. (Overflow check: `top == MAX_SIZE - 1`)
    *   *Pop:* `value = arr[top]`, then `top--`. (Underflow check: `top == -1`)
*   **Stack Using Linked List:**
    Insertions and deletions are performed at the head node ($O(1)$):
    $$\text{Top} \longrightarrow [30 \mid \bullet] \longrightarrow [20 \mid \bullet] \longrightarrow [10 \mid \text{NULL}]$$

#### B) Queues
A Queue is a horizontally oriented structure:

```
QUEUE Architecture:
Front                                      Rear
  │                                         │
  ▼                                         ▼
┌────┬────┬────┬────┐
│ 10 │ 20 │ 30 │ 40 │
└────┴────┴────┴────┘
```

*   **Queue Using Linked List:**
    Elements are enqueued at the `rear` and dequeued at the `front`:
    $$\text{Front} \longrightarrow [10 \mid \bullet] \longrightarrow [20 \mid \bullet] \longrightarrow [30 \mid \bullet] \longleftarrow \text{Rear}$$

#### C) Queue Variants

##### 1. Simple Queue (Linear Queue)
*   *Limitation:* As elements are dequeued, the `front` pointer moves forward, leaving unusable empty spaces at the front of the array. Even if the array has free slots, a queue can falsely report an "Overflow" if `rear == capacity - 1`.

##### 2. Circular Queue
Resolves linear queue space wastage by wrapping pointers back to index 0 using modulo arithmetic:
```
Circular Array Layout:
         0      1      2      3
       [ 40 ] [ 10 ] [ 20 ] [ 30 ]
         ▲                   ▲
         Front               Rear
```
*   *Enqueue Index:* $\text{rear} = (\text{rear} + 1) \mathbin{\%} \text{capacity}$
*   *Dequeue Index:* $\text{front} = (\text{front} + 1) \mathbin{\%} \text{capacity}$
*   *Full Condition:* $(\text{rear} + 1) \mathbin{\%} \text{capacity} == \text{front}$
*   *Empty Condition:* $\text{front} == -1$

##### 3. Priority Queue
Elements are assigned a priority rating. Higher priority elements are processed before lower priority ones, regardless of enqueue order.
*   *Real-World Analogy:* A hospital emergency room triage where a patient with a critical chest wound is seen before a patient with a sprained ankle.
*   *Priority Levels:* $\text{Critical} \longrightarrow \text{Moderate} \longrightarrow \text{Normal}$

##### 4. Deque (Double-Ended Queue)
Allows enqueue and dequeue operations at both the Front and Rear ends in $O(1)$ time:
$$\text{Front} \rightleftharpoons [10 \mid \bullet] \rightleftharpoons [20 \mid \bullet] \rightleftharpoons [30 \mid \bullet] \longleftarrow \text{Rear}$$

---

### 📊 3.4 Process Flows & Comparison Tables

#### Stack Flowchart
$$\text{START} \longrightarrow \text{Push(x)} \longrightarrow \text{Stack Store} \longrightarrow \text{Pop()} \longrightarrow \text{Retrieve x} \longrightarrow \text{END}$$

#### Queue Flowchart
$$\text{START} \longrightarrow \text{Enqueue(x)} \longrightarrow \text{Queue Line} \longrightarrow \text{Dequeue()} \longrightarrow \text{Retrieve x} \longrightarrow \text{END}$$

#### Stack vs. Queue Comparison
| Feature | Stack | Queue |
| :--- | :--- | :--- |
| **Principle** | LIFO (Last In First Out) | FIFO (First In First Out) |
| **Insertion Point** | Top | Rear |
| **Deletion Point** | Top | Front |
| **Access Restriction**| Can only access the Top element | Can only access the Front element |
| **Real-life Analogy** | Pile of dinner plates | People standing in a ticket line |
| **Advantages** | Simple, fast, recursion-friendly | Fair scheduling, preserves input order |
| **Disadvantages** | No random access, overflow risks | No random access, linear queue space wastage |

#### Exam Trap Table
| Term | Often Confused With | The Difference |
| :--- | :--- | :--- |
| **Push** | Enqueue | Push is for Stacks (top); Enqueue is for Queues (rear). |
| **Pop** | Dequeue | Pop removes from Stack (top); Dequeue removes from Queue (front). |
| **LIFO** | FIFO | LIFO is stack order (last out); FIFO is queue order (first out). |
| **Top** | Front | Top is the active stack cell; Front is the oldest queue cell. |

---

### 🧠 3.5 Memory System & Student Confusions
*   **STACK Mnemonic:**
    *   **S** $\to$ Store at Top
    *   **T** $\to$ Top Pointer
    *   **A** $\to$ Access restricted to top
    *   **C** $\to$ Call Stack implementation
    *   **K** $\to$ Keep LIFO order
*   **QUEUE Mnemonic:**
    *   **Q** $\to$ Quick Service
    *   **U** $\to$ User Line
    *   **E** $\to$ Enter at Rear
    *   **U** $\to$ Use FIFO
    *   **E** $\to$ Exit at Front
*   **Common Confusion (Recursion Call Stack):** Why is recursion implemented using stacks?
    *   *The Reason:* Functions execute in nested layers. The last function called must resolve and return its value before the calling function can continue. This matches LIFO behavior perfectly.
*   **Common Confusion (Queue = LIFO?):** Students often confuse Queue with Stack.
    *   *Recall Association:* Remember waiting in a checkout line. If the cashier served the last person who arrived first, people at the front of the line would riot! Queues are always **FIFO**.

---


## 4. Trees: Binary Trees, BST, and Self-Balancing Trees

### 🎓 4.1 Foundation & Historical Context
*   **Formal Definition:** A Tree is a hierarchical, non-linear data structure consisting of nodes connected by edges, containing no cycles. Unlike linear structures (Arrays, Linked Lists, Stacks, Queues), trees organize data in levels.
*   **Simple Analogy (The Family Tree):** Think of a family ancestry chart:
    ```
        Grandfather
             │
         ┌───┴───┐
       Father  Uncle
         │
        Son
    ```
*   **History & Motivation (1960s):** As file directories grew and databases expanded, linear searching became a performance bottleneck ($O(N)$). Computer scientists developed Trees to enable hierarchical grouping and reduce searching complexity to logarithmic time ($O(\log N)$).

#### Why Trees Exist
They bridge the gap between fast search times (like a sorted array) and fast insert/delete times (like a linked list):
1.  **Hierarchical Representation:** Naturally represents nested structures (folder paths, parser expressions).
2.  **Logarithmic Operations:** Maintains balanced paths, allowing $O(\log N)$ search, insertion, and deletion.

*   **Real-World Applications:**
    *   *File Systems:* Windows/macOS file folder navigation (`C:\Users\Documents`).
    *   *Search Indexing:* Google Search uses Trie and B-Trees to index web pages.
    *   *Databases:* MySQL and Oracle use B/B+ trees to perform quick queries on tables.
    *   *AI and Game Design:* Decision Trees help non-player characters choose actions based on game states.
    *   *Compilers:* Parse Trees analyze code syntax before translation.

---

### 📖 4.2 Terminology
*   **Node:** The individual data element containing a value and pointers to child nodes.
*   **Edge:** The physical link or connection line between two nodes.
*   **Root:** The single topmost node in a tree; it has no parent.
*   **Parent:** A node that has edges leading to nodes at the level below it.
*   **Child:** A node connected to a parent node from the level above.
*   **Sibling:** Nodes that share the same parent node.
*   **Leaf Node (External Node):** A node that has no children (degree = 0).
*   **Internal Node:** A node with at least one child (non-leaf).
*   **Degree:** The number of children connected to a node.
*   **Height:** The length of the longest path from a node to a leaf (measured in edges). The height of a leaf is 0.
*   **Depth:** The path length from the root node to a given node. The depth of the root is 0.
*   **Subtree:** A subset tree formed by a node and all of its descendants.

---

### ⚙️ 4.3 Complete Theory: Tree Types & Architecture

```
TREE Concept Map:
                TREE
                 │
      ┌──────────┴──────────┐
  General Tree          Binary Tree
                             │
     ┌──────────┬────────────┼────────────┬──────────┐
   Full      Complete     Perfect      BST        AVL
```

#### A) General Tree vs. Binary Tree
*   **General Tree:** A node can have any number of children.
*   **Binary Tree:** Each node can have at most **two children** (Left Child and Right Child).
*   *Node Structure in C++:*
    ```cpp
    struct TreeNode {
        int data;
        TreeNode* left;
        TreeNode* right;
        TreeNode(int val) : data(val), left(nullptr), right(nullptr) {}
    };
    ```

#### B) Binary Tree Classification
1.  **Full (Strict) Binary Tree:** Every node has either $0$ or $2$ children. No node has exactly $1$ child.
2.  **Complete Binary Tree:** All levels are completely filled except possibly the last level, which is filled from left to right.
3.  **Perfect Binary Tree:** All internal nodes have exactly $2$ children, and all leaf nodes reside at the identical bottom level.
4.  **Skewed Binary Tree:** Every node has only one child, resembling a Linked List. It exhibits poor search performance ($O(N)$).

---

### 🔍 4.4 Binary Search Tree (BST)
A Binary Search Tree is a binary tree that enforces a strict sorting constraint:
$$\text{Left Subtree Keys} < \text{Root Key} < \text{Right Subtree Keys}$$

```
BST Representation:
              ( 50 )
             /      \
          ( 30 )  ( 70 )
          /    \  /    \
       ( 20 ) (40)(60) (80)
```

#### Search Execution Walkthrough
Let's find key `60` in the BST above:
1.  **Start at Root (50):** Compare search key `60` with root `50`. Since $60 > 50$, search the **right subtree**.
2.  **Move to Right Node (70):** Compare `60` with `70`. Since $60 < 70$, search the **left subtree**.
3.  **Move to Left Node (60):** Compare `60` with `60`. Match found! (Took only 3 comparisons).

---

### ⚖️ 4.5 Self-Balancing Trees (AVL, Red-Black, B-Trees)

#### A) AVL Tree
An AVL tree is a BST where the height difference (**Balance Factor**) between the left and right subtrees of any node is at most $\pm 1$:
$$\text{Balance Factor (BF)} = \text{Height}(Left) - \text{Height}(Right) \quad \text{where } BF \in \{-1, 0, 1\}$$

If $|BF| \ge 2$, balance is restored using rotations:
1.  **Single Left-Left (LL) Rotation:** Used for left-heavy trees. Right-rotate the parent node.
    ```mermaid
    graph TD
        30((30)) --> 20((20))
        20 --> 10((10))
        style 30 fill:#f9f,stroke:#333
        style 20 fill:#bbf,stroke:#333
        style 10 fill:#fff,stroke:#333
    ```
    *Rotates right to:*
    ```mermaid
    graph TD
        20((20)) --> 10((10))
        20 --> 30((30))
        style 20 fill:#bbf,stroke:#333
        style 10 fill:#fff,stroke:#333
        style 30 fill:#fff,stroke:#333
    ```
2.  **Single Right-Right (RR) Rotation:** Used for right-heavy trees. Left-rotate the parent node.
3.  **Double Left-Right (LR) Rotation:** Left-rotate the child node, then right-rotate the parent node.
4.  **Double Right-Left (RL) Rotation:** Right-rotate the child node, then left-rotate the parent node.

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

### 📊 4.6 Comparison Tables & Relationships

#### Tree vs. Linked List
| Feature | Tree | Linked List |
| :--- | :--- | :--- |
| **Structure** | Hierarchical / Non-linear | Linear |
| **Search Time** | Average $O(\log N)$ | Worst-case $O(N)$ |
| **Children** | Multiple children possible | One next node reference only |
| **Relation** | Parent-Child parent relationship | Sequential node chaining |

#### Binary Tree vs. BST
| Feature | Binary Tree | Binary Search Tree (BST) |
| :--- | :--- | :--- |
| **Ordering Constraint**| No placement constraints | Left subtree < Root < Right subtree |
| **Search Complexity** | $O(N)$ sequential traversal | $O(\log N)$ average search time |
| **Sorted Output** | No sorted output property | Inorder traversal yields sorted output |

#### BST vs. AVL Tree
| Feature | Binary Search Tree (BST) | AVL Tree |
| :--- | :--- | :--- |
| **Height Balance** | Not guaranteed (can skew) | Guaranteed balance ($BF \in \{-1,0,1\}$) |
| **Search Time** | Average $O(\log N)$, Worst $O(N)$| Always $O(\log N)$ |
| **Rotations** | Not applicable | Rotates to balance on insertion/deletion |
| **Performance** | Variable depending on input order| Highly stable performance |

---

### 🧠 4.7 Memory System & Common Confusions
*   **BST Mnemonic: L.R.R:** **L**eft is smaller, **R**oot is middle, **R**ight is larger.
*   **AVL Mnemonic: A.V.L:** **A**lways **V**ery **L**evelled (meaning balance is strictly maintained).
*   **Height vs. Depth Confusion:**
    *   *Height:* Start from the bottom leaves and count upwards to the node (leaves are height 0).
    *   *Depth:* Start from the root and count downwards to the node (root is depth 0).
*   **Balanced vs. Complete Tree Confusion:**
    *   *Balanced:* Restricts node heights to prevent skewing.
    *   *Complete:* Restricts shape properties (nodes must be packed left-to-right).
*   **Interview Trap:** Can a BST become a Linked List?
    *   *Answer:* Yes. If you insert elements in sorted order (e.g. `10, 20, 30, 40`), each node will be appended as a right-child, creating a skewed tree that functions like a linear list.
*   **MCQ Trap:** Which tree structure guarantees $O(\log N)$ search times?
    *   *Mistake:* Selecting "Binary Search Tree" (BST).
    *   *Reality:* A BST can degrade to $O(N)$ if skewed. Only self-balancing trees like **AVL Trees** or **Red-Black Trees** guarantee $O(\log N)$ performance.

---


## 5. Graphs: Representations & Traversals

### 🎓 5.1 Foundation & Historical Context
*   **Formal Definition:** A Graph $G = (V, E)$ is a non-linear data structure consisting of a set of vertices $V$ (nodes) connected by a set of edges $E$ (connections), representing arbitrary relationships between objects.
*   **Simple Analogy (The Social Network):** Think of a friendship circle:
    $$\text{Ravi} \longleftrightarrow \text{Amit} \longleftrightarrow \text{Priya}$$
    Vertices represent individuals, and edges represent friendship connections.
*   **History & Motivation (1736):** Born from Leonhard Euler's Seven Bridges of Königsberg problem, which investigated if a route existed to cross each of the city's seven bridges exactly once. This birthed Graph Theory.

#### Why Graphs Exist
Linear structures (arrays, lists) represent sequence, and trees represent hierarchy. However, many real-world systems are networks of many-to-many relationships (e.g. internet routers, flight networks, social connections) which only graphs can model.

*   **Real-World Applications:**
    *   *Google Maps / Uber:* Cities/intersections are vertices, roads are edges with weights representing distances/travel times.
    *   *Social Networks:* Users are vertices, and links (friendships, followers) are edges.
    *   *Computer Networking:* Routers are vertices, and cables/wireless links are edges.
    *   *Airline Logistics:* Airports are vertices, and flight routes are edges.
    *   *AI Knowledge Graphs:* Concept nodes connected by relational links to represent semantic knowledge.

---

### 📖 5.2 Terminology
*   **Vertex (Node):** The basic data point/element in a graph.
*   **Edge:** The line representing a connection between two vertices.
*   **Adjacent Vertices:** Two vertices connected directly by an edge.
*   **Degree:** The number of edges connected to a vertex. In directed graphs:
    *   *Indegree:* Number of incoming edges.
    *   *Outdegree:* Number of outgoing edges.
*   **Path:** A sequence of vertices where each consecutive pair is connected by an edge.
*   **Cycle:** A path that starts and ends at the identical vertex.
*   **Connected Graph:** A graph where a path exists between every pair of vertices.
*   **Disconnected Graph:** A graph containing isolated components that cannot reach each other.
*   **Weighted Graph:** A graph where edges carry values representing cost, distance, or time.
*   **Directed Graph (Digraph):** Edges have arrows indicating unidirectional navigation.
*   **Undirected Graph:** Edges are bidirectional and have no arrows.

---

### ⚙️ 5.3 Complete Theory: Graph Representation Methods

```
Graph Structure:
      A
     / \
    B───C
    │
    D
```

#### Method 1: Adjacency Matrix
A 2D array of size $V \times V$ where `matrix[i][j] = 1` (or weight) indicates an edge between node $i$ and node $j$, and `0` indicates no edge.
```
Adjacency Matrix:
    A  B  C  D
A   0  1  1  0
B   1  0  1  1
C   1  1  0  0
D   0  1  0  0
```
*   *Pros:* $O(1)$ time to check if an edge exists between two nodes.
*   *Cons:* Consumes $O(V^2)$ memory space, making it wasteful for sparse graphs (graphs with few edges).

#### Method 2: Adjacency List
An array of size $V$ where each cell contains a linked list of adjacent neighbors of that vertex.
```
Adjacency List:
A ──► B ──► C
B ──► A ──► C ──► D
C ──► A ──► B
D ──► B
```
*   *Pros:* Space-efficient ($O(V + E)$), storing only existing edges.
*   *Cons:* Finding if an edge exists takes $O(\text{degree}(v))$ time due to list traversal.

| Feature | Adjacency Matrix | Adjacency List |
| :--- | :--- | :--- |
| **Memory Space** | $O(V^2)$ | $O(V + E)$ |
| **Edge Search Time**| $O(1)$ constant time | $O(V)$ worst-case search time |
| **Edge Insertion** | $O(1)$ | $O(1)$ |
| **Ideal For** | Dense graphs ($E \approx V^2$) | Sparse graphs ($E \ll V^2$) |

---

### 🔄 5.4 Graph Traversals: BFS & DFS

#### 1. Breadth-First Search (BFS)
Explores neighbors layer-by-layer (wide exploration) using a **Queue** (FIFO) data structure.
```
BFS Queue Tracing (Start Node A):
Queue State      Processed Vertex      Visited Set
[A]              A                     {A}
[B, C]           B                     {A, B, C}
[C, D]           C                     {A, B, C, D}
[D]              D                     {A, B, C, D}
[]               -                     -
BFS Order: A, B, C, D
```
*   **BFS Algorithm:**
    1.  Enqueue start node and mark as visited.
    2.  While queue is not empty:
        *   Dequeue front node.
        *   Visit node.
        *   Enqueue all unvisited neighbor nodes and mark them as visited.

#### 2. Depth-First Search (DFS)
Explores deep along a path branch before backtracking using a **Stack (LIFO)** or **Recursion**.
*   **DFS Algorithm:**
    1.  Visit current node and mark as visited.
    2.  Recursively call DFS for each unvisited neighbor.
*   *DFS Order (Start Node A):* A, B, C, D (for same graph).

---

### 📊 5.5 Comparison Tables & Relationships

#### Tree vs. Graph
| Feature | Tree | Graph |
| :--- | :--- | :--- |
| **Root Node** | Exactly one root node | No designated root node |
| **Cycles** | Cycles are strictly forbidden | Cycles can exist |
| **Paths** | Exactly one path between any two nodes| Multiple paths can exist |
| **Structure** | Hierarchical | Network / Arbitrary |

#### Directed vs. Undirected Graphs
| Feature | Directed Graph | Undirected Graph |
| :--- | :--- | :--- |
| **Edge Navigation** | One-way arrows (unidirectional) | Bidirectional links |
| **Degree Calculation**| Indegree and Outdegree | Simple degree count |
| **Analogy** | Twitter following (A follows B) | Facebook friendship (A connected to B) |

#### BFS vs. DFS
| Feature | BFS | DFS |
| :--- | :--- | :--- |
| **Helper Data Structure**| Queue (FIFO) | Stack (LIFO) or Recursion |
| **Traversal Behavior** | Level-by-level (wide) | Depth-first (deep) |
| **Shortest Path** | Guarantees shortest path for unweighted| Does not guarantee shortest path |
| **Memory Space** | More memory ($O(V)$ queue size) | Less memory ($O(\text{height})$ stack) |

#### Graph Traversal Flowcharts
```
BFS Flow: Start ──► Enqueue Root ──► Visit Node ──► Enqueue Neighbors ──► Queue Empty? (No ──► Repeat / Yes ──► End)

DFS Flow: Start ──► Visit Node ──► Go Deep to Neighbor ──► Dead End? (No ──► Go Deep / Yes ──► Backtrack ──► End)
```

#### Connection & Future Topics
$$\text{Arrays/Lists} \longrightarrow \text{Trees} \longrightarrow \mathbf{Graphs} \longrightarrow \begin{cases} \text{Dijkstra's Shortest Path} \\ \text{Bellman-Ford / Floyd-Warshall} \\ \text{Kruskal's & Prim's MST} \\ \text{Topological Sorting} \end{cases}$$

---

### 🧠 5.6 Common Confusions & Memory Systems
*   **Memory Association:**
    *   *BFS* $\to$ Breadth $\to$ Wide (like ripples expanding in water). Uses **Queue**.
    *   *DFS* $\to$ Depth $\to$ Deep (like exploring a deep cave path). Uses **Stack**.
*   **The Connected Cycle Rule:** A tree is simply a special graph: it is a *connected graph containing no cycles*.
*   **Interview Trap (DFS Stack Overhead):** Even though DFS uses $O(V)$ auxiliary space, on a skewed graph the recursion depth reaches $V$, which can trigger a **Stack Overflow** on systems with small call stack sizes.
*   **Recall Trick (Matrix vs List):**
    *   Matrix is like a grid of seats (wastes space if empty, but quick to check seat coordinates).
    *   List is like a line of names (only lists present people, but you must scan list to check a name).

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

## 8. Disjoint Set Data Structures (Union-Find)

### 📖 The Social Group Mergers Analogy
Imagine a party where everyone starts as a stranger (individual groups of size 1). 
- If Person A and Person B chat and become friends, they merge their groups.
- If we want to check if Person X and Person Y know each other (either directly or through a chain of friends), we find the "representative" (leader) of their groups. If they have the same leader, they are in the same social group.

In computer science, a **Disjoint Set (Union-Find)** keeps track of elements partitioned into non-overlapping (disjoint) subsets.

---

### 8.1 Key Operations
1.  **`MakeSet(x)`:** Creates a new set containing only element `x` (parent of `x` is `x`).
2.  **`Find(x)`:** Returns the representative (leader) of the set containing `x` by traversing up parent pointers until it finds a node that is its own parent.
3.  **`Union(x, y)`:** Merges the sets containing `x` and `y` by setting the parent of one representative to be the other representative.

---

### 8.2 Crucial Optimizations
Without optimization, `Union` and `Find` can degenerate to $O(N)$ time (like a skewed tree/linked list). Two optimizations achieve near-$O(1)$ performance:
1.  **Union by Rank:** Always attach the tree with the smaller height (rank) under the root of the tree with the larger height. This prevents trees from growing skewedly.
2.  **Path Compression:** During `Find(x)`, update the parent pointer of every node along the traversal path to point directly to the root representative. This flattens the tree structure dynamically!

```
    Without Path Compression:               With Path Compression:
             ( Root )                             ( Root )
              /    \                               / | \ \
            (A)    (B)                           (A)(B)(C)(D)
            /
          (C)
          /
        (D)
```

*   **Time Complexity:** With Union by Rank and Path Compression, operations run in $O(\alpha(N))$ time, where $\alpha$ is the inverse Ackermann function. For all practical values of $N$, $\alpha(N) < 5$, yielding virtually **$O(1)$ constant time**.

---

## 9. Trie & Advanced Data Structures

### 📖 The Dictionary Prefix Index Analogy
If you are looking up words in an English dictionary starting with "cat", you don't read the whole dictionary. You find the letter 'c', then 'a', then 't'.
A **Trie (Prefix Tree)** is a tree-like search structure used to store and retrieve keys (usually strings) over a shared alphabet. Every node (except root) represents a single character, and paths from root to leaf reconstruct words.

```
                  (root)
                   /  \
                 (c)  (d)
                 /      \
               (a)      (o)
               /          \
             (t*)         (g*)   (* indicates end of word)
```

---

### 9.1 Trie Complexity
If word length $= m$, then:
*   **Insertion:** $O(m)$
*   **Search:** $O(m)$
*   **Deletion:** $O(m)$
*   **Key Fact:** Trie time complexity depends **only on the length of the word ($m$)**, not the total number of words stored in the Trie! Excellent for autocomplete and IP routing prefixes.

---

### 9.2 Other Advanced Structures
*   **AVL Tree:** Height-balanced BST. The heights of the left and right subtrees of any node differ by at most $\pm 1$. Restores balance using rotations.
*   **B-Tree / B+ Tree:** Multi-way search trees optimized for reading and writing large blocks of data. Widely used in database indexes and file systems.

---

## 10. Choosing the Right Data Structure

To solve software problems efficiently, you must select the right structure:

| Use Case Requirement | Best Data Structure | Rationale / Key Benefit |
| :--- | :--- | :--- |
| **Fast random access by index** | Array / ArrayList | Contiguous memory provides $O(1)$ access. |
| **Frequent insertions/deletions** | Linked List | Modifying pointers takes $O(1)$ without element shifting. |
| **Undo/Redo history, Parentheses matching**| Stack | LIFO (Last-In, First-Out) matching. |
| **BFS traversal, Print queues** | Queue | FIFO (First-In, First-Out) scheduling. |
| **Hierarchical relations (e.g., Folder directory)**| Tree | Naturally represents parent-child structures. |
| **Social network, road maps** | Graph | Network nodes connected by directional/weighted edges. |
| **Fast lookups by custom key** | Hash Table | $O(1)$ average search time via hash index. |
| **Priority scheduling, finding min/max** | Binary Heap | Root is always min/max; updates in $O(\log N)$. |
| **Autocomplete, dictionary prefix search** | Trie | Searches strings in $O(word\_length)$ time. |
| **Connectivity / cycle checking** | Disjoint Set | Near $O(1)$ disjoint set membership testing. |

---

## 11. Important Formulas and Concepts

*   **Tree Node-Edge Count:** A tree containing $N$ nodes always contains exactly:
    $$\text{Edges} = N - 1$$
*   **Max Nodes at Level $l$** (root is level 0):
    $$\text{Max Nodes} = 2^l$$
*   **Total Nodes in Perfect Binary Tree of height $h$:**
    $$\text{Nodes} = 2^{h+1} - 1$$
*   **Leaf Nodes in Perfect Binary Tree:**
    $$\text{Leaves} = 2^h = \text{Internal Nodes} + 1$$
*   **Binary Heap Indexing** (for node at index $i$, 0-indexed):
    - Left Child: $2i + 1$
    - Right Child: $2i + 2$
    - Parent: $\lfloor (i - 1) / 2 \rfloor$
*   **Hashing Load Factor:**
    $$\alpha = \frac{N}{M} \quad (\text{where } N = \text{keys stored}, M = \text{table capacity})$$

---

## 12. Top 25 Last-Minute Exam Facts

1.  Arrays use contiguous memory; Linked Lists use non-contiguous memory.
2.  Stacks follow LIFO (Last In First Out); Queues follow FIFO (First In First Out).
3.  BFS uses a Queue; DFS uses a Stack (or recursion).
4.  Binary Search runs in $O(\log N)$ and requires a sorted array.
5.  Inorder traversal of a BST always yields keys in sorted order.
6.  A tree with $N$ nodes has $N-1$ edges.
7.  A Binary Heap is a complete binary tree represented inside an array.
8.  Max-Heap root contains the largest element; Min-Heap root contains the smallest.
9.  Heap Sort runs in $O(N \log N)$ in all cases (best, average, worst).
10. Hash Table searches take $O(1)$ on average and $O(N)$ in the worst case.
11. Hashing collision occurs when two distinct keys map to the same table index.
12. Chaining resolves collisions by building linked lists at table slots.
13. Linear Probing scans slots sequentially, causing Primary Clustering.
14. Trie is also called a Prefix Tree, commonly used in autocomplete.
15. Disjoint Set uses Union and Find operations to manage partitions.
16. Path Compression flattens trees to speed up Find operations.
17. Union by Rank prevents unbalanced, deep trees by attaching shorter trees below taller ones.
18. Kruskal's MST algorithm uses Disjoint Sets to check for cycles.
19. AVL Tree is a self-balancing BST where heights differ by at most $\pm 1$.
20. B-Trees are widely used in databases to minimize disk I/O.
21. Dynamic Array resizing (e.g. vector) takes $O(1)$ amortized insertion time.
22. Doubly Linked List nodes hold pointers to both next and previous nodes.
23. Stack overflow is caused by pushing onto a full stack; underflow by popping from an empty one.
24. Circular Queue avoids space wastage by wrapping rear/front pointers back to index 0.
25. The height of a balanced tree with $N$ nodes is $O(\log N)$.

---

## 13. Common Pitfalls & Mistakes to Avoid

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
