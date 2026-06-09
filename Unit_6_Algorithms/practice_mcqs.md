# Unit VI: Algorithms - MCQ Bank

Test your mastery of runtime analysis, recurrences, sorting benchmarks, Dynamic Programming, and Greedy strategies with these 130 solved, high-probability Multiple Choice Questions.

---

## 🔷 Topic 1: Complexity Analysis & Recurrences

#### Q1. Which asymptotic notation represents a mathematically tight bound (average case)?
- A) Big-O ($O$)
- B) Big-Omega ($\Omega$)
- C) Big-Theta ($\Theta$)
- D) Little-o ($o$)
- **Answer: ✅ C**
- **Explanation**: Big-O is an upper bound, Big-Omega is a lower bound, and Big-Theta is a tight bound (both upper and lower bound).

#### Q2. What is the correct order of growth rates from fastest (best) to slowest (worst)?
- A) $O(1) < O(N) < O(\log N) < O(N^2)$
- B) $O(1) < O(\log N) < O(N) < O(N \log N) < O(N^2) < O(2^N)$
- C) $O(\log N) < O(1) < O(N) < O(N^2)$
- D) $O(1) < O(N) < O(N \log N) < O(2^N) < O(N^2)$
- **Answer: ✅ B**
- **Explanation**: Constant time $O(1)$ is fastest, followed by logarithmic $O(\log N)$, linear $O(N)$, linearithmic $O(N \log N)$, quadratic $O(N^2)$, and exponential $O(2^N)$.

#### Q3. Solve the recurrence relation $T(N) = 2T(N/2) + N$ using the Master Theorem:
- A) $T(N) = \Theta(\log N)$
- B) $T(N) = \Theta(N)$
- C) $T(N) = \Theta(N \log N)$
- D) $T(N) = \Theta(N^2)$
- **Answer: ✅ C**
- **Explanation**: Here, $a=2, b=2, d=1$ since $f(N) = N = N^1$. 
  - Compare $\log_b a = \log_2 2 = 1$ with $d = 1$.
  - Since $d = \log_b a$ (Case 2 of the Master Theorem), the solution is $T(N) = \Theta(N^{\log_b a} \log N) = \Theta(N \log N)$.

#### Q4. Solve the recurrence relation $T(N) = T(N/2) + 1$:
- A) $T(N) = \Theta(\log N)$
- B) $T(N) = \Theta(N)$
- C) $T(N) = \Theta(N \log N)$
- D) $T(N) = \Theta(1)$
- **Answer: ✅ A**
- **Explanation**: This is the recurrence for Binary Search. $a=1, b=2, d=0$ since $f(N) = 1 = N^0$.
  - $\log_b a = \log_2 1 = 0$. Since $d = \log_b a = 0$ (Case 2), the solution is $T(N) = \Theta(N^0 \log N) = \Theta(\log N)$.

#### Q5. What is the time complexity of the following code snippet?
```cpp
for (int i = 0; i < n; i++) {
    for (int j = 1; j < n; j = j * 2) {
        // Constant time operation
    }
}
```
- A) $O(N^2)$
- B) $O(N \log N)$
- C) $O(N)$
- D) $O(\log N)$
- **Answer: ✅ B**
- **Explanation**: The outer loop runs $N$ times. The inner loop variable $j$ doubles each step, running $\log N$ times. Thus, the total complexity is $O(N \log N)$.

---

## 🔷 Topic 2: Sorting Algorithms

#### Q6. Which sorting algorithm has an optimal best-case time complexity of $O(N)$ when the input array is already sorted?
- A) Selection Sort
- B) Merge Sort
- C) Insertion Sort
- D) Heap Sort
- **Answer: ✅ C**
- **Explanation**: Insertion sort only performs one comparison per element and no shifts when the array is sorted, leading to a linear $O(N)$ runtime. Selection sort always performs $O(N^2)$ comparisons.

#### Q7. Which sorting algorithm is stable but requires $O(N)$ auxiliary space?
- A) Quick Sort
- B) Heap Sort
- C) Merge Sort
- D) Bubble Sort
- **Answer: ✅ C**
- **Explanation**: Merge sort requires a temporary array of size $N$ to merge sub-arrays, taking $O(N)$ space. It is a stable sort. Heap sort takes $O(1)$ space but is unstable.

#### Q8. What is the worst-case complexity of Quick Sort, and when does it occur?
- A) $O(N \log N)$, when the array is randomly shuffled
- B) $O(N^2)$, when the array is already sorted and the pivot is chosen as the first or last element
- C) $O(N^2)$, when the array has duplicate values
- D) $O(N \log N)$, when the pivot is the median
- **Answer: ✅ B**
- **Explanation**: If the array is sorted and the pivot is the first or last element, the partitions are unbalanced ($0$ and $N-1$ elements). This results in a recursion depth of $N$ and a total complexity of $O(N^2)$.

#### Q9. Which of the following sorting algorithms is NOT stable?
- A) Merge Sort
- B) Bubble Sort
- C) Insertion Sort
- D) Selection Sort
- **Answer: ✅ D**
- **Explanation**: Selection sort can swap non-adjacent duplicate elements, altering their relative order.

---

## 🔷 Topic 3: Divide & Conquer

#### Q10. The Divide and Conquer paradigm involves which three steps?
- A) Select, Sort, Merge
- B) Divide, Conquer, Combine
- C) Memoize, Tabulate, Solve
- D) Input, Process, Output
- **Answer: ✅ B**
- **Explanation**: It divides the problem into subproblems, conquers them recursively, and combines their solutions.

#### Q11. Which algorithm uses Divide and Conquer to multiply two matrices in $O(N^{2.81})$ time instead of the naive $O(N^3)$ time?
- A) Dijkstra's Algorithm
- B) Strassen's Matrix Multiplication
- C) Floyd-Warshall Algorithm
- D) Kruskal's Algorithm
- **Answer: ✅ B**
- **Explanation**: Strassen's algorithm uses algebraic groupings to reduce the number of recursive matrix multiplications from 8 to 7, bringing the runtime down to $O(N^{2.81})$.

#### Q12. Binary Search is a classic example of:
- A) Greedy Strategy
- B) Dynamic Programming
- C) Divide and Conquer (specifically Decrease and Conquer)
- D) Backtracking
- **Answer: ✅ C**
- **Explanation**: Binary Search divides the search space in half at each step, conquering the active half and discarding the other.

---

## 🔷 Topic 4: Dynamic Programming

#### Q13. What are the two core properties required to apply Dynamic Programming to a problem?
- A) Optimal Substructure and Greedy Choice
- B) Overlapping Subproblems and Optimal Substructure
- C) Independency and Base Cases
- D) Recursion and Backtracking
- **Answer: ✅ B**
- **Explanation**: DP requires overlapping subproblems (so subproblem results can be reused) and optimal substructure (so optimal subproblem solutions build the global optimal solution).

#### Q14. The difference between Memoization and Tabulation is:
- A) Memoization is bottom-up, Tabulation is top-down
- B) Memoization is recursive (top-down), Tabulation is iterative (bottom-up)
- C) Tabulation uses more memory than Memoization
- D) Memoization is used for greedy algorithms
- **Answer: ✅ B**
- **Explanation**: Memoization is a top-down approach that caches recursive calls. Tabulation is a bottom-up approach that fills an iteration table starting from the base cases.

#### Q15. What is the time complexity of the Dynamic Programming solution to the 0/1 Knapsack problem with $N$ items and a knapsack capacity of $W$?
- A) $O(N \log N)$
- B) $O(2^N)$
- C) $O(N \cdot W)$
- D) $O(N^2)$
- **Answer: ✅ C**
- **Explanation**: The DP table has size $(N+1) \times (W+1)$, taking $O(N \cdot W)$ time to compute. This is a pseudo-polynomial time complexity.

#### Q16. Which of the following is solved optimally using Dynamic Programming?
- A) Fractional Knapsack
- B) Huffman Coding
- C) Longest Common Subsequence (LCS)
- D) Minimum Spanning Tree
- **Answer: ✅ C**
- **Explanation**: LCS is a classic DP problem ($O(M \cdot N)$ complexity). Fractional Knapsack, Huffman Coding, and MST are solved using Greedy algorithms.

#### Q17. The Floyd-Warshall algorithm finds the shortest path between all pairs of nodes in a graph in:
- A) $O((V+E)\log V)$ time
- B) $O(V \cdot E)$ time
- C) $O(V^3)$ time
- D) $O(V^2)$ time
- **Answer: ✅ C**
- **Explanation**: Floyd-Warshall is a DP-based algorithm that uses three nested loops over the vertices, resulting in $O(V^3)$ runtime.

---

## 🔷 Topic 5: Greedy Algorithms

#### Q18. A Greedy algorithm:
- A) Guarantees an optimal solution for all problems
- B) Backtracks when a choice leads to a sub-optimal state
- C) Makes the locally optimal choice at each step without backtracking
- D) Solves all overlapping subproblems first
- **Answer: ✅ C**
- **Explanation**: Greedy algorithms make immediate, locally optimal choices and never backtrack, making them fast but not always globally optimal.

#### Q19. Huffman Coding is used for:
- A) Finding shortest paths in graphs
- B) Lossless data compression using variable-length codes
- C) Encryption
- D) Sorting strings
- **Answer: ✅ B**
- **Explanation**: Huffman coding assigns shorter binary codes to more frequent characters, optimizing data compression.

#### Q20. Dijkstra's Single-Source Shortest Path algorithm is a Greedy algorithm that:
- A) Works correctly on graphs with negative edge weights
- B) Requires $O(V^3)$ time
- C) Fails on graphs with negative edge weights
- D) Finds the Minimum Spanning Tree
- **Answer: ✅ C**
- **Explanation**: Dijkstra's algorithm assumes that once a vertex is visited, its shortest path is finalized. This assumption fails if there are negative edge weights.

#### Q21. Which algorithm constructs a Minimum Spanning Tree (MST) by sorting all edges by weight and adding them one by one if they do not create a cycle?
- A) Prim's Algorithm
- B) Dijkstra's Algorithm
- C) Kruskal's Algorithm
- D) Bellman-Ford Algorithm
- **Answer: ✅ C**
- **Explanation**: Kruskal's is an edge-based greedy algorithm that uses a Union-Find data structure to check for cycles while adding sorted edges.

#### Q22. Prim's MST algorithm builds the tree by:
- A) Sorting all edges in the graph
- B) Growing the tree vertex-by-vertex, adding the cheapest edge connected to the current tree
- C) Using dynamic programming
- D) Dividing the graph into sub-graphs
- **Answer: ✅ B**
- **Explanation**: Prim's is a vertex-based greedy algorithm. It starts at a root vertex and adds the cheapest edge connecting a visited vertex to an unvisited vertex.

---

## 🔷 Topic 6: Graph & String Algorithms

