# ⚙️ Algorithms — Unit VI: Complete Comprehensive Notes

Welcome to the ultimate learning module for **Unit VI: Algorithms**. These notes are designed in a highly pedagogical "world-class professor" style: combining intuitive analogies, formal mathematics, step-by-step trace guides, and comprehensive exam preparations.

---

## 📌 Table of Contents
*   [Algorithms Chapter Overview & Roadmap](#algorithms-chapter-overview--roadmap)
*   [Visual Learning ASCII Maps](#visual-learning-ascii-maps)
*   [Topic Relationships & Dependency Map](#topic-relationships--dependency-map)
*   [Examination View & Exam Strategies](#examination-view--exam-strategies)
*   [Study Plan & Graded Learning Orders](#study-plan--graded-learning-orders)
*   [Section 1: Understanding Algorithms and Analysis (10 Parts)](#section-1-understanding-algorithms-and-analysis-10-parts)
*   [Section 2: Running Time Analysis and Rate of Growth (10 Parts)](#section-2-running-time-analysis-and-rate-of-growth-10-parts)
*   [Section 3: Asymptotic Notation (10 Parts)](#section-3-asymptotic-notation-10-parts)
*   [Section 4: Recurrence Relations & The Master Theorem](#section-4-recurrence-relations--the-master-theorem)
*   [Section 5: Backtracking & State Space Trees](#section-5-backtracking--state-space-trees)
*   [Section 6: Dynamic Programming (DP)](#section-6-dynamic-programming-dp)
*   [Section 7: Greedy Algorithms](#section-7-greedy-algorithms)
*   [Section 8: Sorting Benchmarks Comparison](#section-8-sorting-benchmarks-comparison)
*   [Section 9: Common Pitfalls & Mistakes to Avoid](#section-9-common-pitfalls--mistakes-to-avoid)

---

# Algorithms Chapter Overview & Roadmap

### 1. What is this Chapter About?
This chapter is about **computational efficiency and optimization**. It teaches how to design, analyze, compare, and optimize step-by-step procedures (algorithms) executed by computers, ensuring they solve problems correctly while consuming minimal physical resources (time and memory).

### 2. Why does this Chapter Exist?
Hardware gets faster every year, but data sizes grow even faster. A poorly designed algorithm running on a supercomputer will run slower than a well-designed algorithm on a smartphone. This chapter exists to transition you from a coder who merely writes working programs to an engineer who designs highly scalable software systems.

### 3. What Problems does this Chapter Solve?
*   **Scale and Performance:** It predicts whether an algorithm will survive 10 million users before buying expensive servers.
*   **Optimal Strategy Choice:** It provides formal frameworks to choose between Greedy, Dynamic Programming, and Backtracking paradigms.
*   **Resource Limitation:** It analyzes memory and compute trade-offs.

### 4. Where is this Used in Real Life?
*   **Google Search & Maps:** Finding the shortest route between two cities in milliseconds (using Dijkstra's/A* search).
*   **Netflix & Spotify:** Dynamic recommendation systems parsing millions of user histories.
*   **Git & File Compression:** Compression algorithms (Huffman coding) and difference tools (longest common subsequence).

### 5. How Companies Use these Concepts?
Tech giants (Meta, Apple, Amazon, Google, Microsoft) use these concepts to minimize data-center energy costs, optimize database querying plans, rank search queries, and route server packages dynamically.

---

# Visual Learning ASCII Maps

### 🌳 Topic Tree
```
                         Unit 6: Algorithms
                                  │
      ┌───────────────────────────┼───────────────────────────┐
      ▼                           ▼                           ▼
[Complexity Analysis]     [Algorithm Design]         [Advanced Topics]
  ├── Algorithms & Analysis  ├── Greedy Strategies     ├── Recurrences
  ├── Rates of Growth        ├── Dynamic Programming   └── Master Theorem
  └── Asymptotic Notation    └── Backtracking
```

### 🧠 Mind Map
```
               [Hardware Independence] ──▶ Asymptotic Notation
                        ▲
                        │
 [Rates of Growth] ──▶ [COMPLEXITY] ──▶ [ALGORITHMS] ──▶ [DESIGN PARADIGMS]
                        │                                    │
                        ▼                                    ├── Greedy
               [Master Recurrences]                          ├── DP
                                                             └── Backtracking
```

### 🔄 Complexity Analysis Flowchart
```
  [Algorithm Design]
          │
          ▼
 [Primitive Counts] ──▶ Express as T(N) ──▶ Drop Constants ──▶ Asymptotic Class
```

### 🛣️ Learning Path
```
[Pre-req: Basic Loops] ➔ [1. Algorithm Analysis] ➔ [2. Rates of Growth] ➔ [3. Asymptotic Notation] ➔ [4. Recurrences] ➔ [5. Paradigms]
```

---

# Topic Relationships & Dependency Map

*   **Understanding Algorithms & Analysis:**
    *   *Why it exists:* To define what makes an algorithm correct and efficient.
    *   *What it solves:* Measures code performance theoretically.
    *   *Prerequisite:* Programming loop logic.
    *   *Future dependents:* Rate of growth analysis.
*   **Running Time Analysis & Rate of Growth:**
    *   *Why it exists:* To track how algorithm cycles scale.
    *   *What it solves:* Determines scalability.
    *   *Prerequisite:* Complexity analysis basics.
    *   *Future dependents:* Asymptotic Notation.
*   **Asymptotic Notation:**
    *   *Why it exists:* To abstract away hardware differences.
    *   *What it solves:* Establishes mathematical classes ($O, \Omega, \Theta$).
    *   *Prerequisite:* Growth rates.
    *   *Future dependents:* Recurrence relations and Sorting benchmarks.

---

# Examination View & Exam Strategies

*   **Most Important Topics:** Asymptotic definitions, loop analysis, Master Theorem cases, and DP Knapsack grids.
*   **Frequently Asked MCQ Areas:** Dropping constants, sorting time complexities, and recursion stack sizes.
*   **High-Weightage Topics:** Master Theorem calculations, Huffman Coding trees, and 0/1 Knapsack grids.
*   **Conceptually Difficult Topics:** Strict limits of $O$ vs. $\Theta$, proving lossless-joins, and recurrence trees.
*   **Topics Students Usually Confuse:**
    *   *Worst Case vs. Big-O:* Big-O is an upper bound and can describe best, average, or worst cases. It is not synonymously "worst case".
    *   *Iterative vs. Recursive space:* Iterative uses $O(1)$ stack; recursive uses $O(N)$ system stack space.

---

# Study Plan & Graded Learning Orders

### 1. Beginner Learning Order (Highly Recommended)
1. Understanding Algorithms and Analysis
2. Running Time Analysis and Rate of Growth
3. Asymptotic Notation
4. Recurrence Relations & Master Theorem
5. Greedy Strategies & Dynamic Programming

### 2. Fast Revision Order
1. Master Theorem cases
2. Sorting Benchmarks table
3. Top 25 Last-Minute Facts
4. Growth Hierarchy comparison

### 3. Exam Preparation Order
1. Solve loop analysis math problems
2. Practice recurrence solving
3. Build Huffman tree nodes
4. Fill 0/1 Knapsack table cells

---

# Section 1: Understanding Algorithms and Analysis (10 Parts)

## Part 1: Foundation
An algorithm analysis is a formal mechanism to evaluate the efficiency of a program.
*   **Why it exists:** Before building massive codebases, companies need to prove mathematically that their design is efficient and will not crash production environments.
*   **Problem it solves:** Prevents writing algorithms that look fast on small datasets but halt under load.
*   **Where it is used:** Designing compilers, search engines, database indexing, and network packet routing.
*   **History & Motivation:** Introduced by computer pioneers (Turing, Knuth) to establish a mathematical foundation for software execution before physical computers were built.

---

## Part 2: Terminology
*   **Algorithm:** A finite, unambiguous set of step-by-step instructions.
*   **Unambiguous:** Every instruction has exactly one meaning.
*   **Finiteness:** The algorithm must terminate after a finite number of steps.
*   **Time Complexity:** The relative execution scaling time.
*   **Space Complexity:** The auxiliary memory scaling requirement.

---

## Part 3: Complete Theory
An algorithm takes input, processes it, and returns output:
```
  [Input] ──▶ [ Unambiguous Step-by-Step Instructions ] ──▶ [Output]
```
To analyze an algorithm:
1.  **Correctness:** Prove that for *all* valid input sets, it terminates with the correct output.
2.  **Complexity Analysis:** Estimate resource utilization:
    - *Theoretical Analysis:* Count **primitive operations** (comparisons, math operations, memory reads/writes) as a function of input size $N$. This is hardware-independent.
    - *Empirical Analysis:* Run the program on a physical CPU and record execution times. This is hardware-dependent and limited to tested inputs.

---

## Part 4: Visualization
```
                      Complexity Analysis
                               │
            ┌──────────────────┴──────────────────┐
            ▼                                     ▼
 [Theoretical Analysis]                 [Empirical Analysis]
 - Count Primitive Operations           - Compile and execute code
 - Hardware-Independent                 - Measure physical seconds
 - Runs for all inputs (N -> infinity)   - Highly machine-dependent
```

---

## Part 5: Relationships
*   **Connects to Previous Topics:** Relies on structural programming (loops, conditionals, functions).
*   **Connects to Future Topics:** Builds the foundation for rates of growth and asymptotic classifications.

---

## Part 6: Comparison Tables
### Theoretical vs. Empirical Analysis
| Feature | Theoretical Analysis | Empirical Analysis |
| :--- | :--- | :--- |
| **Measurement Unit** | Primitive operations count. | Physical seconds/microseconds. |
| **Hardware Dependency** | Fully independent. | Highly dependent on CPU, RAM, OS. |
| **Input Limitations** | Represents all inputs mathematically. | Limited to test cases run. |
| **Usage** | Used during design phase. | Used during testing/profiling. |

---

## Part 7: Common Confusions
*   **Confusion:** "An algorithm is the same as a program."
*   *Clarification:* No, an algorithm is a high-level logical design (described in pseudocode or plain English); a program is the concrete implementation of that algorithm in a programming language (like C++ or Java).

---

## Part 8: Memory System
*   **Mnemonic: C-I-F-E-O (Clean Algorithms)**
    *   **C**orrectness
    *   **I**nput
    *   **F**initeness
    *   **E**fficiency
    *   **O**utput

---

## Part 9: Exam Preparation
### Solved MCQ
Which of the following is a primary benefit of theoretical analysis over empirical analysis?
- A) It measures exact execution time in nanoseconds
- B) It is fully independent of compiler and CPU hardware profiles
- C) It does not require mathematical formulas
- D) It only works on sorted arrays
- **Answer: ✅ B**
- **Explanation:** Theoretical analysis counts primitive instructions, making it hardware-independent.

---

## Part 10: Revision
*   **60-Second Revision:** Algorithms must be correct, finite, and unambiguous. We evaluate them using theoretical complexity analysis to remain independent of hardware.

---

# Section 2: Running Time Analysis and Rate of Growth (10 Parts)

## Part 1: Foundation
Running time analysis measures how the number of executed statements changes relative to input size $N$.
*   **Why it exists:** To track the efficiency profile of program loops.
*   **Problem it solves:** Demonstrates how nested structures cause time scaling to grow non-linearly.
*   **Where it is used:** Query scaling, image rendering computations, and sorting dataset elements.

---

## Part 2: Terminology
*   **Primitive Operation:** An instruction that takes a constant amount of time (e.g. `x = y + z`).
*   **Linear Growth ($N$):** Work scales directly with input size.
*   **Quadratic Growth ($N^2$):** Work scales with the square of the input size.
*   **Logarithmic Growth ($\log N$):** Work division halves the search space at each step.

---

## Part 3: Complete Theory
Let's trace two algorithms with different loop structures:

### Algorithm A (Single Loop)
```cpp
for (int i = 0; i < N; i++) {
    // 1 Primitive Operation
}
```
*Total Operations:* $T(N) = c_1 \cdot N$. This is a **Linear Rate of Growth**.

### Algorithm B (Nested Loops)
```cpp
for (int i = 0; i < N; i++) {
    for (int j = 0; j < N; j++) {
        // 1 Primitive Operation
    }
}
```
*Total Operations:* $T(N) = c_2 \cdot N^2$. This is a **Quadratic Rate of Growth**.

### The Scaling Math
Let's see what happens if we double the input size ($N \to 2N$):
*   **Algorithm A:** $T(2N) = c_1 \cdot (2N) = 2 \cdot T(N)$. The runtime **doubles**.
*   **Algorithm B:** $T(2N) = c_2 \cdot (2N)^2 = 4 \cdot T(N)$. The runtime **quadruples**!
This is why the rate of growth is the most critical metric for scalability.

---

## Part 4: Visualization
```
  Operations
      ▲
      │                              / Quadratic Growth (N^2)
      │                             /
      │                            /
      │                           /
      │                          /
      │  ───────────────────────/── Linear Growth (N)
      │                       /
      │                    /
      └───────────────────┴──────────────────▶ Input Size (N)
```

---

## Part 5: Relationships
*   **Prerequisite:** Complexity analysis.
*   **Future dependent:** Asymptotic Notation.

---

## Part 6: Comparison Tables
### Growth Rate Comparison
| Class | Math | Double Input ($N \to 2N$) | Scalability for Large $N$ |
| :--- | :--- | :--- | :--- |
| **Constant** | $O(1)$ | No change. | Ideal. |
| **Logarithmic**| $O(\log N)$ | Negligible change. | Excellent. |
| **Linear** | $O(N)$ | Doubles. | Good. |
| **Quadratic** | $O(N^2)$ | Quadruples. | Slow / Poor. |
| **Exponential**| $O(2^N)$ | Squares the cost! | Impractical. |

---

## Part 7: Common Confusions
*   **Confusion:** "An algorithm taking $2^N$ steps is fast if $N$ is small."
*   *Clarification:* True, for $N = 5$, $2^5 = 32$ steps (extremely fast). However, for $N = 100$, $2^{100}$ is larger than the number of atoms in the universe. Rate of growth evaluates **asymptotic behavior** ($N \to \infty$).

---

## Part 8: Memory System
*   **Hierarchy Mnemonic: C-L-L-M-Q-C-E (Fast to Slow)**
    *   **C**onstant ($1$)
    *   **L**ogarithmic ($\log N$)
    *   **L**inear ($N$)
    *   **M**erge-sort ($N \log N$)
    *   **Q**uadratic ($N^2$)
    *   **C**ubic ($N^3$)
    *   **E**xponential ($2^N$)

---

## Part 9: Exam Preparation
### Solved MCQ
If an algorithm's running time scales quadratically, what happens to the number of operations when the input size is tripled?
- A) It triples
- B) It increases by 6 times
- C) It increases by 9 times
- D) It remains constant
- **Answer: ✅ C**
- **Explanation:** Since growth is quadratic ($N^2$), tripling $N$ yields $(3N)^2 = 9N^2$.

---

## Part 10: Revision
*   **60-Second Revision:** Doubling inputs to a linear algorithm doubles operations; doubling inputs to a quadratic one quadruples operations. Focus on the scaling factor for large $N$.

---

# Section 3: Asymptotic Notation (10 Parts)

## Part 1: Foundation
Asymptotic Notation is the mathematical language used to categorize growth rates by ignoring constants and lower-order terms.
*   **Why it exists:** Provides standard runtime classes ($O, \Omega, \Theta$) to compare algorithm design objectively.
*   **Problem it solves:** Eliminates tedious algebraic tracking of small terms (e.g. $T(N) = 3N^2 + 5N + 10$ simplifies to $O(N^2)$).
*   **Where it is used:** Every technical algorithm description and database performance benchmark.

---

## Part 2: Terminology
*   **Big-O ($O$):** Asymptotic Upper Bound.
*   **Big-Omega ($\Omega$):** Asymptotic Lower Bound.
*   **Big-Theta ($\Theta$):** Asymptotic Tight Bound.
*   **$c$ and $n_0$:** Constants used to prove asymptotic boundary thresholds.

---

## Part 3: Complete Theory
Asymptotic analysis evaluates behavior when $N \to \infty$.

### 3.1 Big-O (Upper Bound)
$f(N) = O(g(N))$ means $f(N)$ grows at most as fast as $g(N)$ up to a constant factor.
*   **Formal Definition:** $0 \le f(N) \le c \cdot g(N)$ for all $N \ge n_0$.
*   *Mathematical Example:* Prove $3N + 5 = O(N)$.
    - We want: $3N + 5 \le c \cdot N$
    - Let $c = 4$: $3N + 5 \le 4N \implies 5 \le N$.
    - Thus, $n_0 = 5$. Since we found positive constants $c=4$ and $n_0=5$, $3N + 5 = O(N)$ holds.

### 3.2 Big-Omega (Lower Bound)
$f(N) = \Omega(g(N))$ means $f(N)$ grows at least as fast as $g(N)$ up to a constant factor.
*   **Formal Definition:** $0 \le c \cdot g(N) \le f(N)$ for all $N \ge n_0$.

### 3.3 Big-Theta (Tight Bound)
$f(N) = \Theta(g(N))$ means $f(N)$ grows exactly as fast as $g(N)$.
*   **Formal Definition:** $c_1 \cdot g(N) \le f(N) \le c_2 \cdot g(N)$ for all $N \ge n_0$.

---

## Part 4: Visualization
```
  f(N) = O(g(N))                    f(N) = Ω(g(N))                    f(N) = Θ(g(N))
      │      / c*g(N)                     │        f(N)                    │     / c2*g(N)
      │     /                             │       /                        │    / / f(N)
      │    / / f(N)                       │      / / c*g(N)                │   / / /
      │   / /                             │     / /                        │  / / / c1*g(N)
      └───┴────────────────               └───┴──────────────              └───┴──────────────
        (N >= n0)                           (N >= n0)                        (N >= n0)
```

---

## Part 5: Relationships
*   **Prerequisite:** Rates of growth.
*   **Future dependent:** Analyzing recursive and iterative routines.

---

## Part 6: Comparison Tables
### Asymptotic Bounds
| Notation | Math Definition | Analogy | Standard Scenario |
| :--- | :--- | :--- | :--- |
| **Big-O ($O$)** | $f(N) \le c \cdot g(N)$ | Ceiling ($\le$). | Worst-Case Bound. |
| **Big-Omega ($\Omega$)**| $f(N) \ge c \cdot g(N)$ | Floor ($\ge$). | Best-Case Bound. |
| **Big-Theta ($\Theta$)**| $c_1 \cdot g(N) \le f(N) \le c_2 \cdot g(N)$ | Tight Fit ($=$). | Average-Case / Exact Bound. |

---

## Part 7: Common Confusions
*   **Confusion:** "Big-O always means worst case."
*   *Clarification:* No. Big-O is an upper bound. You can describe the best case of an algorithm using Big-O. For instance, the best case of Linear Search is finding the key at index 0, which is $O(1)$. The worst case is $O(N)$.

---

## Part 8: Memory System
*   **Anchor Mnemonics:**
    *   **O** $\to$ **O**verhead / Ceiling (Upper limit)
    *   **Omega ($\Omega$)** $\to$ **U**nderneath / Floor (Lower limit)
    *   **Theta ($\Theta$)** $\to$ **T**ight / Middle (Exact limit)

---

## Part 9: Exam Preparation
### Solved MCQ
If $f(N) = 10N^2 + 5N \log N$, which of the following is correct?
- A) $f(N) = O(N \log N)$
- B) $f(N) = \Theta(N^2)$
- C) $f(N) = \Omega(N^3)$
- D) $f(N) = O(N)$
- **Answer: ✅ B**
- **Explanation:** The dominant term is $10N^2$. Dropping the constant coefficient $10$ leaves $N^2$. Thus, $f(N) = \Theta(N^2)$.

---

## Part 10: Revision
*   **60-Second Revision:** Drop constants and lower-order terms. Keep the highest-order term. Big-O is upper bound, Omega is lower bound, Theta is tight bound.

---

# Section 4: Recurrence Relations & The Master Theorem

A **Recurrence** describes the runtime of a recursive function by referencing its own runtime on smaller inputs.

### 🛠️ The Master Theorem
For recurrences of the form:
$$T(N) = aT(N/b) + \Theta(N^d)$$
where $a \ge 1$ (number of recursive branches), $b > 1$ (input division factor), and $d \ge 0$ (exponent of work done outside recursion).

We compare the non-recursive work exponent $d$ with the critical value $\log_b a$:

```
                             COMPARE d with log_b(a)
                                         │
            ┌────────────────────────────┼────────────────────────────┐
            ▼                            ▼                            ▼
      [ d < log_b(a) ]             [ d == log_b(a) ]            [ d > log_b(a) ]
      Recursion dominates          Equal work everywhere        Split/Merge dominates
      T(N) = Θ(N^log_b(a))         T(N) = Θ(N^d * log N)        T(N) = Θ(N^d)
```

#### Worked Example:
Solve $T(N) = 2T(N/2) + N$ (Merge Sort recurrence):
*   $a = 2, b = 2, d = 1$.
*   Compute $\log_b a = \log_2 2 = 1$.
*   Since $d == \log_b a$ ($1 == 1$), this falls into **Case 2**:
    $$T(N) = \Theta(N^1 \log N) = \Theta(N \log N)$$

---

# Section 5: Backtracking & State Space Trees

**Backtracking** is a systematic method for searching all configuration states to solve a constraint problem.
*   **Mechanism:** It builds candidates for a solution incrementally and abandons a candidate ("backtracks") as soon as it determines that the candidate cannot lead to a valid final solution.
*   **State Space Tree:** A tree representing all possible states (choices) generated by the algorithm.

```
                   [ Root: Start (Empty Board) ]
                      /          │          \
                [Q at (0,0)] [Q at (0,1)] [Q at (0,2)]
                   /             │             \
             [Invalid]      [Q at (1,3)]     [Invalid]  <-- Prunes branches early!
```
*   **Key Advantage:** Avoids checking all brute-force permutations by pruning branches of the state space tree early using bounding constraints.
*   **Classical Examples:** N-Queens Problem, Sudoku Solver, Hamiltonian Cycle.

---

# Section 6: Dynamic Programming (DP)

DP is an optimization technique used for problems containing overlapping subproblems and optimal substructures. It solves each subproblem exactly once and caches the result.

```
        DECOMPOSITION METHOD                       DP STRATEGY
  ┌─────────────────────────────┐         ┌─────────────────────────────┐
  |   Divide & Conquer (Merge)  |         |     Dynamic Programming     |
  |   - Disjoint subproblems    |         |   - Overlapping subproblems |
  |   - Solve independently     |         |   - Cache subproblem outputs|
  └─────────────────────────────┘         └─────────────────────────────┘
```

### 5.1 Memoization vs. Tabulation
*   **Memoization (Top-down):** Write the solution recursively, caching results in a lookup table before returning them. Solves only required subproblems.
*   **Tabulation (Bottom-up):** Solves base cases first and fills a lookup table iteratively. Avoids recursion stack overhead.

---

### 5.2 Case Study: 0/1 Knapsack Tabulation
You have a knapsack of capacity **$W = 5$** and four items:

| Item ($i$) | Weight ($w_i$) | Value ($v_i$) |
| :--- | :--- | :--- |
| **1** | 1 | 10 |
| **2** | 2 | 15 |
| **3** | 3 | 40 |
| **4** | 4 | 50 |

#### DP Recurrence Relation:
$$dp[i][w] = \max(dp[i-1][w], \ v_i + dp[i-1][w - w_i])$$

#### The DP Grid:
`dp[i][w]` stores the maximum value using a subset of items $1..i$ with remaining capacity $w$:

```
  Cap (w):  0     1     2     3     4     5
Item 0:    [0]   [0]   [0]   [0]   [0]   [0]
Item 1:    [0]  [10]  [10]  [10]  [10]  [10]
Item 2:    [0]  [10]  [15]  [25]  [25]  [25]
Item 3:    [0]  [10]  [15]  [40]  [50]  [55]
Item 4:    [0]  [10]  [15]  [40]  [50]  [65]  ◄── MAX VALUE = 65!
```

#### Step-by-Step State Calculation for `dp[3][5]` (Item 3, Cap 5):
*   **Option 1 (Exclude Item 3):** Take value from row above: `dp[2][5]` = 25.
*   **Option 2 (Include Item 3):** Take value of Item 3 (40) plus maximum value of remaining capacity `dp[2][5 - 3]` = `dp[2][2]` (15):
    $$\text{Value} = 40 + 15 = 55$$
*   **Result:** $\max(25, 55) = 55$.

---

# Section 7: Greedy Algorithms

A **Greedy Algorithm** builds a solution step-by-step, making the locally optimal choice at each stage in the hope of finding a global optimum.
*   **Greedy Choice Property:** A global optimum can be reached by making local choices.
*   *Contrast:* Unlike DP, a Greedy algorithm commits to a choice immediately and never backtracks or recalculates options.

### 6.1 Classical Greedy Algorithms
*   **Fractional Knapsack:** Sort items by value-to-weight density ($v_i / w_i$) and take items greedily (allows fractions). Provably optimal.
*   **Dijkstra's Algorithm:** Builds shortest paths from a single source by greedily selecting the nearest unvisited node.
*   **Kruskal's & Prim's Algorithms:** Build the Minimum Spanning Tree (MST) of a weighted graph by greedily adding the cheapest valid edges.

---

### 6.2 Huffman Coding Walkthrough
Huffman coding is a lossless compression algorithm that assigns variable-length binary codes to characters based on their frequency.

#### The Scenario:
Characters and their frequencies: `A: 45, B: 13, C: 12, D: 16, E: 9, F: 5`

```
Step 1: Create leaf nodes for each char and insert into a priority queue sorted by frequency:
        [F:5, E:9, C:12, B:13, D:16, A:45]

Step 2: Extract the two lowest frequency nodes: F(5) and E(9).
        Create parent node N1 with frequency = 5 + 9 = 14.
        Insert N1 back into the queue:
        [C:12, B:13, N1:14, D:16, A:45]

Step 3: Extract the two lowest: C(12) and B(13).
        Create parent node N2 with frequency = 12 + 13 = 25.
        Insert N2:
        [N1:14, D:16, N2:25, A:45]

Step 4: Extract N1(14) and D(16).
        Create parent N3 = 14 + 16 = 30.
        Insert N3:
        [N2:25, N3:30, A:45]

Step 5: Extract N2(25) and N3(30).
        Create parent N4 = 25 + 30 = 55.
        Insert N4:
        [A:45, N4:55]

Step 6: Extract A(45) and N4(55).
        Create final Root node = 45 + 55 = 100.
```

#### The Huffman Tree:
Assign `0` to left branches and `1` to right branches:

```
               [ Root: 100 ]
               /           \
           ( A:45 )       [ N4: 55 ]
            Code: 0       /         \
                      [N2: 25]     [N3: 30]
                      /      \     /      \
                    (C:12)  (B:13)(N1:14) (D:16)
                    Code:10 Code:11 /    \ Code:111
                                 (F:5)  (E:9)
                                 Code:   Code:
                                 1100    1101
```
*   **Resulting Prefix Codes:** `A: 0`, `C: 100`, `B: 101`, `D: 111`, `F: 1100`, `E: 1101`. Highly frequent characters receive shorter codes, saving transmission bits.

---

# Section 8: Sorting Benchmarks Comparison

Sorting benchmarks are core topics in algorithm design.

| Algorithm | Best Case | Average Case | Worst Case | Space Complexity | Stable? | In-Place? |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Bubble Sort** | $O(N)$ | $O(N^2)$ | $O(N^2)$ | $O(1)$ | Yes | Yes |
| **Selection Sort** | $O(N^2)$ | $O(N^2)$ | $O(N^2)$ | $O(1)$ | No | Yes |
| **Insertion Sort** | $O(N)$ | $O(N^2)$ | $O(N^2)$ | $O(1)$ | Yes | Yes |
| **Merge Sort** | $O(N \log N)$ | $O(N \log N)$ | $O(N \log N)$ | $O(N)$ | Yes | No |
| **Quick Sort** | $O(N \log N)$ | $O(N \log N)$ | $O(N^2)$ | $O(\log N)$ | No | Yes |
| **Heap Sort** | $O(N \log N)$ | $O(N \log N)$ | $O(N \log N)$ | $O(1)$ | No | Yes |

*   **Stability:** Preserves the relative order of duplicate elements.
*   **In-Place:** Requires $O(1)$ auxiliary space during sorting.

---

# Section 9: Common Pitfalls & Mistakes to Avoid

> [!WARNING]
> ### 1. Inapplicability of the Master Theorem
> *   **The Mistake:** Trying to apply the Master Theorem to recurrences containing non-constant coefficient values (e.g. $T(N) = 2T(N/2) + N \log N$) or non-polynomial divisions (e.g. $T(N) = T(N-1) + 1$).
> *   **The Reality:** The Master Theorem strictly requires recurrences of the form $T(N) = aT(N/b) + f(N)$, where $a \ge 1$ and $b > 1$. For equations like $T(N) = T(N-1) + 1$ or non-constant coefficients, you must use the **Recursion Tree Method** or **Substitution Method**.

> [!WARNING]
> ### 2. Greedy Choice vs. Dynamic Programming
> *   **The Mistake:** Using a Greedy strategy to solve the 0/1 Knapsack problem.
> *   **The Reality:** A greedy choice based on value-to-weight ratio fails for 0/1 Knapsack because items cannot be split. For example, if capacity is 5, and items are `(W:4, V:40)`, `(W:3, V:30)`, and `(W:2, V:25)`, the greedy approach selects item 1, leaving capacity 1 (Total value = 40). The optimal choice is selecting items 2 and 3 (Total value = $30 + 25 = 55$). 0/1 Knapsack requires Dynamic Programming.

> [!WARNING]
> ### 3. Forgetting the Base Case in Recursion
> *   **The Mistake:** Writing recursive equations or backtracking code without a clear termination condition.
> *   **The Reality:** If the base case is omitted or is mathematically unreachable, the recursion stack will grow indefinitely, resulting in a **Stack Overflow** error.

> [!WARNING]
> ### 4. Confusion between Permutations and Subsets
> *   **The Mistake:** Generating permutations when the problem requires subsets (or vice versa).
> *   **The Reality:**
>     - **Subsets (Combinations):** Order does not matter. The number of subsets of a set of size $N$ is $2^N$.
>     - **Permutations:** Order matters. The number of permutations of a set of size $N$ is $N!$.
>     - Confusing these in backtracking algorithms results in incorrect state spaces and bad time complexities.
