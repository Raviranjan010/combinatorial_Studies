# Unit VI: Algorithms - MCQ Bank

Test your mastery of runtime analysis, recurrences, sorting benchmarks, Dynamic Programming, and Greedy strategies with these 50 solved, high-probability Multiple Choice Questions.

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