#### Q23. Which algorithm should be used to find the shortest path in a graph containing negative edge weights and detect negative weight cycles?
- A) Dijkstra's Algorithm
- B) Bellman-Ford Algorithm
- C) Floyd-Warshall Algorithm
- D) Kruskal's Algorithm
- **Answer: ✅ B**
- **Explanation**: Bellman-Ford runs in $O(V \cdot E)$ time. It handles negative weights and detects negative cycles by running a final relaxation step.

#### Q24. What is the time complexity of the Knuth-Morris-Pratt (KMP) string matching algorithm for a text of length $N$ and pattern of length $M$?
- A) $O(N \cdot M)$
- B) $O(N + M)$
- C) $O(N \log M)$
- D) $O(M \log N)$
- **Answer: ✅ B**
- **Explanation**: KMP precomputes a prefix function (pi array) in $O(M)$ time and searches the text in $O(N)$ time, avoiding backtracking over the text.

#### Q25. The Rabin-Karp string matching algorithm uses which technique to search for a pattern?
- A) A prefix tree (Trie)
- B) Rolling Hash function
- C) Dynamic programming
- D) Greedy choices
- **Answer: ✅ B**
- **Explanation**: Rabin-Karp calculates hash values for the pattern and for sliding windows of the text. It uses a rolling hash to update values in $O(1)$ time.

---

## 🔷 Topic 7: General Algorithmic Concepts

#### Q26. Space complexity measures:
- A) The physical disk space occupied by the program code
- B) The maximum RAM memory required by the algorithm during execution as a function of input size
- C) The CPU cache lines utilized
- D) The size of the compiler
- **Answer: ✅ B**
- **Explanation**: Space complexity measures the auxiliary memory needed by the algorithm during execution, excluding the input space itself.

#### Q27. What is the time complexity of building a heap of size $N$?
- A) $O(N)$
- B) $O(N \log N)$
- C) $O(\log N)$
- D) $O(N^2)$
- **Answer: ✅ A**
- **Explanation**: Floyd's heap construction method runs in $O(N)$ time by processing nodes bottom-up.

#### Q28. An algorithm with a time complexity of $O(2^N)$ is classified as:
- A) Polynomial time
- B) Logarithmic time
- C) Exponential time
- D) Factorial time
- **Answer: ✅ C**
- **Explanation**: $O(2^N)$ is exponential, meaning runtime doubles with each incremental addition to the input size.

#### Q29. In a greedy fractional knapsack problem, items are sorted by:
- A) Maximum value
- B) Minimum weight
- C) Value-to-weight ratio ($v_i / w_i$)
- D) Random selection
- **Answer: ✅ C**
- **Explanation**: Sorting items by value-to-weight ratio allows us to maximize total value by greedily taking the most valuable density items first.

#### Q30. The Bellman-Ford algorithm relax all edges in the graph how many times?
- A) $V$ times
- B) $V - 1$ times
- C) $E$ times
- D) $E - 1$ times
- **Answer: ✅ B**
- **Explanation**: The shortest path in a graph with $V$ vertices can contain at most $V-1$ edges. Thus, Bellman-Ford relaxes all edges $V-1$ times.

#### Q31. What is the recurrence relation for the Tower of Hanoi problem?
- A) $T(N) = T(N-1) + 1$
- B) $T(N) = 2T(N-1) + 1$
- C) $T(N) = 2T(N/2) + 1$
- D) $T(N) = T(N-2) + 2$
- **Answer: ✅ B**
- **Explanation**: Tower of Hanoi requires moving $N-1$ disks to an auxiliary peg ($T(N-1)$), moving the largest disk to the target peg ($1$), and moving the $N-1$ disks to the target peg ($T(N-1)$). This yields $T(N) = 2T(N-1) + 1$, which solves to $O(2^N)$.

#### Q32. What is the time complexity of the recursion tree representing the Fibonacci recurrence $T(N) = T(N-1) + T(N-2)$ without memoization?
- A) $O(N)$
- B) $O(\log N)$
- C) $O(2^N)$
- D) $O(N^2)$
- **Answer: ✅ C**
- **Explanation**: The recursion tree branches twice at each level, leading to an exponential number of redundant calculations ($O(2^N)$).

#### Q33. Dynamic Programming Fibonacci calculation takes how much time with memoization/tabulation?
- A) $O(N)$
- B) $O(2^N)$
- C) $O(N^2)$
- D) $O(\log N)$
- **Answer: ✅ A**
- **Explanation**: Caching subproblem results reduces the number of calculations to $N$, yielding a linear $O(N)$ runtime.

#### Q34. Topological sort is applicable to which type of graphs?
- A) Any directed graph
- B) Undirected graphs
- C) Directed Acyclic Graphs (DAGs)
- D) Complete graphs
- **Answer: ✅ C**
- **Explanation**: Topological sort orders vertices such that for every directed edge $U \to V$, $U$ comes before $V$. This is only possible if the graph is directed and contains no cycles (DAG).

#### Q35. What is the maximum number of edges in a Minimum Spanning Tree of a graph with $V$ vertices?
- A) $V$
- B) $V - 1$
- C) $V + 1$
- D) $E$
- **Answer: ✅ B**
- **Explanation**: An MST must connect all $V$ vertices without forming cycles, which requires exactly $V-1$ edges.

#### Q36. In Kruskal's algorithm, cycle detection is performed using which data structure?
- A) Stack
- B) Queue
- C) Disjoint Set Union (DSU / Union-Find)
- D) Hash Table
- **Answer: ✅ C**
- **Explanation**: DSU tracks connected components and checks if two vertices belong to the same set in near-constant time ($O(\alpha(V))$).

#### Q37. What is the runtime complexity of the naive string matching algorithm?
- A) $O(N + M)$
- B) $O(N \cdot M)$
- C) $O(N^2)$
- D) $O(M^2)$
- **Answer: ✅ B**
- **Explanation**: The naive algorithm shifts the pattern one character at a time and compares it against the text, taking $O(N \cdot M)$ time in the worst case.

#### Q38. In the Master Theorem, if $T(N) = 8T(N/2) + N^2$, the time complexity is:
- A) $\Theta(N^2)$
- B) $\Theta(N^3)$
- C) $\Theta(N^2 \log N)$
- D) $\Theta(N \log N)$
- **Answer: ✅ B**
- **Explanation**: $a=8, b=2 \implies N^{\log_2 8} = N^3$.
  - Compare $N^3$ with $f(N) = N^2$.
  - Since $f(N) = O(N^2) = O(N^{3-\epsilon})$ (Case 1), the solution is $T(N) = \Theta(N^3)$.

#### Q39. What is the space complexity of in-place Quick Sort in the average case?
- A) $O(1)$
- B) $O(N)$
- C) $O(\log N)$
- D) $O(N \log N)$
- **Answer: ✅ C**
- **Explanation**: Quick Sort is in-place (it doesn't use temporary arrays), but its recursive call stack requires $O(\log N)$ space on average.

#### Q40. Which algorithm is best suited for finding the shortest path between all pairs of vertices in a sparse graph?
- A) Floyd-Warshall
- B) Running Dijkstra's algorithm $V$ times with a binary heap
- C) Bellman-Ford
- D) Prim's
- **Answer: ✅ B**
- **Explanation**: For sparse graphs ($E \ll V^2$), running Dijkstra $V$ times takes $O(V \cdot E \log V)$ time, which is faster than Floyd-Warshall's $O(V^3)$ runtime.

#### Q41. In dynamic programming, the Matrix Chain Multiplication problem is solved in:
- A) $O(N)$ time
- B) $O(N \log N)$ time
- C) $O(N^2)$ time
- D) $O(N^3)$ time
- **Answer: ✅ D**
- **Explanation**: The DP recurrence calculates parenthesization options over three nested loops, taking $O(N^3)$ time.

#### Q42. The prefix function (LPS array) in KMP string matching stores:
- A) The hash values of substrings
- B) The length of the longest proper prefix that is also a suffix for each substring of the pattern
- C) Character frequencies
- D) Pointer jumps
- **Answer: ✅ B**
- **Explanation**: The LPS (Longest Prefix Suffix) array tells KMP how many characters of the pattern can be skipped during a mismatch.

#### Q43. What is the worst-case time complexity of the Rabin-Karp algorithm?
- A) $O(N + M)$
- B) $O(N \cdot M)$
- C) $O(N^2)$
- D) $O(M^2)$
- **Answer: ✅ B**
- **Explanation**: In the worst-case scenario (e.g., matching a pattern like `AAAA` in a text of `AAAAAA` where all hash values collide), Rabin-Karp performs character comparisons for every step, degrading to $O(N \cdot M)$ time.

#### Q44. An algorithm's space complexity includes:
- A) Only the stack memory
- B) Only the heap memory
- C) The input space and auxiliary space used during execution
- D) The source code size
- **Answer: ✅ C**
- **Explanation**: Total space complexity is the sum of the input space and the auxiliary space used by variables, structures, and the call stack.

#### Q45. Which data structure is used to implement a priority queue in Dijkstra's algorithm for optimal time complexity?
- A) Queue
- B) Min-Heap (or Fibonacci Heap)
- C) Stack
- D) BST
- **Answer: ✅ B**
- **Explanation**: A Min-Heap extracts the minimum distance vertex in $O(\log V)$ time, optimizing Dijkstra's runtime.

#### Q46. If an algorithm takes $T(N) = T(N-1) + O(1)$ time, its time complexity is:
- A) $O(1)$
- B) $O(\log N)$
- C) $O(N)$
- D) $O(N^2)$
- **Answer: ✅ C**
- **Explanation**: $T(N) = T(N-1) + c = T(N-2) + 2c = \dots = N \cdot c = O(N)$.

#### Q47. If an algorithm takes $T(N) = T(N-1) + O(N)$ time, its time complexity is:
- A) $O(N)$
- B) $O(N \log N)$
- C) $O(N^2)$
- D) $O(2^N)$
- **Answer: ✅ C**
- **Explanation**: $T(N) = T(N-1) + N = T(N-2) + (N-1) + N = \sum_{i=1}^{N} i = \frac{N(N+1)}{2} = O(N^2)$. This is the recurrence for Selection/Insertion sort.

#### Q48. Which sorting algorithm is stable and has a guaranteed time complexity of $O(N \log N)$ in all cases?
- A) Quick Sort
- B) Selection Sort
- C) Merge Sort
- D) Insertion Sort
- **Answer: ✅ C**
- **Explanation**: Merge sort divides the array in half and merges them in $O(N)$ time, guaranteeing $O(N \log N)$ runtime in the best, average, and worst cases.

#### Q49. The activity selection problem (greedy approach) selects the next activity based on:
- A) Earliest start time
- B) Earliest finish time
- C) Shortest duration
- D) Maximum profit
- **Answer: ✅ B**
- **Explanation**: Selecting the activity that finishes first leaves the maximum amount of time for subsequent activities.

#### Q50. Can the Master Theorem be used to solve the recurrence $T(N) = 2T(N/2) + N \log N$?
- A) Yes, directly
- B) No, because $f(N) = N \log N$ is not polynomial
- C) Yes, using Case 2 extension where $T(N) = \Theta(N \log^2 N)$
- D) No, because $a < 1$
- **Answer: ✅ C**
- **Explanation**: Although not solvable by the standard Master Theorem, the Case 2 extension ($f(N) = \Theta(N^{\log_b a} \log^k N)$ with $k=1$) yields $T(N) = \Theta(N \log^2 N)$.

---

## 🔷 Topic 3: Advanced Complexity & Recurrence Solvers

#### Q51. What is the asymptotic tight bound ($\Theta$) of the function $f(N) = 3N^2 + 5N \log N + 100$?
- A) $\Theta(N \log N)$
- B) $\Theta(N^2)$
- C) $\Theta(N^2 \log N)$
- D) $\Theta(1)$
- **Answer: ✅ B**
- **Explanation**: In complexity analysis, we ignore constant factors (3 and 100) and focus on the highest-order growing term as $N \to \infty$. Since $N^2$ grows faster than $N \log N$ and constant terms, the tight bound is $\Theta(N^2)$.

#### Q52. Which of the following statements is mathematically correct regarding asymptotic notations?
- A) If $f(N) = O(g(N))$, then $g(N) = O(f(N))$
- B) If $f(N) = \Theta(g(N))$, then $f(N) = O(g(N))$ and $f(N) = \Omega(g(N))$
- C) If $f(N) = \Omega(g(N))$, then $f(N) = O(g(N))$
- D) $N^2 = \Omega(N^3)$
- **Answer: ✅ B**
- **Explanation**: By definition, $f(N)$ is a tight bound ($\Theta$) of $g(N)$ if and only if it is simultaneously an upper bound ($O$) and a lower bound ($\Omega$).

#### Q53. Solve the recurrence relation $T(N) = 4T(N/2) + N$ using the Master Theorem:
- A) $T(N) = \Theta(N)$
- B) $T(N) = \Theta(N \log N)$
- C) $T(N) = \Theta(N^2)$
- D) $T(N) = \Theta(N^3)$
- **Answer: ✅ C**
- **Explanation**: Here, $a=4, b=2, d=1$ since $f(N) = N^1$.
  - Compute $\log_b a = \log_2 4 = 2$.
  - Compare $d=1$ with $\log_b a = 2$.
  - Since $d < \log_b a$ ($1 < 2$), Case 1 of the Master Theorem applies: $T(N) = \Theta(N^{\log_b a}) = \Theta(N^2)$.

#### Q54. Solve the recurrence relation $T(N) = 3T(N/3) + N$ using the Master Theorem:
- A) $T(N) = \Theta(N \log N)$
- B) $T(N) = \Theta(N)$
- C) $T(N) = \Theta(\log N)$
- D) $T(N) = \Theta(N^3)$
- **Answer: ✅ A**
- **Explanation**: Here, $a=3, b=3, d=1$ since $f(N) = N^1$.
  - Compute $\log_b a = \log_3 3 = 1$.
  - Since $d == \log_b a$ ($1 == 1$), Case 2 of the Master Theorem applies: $T(N) = \Theta(N^d \log N) = \Theta(N \log N)$.

#### Q55. Solve the recurrence relation $T(N) = 2T(N/2) + N^2$:
- A) $T(N) = \Theta(N \log N)$
- B) $T(N) = \Theta(N^2)$
- C) $T(N) = \Theta(N^2 \log N)$
- D) $T(N) = \Theta(N^3)$
- **Answer: ✅ B**
- **Explanation**: Here, $a=2, b=2, d=2$ since $f(N) = N^2$.
  - Compute $\log_b a = \log_2 2 = 1$.
  - Compare $d=2$ with $\log_b a = 1$.
  - Since $d > \log_b a$ ($2 > 1$), Case 3 of the Master Theorem applies: $T(N) = \Theta(N^d) = \Theta(N^2)$.

#### Q56. Solve the recurrence relation $T(N) = 8T(N/4) + N^2$:
- A) $T(N) = \Theta(N^2)$
- B) $T(N) = \Theta(N^{1.5})$
- C) $T(N) = \Theta(N^2 \log N)$
- D) $T(N) = \Theta(N^3)$
- **Answer: ✅ A**
- **Explanation**: Here, $a=8, b=4, d=2$ since $f(N) = N^2$.
  - Compute $\log_b a = \log_4 8 = 1.5$.
  - Compare $d=2$ with $\log_b a = 1.5$.
  - Since $d > \log_b a$ ($2 > 1.5$), Case 3 applies: $T(N) = \Theta(N^d) = \Theta(N^2)$.

#### Q57. What is the time complexity of the following recurrence?
$$T(N) = T(N-1) + \log N$$
- A) $O(N \log N)$
- B) $O(N)$
- C) $O(2^N)$
- D) $O(\log N)$
- **Answer: ✅ A**
- **Explanation**: Expanding the recurrence gives:
  $$T(N) = T(N-1) + \log N = T(N-2) + \log(N-1) + \log N = \sum_{i=1}^{N} \log i$$
  By log properties:
  $$\sum \log i = \log(N!) \approx N \log N$$
  Thus, the complexity is $O(N \log N)$.

#### Q58. In the analysis of algorithms, the space complexity of a recursive function is determined by:
- A) The number of loops in the function
- B) The maximum depth of the recursive call stack during execution
- C) The size of the compiled binary file
- D) The number of input parameters
- **Answer: ✅ B**
- **Explanation**: Each active recursive call allocates a frame on the system call stack. Thus, the space complexity is proportional to the maximum depth of the recursion tree.

#### Q59. What is the time complexity of the following code snippet?
```cpp
int sum = 0;
for (int i = 1; i <= n; i = i * 2) {
    for (int j = 1; j <= i; j++) {
        sum++;
    }
}
```
- A) $O(N^2)$
- B) $O(N \log N)$
- C) $O(N)$
- D) $O(\log N)$
- **Answer: ✅ C**
- **Explanation**: The outer loop runs for values $i = 1, 2, 4, 8, \dots$ up to $N$. The inner loop runs $i$ times for each step. The total operations are:
  $$1 + 2 + 4 + 8 + \dots + 2^{\lfloor \log N \rfloor} \approx 2 \cdot N = O(N)$$
  This is a geometric series sum, resulting in $O(N)$ runtime.

#### Q60. If an algorithm has a time complexity of $T(N) = 3T(N/2) + \Theta(N)$, what is its asymptotic behavior?
- A) $\Theta(N)$
- B) $\Theta(N \log N)$
- C) $\Theta(N^{\log_2 3}) \approx \Theta(N^{1.58})$
- D) $\Theta(N^2)$
- **Answer: ✅ C**
- **Explanation**: Here, $a=3, b=2, d=1$. Since $\log_2 3 \approx 1.58 > 1$, Case 1 applies: $T(N) = \Theta(N^{\log_2 3})$.

---

## 🔷 Topic 4: Backtracking & Optimization

#### Q61. In backtracking, what is the main purpose of "Pruning" a branch in the state space tree?
- A) To sort the output array
- B) To terminate search down a branch that is guaranteed to violate constraints, saving calculation time
- C) To allocate memory dynamically
- D) To convert recursion to iteration
- **Answer: ✅ B**
- **Explanation**: Pruning cuts off subtrees as soon as the bounding function evaluates that they cannot lead to a valid solution, saving the cost of exploring fruitless paths.

#### Q62. For the N-Queens problem on an $N \times N$ board, what is the worst-case space complexity of the backtracking algorithm?
- A) $O(N^2)$
- B) $O(N)$
- C) $O(N!)$
- D) $O(2^N)$
- **Answer: ✅ B**
- **Explanation**: The backtracking call stack has a maximum depth of $N$ (placing one queen per row). We only need arrays of size $N$ to track column, diagonal, and anti-diagonal attack lines. Hence, space is $O(N)$.

#### Q63. What is the time complexity of a brute-force solver for the N-Queens problem that checks all board configurations?
- A) $O(N)$
- B) $O(N^2)$
- C) $O(N^N)$ or $O(N!)$
- D) $O(\log N)$
- **Answer: ✅ C**
- **Explanation**: A naive solver placing $N$ queens on $N^2$ squares has an exponential state space, leading to $O(N^N)$ or $O(N!)$ worst-case evaluations.

#### Q64. The Hamiltonian Cycle problem asks if there exists a closed loop in a graph that visits:
- A) Every edge exactly once
- B) Every vertex exactly once
- C) The source vertex multiple times
- D) Only leaf nodes
- **Answer: ✅ B**
- **Explanation**: A Hamiltonian cycle visits every vertex exactly once and returns to the starting vertex. (An Eulerian path visits every *edge* exactly once).

#### Q65. Backtracking is best suited to solve which type of problems?
- A) Finding shortest paths in weighted graphs
- B) Generating all permutations or combinations that satisfy specific constraints
- C) Large-scale sorting of numbers
- D) Hashing operations
- **Answer: ✅ B**
- **Explanation**: Backtracking systematically explores configuration options (permutations, combinations, subsets) under constraints, pruning invalid branches.

---

## 🔷 Topic 5: Dynamic Programming Strategies

#### Q66. In dynamic programming, the "Optimal Substructure" property means:
- A) Subproblems overlap and are recalculated repeatedly
- B) The optimal solution to the global problem contains optimal solutions to its constituent subproblems
- C) The algorithm makes the best choice at each step without looking back
- D) The recursion tree is perfectly balanced
- **Answer: ✅ B**
- **Explanation**: Optimal substructure allows building the overall optimal solution by combining optimal solutions to smaller subproblems.

#### Q67. What is the time complexity to find the Longest Common Subsequence (LCS) of two strings of lengths $M$ and $N$ using Dynamic Programming?
- A) $O(M \log N)$
- B) $O(M \cdot N)$
- C) $O(2^{\min(M,N)})$
- D) $O(M + N)$
- **Answer: ✅ B**
- **Explanation**: The DP table has size $(M+1) \times (N+1)$. Filling each cell takes $O(1)$ time. Thus, the total time is $O(M \cdot N)$.

#### Q68. What is the recurrence relation for the LCS problem when comparing characters $X[i]$ and $Y[j]$?
- A) If $X[i] == Y[j]$, $LCS(i, j) = 1 + LCS(i-1, j-1)$; else $\max(LCS(i-1, j), LCS(i, j-1))$
- B) $LCS(i, j) = LCS(i-1, j-1) + 1$ always
- C) $LCS(i, j) = \max(LCS(i-1, j), LCS(i, j-1))$ always
- D) $LCS(i, j) = LCS(i-1, j-1)$
- **Answer: ✅ A**
- **Explanation**: If characters match, we extend the subsequence by 1. If they mismatch, we find the maximum subsequence length by either ignoring character $X[i]$ or ignoring $Y[j]$.

#### Q69. Under 0/1 Knapsack, if the weight of item $i$ is greater than the remaining capacity $w$ ($w_i > w$), what is the state transition?
- A) $dp[i][w] = v_i + dp[i-1][w]$
- B) $dp[i][w] = dp[i-1][w]$
- C) $dp[i][w] = 0$
- D) $dp[i][w] = \max(dp[i-1][w], \ v_i)$
- **Answer: ✅ B**
- **Explanation**: If the item is too heavy to fit into the knapsack, we have no choice but to exclude it. Thus, the maximum value remains the same as considering only the previous $i-1$ items at the same capacity: `dp[i-1][w]`.

#### Q70. What is the time complexity of the Matrix Chain Multiplication problem solved via Dynamic Programming with $N$ matrices?
- A) $O(N)$
- B) $O(N \log N)$
- C) $O(N^2)$
- D) $O(N^3)$
- **Answer: ✅ D**
- **Explanation**: The DP state is defined by a 2D table of size $N \times N$. Computing each state requires checking $K$ split points ($i \le K < j$), adding a third loop and yielding a total time of $O(N^3)$.

#### Q71. The Edit Distance problem (Levensthein Distance) finds the minimum operations (insert, delete, replace) to convert string $X$ to $Y$. What is its DP space complexity?
- A) $O(M \cdot N)$
- B) $O(M + N)$
- C) $O(\min(M,N))$
- D) Both A and C are correct (C via space optimization)
- **Answer: ✅ D**
- **Explanation**: A standard implementation uses an $(M+1) \times (N+1)$ table ($O(M \cdot N)$ space). However, because computing a row only requires values from the current and previous rows, we can optimize space to use only two rows of size $O(\min(M,N))$.

#### Q72. Why does the naive recursive Fibonacci implementation take $O(2^N)$ time?
- A) It uses a loop
- B) It repeatedly recalculates solutions to identical subproblems (overlapping subproblems)
- C) It is a backtracking algorithm
- D) It uses too much memory
- **Answer: ✅ B**
- **Explanation**: Without caching, the recursion tree branches twice per call, solving duplicate subproblems (e.g. calculating `fib(5)` resolves `fib(3)` multiple times), resulting in exponential growth.

#### Q73. In DP, what does the term "Tabulation" refer to?
- A) A top-down recursive strategy with lookup tables
- B) A bottom-up iterative strategy that solves base cases first and fills a table
- C) A greedy sorting approach
- D) An execution trace log
- **Answer: ✅ B**
- **Explanation**: Tabulation is the bottom-up approach of filling an iteration grid, avoiding recursive function call stacks.

#### Q74. Which of the following is a classic Dynamic Programming problem?
- A) Huffman Coding
- B) Longest Common Subsequence
- C) Fractional Knapsack
- D) Kruskal's MST
- **Answer: ✅ B**
- **Explanation**: LCS is solved via DP. Huffman Coding, Fractional Knapsack, and Kruskal's MST are solved using Greedy strategies.

#### Q75. Can the 0/1 Knapsack problem be solved in polynomial time?
- A) Yes, in $O(N \cdot W)$ time
- B) No, it is NP-Complete, and $O(N \cdot W)$ is pseudo-polynomial because it depends on the capacity value $W$, not just the input size
- C) Yes, using binary search
- D) No, it cannot be solved at all
- **Answer: ✅ B**
- **Explanation**: $O(N \cdot W)$ is pseudo-polynomial. If $W$ is represented by $B$ bits, $W = 2^B$, making the time complexity exponential in terms of the input size of $W$ (number of bits). The problem is NP-Complete.

---

## 🔷 Topic 6: Greedy Algorithms

#### Q76. What is the fundamental difference between Greedy and Dynamic Programming?
- A) DP makes choices that cannot be changed; Greedy backtracks
- B) Greedy makes a locally optimal choice immediately; DP calculates and compares solutions to all subproblems
- C) DP is faster
- D) Greedy guarantees an optimal solution for all problems
- **Answer: ✅ B**
- **Explanation**: Greedy makes the best local choice at each step without looking back. DP builds solutions bottom-up, evaluating all possibilities to guarantee global optimality.

#### Q77. Huffman coding creates prefix codes, which means:
- A) All codes start with the bit 0
- B) No code is a prefix of any other code, ensuring unambiguous decoding
- C) Every code has equal length
- D) The codes are sorted alphabetically
- **Answer: ✅ B**
- **Explanation**: The prefix property means no character code is a prefix of another (e.g. if `A = 0`, no other code starts with `0`). This allows parsing a continuous stream of bits from left to right without separators.

#### Q78. In Huffman Coding, if character frequencies are `A: 10, B: 20, C: 30, D: 40`, which character will receive the shortest binary code?
- A) A
- B) B
- C) C
- D) D
- **Answer: ✅ D**
- **Explanation**: Huffman coding assigns shorter codes to characters with higher frequencies. Since `D` has the highest frequency (40), it will be closest to the root of the tree and receive the shortest code.

#### Q79. What is the time complexity of the Greedy algorithm for the Fractional Knapsack problem with $N$ items?
- A) $O(N)$
- B) $O(N \log N)$
- C) $O(N^2)$
- D) $O(2^N)$
- **Answer: ✅ B**
- **Explanation**: The algorithm must sort the items by their value-to-weight ratio first, which takes $O(N \log N)$ time. The subsequent greedy selection loop runs in $O(N)$ time, resulting in a total runtime of $O(N \log N)$.

#### Q80. Dijkstra's shortest path algorithm fails under which condition?
- A) The graph contains cycles
- B) The graph is unweighted
- C) The graph contains negative edge weights
- D) The graph is directed
- **Answer: ✅ C**
- **Explanation**: Dijkstra's algorithm assumes that once a vertex is added to the visited set, its shortest path cost is finalized. This greedy assumption fails if there are negative edge weights that could reduce path costs later.

#### Q81. What is the time complexity of Prim's MST algorithm implemented using a binary heap priority queue?
- A) $O(V^2)$
- B) $O(E \log V)$
- C) $O(V^3)$
- D) $O(V + E)$
- **Answer: ✅ B**
- **Explanation**: Prim's extracts the minimum edge from the heap $V$ times ($O(V \log V)$) and relaxes neighbor edges $E$ times ($O(E \log V)$). This yields a total runtime of $O(E \log V)$.

#### Q82. What is the time complexity of Kruskal's MST algorithm?
- A) $O(V^2)$
- B) $O(E \log E)$ or $O(E \log V)$
- C) $O(V \log V)$
- D) $O(V + E)$
- **Answer: ✅ B**
- **Explanation**: Kruskal's sorts all $E$ edges by weight ($O(E \log E)$) and uses a Union-Find structure to check for cycles ($O(E \cdot \alpha(V))$). Since $E \le V^2$, $O(E \log E)$ is equivalent to $O(E \log V)$.

#### Q83. What is the main structural difference between Kruskal's and Prim's algorithms?
- A) Kruskal's is DP; Prim's is Greedy
- B) Kruskal's grows the MST by adding the cheapest valid edges globally (can form a forest initially); Prim's grows a single connected tree vertex-by-vertex
- C) Prim's uses Union-Find
- D) Kruskal's does not work on weighted graphs
- **Answer: ✅ B**
- **Explanation**: Kruskal's is edge-based and joins disconnected components. Prim's is vertex-based and always grows a single connected tree. Both are Greedy.

#### Q84. The "Cut Property" in minimum spanning trees states that:
- A) Cutting any edge of the graph splits it in half
- B) For any cut of the graph, the minimum-weight edge crossing the cut must belong to the MST
- C) The MST must not contain cycles
- D) No vertex can have a degree greater than 2
- **Answer: ✅ B**
- **Explanation**: The cut property guarantees that the cheapest edge connecting two partitioned sets of vertices must be part of the MST.

#### Q85. Which of the following problems can be solved optimally using a Greedy algorithm?
- A) 0/1 Knapsack
- B) Longest Common Subsequence
- C) Activity Selection Problem
- D) Matrix Chain Multiplication
- **Answer: ✅ C**
- **Explanation**: The Activity Selection Problem is solved optimally by greedily selecting the activity that finishes first. The other options require Dynamic Programming.

---

## 🔷 Topic 7: String & Advanced Algorithms

#### Q86. What is the time complexity of the Knuth-Morris-Pratt (KMP) string matching algorithm for a text of length $N$ and pattern of length $M$?
- A) $O(N \cdot M)$
- B) $O(N + M)$
- C) $O(N \log M)$
- D) $O(M \log N)$
- **Answer: ✅ B**
- **Explanation**: KMP precomputes the prefix function (pi array) in $O(M)$ time and searches the text in $O(N)$ time, avoiding backtracking over the text.

#### Q87. The Rabin-Karp string matching algorithm uses which technique to search for a pattern?
- A) A prefix tree (Trie)
- B) Rolling Hash function
- C) Dynamic programming
- D) Greedy choices
- **Answer: ✅ B**
- **Explanation**: Rabin-Karp calculates hash values for the pattern and for sliding windows of the text. It uses a rolling hash to update values in $O(1)$ time.

#### Q88. What is the worst-case time complexity of the Rabin-Karp algorithm?
- A) $O(N + M)$
- B) $O(N \cdot M)$
- C) $O(N^2)$
- D) $O(M^2)$
- **Answer: ✅ B**
- **Explanation**: In the worst-case scenario (e.g., matching a pattern like `AAAA` in a text of `AAAAAA` where all hash values collide), Rabin-Karp performs character comparisons for every step, degrading to $O(N \cdot M)$ time.

#### Q89. The prefix function (LPS array) in KMP string matching stores:
- A) The hash values of substrings
- B) The length of the longest proper prefix that is also a suffix for each substring of the pattern
- C) Character frequencies
- D) Pointer jumps
- **Answer: ✅ B**
- **Explanation**: The LPS (Longest Prefix Suffix) array tells KMP how many characters of the pattern can be skipped during a mismatch.

#### Q90. What is the time complexity of building the LPS array in the KMP algorithm for a pattern of length $M$?
- A) $O(M)$
- B) $O(M^2)$
- C) $O(\log M)$
- D) $O(1)$
- **Answer: ✅ A**
- **Explanation**: The LPS array is constructed in a single pass over the pattern using two pointers, running in $O(M)$ linear time.

#### Q91. What is the lower bound for comparison-based sorting algorithms in the worst case?
- A) $\Omega(N)$
- B) $\Omega(N \log N)$
- C) $\Omega(N^2)$
- D) $\Omega(1)$
- **Answer: ✅ B**
- **Explanation**: Any comparison-based sorting algorithm can be represented as a decision tree. To sort $N$ elements, the decision tree must have at least $N!$ leaves, yielding a minimum height of:
  $$\log_2(N!) \approx N \log_2 N - N \log_2 e = \Omega(N \log N)$$

#### Q92. Why is Radix Sort able to sort an array of $N$ integers in $O(N)$ time, bypassing the $\Omega(N \log N)$ lower bound?
- A) It is a comparison-based sort
- B) It is a non-comparison sort that groups integers by their individual digits, bypassing comparison constraints
- C) It only works on sorted arrays
- D) It uses dynamic programming
- **Answer: ✅ B**
- **Explanation**: Non-comparison-based sorting algorithms (like Radix Sort, Counting Sort) do not compare elements directly. They use bucket distributions, allowing them to bypass the $\Omega(N \log N)$ comparison lower bound.

#### Q93. What does it mean if a problem is classified as "NP-Complete"?
- A) It can be solved in polynomial time
- B) It is in NP (verifiable in polynomial time) and is at least as hard as any other problem in NP (any NP problem can be reduced to it in polynomial time)
- C) It is impossible to solve
- D) It requires exponential space
- **Answer: ✅ B**
- **Explanation**: NP-Complete represents the hardest problems in NP. They are verifiable in polynomial time, but no polynomial-time solving algorithm has been found. If one NP-Complete problem is solved in polynomial time, all NP problems can be solved in polynomial time ($P = NP$).

#### Q94. What is the complexity class "P"?
- A) Problems solvable in polynomial space
- B) Decision problems solvable by a deterministic Turing machine in polynomial time
- C) Problems that are unsolvable
- D) Parallelizable problems
- **Answer: ✅ B**
- **Explanation**: Class P consists of decision problems that can be solved in $O(N^k)$ time on a standard CPU.

#### Q95. What is the complexity class "NP"?
- A) Non-Polynomial time problems
- B) Decision problems whose proposed solutions can be verified by a deterministic Turing machine in polynomial time
- C) Problems that cannot be solved by computers
- D) Numeric Processing problems
- **Answer: ✅ B**
- **Explanation**: NP stands for **Nondeterministic Polynomial time**. It is the set of decision problems for which a candidate solution can be verified as correct or incorrect in polynomial time.

---

## 🔷 Topic 8: Sorting Benchmarks & Code Mechanics

#### Q96. Which sorting algorithm has a worst-case time complexity of $O(N^2)$, but is highly preferred in practice due to its low constant factors and in-place average $O(N \log N)$ performance?
- A) Merge Sort
- B) Quick Sort
- C) Heap Sort
- D) Bubble Sort
- **Answer: ✅ B**
- **Explanation**: Quick Sort is in-place and has excellent cache performance. By choosing a random or median-of-three pivot, the worst-case $O(N^2)$ scenario is practically avoided, making it faster than Merge Sort and Heap Sort in practice.

#### Q97. Under Quick Sort, what is the role of the partition algorithm (e.g. Lomuto or Hoare)?
- A) To split the array in half exactly
- B) To place the pivot element at its correct sorted position and group smaller elements to the left, larger to the right
- C) To sort the array recursively
- D) To build a heap
- **Answer: ✅ B**
- **Explanation**: Partitioning selects a pivot, moves elements smaller than the pivot to the left, and moves larger elements to the right, returning the pivot's final index.

#### Q98. Which sorting algorithm is stable and preserves the relative order of duplicate elements?
- A) Selection Sort
- B) Quick Sort
- C) Merge Sort
- D) Heap Sort
- **Answer: ✅ C**
- **Explanation**: Merge Sort is stable because during the merge step, if two elements are equal, the element from the left sub-array is chosen first, preserving their original order.

#### Q99. What is the space complexity of Merge Sort on an array of size $N$?
- A) $O(1)$
- B) $O(\log N)$
- C) $O(N)$
- D) $O(N \log N)$
- **Answer: ✅ C**
- **Explanation**: Merge Sort requires an auxiliary array of size $N$ to merge sorted halves, resulting in a space complexity of $O(N)$.

#### Q100. How can Bubble Sort be optimized to run in $O(N)$ time in the best case?
- A) By using recursion
- B) By maintaining a flag that tracks if any swaps occurred during a pass; if no swaps occur, the array is sorted and the loop terminates
- C) By sorting from both ends
- D) By using a heap
- **Answer: ✅ B**
- **Explanation**: If a pass completes with zero swaps, the array is already sorted. Checking this flag allows the algorithm to terminate early, achieving $O(N)$ best-case runtime.

#### Q101. What is the time complexity of the closest pair of points problem using Divide and Conquer?
- A) $O(N^2)$
- B) $O(N \log N)$
- C) $O(N)$
- D) $O(N \log^2 N)$
- **Answer: ✅ B**
- **Explanation**: The divide-and-conquer algorithm divides points in half, finds the closest pair in each half recursively, and checks points in a middle strip. By sorting points by coordinates, it runs in $O(N \log N)$ time.

#### Q102. Which algorithm is used to find the strongly connected components of a directed graph in $O(V+E)$ time?
- A) Dijkstra's Algorithm
- B) Tarjan's or Kosaraju's Algorithm
- C) Floyd-Warshall
- D) Prim's
- **Answer: ✅ B**
- **Explanation**: Kosaraju's uses two passes of DFS (the second on the transpose graph) to find SCCs in $O(V+E)$ time. Tarjan's finds SCCs in a single pass of DFS using low-link values.

#### Q103. If we want to sort an array of $N$ strings, each of length $L$, what is the time complexity of Radix Sort?
- A) $O(N \log N)$
- B) $O(L \cdot N)$
- C) $O(L + N)$
- D) $O(N^2)$
- **Answer: ✅ B**
- **Explanation**: Radix sort processes each of the $L$ digits/characters using Counting Sort ($O(N)$) as a stable sort. Thus, it runs in $O(L \cdot N)$ time.

#### Q104. In the Boyer-Moore string matching algorithm, the "Bad Character Rule" allows:
- A) Skipping characters by shifting the pattern based on the last occurrence of the mismatched character in the pattern
- B) Hashing text windows
- C) Building a prefix tree
- D) Skipping entire lines
- **Answer: ✅ A**
- **Explanation**: The bad character rule shifts the pattern to align the mismatched character in the text with its rightmost occurrence in the pattern, enabling large shifts.


#### Q105. What is the time complexity of the Floyd-Warshall all-pairs shortest path algorithm?
- A) $O(V \cdot E \log V)$
- B) $O(V^3)$
- C) $O(V^2)$
- D) $O(V \cdot E)$
- **Answer: ✅ B**
- **Explanation**: Floyd-Warshall uses three nested loops over the vertices $V$ to compute shortest paths between all pairs of vertices in $O(V^3)$ time.

---

## 🔷 Topic 9: Advanced Exam-Style Challenges

#### Q106. In the formal definition of Big-O notation, to prove that $3N^2 + 5N = O(N^2)$, which pair of positive constants $c$ and $n_0$ satisfies the condition $3N^2 + 5N \le c \cdot N^2$ for all $N \ge n_0$?
- A) $c = 3, n_0 = 1$
- B) $c = 5, n_0 = 3$
- C) $c = 8, n_0 = 1$
- D) $c = 2, n_0 = 5$
- **Answer: ✅ C**
- **Explanation**: According to the definition of $O(g(N))$, we must find positive constants $c$ and $n_0$ such that $f(N) \le c \cdot g(N)$ for all $N \ge n_0$.
  Here, $f(N) = 3N^2 + 5N$ and $g(N) = N^2$.
  If we choose $c = 8$:
  $$3N^2 + 5N \le 8N^2 \implies 5N \le 5N^2 \implies 1 \le N$$
  This holds true for all $N \ge 1$. Hence, the pair $(c = 8, n_0 = 1)$ is mathematically valid. Option A is invalid because $3N^2 + 5N \le 3N^2 \implies 5N \le 0$, which is false for positive $N$.

#### Q107. Let $f(N)$ and $g(N)$ be asymptotically positive functions. Which of the following statements is mathematically FALSE?
- A) $f(N) = O(g(N)) \implies g(N) = \Omega(f(N))$
- B) $f(N) = \Theta(g(N)) \implies f(N) = O(g(N))$ and $f(N) = \Omega(g(N))$
- C) $f(N) = O(g(N)) \implies 2^{f(N)} = O(2^{g(N)})$
- D) $f(N) = o(g(N)) \implies \lim_{N \to \infty} \frac{f(N)}{g(N)} = 0$
- **Answer: ✅ C**
- **Explanation**: Asymptotic notation does not automatically preserve exponentiation. Consider $f(N) = 2N$ and $g(N) = N$. Clearly, $2N = O(N)$ (with $c=2$). However:
  $$2^{f(N)} = 2^{2N} = 4^N \quad \text{and} \quad 2^{g(N)} = 2^N$$
  Since $\lim_{N \to \infty} \frac{4^N}{2^N} = \lim_{N \to \infty} 2^N = \infty$, it is false that $4^N = O(2^N)$. Thus, $2^{f(N)} = O(2^{g(N)})$ does not follow.

#### Q108. What is the time complexity of the following code snippet?
```cpp
int count = 0;
for (int i = 2; i <= n; i = i * i) {
    for (int j = 1; j <= n; j = j * 2) {
        count++;
    }
}
```
- A) $O(N \log N)$
- B) $O(\log N \log \log N)$
- C) $O(\log^2 N)$
- D) $O(\log \log N \log N)$
- **Answer: ✅ D**
- **Explanation**: Let's analyze the loops independently:
  1. The outer loop variable $i$ starts at $2$ and square-steps: $i = 2, 4, 16, 256, \dots, 2^{2^k}$. The loop terminates when $2^{2^k} > N \implies 2^k > \log_2 N \implies k > \log_2(\log_2 N)$. Thus, the outer loop runs $O(\log \log N)$ times.
  2. The inner loop variable $j$ doubles at each step from $1$ to $N$, which runs exactly $O(\log N)$ times.
  Since the inner loop runs $O(\log N)$ times for every iteration of the outer loop, the total time complexity is $O(\log \log N \cdot \log N)$.

#### Q109. What is the time complexity of the following loop structure?
```cpp
int value = 0;
for (int i = 1; i <= n; i++) {
    for (int j = 1; j * j <= i; j++) {
        value++;
    }
}
```
- A) $O(N \log N)$
- B) $O(N \sqrt{N})$
- C) $O(N)$
- D) $O(N^2)$
- **Answer: ✅ B**
- **Explanation**: The outer loop runs $N$ times. For a given value of $i$, the inner loop variable $j$ runs as long as $j^2 \le i \implies j \le \sqrt{i}$.
  The total number of operations is:
  $$\sum_{i=1}^{N} \sqrt{i} \approx \int_{1}^{N} x^{1/2} dx = \left[ \frac{2}{3} x^{3/2} \right]_1^N = \Theta(N^{3/2}) = O(N\sqrt{N})$$
  Hence, the complexity is $O(N\sqrt{N})$.

#### Q110. Which of the following is the correct solution for the recurrence relation $T(N) = T(\sqrt{N}) + \Theta(1)$?
- A) $T(N) = \Theta(\log N)$
- B) $T(N) = \Theta(\log \log N)$
- C) $T(N) = \Theta(\sqrt{N})$
- D) $T(N) = \Theta(1)$
- **Answer: ✅ B**
- **Explanation**: To solve $T(N) = T(N^{1/2}) + c$, we use a change of variables. Let $N = 2^k \implies k = \log_2 N$.
  Let $S(k) = T(2^k)$.
  Then:
  $$S(k) = T(2^{k/2}) + c = S(k/2) + c$$
  This is the standard recurrence for Binary Search on $k$, which yields:
  $$S(k) = \Theta(\log k)$$
  Substituting back $k = \log_2 N$, we get:
  $$T(N) = \Theta(\log \log N)$$

#### Q111. Solve the recurrence relation $T(N) = 4T(N/2) + N^2 \log N$:
- A) $T(N) = \Theta(N^2 \log N)$
- B) $T(N) = \Theta(N^2 \log^2 N)$
- C) $T(N) = \Theta(N^2)$
- D) $T(N) = \Theta(N^3)$
- **Answer: ✅ B**
- **Explanation**: Using the Master Theorem Case 2 Extension:
  Here, $a = 4, b = 2 \implies N^{\log_b a} = N^{\log_2 4} = N^2$.
  The driving function is $f(N) = N^2 \log^1 N$, which is in the form $\Theta(N^{\log_b a} \log^k N)$ for $k = 1$.
  According to Case 2 extension, if $f(N) = \Theta(N^{\log_b a} \log^k N)$ with $k \ge 0$, then the solution is:
  $$T(N) = \Theta(N^{\log_b a} \log^{k+1} N) = \Theta(N^2 \log^2 N)$$

#### Q112. Consider the recurrence relation $T(N) = T(N/3) + T(2N/3) + N$. What is the asymptotic behavior of $T(N)$?
- A) $T(N) = \Theta(N)$
- B) $T(N) = \Theta(N^2)$
- C) $T(N) = \Theta(N \log N)$
- D) $T(N) = \Theta(2^N)$
- **Answer: ✅ C**
- **Explanation**: The Master Theorem cannot be applied because the subproblems are unbalanced. We can use the recursion tree method:
  - At level 0 (root): Work is $N$.
  - At level 1: Work is $\frac{N}{3} + \frac{2N}{3} = N$.
  - At level 2: Work is $\frac{N}{9} + \frac{2N}{9} + \frac{2N}{9} + \frac{4N}{9} = N$.
  At each level $i$ of the tree, the sum of work is exactly $N$.
  - The shortest path to a leaf goes through the left branch: $N \to N/3 \to N/9 \to \dots$, having a depth of $\log_3 N$.
  - The longest path goes through the right branch: $N \to 2N/3 \to 4N/9 \to \dots$, having a depth of $\log_{3/2} N$.
  Since every level does $N$ work and the tree depth is bounded between $\log_3 N$ and $\log_{3/2} N$, the total work is bounded by:
  $$N \log_3 N \le T(N) \le N \log_{3/2} N \implies T(N) = \Theta(N \log N)$$

#### Q113. In the space-optimized Dynamic Programming solution for the 0/1 Knapsack problem using a 1D array `dp[w]`, why must the inner loop for capacity `w` run backward from capacity `W` down to item weight `w_i`?
- A) To optimize cache locality
- B) Running forward would result in using the same item multiple times (solving Fractional Knapsack instead)
- C) Running forward would result in using the same item multiple times (solving Unbounded Knapsack instead)
- D) It avoids accessing negative indices
- **Answer: ✅ C**
- **Explanation**: In the 1D DP update:
  `dp[w] = max(dp[w], dp[w - w_i] + v_i)`
  We need `dp[w - w_i]` to represent the optimal value *before* considering the current item $i$ (i.e. from the previous row $i-1$).
  If the loop ran forward, `dp[w - w_i]` would already have been updated in the current pass and would contain the current item $i$. This would allow the item to be selected multiple times, which solves the **Unbounded Knapsack** problem instead of the **0/1 Knapsack** problem (where each item is limited to at most one selection). By running the loop backward, we guarantee that `dp[w - w_i]` is accessed before it is updated, ensuring it represents the $i-1$ state.

#### Q114. Trace the Dynamic Programming grid to find the length of the Longest Common Subsequence (LCS) between strings $X = \text{"ALGORITHM"}$ and $Y = \text{"LOGARITHM"}$. What is the length?
- A) 6
- B) 7
- C) 8
- D) 9
- **Answer: ✅ B**
- **Explanation**: Let's find the matching characters in sequence:
  We can align $X$ and $Y$ to extract the subsequence `L-G-R-I-T-H-M` (length 7):
  - $X$: A **L** **G** O **R** I **T** **H** **M**
  - $Y$: **L** O **G** A **R** I **T** **H** **M**
  Let's list the positions of `L G R I T H M` in both:
  - In $X$: `L` (idx 1), `G` (idx 2), `R` (idx 4), `I` (idx 5), `T` (idx 6), `H` (idx 7), `M` (idx 8)
  - In $Y$: `L` (idx 0), `G` (idx 2), `R` (idx 4), `I` (idx 5), `T` (idx 6), `H` (idx 7), `M` (idx 8)
  Wait, let's verify indices. In $X$, the characters are `A`(0), `L`(1), `G`(2), `O`(3), `R`(4), `I`(5), `T`(6), `H`(7), `M`(8).
  In $Y$, they are `L`(0), `O`(1), `G`(2), `A`(3), `R`(4), `I`(5), `T`(6), `H`(7), `M`(8).
  The indices of matched characters in $X$ are 1, 2, 4, 5, 6, 7, 8 (strictly increasing).
  The indices of matched characters in $Y$ are 0, 2, 4, 5, 6, 7, 8 (strictly increasing).
  So `L G R I T H M` is indeed a valid common subsequence of length 7.
  Is there any common subsequence of length 8? Let's check:
  Characters of $X$ matching $Y$:
  `L` (1), `O` (3), `G` (2) - indices in $X$ are not increasing, so we cannot match both `O` and `G` in this order.
  `A` (0), `L` (1), `G` (2) - `A` in $Y$ is at idx 3. So if we match `A`, we cannot match `L`(0) or `G`(2) before it.
  Therefore, the longest common subsequence length is exactly 7.

#### Q115. In the Matrix Chain Multiplication problem, we are given three matrices with dimensions: $A_1$ is $10 \times 20$, $A_2$ is $20 \times 5$, and $A_3$ is $5 \times 30$. What is the minimum number of scalar multiplications required to compute $A_1 \times A_2 \times A_3$?
- A) 4,000
- B) 2,500
- C) 1,750
- D) 6,000
- **Answer: ✅ B**
- **Explanation**: We have two parenthesization options:
  1. $(A_1 \times A_2) \times A_3$:
     - Multiplications for $A_1 \times A_2$: $10 \times 20 \times 5 = 1,000$. The resulting matrix $A_{12}$ has dimensions $10 \times 5$.
     - Multiplications for $A_{12} \times A_3$: $10 \times 5 \times 30 = 1,500$.
     - Total: $1,000 + 1,500 = 2,500$ scalar multiplications.
  2. $A_1 \times (A_2 \times A_3)$:
     - Multiplications for $A_2 \times A_3$: $20 \times 5 \times 30 = 3,000$. The resulting matrix $A_{23}$ has dimensions $20 \times 30$.
     - Multiplications for $A_1 \times A_{23}$: $10 \times 20 \times 30 = 6,000$.
     - Total: $3,000 + 6,000 = 9,000$ scalar multiplications.
  Comparing the two, the minimum multiplications required is $2,500$.

#### Q116. A message contains characters with the following frequencies: `A: 0.40, B: 0.25, C: 0.15, D: 0.12, E: 0.08`. If we construct a Huffman code for this message, what is the expected (average) number of bits per character?
- A) 2.00
- B) 2.15
- C) 2.20
- D) 2.35
- **Answer: ✅ B**
- **Explanation**: Let's build the Huffman tree step-by-step:
  1. Combine the two lowest frequencies: `E (0.08)` and `D (0.12)` $\implies$ Node `DE (0.20)`.
  2. The active set is now: `C (0.15), DE (0.20), B (0.25), A (0.40)`.
  3. Combine the two lowest: `C (0.15)` and `DE (0.20)` $\implies$ Node `CDE (0.35)`.
  4. The active set is now: `B (0.25), CDE (0.35), A (0.40)`.
  5. Combine the two lowest: `B (0.25)` and `CDE (0.35)` $\implies$ Node `BCDE (0.60)`.
  6. The active set is now: `A (0.40), BCDE (0.60)`.
  7. Combine the two: `A` and `BCDE` $\implies$ Root node `1.00`.
  Now, let's trace the path lengths (number of bits) from the root:
  - `A`: 1 bit (path length 1)
  - `B`: 2 bits (path length 2, path: root $\to$ BCDE $\to$ B)
  - `C`: 3 bits (path length 3, path: root $\to$ BCDE $\to$ CDE $\to$ C)
  - `D`: 4 bits (path length 4, path: root $\to$ BCDE $\to$ CDE $\to$ DE $\to$ D)
  - `E`: 4 bits (path length 4, path: root $\to$ BCDE $\to$ CDE $\to$ DE $\to$ E)
  Let's calculate the expected length:
  $$L_{\text{avg}} = (0.40 \times 1) + (0.25 \times 2) + (0.15 \times 3) + (0.12 \times 4) + (0.08 \times 4)$$
  $$L_{\text{avg}} = 0.40 + 0.50 + 0.45 + 0.48 + 0.32 = 2.15 \text{ bits/character}$$

#### Q117. What is the maximum possible height of a Huffman tree containing $N$ unique characters, and what conditions produce this height?
- A) Height $O(\log N)$, produced when all character frequencies are equal
- B) Height $O(N)$, produced when the character frequencies follow the Fibonacci sequence ($f_i = f_{i-1} + f_{i-2}$)
- C) Height $O(\sqrt{N})$, produced when frequencies are prime numbers
- D) Height $O(N)$, produced when all frequencies are equal
- **Answer: ✅ B**
- **Explanation**: A Huffman tree is highly unbalanced (linear or "skewed" like a vine, representing a maximum height of $N-1$) when the frequency of each character is greater than or equal to the sum of the frequencies of the two preceding characters. The Fibonacci sequence satisfies this condition ($F_n = F_{n-1} + F_{n-2}$). In this case, at each step of building the tree, the algorithm merges the newly formed parent node with the next single character, producing a tree of height $N-1$ (i.e., $O(N)$). Equal frequencies, on the other hand, produce a nearly balanced binary tree of height $O(\log N)$.

#### Q118. Consider a directed graph with vertices $S$, $A$, and $B$. The edges are: $S \to A$ with weight 3, $S \to B$ with weight 4, and $B \to A$ with weight -2. If we run Dijkstra's algorithm starting from source $S$, what path distance does it find to vertex $A$, and why is this incorrect?
- A) Distance 2; Dijkstra finds the correct path
- B) Distance 3; Dijkstra incorrectly misses the path $S \to B \to A$ (actual distance 2) because it greedily processes and freezes vertex $A$ when it is extracted from the queue with distance 3
- C) Distance 4; Dijkstra fails to process negative weights entirely
- D) Distance 1; Dijkstra calculates incorrect values due to division by zero
- **Answer: ✅ B**
- **Explanation**: Let's trace Dijkstra's algorithm step-by-step:
  1. Initialize distances: $dist[S] = 0$, $dist[A] = \infty$, $dist[B] = \infty$.
  2. Extract the minimum distance vertex: $S$ is extracted.
  3. Relax neighbors of $S$:
     - $S \to A$: $dist[A]$ becomes $\min(\infty, 0 + 3) = 3$.
     - $S \to B$: $dist[B]$ becomes $\min(\infty, 0 + 4) = 4$.
  4. Extract the next minimum distance vertex: $A$ (distance 3) is extracted and marked as visited. Its distance is now frozen at 3.
  5. Extract the next minimum distance vertex: $B$ (distance 4) is extracted.
  6. Relax neighbors of $B$:
     - $B \to A$: $dist[A]$ would become $\min(3, 4 + (-2)) = 2$. However, since $A$ has already been processed (visited), standard Dijkstra does not update its distance.
  Thus, Dijkstra returns $dist[A] = 3$, missing the shorter path $S \to B \to A$ which has a cost of $2$. This illustrates why Dijkstra fails in the presence of negative edge weights.

#### Q119. In the backtracking solution for the N-Queens problem on an $N \times N$ chessboard, how do we track if a square $(r, c)$ is threatened by a queen already placed at row $r'$ and column $c'$ on the diagonals?
- A) A square is threatened if $r + c == r' + c'$ (major diagonal) or $r - c == r' - c'$ (minor diagonal)
- B) A square is threatened if $r \cdot c == r' \cdot c'$
- C) A square is threatened if $r + c'$ is prime
- D) A square is threatened if $r' - r == c' - c$ (anti-diagonal) or $r' - r == c - c'$ (main diagonal)
- **Answer: ✅ D**
- **Explanation**: A queen at $(r', c')$ threatens any square $(r, c)$ on the same main diagonal (which runs top-left to bottom-right) and same anti-diagonal (top-right to bottom-left).
  - For the **main diagonal**, the difference between row and column is constant: $r' - c' = r - c \implies r' - r = c' - c$.
  - For the **anti-diagonal**, the sum of row and column is constant: $r' + c' = r + c \implies r' - r = c - c'$.
  Using Boolean arrays indexed by $r - c + (N - 1)$ and $r + c$, we can check diagonal conflicts in $O(1)$ time.

#### Q120. In the Graph Coloring problem, we use backtracking to find if a graph can be colored using $M$ colors. Which of the following represents a valid bounding/pruning condition that allows terminating a recursive branch early?
- A) If the number of colors used so far is less than $M$
- B) If the degree of the current vertex is less than the number of available colors
- C) If the partial coloring of a vertex conflicts with the color of an adjacent, already colored vertex
- D) If the graph contains a clique of size greater than $M$
- **Answer: ✅ C**
- **Explanation**: The core constraint of the Graph Coloring problem is that no two adjacent vertices share the same color. Therefore, if assigning color $C$ to vertex $V$ matches the color of any adjacent vertex that has already been colored, the constraint is violated. The backtracking algorithm prunes this branch immediately by backtracking, rather than proceeding to color the remaining vertices. Option D is a global property that can be used as a preprocessing check, but Option C is the active bounding/pruning condition used during the backtracking search.

#### Q121. In a backtracking search to find all Hamiltonian Cycles in a complete graph $K_V$ with $V$ vertices, what is the maximum number of leaf nodes in the search tree before pruning?
- A) $V^2$
- B) $2^V$
- C) $(V - 1)!$
- D) $V!$
- **Answer: ✅ C**
- **Explanation**: A complete graph has a directed edge between every pair of vertices. To find all Hamiltonian cycles:
  1. Fix the starting vertex (say, $v_0$).
  2. For the next step, there are $V - 1$ choices of vertices to visit.
  3. For the subsequent step, there are $V - 2$ choices.
  4. Continuing this process, we get a permutation tree of height $V$.
  The number of branches at the leaf level is $(V-1) \times (V-2) \times \dots \times 1 = (V-1)!$. This is the size of the unpruned search space.

#### Q122. The mathematical proof that any comparison-based sorting algorithm requires at least $\Omega(N \log N)$ comparisons in the worst case relies on which mathematical approximation?
- A) Euler's Formula
- B) Taylor Series expansion of $\log(1 + x)$
- C) Stirling's Approximation for $N!$
- D) L'Hopital's Rule
- **Answer: ✅ C**
- **Explanation**: A comparison-based sorting algorithm has a binary decision tree where each node represents a comparison.
  - To sort $N$ items, the tree must have at least $N!$ leaf nodes (one for each possible permutation of the input).
  - A binary tree of height $H$ has at most $2^H$ leaves.
  - Thus, $2^H \ge N! \implies H \ge \log_2(N!)$.
  Using **Stirling's Approximation** for large $N$:
  $$\ln(N!) \approx N \ln N - N$$
  Substituting this into the inequality:
  $$H \ge \log_2(N!) \approx N \log_2 N - N \log_2 e = \Omega(N \log N)$$
  This establishes the lower bound of $\Omega(N \log N)$.

#### Q123. Counting Sort is a stable, non-comparison sorting algorithm that runs in $O(N + K)$ time, where $K$ is the range of input values. How does it maintain stability during the final scatter phase?
- A) By comparing elements directly from left to right
- B) By iterating through the input array from right to left (backward) and placing elements in the output array using prefix-sum offsets, then decrementing the count
- C) By using a temporary linked list for each bucket
- D) By sorting the count array itself using insertion sort
- **Answer: ✅ B**
- **Explanation**: Counting Sort computes a histogram of element counts, then calculates prefix sums to determine the ending position of each element group.
  To preserve stability (maintaining the relative order of duplicate elements):
  - We scan the input array from **right to left (backward)**.
  - For each element `arr[i]`, we lookup its position using the prefix sum of `arr[i]`, place it in the output array, and **decrement** the prefix sum.
  - Because we scan backward, the last occurrence of a duplicate element in the input is placed at the highest available index in its range, and subsequent occurrences are placed at lower indices. This preserves their original relative order. Scanning forward without decrementing from the end would reverse the order, making it unstable.

#### Q124. Radix Sort sorts $N$ numbers with values in the range $[0, M-1]$ by processing them digit-by-digit using Counting Sort as a stable sub-routine. If we represent the numbers in base $d$, what is the total time complexity?
- A) $O(N \log N)$
- B) $O\left( \log_d M \cdot (N + d) \right)$
- C) $O(N \cdot M)$
- D) $O(N + d)$
- **Answer: ✅ B**
- **Explanation**: Let's analyze the steps:
  1. The number of digits of a number up to $M-1$ in base $d$ is $\lceil \log_d M \rceil$.
  2. For each digit, we run Counting Sort. Since the base is $d$, the range of digit values is $[0, d-1]$. The time complexity of Counting Sort for $N$ elements in range $d$ is $O(N + d)$.
  3. Multiplying the number of digits by the cost per digit gives the total runtime:
     $$O\left( \log_d M \cdot (N + d) \right)$$
  If $d = \Theta(N)$ and $M = N^c$, this becomes $O(c \cdot (N + N)) = O(N)$ linear time.

#### Q125. In the Knuth-Morris-Pratt (KMP) string matching algorithm, construct the prefix function (LPS/$\pi$ array) for the pattern $P = \text{"ABACABA"}$. What is the resulting array?
- A) $[0, 0, 1, 0, 1, 2, 3]$
- B) $[0, 0, 1, 0, 1, 2, 1]$
- C) $[0, 0, 1, 2, 3, 4, 5]$
- D) $[0, 1, 0, 1, 2, 3, 2]$
- **Answer: ✅ A**
- **Explanation**: The LPS array stores the length of the longest proper prefix of $P[0..i]$ that is also a suffix of $P[0..i]$. Let's compute it index-by-index:
  - $i=0$: `A` $\to$ proper prefix/suffix has length 0. `LPS[0] = 0`.
  - $i=1$: `AB` $\to$ prefixes: `A`; suffixes: `B`. No match. `LPS[1] = 0`.
  - $i=2$: `ABA` $\to$ prefix `A` matches suffix `A` (length 1). `LPS[2] = 1`.
  - $i=3$: `ABAC` $\to$ no matching prefix/suffix. `LPS[3] = 0`.
  - $i=4$: `ABACA` $\to$ prefix `A` matches suffix `A` (length 1). `LPS[4] = 1`.
  - $i=5$: `ABACAB` $\to$ prefix `AB` matches suffix `AB` (length 2). `LPS[5] = 2`.
  - $i=6$: `ABACABA` $\to$ prefix `ABA` matches suffix `ABA` (length 3). `LPS[6] = 3`.
  Thus, the LPS array is `[0, 0, 1, 0, 1, 2, 3]`.

#### Q126. Rabin-Karp calculates rolling hashes to find a pattern in a text. If we use a simple polynomial rolling hash:
$$H(S[i..i+M-1]) = \left( \sum_{j=0}^{M-1} S[i+j] \cdot p^{M-1-j} \right) \pmod q$$
What is the mathematical recurrence formula to calculate the hash of the next window $H(S[i+1..i+M])$ in $O(1)$ time?
- A) $H_{\text{next}} = \left( (H_{\text{prev}} - S[i] \cdot p^{M-1}) \cdot p + S[i+M] \right) \pmod q$
- B) $H_{\text{next}} = \left( H_{\text{prev}} \cdot p + S[i+M] - S[i] \right) \pmod q$
- C) $H_{\text{next}} = \left( H_{\text{prev}} - S[i] + S[i+M] \cdot p^{M-1} \right) \pmod q$
- D) $H_{\text{next}} = \left( (H_{\text{prev}} + S[i+M] \cdot p^M) / p \right) \pmod q$
- **Answer: ✅ A**
- **Explanation**: To slide the hash window by one character to the right:
  1. Remove the high-order term corresponding to the leftmost character $S[i]$: subtract $S[i] \cdot p^{M-1}$.
  2. Shift the remaining characters one position to the left (increase their powers of $p$ by multiplying by the base $p$).
  3. Add the low-order term for the new incoming character $S[i+M]$ at the rightmost position (power $p^0 = 1$).
  4. Perform modulo $q$ to prevent integer overflow.
  This gives:
  $$H_{\text{next}} = \left( (H_{\text{prev}} - S[i] \cdot p^{M-1}) \cdot p + S[i+M] \right) \pmod q$$

#### Q127. In the Boyer-Moore string matching algorithm, let the pattern $P = \text{"NEEDLE"}$ and we are matching from right to left. Suppose we align $P$ against a text window and find a mismatch at index 4 of the pattern (character 'L') where the corresponding text character is 'A'. Using the Bad Character Rule, how many positions should we shift the pattern to the right? (Note: 'A' does not appear in $P$).
- A) 1
- B) 3
- C) 5
- D) 6
- **Answer: ✅ C**
- **Explanation**: The Bad Character Rule states that when a mismatch occurs at pattern index $i$ with text character $T[k]$:
  - If the mismatched text character $T[k]$ does not exist in the pattern, we can shift the pattern completely past the mismatch.
  - The shift distance is computed as:
    $$\text{shift} = i - \text{last\_occurrence}(T[k], P)$$
    Since 'A' does not appear anywhere in $P = \text{"NEEDLE"}$, its last occurrence index is $-1$.
    The mismatch occurred at pattern index $i = 4$.
    Therefore, the shift distance is:
    $$\text{shift} = 4 - (-1) = 5 \text{ positions}$$
    (Specifically, this shifts the start of the pattern past the mismatched character 'A').

#### Q128. What is the worst-case number of character comparisons performed by the KMP algorithm when searching for a pattern of length $M$ in a text of length $N$ (excluding the preprocessing phase)?
- A) $2N$
- B) $N \cdot M$
- C) $N + M$
- D) $N^2$
- **Answer: ✅ A**
- **Explanation**: In KMP, although the pattern pointer can backtrack when a mismatch occurs, the text pointer *never* backtracks—it only increments forward.
  - For each character in the text, we either match (advancing the text pointer) or mismatch (which backtracks the pattern pointer using the LPS array).
  - Since we can backtrack at most as many times as we advance, and we advance the text pointer at most $N$ times, the total number of comparisons is bounded by $2N$ in the absolute worst case. This guarantees linear $O(N)$ comparisons, unlike the naive search which can take $O(N \cdot M)$ comparisons.

#### Q129. When analyzing a dynamic array (like `std::vector` in C++ or `ArrayList` in Java), insertions take $O(1)$ time on average, but $O(N)$ when the array is full and must resize (doubling its capacity). Using the Potential Method of Amortized Analysis, what potential function $\Phi(D_i)$ proves that the amortized cost of an insertion is $O(1)$? (Let $size_i$ be the number of elements and $cap_i$ be the capacity at step $i$).
- A) $\Phi(D_i) = cap_i - size_i$
- B) $\Phi(D_i) = 2 \cdot size_i - cap_i$
- C) $\Phi(D_i) = size_i^2$
- D) $\Phi(D_i) = cap_i / 2$
- **Answer: ✅ B**
- **Explanation**: Let's check the potential function $\Phi(D_i) = 2 \cdot size_i - cap_i$:
  - Immediately after a resize, the capacity is doubled, so $cap = 2 \cdot size \implies \Phi = 2 \cdot size - 2 \cdot size = 0$.
  - When the array is completely full (just before resizing), $size = cap \implies \Phi = 2 \cdot size - size = size$.
  Let's calculate the amortized cost $a_i = c_i + \Phi(D_i) - \Phi(D_{i-1})$:
  1. **Case 1: Insertion without resizing** (actual cost $c_i = 1$):
     - $size_i = size_{i-1} + 1$, and $cap_i = cap_{i-1}$.
     - $\Delta \Phi = (2 \cdot size_i - cap_i) - (2 \cdot size_{i-1} - cap_{i-1}) = 2(size_i - size_{i-1}) = 2$.
     - Amortized cost: $a_i = c_i + \Delta \Phi = 1 + 2 = 3$.
  2. **Case 2: Insertion triggers resize** (actual cost $c_i = size_{i-1} + 1$, where copying takes $size_{i-1}$ steps):
     - $size_i = size_{i-1} + 1$.
     - $cap_i = 2 \cdot cap_{i-1} = 2 \cdot size_{i-1}$.
     - $\Phi(D_{i-1}) = 2 \cdot size_{i-1} - cap_{i-1} = size_{i-1}$ (since capacity was full).
     - $\Phi(D_i) = 2 \cdot size_i - cap_i = 2(size_{i-1} + 1) - 2 \cdot size_{i-1} = 2$.
     - $\Delta \Phi = \Phi(D_i) - \Phi(D_{i-1}) = 2 - size_{i-1}$.
     - Amortized cost: $a_i = c_i + \Delta \Phi = (size_{i-1} + 1) + (2 - size_{i-1}) = 3$.
  In both cases, the amortized cost is a constant ($3$), which proves that insertion runs in amortized $O(1)$ time.

#### Q130. Suppose there is a decision problem $X$. To prove that $X$ is NP-Complete, which two steps are mathematically required?
- A) Show that $X$ is in P, and reduce $X$ to a known NP-Complete problem in polynomial time
- B) Show that $X$ is in NP, and reduce $X$ to a known NP-Hard problem in polynomial time
- C) Show that $X$ is in NP, and reduce a known NP-Complete problem to $X$ in polynomial time
- D) Show that $X$ is in NP-Hard, and show that $X$ is in P
- **Answer: ✅ C**
- **Explanation**: By definition, a problem $X$ is NP-Complete if:
  1. It is in the class NP ($X \in \text{NP}$), meaning a candidate solution can be verified in polynomial time.
  2. It is NP-Hard, meaning it is at least as hard as any problem in NP. To prove this, we select a known NP-Complete problem $Y$ and show that $Y \le_P X$ (reduce $Y$ to $X$ in polynomial time). This proves that if we could solve $X$ in polynomial time, we could solve $Y$ (and by extension, any NP problem) in polynomial time.
  Option A is incorrect because reducing $X \le_P Y$ only proves $X$ is no harder than $Y$, not that $X$ is NP-Hard.

#### Q131. The time complexity of the standard binary search algorithm operates as:
- A) $O(n)$
- B) $O(\log n)$
- C) $O(n \log n)$
- D) $O(1)$
- **Answer: ✅ B**
- **Explanation**: Binary search repeatedly halves the search space in each step, yielding a logarithmic time complexity of $O(\log n)$.

#### Q132. If each and every vertex in graph $G$ has a degree at most 23, then $G$ can have a vertex coloring of:
- A) 23
- B) 24
- C) 46
- D) 12
- **Answer: ✅ B**
- **Explanation**: According to the vertex coloring bound theorem, any graph $G$ with maximum degree $\Delta$ can be colored with at most $\Delta + 1$ colors. Thus, $\text{Color Count} \le 23 + 1 = 24$.

#### Q133. If $G$ represents a forest mapping with 54 vertices and 17 connected components, trace the total number of edges:
- A) 71
- B) 37
- C) 54
- D) 17
- **Answer: ✅ B**
- **Explanation**: For a forest, the relation between the number of vertices ($V$), connected components ($C$), and edges ($E$) is given by the formula: $\text{Edges} = V - C = 54 - 17 = 37$.

#### Q134. The number of edges in a regular graph with degree 46 and 8 distinct vertices equals:
- A) 368
- B) 184
- C) 92
- D) 46
- **Answer: ✅ B**
- **Explanation**: Under the Handshaking Lemma, the sum of degrees of all vertices equals twice the number of edges: $\sum \text{deg}(v) = 2E \implies N \times R = 2E \implies \text{Edges} = \frac{8 \times 46}{2} = 184$.

#### Q135. An algorithm which utilizes the past tracking results and directly leverages them to discover a new result is called:
- A) Greedy Algorithm
- B) Divide and Conquer Algorithm
- C) Dynamic Programming Algorithm
- D) Backtracking Algorithm
- **Answer: ✅ C**
- **Explanation**: Dynamic programming resolves problems by solving subproblems once and caching their results (memoization/tabulation) to build the global optimal solution.

#### Q136. To sort a list with $n$ elements, the insertion sort begins execution at the _______ element slot context.
- A) First
- B) Second
- C) Middle
- D) Last
- **Answer: ✅ B**
- **Explanation**: Insertion sort considers the first element (index 0) to be a sorted sublist of size 1 and begins inserting the second element (index 1) into its sorted position.

#### Q137. Trace the precise list obtained in the third execution pass of Selection Sort for arrays matching: [3, 5, 4, 1, 2]
- A) [1, 2, 4, 3, 5]
- B) [1, 2, 3, 4, 5]
- C) [1, 5, 4, 3, 2]
- D) [3, 4, 5, 1, 2]
- **Answer: ✅ B**
- **Explanation**: Selection sort repeatedly finds the minimum element from the unsorted portion and swaps it into its correct position:
  - Pass 1: Find min (1), swap with 3 $\to$ [1, 5, 4, 3, 2]
  - Pass 2: Find min in unsorted [5, 4, 3, 2] (which is 2), swap with 5 $\to$ [1, 2, 4, 3, 5]
  - Pass 3: Find min in unsorted [4, 3, 5] (which is 3), swap with 4 $\to$ [1, 2, 3, 4, 5]

#### Q138. The average/worst-case time complexity of the bubble sort algorithm operates as:
- A) $O(n \log n)$
- B) $O(n^2)$
- C) $O(n)$
- D) $O(2^n)$
- **Answer: ✅ B**
- **Explanation**: Bubble sort compares and swaps adjacent out-of-order elements in nested loops, running in $O(n^2)$ time in both average and worst cases.

#### Q139. Time complexity of the Breadth-First Search (BFS) algorithm scales as:
- A) $O(V^2)$
- B) $O(V + E)$
- C) $O(E \log V)$
- D) $O(V \cdot E)$
- **Answer: ✅ B**
- **Explanation**: BFS visits all $V$ vertices and explores all $E$ edges once, yielding a time complexity of $O(V + E)$.

#### Q140. The BFS traversal approach run directly over standard graph maps outputs a:
- A) Tree structure
- B) Stack configuration
- C) Cycle path
- D) Matrix representation
- **Answer: ✅ A**
- **Explanation**: BFS traversal starting from a source node yields a cycle-free spanning tree (BFS tree) representing the shortest path paths from the source.

#### Q141. The maximum number of times the decrease-key operation is performed in Dijkstra's algorithm will be equal to:
- A) Total number of vertices
- B) Total number of edges
- C) $V \log V$
- D) $V^2$
- **Answer: ✅ B**
- **Explanation**: The decrease-key operation is triggered whenever we find a shorter path to a vertex. In the worst case, this relaxation check can occur once for every edge in the graph.

#### Q142. What happens when the value of parameter $K$ settles at zero inside the Floyd-Warshall algorithm framework?
- A) The algorithm terminates
- B) Zero intermediate vertices are allowed
- C) The algorithm starts from vertex 0
- D) A negative cycle is detected
- **Answer: ✅ B**
- **Explanation**: In Floyd-Warshall, the recurrence tracks shortest paths using intermediate vertices from the set $\{1, \dots, K\}$. When $K=0$, zero intermediate vertices are allowed, meaning paths must consist of direct edges only.

#### Q143. Given available coin denominations 1, 3, 4. If a greedy strategy picks the largest possible element denomination layer each turn, for which target sum will it resolve an OPTIMAL calculation profile?
- A) 6
- B) 10
- C) 100
- D) 15
- **Answer: ✅ C**
- **Explanation**:
  - For 6, greedy picks 4, 1, 1 (3 coins); optimal is 3, 3 (2 coins).
  - For 10, greedy picks 4, 4, 1, 1 (4 coins); optimal is 4, 3, 3 (3 coins).
  - For 100, greedy picks twenty-five 4-value coins (25 coins), which matches the absolute optimal dynamic programming resolution.

#### Q144. If a problem can be solved efficiently by combining optimal solutions to non-overlapping subproblems, the strategy is called:
- A) Dynamic Programming
- B) Divide and Conquer
- C) Greedy Strategy
- D) Backtracking
- **Answer: ✅ B**
- **Explanation**: Divide and Conquer splits problems into independent, non-overlapping subproblems (like Merge Sort). Overlapping subproblems are resolved using Dynamic Programming.

