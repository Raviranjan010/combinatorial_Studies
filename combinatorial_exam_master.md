# 📘 Combinatorial / CS Exam Master Notes

> **🎯 Quick Start**: Read Rapid Revision Sheets first → MCQ Bank → Top 100 → Shortcuts. Total time: 2-3 hours.

---

## 📌 CHAPTER 1: OPERATING SYSTEMS

### 1.1 Operating System Concepts

**🔹 Key Concepts:**
- **OS**: Interface between user and hardware
- **Goals**: Convenience, efficiency, ability to evolve
- **Types**: Batch, Time-sharing, Distributed, Real-time, Embedded
- **Kernel**: Core component, runs in **privileged mode**

**🧠 Must-Remember:**
- **System Programs** ≠ System Calls (programs use system calls)
- OS is a **resource allocator** and **control program**

**⚠️ Trap Concepts:**
- ❌ OS manages only CPU → ✅ Manages ALL resources (CPU, memory, I/O, files)
- ❌ User mode can execute privileged instructions → ✅ Only kernel mode can

**⚡ Memory Trick:**
- OS Types: **BT-DRE** (Batch, Time-sharing, Distributed, Real-time, Embedded)

---

### 1.2 Kernel

**🔹 Key Concepts:**
- **Monolithic Kernel**: All services in single address space (Linux)
- **Microkernel**: Minimal services, rest as user processes (QNX, MINIX)
- **Hybrid Kernel**: Combination (Windows, macOS)

**🧠 Must-Remember:**
- Kernel runs in **Ring 0** (highest privilege)
- User applications run in **Ring 3**

**⚠️ Trap Concepts:**
- ❌ Microkernel is faster → ✅ Monolithic is faster (less context switching)
- ❌ Microkernel is less secure → ✅ More secure (isolation)

---

### 1.3 System Calls

**🔹 Key Concepts:**
- Interface between process and OS kernel
- **Types**: Process control, File management, Device management, Information maintenance, Communication
- Examples: `fork()`, `exec()`, `read()`, `write()`, `open()`, `close()`

**🧠 Must-Remember:**
- `fork()` returns **0 to child**, **PID to parent**, **-1 on error**
- System calls cause **mode switch** (user → kernel)

**⚠️ Trap Concepts:**
- ❌ System call = Function call → ✅ System call = Kernel entry (expensive)
- ❌ `fork()` creates thread → ✅ Creates process

**⚡ Memory Trick:**
- Process Control: **FEW** (Fork, Exec, Wait/Exit)

---

### 1.4 Process & Process Scheduling

**🔹 Key Concepts:**
- **Process**: Program in execution
- **Process States**: New → Ready → Running → Waiting → Terminated
- **PCB** (Process Control Block): Stores process info (PID, PC, registers, state)
- **Scheduling Queues**: Job queue, Ready queue, Device queue

**🧠 Must-Remember:**
- **Context Switch**: Save state of old process, load state of new process
- **Overhead**: Pure overhead (no useful work)
- **Degree of Multiprogramming**: Number of processes in memory

**⚠️ Trap Concepts:**
- ❌ Ready → Waiting directly → ✅ Must go through Running first
- ❌ Context switch is useful → ✅ Pure overhead

**⚡ Memory Trick:**
- Process States: **NR-RWT** (New, Ready, Running, Waiting, Terminated)

---

### 1.5 CPU Scheduling

**🔹 Key Concepts:**

| Algorithm | Type | Key Feature | Waiting Time |
|-----------|------|-------------|--------------|
| **FCFS** | Non-preemptive | First come first serve | Convoy effect |
| **SJF** | Both | Shortest job first | Optimal (minimum avg) |
| **Round Robin** | Preemptive | Time quantum | Fair sharing |
| **Priority** | Both | Priority-based | Starvation possible |
| **Multilevel Queue** | Both | Multiple queues | Class-based |

**🧠 Must-Remember:**
- **SJF** gives **minimum average waiting time** (OPTIMAL)
- **Starvation** occurs in: SJF, Priority (solved by **Aging**)
- **Response Time** important for interactive systems
- **Turnaround Time** = Completion - Arrival
- **Waiting Time** = Turnaround - Burst

**⚠️ Trap Concepts:**
- ❌ Round Robin is non-preemptive → ✅ Preemptive (time quantum)
- ❌ FCFS always optimal → ✅ SJF optimal for waiting time
- ❌ Smaller quantum always better → ✅ Too small = high context switch overhead

**⚡ Memory Trick:**
- Scheduling Types: **F-SRP** (FCFS, SJF, RR, Priority)

---

### 1.6 Threads

**🔹 Key Concepts:**
- **Thread**: Lightweight process, shares code, data, files with other threads
- **User-level threads**: Managed by user library (fast creation, blocking issue)
- **Kernel-level threads**: Managed by OS (slower, better concurrency)
- **Multithreading Models**: Many-to-One, One-to-One, Many-to-Many

**🧠 Must-Remember:**
- Threads share: **Code section, Data section, Files, Signals**
- Threads have own: **Thread ID, PC, Registers, Stack**
- **One-to-One** model: Linux, Windows
- **Many-to-Many**: Most flexible

**⚠️ Trap Concepts:**
- ❌ Threads have separate memory → ✅ Share memory space
- ❌ User threads = Kernel threads → ✅ Different management levels

---

### 1.7 Synchronization

**🔹 Key Concepts:**
- **Critical Section**: Code segment accessing shared resources
- **Race Condition**: Output depends on execution order
- **Requirements**: Mutual Exclusion, Progress, Bounded Waiting

**🧠 Must-Remember:**
- **Peterson's Solution**: Software-based, 2 processes only
- **TestAndSet**, **Swap**: Hardware solutions
- **Critical Section Problem**: Must satisfy all 3 conditions

**⚠️ Trap Concepts:**
- ❌ Mutual Exclusion alone is sufficient → ✅ Need all 3 conditions
- ❌ Peterson's works for n processes → ✅ Only 2 processes

---

### 1.8 Semaphores & Mutex

**🔹 Key Concepts:**
- **Semaphore**: Integer variable with `wait()` and `signal()` operations
- **Binary Semaphore**: Value 0 or 1 (like mutex)
- **Counting Semaphore**: Any integer value (resource counting)
- **Mutex**: Lock mechanism (lock/unlock)

**🧠 Must-Remember:**
- **wait(S)**: Decrements S, blocks if S < 0
- **signal(S)**: Increments S, wakes up waiting process
- **Mutex**: Only owner can release (ownership property)
- **Binary Semaphore** ≠ **Mutex** (mutex has ownership)

**⚠️ Trap Concepts:**
- ❌ Mutex and Binary Semaphore are same → ✅ Mutex has ownership
- ❌ Semaphore value can't be negative → ✅ Can be negative (waiting processes count)

**⚡ Memory Trick:**
- wait = P (proberen = test), signal = V (verhogen = increment)

---

### 1.9 Deadlock

**🔹 Key Concepts:**
- **Deadlock**: Set of processes waiting for resources held by others
- **4 Necessary Conditions** (Coffman Conditions):
  1. **Mutual Exclusion**
  2. **Hold and Wait**
  3. **No Preemption**
  4. **Circular Wait**

**🧠 Must-Remember:**
- **Deadlock Prevention**: Break one of 4 conditions
- **Deadlock Avoidance**: Banker's Algorithm (safe state checking)
- **Deadlock Detection**: Resource Allocation Graph (with multiple instances)
- **Recovery**: Process termination, Resource preemption

**⚠️ Trap Concepts:**
- ❌ RAG with single instance detects deadlock → ✅ Single instance: cycle = deadlock
- ❌ Banker's Algorithm prevents deadlock → ✅ Avoids (not prevents)
- ❌ All 4 conditions sufficient → ✅ Necessary but not sufficient in all cases

**⚡ Memory Trick:**
- 4 Conditions: **M-HNC** (Mutual exclusion, Hold & wait, No preemption, Circular wait)

---

### 1.10 Types of Memory

**🔹 Key Concepts:**

| Type | Speed | Cost | Volatile | Example |
|------|-------|------|----------|--------|
| **Register** | Fastest | Highest | Yes | CPU registers |
| **Cache** | Very fast | High | Yes | L1, L2, L3 |
| **RAM** | Fast | Medium | Yes | DRAM, SRAM |
| **Disk** | Slow | Low | No | HDD, SSD |
| **Tape** | Slowest | Lowest | No | Magnetic tape |

**🧠 Must-Remember:**
- **SRAM**: Faster, expensive, used for cache
- **DRAM**: Slower, cheaper, used for main memory
- **Locality of Reference**: Temporal (recent) + Spatial (nearby)

**⚠️ Trap Concepts:**
- ❌ Cache is non-volatile → ✅ Volatile
- ❌ SRAM used for main memory → ✅ DRAM used for main memory

---

### 1.11 Memory Management Schemes

**🔹 Key Concepts:**
- **Contiguous Allocation**: Fixed/Variable partitions
- **Paging**: Non-contiguous, logical → physical via page table
- **Segmentation**: User's view of memory (logical segments)
- **Virtual Memory**: Larger than physical memory (demand paging)

**🧠 Must-Remember:**
- **Page Size** = **Frame Size** (power of 2)
- **Page Table**: Maps logical page → physical frame
- **TLB** (Translation Lookaside Buffer): Cache for page table
- **Effective Access Time** with TLB: `EAT = h×(t+m) + (1-h)×(t+2m)`
- **Page Fault**: Page not in memory, must fetch from disk
- **Belady's Anomaly**: More frames → more page faults (FIFO only)

**⚠️ Trap Concepts:**
- ❌ Paging has external fragmentation → ✅ Internal fragmentation only
- ❌ Segmentation has internal fragmentation → ✅ External fragmentation only
- ❌ Optimal page replacement is practical → ✅ Impossible (future knowledge needed)

**⚡ Memory Trick:**
- Page Replacement: **F-O-L** (FIFO has anomaly, Optimal best, LRU practical)

---

### 1.12 Secondary Storage

**🔹 Key Concepts:**
- **Magnetic Disks**: Platters, tracks, sectors, cylinders
- **SSD**: Flash memory, no moving parts, faster than HDD
- **Disk Scheduling**: FCFS, SSTF, SCAN, C-SCAN, LOOK, C-LOOK

**🧠 Must-Remember:**
- **SSTF**: May cause starvation
- **SCAN**: Elevator algorithm (back-and-forth)
- **C-SCAN**: Circular SCAN (uniform wait time)
- **LOOK/C-LOOK**: Like SCAN/C-SCAN but don't go to end

**⚡ Memory Trick:**
- Disk Scheduling: **F-S-S-C-L-CL** (FCFS, SSTF, SCAN, C-SCAN, LOOK, C-LOOK)

---

### 1.13 RAID (Redundant Array of Independent Disks)

**🔹 Key Concepts:**

| RAID Level | Min Disks | Technique | Fault Tolerance |
|------------|-----------|-----------|-----------------|
| **RAID 0** | 2 | Striping | None |
| **RAID 1** | 2 | Mirroring | 1 disk |
| **RAID 5** | 3 | Striping + Parity | 1 disk |
| **RAID 6** | 4 | Striping + Double Parity | 2 disks |
| **RAID 10** | 4 | Mirror + Stripe | 1 per mirror |

**🧠 Must-Remember:**
- **RAID 0**: Fastest but NO redundancy
- **RAID 1**: 50% storage efficiency
- **RAID 5**: Good balance (performance + redundancy)

**⚠️ Trap Concepts:**
- ❌ RAID 0 provides fault tolerance → ✅ NO redundancy
- ❌ RAID 1 needs 3 disks → ✅ Only 2 disks

---

### 1.14 File System

**🔹 Key Concepts:**
- **File**: Named collection of related information
- **Directory**: Contains file metadata
- **File Allocation Methods**: Contiguous, Linked, Indexed
- **Free Space Management**: Bit vector, Linked list, Grouping, Counting

**🧠 Must-Remember:**
- **Contiguous**: External fragmentation, suffers from Belady's
- **Linked**: No external fragmentation, no random access
- **Indexed**: Supports random access, overhead of index block
- **Inode**: Index node (Unix), stores file metadata

**⚠️ Trap Concepts:**
- ❌ Linked allocation supports direct access → ✅ Sequential only
- ❌ Contiguous has no fragmentation → ✅ External fragmentation

---

### 1.15 Disk Scheduling (Detailed)

**🔹 Key Concepts:**

| Algorithm | Movement | Starvation | Use Case |
|-----------|----------|------------|----------|
| **FCFS** | Fair | No | Light load |
| **SSTF** | Shortest first | Yes | Moderate load |
| **SCAN** | Both directions | No | Heavy load |
| **C-SCAN** | One direction | No | Uniform response |

**🧠 Must-Remember:**
- Calculate **total head movement** for exam problems
- **SSTF** picks closest request (greedy approach)

---

### 1.16 Important Linux Commands

**🧠 Must-Remember Commands:**

| Command | Purpose |
|---------|--------|
| `ls -l` | List files (detailed) |
| `chmod` | Change permissions |
| `ps` | Process status |
| `kill` | Terminate process |
| `grep` | Search text |
| `find` | Find files |
| `top` | System monitor |
| `df` | Disk space |
| `du` | Directory size |
| `man` | Manual pages |

**⚡ Memory Trick:**
- Permissions: **rwx** (read=4, write=2, execute=1)
- `chmod 755` = rwxr-xr-x

---

## 🧠 CHAPTER 1: OS - MCQ BANK (50 Questions)

**Q1.** Which of the following is NOT a type of operating system?
- A) Batch OS
- B) Time-sharing OS
- C) Compiler OS
- D) Real-time OS

**Answer:** ✅ C

**Explanation:** Compiler is a program, not an OS type. Batch, Time-sharing, and Real-time are valid OS types.

---

**Q2.** The core component of the operating system is called:
- A) Shell
- B) Kernel
- C) API
- D) GUI

**Answer:** ✅ B

**Explanation:** Kernel is the core that manages hardware and system resources. Shell is the user interface.

---

**Q3.** Which scheduling algorithm gives the minimum average waiting time?
- A) FCFS
- B) Round Robin
- C) SJF
- D) Priority

**Answer:** ✅ C

**Explanation:** SJF (Shortest Job First) is proven optimal for minimizing average waiting time.

---

**Q4.** In Round Robin scheduling, if the time quantum is too large, it behaves like:
- A) SJF
- B) FCFS
- C) Priority
- D) LIFO

**Answer:** ✅ B

**Explanation:** Large quantum means processes complete without preemption, similar to FCFS.

---

**Q5.** Context switching is:
- A) Useful work
- B) Pure overhead
- C) Both useful and overhead
- D) None of the above

**Answer:** ✅ B

**Explanation:** Context switching saves/restores state but performs no useful computation.

---

**Q6.** Which of the following is a necessary condition for deadlock?
- A) Preemption
- B) Circular wait
- C) No mutual exclusion
- D) No hold and wait

**Answer:** ✅ B

**Explanation:** Circular wait is one of the 4 Coffman conditions. Others are: Mutual exclusion, Hold and wait, No preemption.

---

**Q7.** Banker's algorithm is used for:
- A) Deadlock prevention
- B) Deadlock avoidance
- C) Deadlock detection
- D) Deadlock recovery

**Answer:** ✅ B

**Explanation:** Banker's algorithm avoids deadlock by ensuring the system stays in a safe state.

---

**Q8.** Which page replacement algorithm suffers from Belady's Anomaly?
- A) LRU
- B) Optimal
- C) FIFO
- D) LFU

**Answer:** ✅ C

**Explanation:** FIFO can show more page faults with more frames (Belady's Anomaly). LRU and Optimal are stack algorithms.

---

**Q9.** In paging, external fragmentation occurs:
- A) Always
- B) Never
- C) Sometimes
- D) Depends on page size

**Answer:** ✅ B

**Explanation:** Paging eliminates external fragmentation (non-contiguous). Internal fragmentation may occur in last page.

---

**Q10.** TLB stands for:
- A) Translation Lookaside Buffer
- B) Table Lookup Buffer
- C) Time Local Buffer
- D) Temporary Load Buffer

**Answer:** ✅ A

**Explanation:** TLB caches page table entries to speed up address translation.

---

**Q11.** Which RAID level provides NO fault tolerance?
- A) RAID 0
- B) RAID 1
- C) RAID 5
- D) RAID 6

**Answer:** ✅ A

**Explanation:** RAID 0 uses only striping for performance, no redundancy.

---

**Q12.** The `fork()` system call returns:
- A) 0 to parent, PID to child
- B) 0 to child, PID to parent
- C) -1 to both
- D) PID to both

**Answer:** ✅ B

**Explanation:** fork() returns 0 to the newly created child process and the child's PID to the parent.

---

**Q13.** Which synchronization construct has the ownership property?
- A) Binary Semaphore
- B) Mutex
- C) Counting Semaphore
- D) All of the above

**Answer:** ✅ B

**Explanation:** Only the thread that locked a mutex can unlock it (ownership). Semaphores don't have this property.

---

**Q14.** In the process state diagram, a process transitions from Ready to:
- A) Waiting
- B) Terminated
- C) Running
- D) New

**Answer:** ✅ C

**Explanation:** Process must be scheduled (Ready → Running) before it can wait or terminate.

---

**Q15.** Which of the following is shared among threads of the same process?
- A) Stack
- B) Registers
- C) Code section
- D) Thread ID

**Answer:** ✅ C

**Explanation:** Threads share code, data, and files. Each thread has its own stack, registers, and thread ID.

---

**Q16.** The elevator algorithm is also known as:
- A) FCFS
- B) SSTF
- C) SCAN
- D) C-SCAN

**Answer:** ✅ C

**Explanation:** SCAN moves back and forth like an elevator servicing requests.

---

**Q17.** SRAM is typically used for:
- A) Main memory
- B) Cache memory
- C) Secondary storage
- D) Virtual memory

**Answer:** ✅ B

**Explanation:** SRAM is faster but expensive, used for cache. DRAM is used for main memory.

---

**Q18.** Which file allocation method does NOT support random access?
- A) Contiguous
- B) Indexed
- C) Linked
- D) All support random access

**Answer:** ✅ C

**Explanation:** Linked allocation requires traversing pointers sequentially.

---

**Q19.** In Linux, `chmod 755` means:
- A) rwxr-xr-x
- B) rwxrwxr-x
- C) rwx------
- D) r-xr-xr-x

**Answer:** ✅ A

**Explanation:** 7=rwx (owner), 5=r-x (group), 5=r-x (others).

---

**Q20.** Peterson's solution works for:
- A) 2 processes
- B) n processes
- C) Threads only
- D) Unlimited processes

**Answer:** ✅ A

**Explanation:** Peterson's solution is designed for exactly 2 processes.

---

**Q21.** Which of the following is NOT a CPU scheduling algorithm?
- A) Round Robin
- B) SJF
- C) LRU
- D) Priority

**Answer:** ✅ C

**Explanation:** LRU is a page replacement algorithm, not a scheduling algorithm.

---

**Q22.** Starvation can occur in:
- A) FCFS
- B) Round Robin
- C) Priority scheduling
- D) All of the above

**Answer:** ✅ C

**Explanation:** Low priority processes may never get CPU in Priority scheduling. Solved by aging.

---

**Q23.** A microkernel:
- A) Has all services in kernel space
- B) Has minimal services in kernel
- C) Is faster than monolithic kernel
- D) Is used in Linux

**Answer:** ✅ B

**Explanation:** Microkernel keeps only essential services in kernel, others as user processes. Linux uses monolithic kernel.

---

**Q24.** The degree of multiprogramming refers to:
- A) Number of CPUs
- B) Number of processes in memory
- C) Number of processes in ready queue
- D) Number of threads

**Answer:** ✅ B

**Explanation:** It's the number of processes residing in main memory at any time.

---

**Q25.** Which memory is the fastest?
- A) Cache
- B) RAM
- C) Registers
- D) Disk

**Answer:** ✅ C

**Explanation:** CPU registers are the fastest, followed by cache, RAM, and disk.

---

**Q26.** Turnaround time is calculated as:
- A) Completion time - Arrival time
- B) Waiting time + Burst time
- C) Both A and B
- D) Completion time - Burst time

**Answer:** ✅ C

**Explanation:** Turnaround time = Completion - Arrival = Waiting + Burst.

---

**Q27.** Aging is a technique to prevent:
- A) Deadlock
- B) Starvation
- C) Fragmentation
- D) Thrashing

**Answer:** ✅ B

**Explanation:** Aging gradually increases priority of waiting processes to prevent starvation.

---

**Q28.** Which is true about RAID 1?
- A) Uses striping
- B) 50% storage efficiency
- C) No fault tolerance
- D) Needs 4 disks minimum

**Answer:** ✅ B

**Explanation:** RAID 1 mirrors data, so only 50% of total disk space is usable.

---

**Q29.** In segmentation, which type of fragmentation occurs?
- A) Internal
- B) External
- C) Both
- D) Neither

**Answer:** ✅ B

**Explanation:** Segmentation suffers from external fragmentation (variable-sized segments).

---

**Q30.** Effective access time with TLB hit ratio 'h' is:
- A) h×m + (1-h)×2m
- B) h×(t+m) + (1-h)×(t+2m)
- C) t + m
- D) h×t + m

**Answer:** ✅ B

**Explanation:** Includes TLB access time (t) and memory access time (m). On miss, need 2 memory accesses.

---

**Q31.** Which system call is used to create a new process?
- A) exec()
- B) fork()
- C) wait()
- D) exit()

**Answer:** ✅ B

**Explanation:** fork() creates a new process. exec() replaces process memory space.

---

**Q32.** Race condition occurs when:
- A) Processes execute sequentially
- B) Output depends on execution order
- C) Deadlock occurs
- D) Resources are preempted

**Answer:** ✅ B

**Explanation:** Race condition: final outcome depends on the order of interleaved execution.

---

**Q33.** Which is NOT a requirement for critical section problem?
- A) Mutual Exclusion
- B) Progress
- C) Bounded Waiting
- D) Preemption

**Answer:** ✅ D

**Explanation:** Three requirements are: Mutual Exclusion, Progress, Bounded Waiting.

---

**Q34.** Many-to-one thread model maps:
- A) Many user threads to one kernel thread
- B) One user thread to many kernel threads
- C) Many kernel threads to one CPU
- D) One process to many threads

**Answer:** ✅ A

**Explanation:** Many user-level threads multiplexed onto single kernel thread.

---

**Q35.** C-SCAN provides:
- A) Non-uniform wait time
- B) More uniform wait time than SCAN
- C) Less throughput than FCFS
- D) Starvation

**Answer:** ✅ B

**Explanation:** C-SCAN moves in one direction only, giving more uniform response time.

---

**Q36.** Locality of reference includes:
- A) Temporal locality
- B) Spatial locality
- C) Both A and B
- D) Neither

**Answer:** ✅ C

**Explanation:** Temporal (recently accessed) and Spatial (nearby addresses).

---

**Q37.** Which is NOT a secondary storage device?
- A) HDD
- B) SSD
- C) Cache
- D) Magnetic tape

**Answer:** ✅ C

**Explanation:** Cache is primary (main) memory, faster than secondary storage.

---

**Q38.** An inode in Unix stores:
- A) File data
- B) File metadata
- C) File name
- D) Directory structure

**Answer:** ✅ B

**Explanation:** Inode stores metadata (permissions, size, timestamps), not file name or data.

---

**Q39.** Thrashing occurs when:
- A) CPU utilization is high
- B) Excessive paging activity
- C) Disk space is full
- D) Network is slow

**Answer:** ✅ B

**Explanation:** Thrashing: system spends more time paging than executing due to insufficient frames.

---

**Q40.** Which algorithm is used for deadlock detection with multiple resource instances?
- A) Banker's Algorithm
- B) Resource Allocation Graph
- C) Wait-for Graph
- D) All of the above

**Answer:** ✅ B

**Explanation:** RAG with multiple instances can detect deadlock. Wait-for graph is for single instances.

---

**Q41.** Virtual memory allows:
- A) Faster execution
- B) Execution of processes larger than physical memory
- C) More CPU cores
- D) Faster disk access

**Answer:** ✅ B

**Explanation:** Virtual memory enables execution of processes larger than available physical memory.

---

**Q42.** Which page replacement algorithm requires future knowledge?
- A) FIFO
- B) LRU
- C) Optimal
- D) Second Chance

**Answer:** ✅ C

**Explanation:** Optimal replaces the page that won't be used for longest time (requires future knowledge).

---

**Q43.** The value of a counting semaphore can be:
- A) Only positive
- B) Only zero
- C) Negative, zero, or positive
- D) Only non-negative

**Answer:** ✅ C

**Explanation:** Negative value indicates number of waiting processes.

---

**Q44.** Which Linux command shows running processes?
- A) ls
- B) ps
- C) df
- D) grep

**Answer:** ✅ B

**Explanation:** ps (process status) shows current processes.

---

**Q45.** Hybrid kernel combines:
- A) Monolithic and Microkernel features
- B) Batch and Time-sharing
- C) Paging and Segmentation
- D) FCFS and RR

**Answer:** ✅ A

**Explanation:** Hybrid kernels (Windows, macOS) combine features of both monolithic and microkernels.

---

**Q46.** In Priority scheduling, if two processes have same priority:
- A) SJF is used
- B) FCFS is used
- C) Round Robin is used
- D) Random selection

**Answer:** ✅ B

**Explanation:** FCFS is typically used as a tie-breaker for same priority.

---

**Q47.** Which is NOT shared between parent and child after fork()?
- A) Code section
- B) Open files
- C) Memory space
- D) Signal handlers

**Answer:** ✅ C

**Explanation:** Child gets a copy of parent's memory space (separate).

---

**Q48.** LOOK disk scheduling differs from SCAN because:
- A) It goes to the end of disk
- B) It only goes as far as last request
- C) It uses circular scan
- D) It has no direction

**Answer:** ✅ B

**Explanation:** LOOK doesn't traverse to disk end, only to last request in that direction.

---

**Q49.** Which RAID level can tolerate 2 disk failures?
- A) RAID 1
- B) RAID 5
- C) RAID 6
- D) RAID 10

**Answer:** ✅ C

**Explanation:** RAID 6 uses double parity, tolerating 2 simultaneous disk failures.

---

**Q50.** The working set model is used to prevent:
- A) Deadlock
- B) Starvation
- C) Thrashing
- D) Fragmentation

**Answer:** ✅ C

**Explanation:** Working set model ensures enough frames are allocated to prevent thrashing.

---

## 📌 CHAPTER 2: DATABASE MANAGEMENT SYSTEMS (DBMS)

### 2.1 Introduction to DBMS

**🔹 Key Concepts:**
- **DBMS**: Software to create, manage, and manipulate databases
- **File System vs DBMS**: DBMS provides data independence, integrity, concurrency control
- **DBA** (Database Administrator): Manages database
- **Data Models**: Hierarchical, Network, Relational, Object-oriented

**🧠 Must-Remember:**
- **Data Independence**: Ability to modify schema without affecting higher levels
  - **Physical**: Change storage without affecting conceptual
  - **Logical**: Change conceptual without affecting external views
- **Three-Schema Architecture**: External → Conceptual → Internal

**⚠️ Trap Concepts:**
- ❌ DBMS eliminates all redundancy → ✅ Minimizes (not eliminates)
- ❌ Data independence means no relationship → ✅ Schema changes don't affect applications

---

### 2.2 Relational Database Concepts

**🔹 Key Concepts:**
- **Relation**: Table (rows=tuples, columns=attributes)
- **Degree**: Number of attributes
- **Cardinality**: Number of tuples
- **Key Types**:
  - **Super Key**: Any set that uniquely identifies tuple
  - **Candidate Key**: Minimal super key
  - **Primary Key**: Selected candidate key (NOT NULL, UNIQUE)
  - **Foreign Key**: References primary key of another relation
  - **Alternate Key**: Candidate keys not chosen as primary

**🧠 Must-Remember:**
- Primary Key **cannot** be NULL
- Foreign Key **can** be NULL
- A relation can have multiple candidate keys but only ONE primary key

**⚠️ Trap Concepts:**
- ❌ Foreign key must be primary key in other table → ✅ Can be any unique key
- ❌ A table can have multiple primary keys → ✅ Only one primary key

**⚡ Memory Trick:**
- Key Hierarchy: **Super → Candidate → Primary** (narrowing down)

---

### 2.3 SQL (Structured Query Language)

**🔹 Key Concepts:**

| Category | Commands | Examples |
|----------|----------|----------|
| **DDL** | Define structure | CREATE, ALTER, DROP, TRUNCATE |
| **DML** | Manipulate data | SELECT, INSERT, UPDATE, DELETE |
| **DCL** | Control access | GRANT, REVOKE |
| **TCL** | Transaction control | COMMIT, ROLLBACK, SAVEPOINT |

**🧠 Must-Remember:**
- `DELETE` vs `TRUNCATE` vs `DROP`:
  - **DELETE**: DML, row-by-row, can rollback, maintains logs
  - **TRUNCATE**: DDL, removes all rows, faster, cannot rollback
  - **DROP**: DDL, removes table structure + data
- **Aggregate Functions**: COUNT, SUM, AVG, MAX, MIN
- `GROUP BY` used with aggregate functions
- `HAVING` filters groups (WHERE filters rows)

**⚠️ Trap Concepts:**
- ❌ TRUNCATE is DML → ✅ DDL (cannot rollback in most DBs)
- ❌ WHERE can use aggregate functions → ✅ Use HAVING for aggregates
- ❌ DELETE removes table structure → ✅ Only TRUNCATE/DROP do

---

### 2.4 Database Design & Normalization

**🔹 Key Concepts:**

| Normal Form | Requirement | Eliminates |
|-------------|-------------|------------|
| **1NF** | Atomic values | Repeating groups |
| **2NF** | 1NF + No partial dependency | Partial dependency |
| **3NF** | 2NF + No transitive dependency | Transitive dependency |
| **BCNF** | 3NF + Every determinant is candidate key | Additional anomalies |

**🧠 Must-Remember:**
- **Functional Dependency**: X → Y (X determines Y)
- **Partial Dependency**: Non-key attribute depends on part of composite key
- **Transitive Dependency**: A → B → C (non-key determines non-key)
- **Lossless Join**: Decomposition doesn't lose information
- **Dependency Preserving**: All FDs maintained after decomposition

**⚠️ Trap Concepts:**
- ❌ BCNF is weaker than 3NF → ✅ BCNF is stricter
- ❌ 3NF always preserves dependencies → ✅ BCNF may not
- ❌ Normalization increases performance → ✅ May decrease (more joins)

**⚡ Memory Trick:**
- Normal Forms: **1-2-3-B** (Atomic → Full Key → Non-Key → Determinant)

---

### 2.5 Indexing & File Organization

**🔹 Key Concepts:**
- **Index**: Data structure to speed up search
- **Types**:
  - **Primary Index**: On ordered key field
  - **Secondary Index**: On non-ordering field
  - **Clustered Index**: Data sorted by index (only ONE per table)
  - **Non-Clustered Index**: Separate structure (multiple allowed)
- **B-Tree**: Balanced tree, used for indexing
- **B+ Tree**: All data in leaves, better for range queries

**🧠 Must-Remember:**
- **Dense Index**: Entry for every search key value
- **Sparse Index**: Entry for some values (requires ordered file)
- **B+ Tree**: Height balanced, all leaves at same level

**⚠️ Trap Concepts:**
- ❌ Multiple clustered indexes allowed → ✅ Only ONE
- ❌ Indexing always speeds up queries → ✅ Slows down INSERT/UPDATE/DELETE

---

### 2.6 Query Processing & Optimization

**🔹 Key Concepts:**
- **Steps**: Parsing → Optimization → Execution
- **Query Tree**: Representation of relational algebra expression
- **Heuristic Optimization**: Apply SELECT early, PROJECT early
- **Cost Estimation**: Disk I/Os, CPU cost, Memory usage

**🧠 Must-Remember:**
- **Selection (σ)**: Filter rows
- **Projection (π)**: Filter columns
- **Join (⋈)**: Combine relations
- **Cartesian Product (×)**: All combinations (expensive)

**⚡ Memory Trick:**
- Optimization: **SPJ** (Select early, Project early, Join last)

---

### 2.7 Transaction Management

**🔹 Key Concepts:**
- **Transaction**: Logical unit of work
- **ACID Properties**:
  - **Atomicity**: All or nothing
  - **Consistency**: Valid state to valid state
  - **Isolation**: Concurrent transactions don't interfere
  - **Durability**: Committed changes persist
- **States**: Active → Partially Committed → Committed/Failed/Aborted

**🧠 Must-Remember:**
- **Serializability**: Concurrent schedule equivalent to some serial schedule
  - **Conflict Serializability**: Swap non-conflicting operations
  - **View Serializability**: Weaker than conflict
- **Precedence Graph**: Cycle = Not conflict serializable
- **Lock Types**: Shared (read), Exclusive (write)
- **2PL** (Two-Phase Locking): Growing phase → Shrinking phase
- **Strict 2PL**: Hold exclusive locks until commit

**⚠️ Trap Concepts:**
- ❌ View serializable = Conflict serializable → ✅ Conflict is stricter
- ❌ 2PL prevents deadlock → ✅ Guarantees serializability (not deadlock-free)

**⚡ Memory Trick:**
- ACID: **A**ll **C**onsistent **I**solated **D**urable

---

### 2.8 NoSQL Databases

**🔹 Key Concepts:**
- **NoSQL**: Not Only SQL, non-relational databases
- **Types**:
  - **Key-Value**: Redis, DynamoDB
  - **Document**: MongoDB, CouchDB
  - **Column-Family**: Cassandra, HBase
  - **Graph**: Neo4j, Amazon Neptune
- **CAP Theorem**: Choose 2 of 3 (Consistency, Availability, Partition Tolerance)

**🧠 Must-Remember:**
- **BASE** properties (vs ACID):
  - **B**asically **A**vailable
  - **S**oft state
  - **E**ventual consistency
- NoSQL: Schema-less, horizontal scaling, high performance

**⚠️ Trap Concepts:**
- ❌ NoSQL has no consistency → ✅ Eventual consistency
- ❌ CAP theorem allows all 3 → ✅ Only 2 simultaneously

---

### 2.9 Big Data & Distributed Databases

**🔹 Key Concepts:**
- **Big Data**: Volume, Velocity, Variety (3Vs)
- **Hadoop**: Distributed processing (MapReduce, HDFS)
- **Distributed DB**: Data stored across multiple locations
- **Replication**: Copy data for availability
- **Fragmentation**: Split data (Horizontal/Vertical)

**🧠 Must-Remember:**
- **MapReduce**: Map (process) → Reduce (aggregate)
- **HDFS**: Hadoop Distributed File System
- **Transparency**: Location, fragmentation, replication transparency

---

### 2.10 Important DBMS Formulas & Concepts

**🧠 Must-Remember:**
- **Number of Super Keys**: If n attributes, max 2^n super keys
- **Candidate Keys from Super Keys**: Minimal super keys only
- **Maximum number of candidate keys**: C(n, n/2) for n attributes

---

## 🧠 CHAPTER 2: DBMS - MCQ BANK (50 Questions)

**Q1.** Which is NOT a characteristic of DBMS?
- A) Data independence
- B) Data redundancy
- C) Data integrity
- D) Concurrency control

**Answer:** ✅ B

**Explanation:** DBMS minimizes redundancy. Data independence, integrity, and concurrency control are DBMS features.

---

**Q2.** A candidate key is:
- A) Any key that uniquely identifies a tuple
- B) Minimal super key
- C) Primary key only
- D) Foreign key

**Answer:** ✅ B

**Explanation:** Candidate key is a minimal super key (no subset can uniquely identify).

---

**Q3.** Which SQL command removes table structure and data?
- A) DELETE
- B) TRUNCATE
- C) DROP
- D) REMOVE

**Answer:** ✅ C

**Explanation:** DROP removes entire table. DELETE removes rows, TRUNCATE removes all rows but keeps structure.

---

**Q4.** In which normal form is a table with no repeating groups?
- A) 1NF
- B) 2NF
- C) 3NF
- D) BCNF

**Answer:** ✅ A

**Explanation:** 1NF eliminates repeating groups (all values atomic).

---

**Q5.** ACID property 'I' stands for:
- A) Integrity
- B) Isolation
- C) Independence
- D) Indexing

**Answer:** ✅ B

**Explanation:** ACID: Atomicity, Consistency, Isolation, Durability.

---

**Q6.** Which index type allows only ONE per table?
- A) Secondary Index
- B) Non-Clustered Index
- C) Clustered Index
- D) All of the above

**Answer:** ✅ C

**Explanation:** Data can be physically sorted in only one way (clustered index).

---

**Q7.** Two-Phase Locking (2PL) ensures:
- A) Deadlock freedom
- B) Serializability
- C) High performance
- D) No locking

**Answer:** ✅ B

**Explanation:** 2PL guarantees serializability but doesn't prevent deadlocks.

---

**Q8.** CAP theorem states you can have only TWO of:
- A) Consistency, Availability, Performance
- B) Consistency, Availability, Partition Tolerance
- C) Concurrency, Availability, Partition Tolerance
- D) Consistency, Atomicity, Partition Tolerance

**Answer:** ✅ B

**Explanation:** CAP: Consistency, Availability, Partition Tolerance (choose 2).

---

**Q9.** Which is a NoSQL database type?
- A) Relational
- B) Document-based
- C) Hierarchical
- D) Network

**Answer:** ✅ B

**Explanation:** Document-based (MongoDB) is NoSQL. Relational, Hierarchical, Network are traditional models.

---

**Q10.** Foreign key can be:
- A) NOT NULL
- B) NULL
- C) Duplicate
- D) Both B and C

**Answer:** ✅ D

**Explanation:** Foreign key can be NULL and can have duplicate values.

---

**Q11.** TRUNCATE is which type of command?
- A) DML
- B) DDL
- C) DCL
- D) TCL

**Answer:** ✅ B

**Explanation:** TRUNCATE is DDL (Data Definition Language), modifies structure.

---

**Q12.** Which is used to filter groups in SQL?
- A) WHERE
- B) HAVING
- C) GROUP BY
- D) ORDER BY

**Answer:** ✅ B

**Explanation:** HAVING filters groups, WHERE filters rows.

---

**Q13.** Transitive dependency is eliminated in:
- A) 1NF
- B) 2NF
- C) 3NF
- D) BCNF

**Answer:** ✅ C

**Explanation:** 3NF removes transitive dependency (non-key → non-key).

---

**Q14.** B+ Tree stores all data in:
- A) Root node
- B) Internal nodes
- C) Leaf nodes
- D) All nodes

**Answer:** ✅ C

**Explanation:** B+ Tree: internal nodes only keys, leaf nodes have data (good for range queries).

---

**Q15.** Which property ensures transaction is all-or-nothing?
- A) Consistency
- B) Atomicity
- C) Isolation
- D) Durability

**Answer:** ✅ B

**Explanation:** Atomicity: transaction either fully completes or has no effect.

---

**Q16.** A schedule is conflict serializable if:
- A) It has no cycles in precedence graph
- B) It has cycles
- C) It's sequential
- D) It uses 2PL

**Answer:** ✅ A

**Explanation:** No cycles in precedence graph = conflict serializable.

---

**Q17.** Which is NOT a big data 'V'?
- A) Volume
- B) Velocity
- C) Variety
- D) Validity

**Answer:** ✅ D

**Explanation:** 3Vs: Volume, Velocity, Variety.

---

**Q18.** Physical data independence allows changing:
- A) Conceptual schema
- B) Internal schema
- C) External schema
- D) Application

**Answer:** ✅ B

**Explanation:** Physical independence: change internal (storage) without affecting conceptual.

---

**Q19.** Which NoSQL database uses key-value pairs?
- A) MongoDB
- B) Redis
- C) Neo4j
- D) Cassandra

**Answer:** ✅ B

**Explanation:** Redis is key-value store. MongoDB is document, Neo4j is graph, Cassandra is column-family.

---

**Q20.** Degree of a relation refers to:
- A) Number of tuples
- B) Number of attributes
- C) Number of keys
- D) Number of indexes

**Answer:** ✅ B

**Explanation:** Degree = number of attributes (columns). Cardinality = number of tuples (rows).

---

**Q21.** Which SQL clause is used with aggregate functions?
- A) WHERE
- B) GROUP BY
- C) ORDER BY
- D) JOIN

**Answer:** ✅ B

**Explanation:** GROUP BY groups rows for aggregate functions (SUM, COUNT, etc.).

---

**Q22.** BCNF is stronger than 3NF because:
- A) It allows more dependencies
- B) Every determinant must be candidate key
- C) It eliminates more anomalies
- D) Both B and C

**Answer:** ✅ D

**Explanation:** BCNF requires every determinant to be candidate key, eliminating more anomalies.

---

**Q23.** MapReduce consists of:
- A) Map and Reduce phases
- B) Sort and Shuffle
- C) Input and Output
- D) Parse and Execute

**Answer:** ✅ A

**Explanation:** MapReduce: Map (process key-value pairs) → Reduce (aggregate results).

---

**Q24.** Shared lock allows:
- A) Read only
- B) Write only
- C) Read and Write
- D) Delete

**Answer:** ✅ A

**Explanation:** Shared lock (S-lock) allows reading. Exclusive lock (X-lock) allows writing.

---

**Q25.** Which command is used to give access privileges?
- A) REVOKE
- B) GRANT
- C) COMMIT
- D) ROLLBACK

**Answer:** ✅ B

**Explanation:** GRANT gives privileges, REVOKE removes them (DCL commands).

---

**Q26.** Lossless join decomposition ensures:
- A) No data loss
- B) Faster queries
- C) Less storage
- D) No redundancy

**Answer:** ✅ A

**Explanation:** Lossless join: original relation can be reconstructed from decomposed relations.

---

**Q27.** Which tree is most commonly used for database indexing?
- A) Binary Tree
- B) BST
- C) B+ Tree
- D) AVL Tree

**Answer:** ✅ C

**Explanation:** B+ Tree: balanced, all leaves at same level, excellent for range queries and disk storage.

---

**Q28.** Eventual consistency is a property of:
- A) ACID databases
- B) NoSQL databases
- C) Relational databases
- D) All databases

**Answer:** ✅ B

**Explanation:** NoSQL uses BASE properties with eventual consistency.

---

**Q29.** Cardinality of a relation is:
- A) Number of attributes
- B) Number of tuples
- C) Number of keys
- D) Degree

**Answer:** ✅ B

**Explanation:** Cardinality = number of rows (tuples). Degree = number of columns (attributes).

---

**Q30.** Which is NOT a transaction state?
- A) Active
- B) Partially Committed
- C) Compensated
- D) Failed

**Answer:** ✅ C

**Explanation:** States: Active → Partially Committed → Committed/Failed/Aborted.

---

**Q31.** Partial dependency occurs in:
- A) 1NF
- B) 2NF
- C) 3NF
- D) BCNF

**Answer:** ✅ B

**Explanation:** 2NF eliminates partial dependency (non-key depends on part of composite key).

---

**Q32.** HDFS stands for:
- A) High Distributed File System
- B) Hadoop Distributed File System
- C) Hierarchical Data File System
- D) Hybrid Distributed File System

**Answer:** ✅ B

**Explanation:** HDFS is Hadoop's distributed file system.

---

**Q33.** Which SQL command is used to modify existing data?
- A) INSERT
- B) UPDATE
- C) ALTER
- D) MODIFY

**Answer:** ✅ B

**Explanation:** UPDATE modifies existing rows. ALTER modifies table structure.

---

**Q34.** Dense index has:
- A) One entry per block
- B) One entry per search key value
- C) One entry per page
- D) Sparse entries

**Answer:** ✅ B

**Explanation:** Dense index: index entry for every search key value.

---

**Q35.** View serializability is:
- A) Stronger than conflict serializability
- B) Weaker than conflict serializability
- C) Same as conflict serializability
- D) Unrelated

**Answer:** ✅ B

**Explanation:** All conflict serializable schedules are view serializable, but not vice versa.

---

**Q36.** Which is an aggregate function?
- A) SELECT
- B) COUNT
- C) WHERE
- D) FROM

**Answer:** ✅ B

**Explanation:** COUNT, SUM, AVG, MAX, MIN are aggregate functions.

---

**Q37.** Horizontal fragmentation splits:
- A) Columns
- B) Rows
- C) Both
- D) Neither

**Answer:** ✅ B

**Explanation:** Horizontal: split by rows. Vertical: split by columns.

---

**Q38.** A primary key must be:
- A) NULL
- B) UNIQUE and NOT NULL
- C) Duplicate allowed
- D) Foreign

**Answer:** ✅ B

**Explanation:** Primary key: UNIQUE (no duplicates) and NOT NULL.

---

**Q39.** COMMIT is which type of command?
- A) DDL
- B) DML
- C) TCL
- D) DCL

**Answer:** ✅ C

**Explanation:** COMMIT, ROLLBACK, SAVEPOINT are TCL (Transaction Control Language).

---

**Q40.** Cassandra is which type of NoSQL database?
- A) Key-Value
- B) Document
- C) Column-Family
- D) Graph

**Answer:** ✅ C

**Explanation:** Cassandra is column-family store. Redis=key-value, MongoDB=document, Neo4j=graph.

---

**Q41.** Which is true about 3NF?
- A) Always lossless
- B) Always dependency preserving
- C) Both A and B
- D) Neither

**Answer:** ✅ C

**Explanation:** 3NF decomposition is always lossless and dependency preserving.

---

**Q42.** Neo4j is a:
- A) Relational database
- B) Document database
- C) Graph database
- D) Key-value store

**Answer:** ✅ C

**Explanation:** Neo4j is a graph database (nodes, edges, properties).

---

**Q43.** Super key can have how many attributes?
- A) 1 only
- B) 2 only
- C) 1 to n
- D) n only

**Answer:** ✅ C

**Explanation:** Super key can have 1 to n attributes (any set that uniquely identifies).

---

**Q44.** Strict 2PL holds locks until:
- A) Operation completes
- B) Transaction commits
- C) Shrinking phase starts
- D) Deadlock detected

**Answer:** ✅ B

**Explanation:** Strict 2PL: hold exclusive locks until transaction commits/aborts.

---

**Q45.** Which optimization heuristic is applied first?
- A) PROJECT early
- B) SELECT early
- C) JOIN early
- D) SORT early

**Answer:** ✅ B

**Explanation:** SELECT (σ) applied first to reduce rows early.

---

**Q46.** Secondary index is created on:
- A) Primary key
- B) Ordering field
- C) Non-ordering field
- D) Foreign key only

**Answer:** ✅ C

**Explanation:** Secondary index on non-ordering field (unordered).

---

**Q47.** BASE property 'E' stands for:
- A) Efficient
- B) Eventual consistency
- C) Effective
- D) Encrypted

**Answer:** ✅ B

**Explanation:** BASE: Basically Available, Soft state, Eventual consistency.

---

**Q48.** DELETE command can be rolled back because it's:
- A) DDL
- B) DML
- C) DCL
- D) TCL

**Answer:** ✅ B

**Explanation:** DELETE is DML (logged, can rollback). TRUNCATE is DDL (usually can't rollback).

---

**Q49.** Maximum super keys for relation with n attributes:
- A) n
- B) 2^n
- C) n^2
- D) n!

**Answer:** ✅ B

**Explanation:** Maximum 2^n super keys (all subsets if all attributes unique).

---

**Q50.** Which transparency hides data location?
- A) Fragmentation transparency
- B) Replication transparency
- C) Location transparency
- D) All of the above

**Answer:** ✅ C

**Explanation:** Location transparency: user doesn't need to know where data is stored.

---

## 📌 CHAPTER 3: COMPUTER NETWORKS

### 3.1 OSI Model (7 Layers)

**🔹 Key Concepts:**

| Layer | Number | Function | Protocols |
|-------|--------|----------|----------|
| **Application** | 7 | User interface | HTTP, FTP, SMTP, DNS |
| **Presentation** | 6 | Translation, encryption | SSL, JPEG, MPEG |
| **Session** | 5 | Dialog control | NetBIOS, RPC |
| **Transport** | 4 | End-to-end delivery | TCP, UDP |
| **Network** | 3 | Routing | IP, ICMP, ARP |
| **Data Link** | 2 | Node-to-node | Ethernet, PPP |
| **Physical** | 1 | Bit transmission | Cables, Hubs |

**🧠 Must-Remember:**
- **Mnemonic**: **A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing (Top to Bottom)
- **PDU** (Protocol Data Unit):
  - Application/Presentation/Session: **Data**
  - Transport: **Segment** (TCP) / **Datagram** (UDP)
  - Network: **Packet**
  - Data Link: **Frame**
  - Physical: **Bits**

**⚠️ Trap Concepts:**
- ❌ TCP is at Network layer → ✅ Transport layer
- ❌ IP is at Transport layer → ✅ Network layer

---

### 3.2 TCP/IP Protocol Suite

**🔹 Key Concepts:**
- **4 Layers**: Application, Transport, Internet, Network Access
- **TCP**: Connection-oriented, reliable, 3-way handshake
- **UDP**: Connectionless, unreliable, faster
- **3-Way Handshake**: SYN → SYN-ACK → ACK

**🧠 Must-Remember:**
- **TCP Header**: 20 bytes minimum
- **UDP Header**: 8 bytes (simpler)
- **TCP** used for: HTTP, FTP, SMTP (need reliability)
- **UDP** used for: DNS, VoIP, Streaming (need speed)

**⚠️ Trap Concepts:**
- ❌ UDP is reliable → ✅ Unreliable (no ACK)
- ❌ TCP is faster → ✅ UDP faster (less overhead)

---

### 3.3 Data Link Layer

**🔹 Key Concepts:**
- **Framing**: Dividing bit stream into frames
- **Error Detection**: Parity, CRC, Checksum
- **Flow Control**: Stop-and-Wait, Sliding Window
- **MAC Address**: 48-bit physical address
- **CSMA/CD**: Ethernet (detect collisions)
- **CSMA/CA**: WiFi (avoid collisions)

**🧠 Must-Remember:**
- **Stop-and-Wait**: Send 1 frame, wait for ACK
- **Sliding Window**: Send multiple frames (window size)
- **Efficiency** (Stop-and-Wait): η = 1 / (1 + 2a) where a = Propagation/Transmission

**⚠️ Trap Concepts:**
- ❌ CSMA/CD used in WiFi → ✅ CSMA/CA
- ❌ MAC address is 32-bit → ✅ 48-bit (6 bytes)

---

### 3.4 Network Layer

**🔹 Key Concepts:**
- **IP Address**: 32-bit (IPv4), 128-bit (IPv6)
- **Subnetting**: Dividing network into subnets
- **Routing Algorithms**: Distance Vector, Link State
- **ICMP**: Error reporting (ping uses ICMP)
- **ARP**: IP → MAC mapping
- **NAT**: Private → Public IP conversion

**🧠 Must-Remember:**
- **Class A**: 0-127 (large networks)
- **Class B**: 128-191 (medium)
- **Class C**: 192-223 (small)
- **Subnet Mask**: Identifies network vs host portion
- **Default Gateway**: Router IP for external communication

**⚡ Memory Trick:**
- Classes: **A-B-C** (0-128-192 boundaries)

---

### 3.5 Transport Layer

**🔹 Key Concepts:**
- **Port Numbers**: 0-65535
  - **Well-known**: 0-1023
  - **Registered**: 1024-49151
  - **Dynamic**: 49152-65535
- **Common Ports**: HTTP=80, HTTPS=443, FTP=21, SSH=22, DNS=53, SMTP=25

**🧠 Must-Remember:**
- **Multiplexing**: Multiple processes share network
- **Demultiplexing**: Deliver to correct process
- **Flow Control**: Window-based (TCP)
- **Congestion Control**: Slow start, Congestion avoidance

**⚠️ Trap Concepts:**
- ❌ Port numbers are 32-bit → ✅ 16-bit (0-65535)
- ❌ HTTPS uses port 80 → ✅ Port 443

---

### 3.6 Application Layer

**🔹 Key Concepts:**

| Protocol | Port | Purpose |
|----------|------|--------|
| **HTTP** | 80 | Web browsing |
| **HTTPS** | 443 | Secure web |
| **FTP** | 21 | File transfer |
| **SMTP** | 25 | Email sending |
| **DNS** | 53 | Domain name resolution |
| **DHCP** | 67/68 | IP assignment |
| **SSH** | 22 | Secure shell |

**🧠 Must-Remember:**
- **DNS**: Hierarchical naming system (Domain → IP)
- **DHCP**: Dynamic Host Configuration Protocol (auto IP)
- **HTTP**: Stateless protocol

---

### 3.7 Network Security

**🔹 Key Concepts:**
- **Symmetric Key**: Same key for encryption/decryption (AES, DES)
- **Asymmetric Key**: Public + Private key (RSA)
- **Firewall**: Filters network traffic
- **VPN**: Virtual Private Network (encrypted tunnel)
- **SSL/TLS**: Secure communication

**🧠 Must-Remember:**
- **Confidentiality**: Only authorized access
- **Integrity**: Data not modified
- **Authentication**: Verify identity
- **Non-repudiation**: Cannot deny action

---

### 3.8 Network Performance

**🧠 Must-Remember Formulas:**
- **Bandwidth**: Data rate (bps)
- **Latency**: Delay (propagation + transmission + queuing + processing)
- **Bandwidth-Delay Product**: Bandwidth × RTT
- **Throughput**: Actual data transfer rate
- **Utilization**: Bandwidth used / Total bandwidth

**⚡ Memory Trick:**
- Delays: **P-T-Q-P** (Propagation, Transmission, Queuing, Processing)

---

## 🧠 CHAPTER 3: NETWORKS - MCQ BANK (50 Questions)

**Q1.** How many layers are in the OSI model?
- A) 4
- B) 5
- C) 6
- D) 7

**Answer:** ✅ D

**Explanation:** OSI has 7 layers: Application, Presentation, Session, Transport, Network, Data Link, Physical.

---

**Q2.** TCP is:
- A) Connectionless
- B) Connection-oriented
- C) Unreliable
- D) Faster than UDP

**Answer:** ✅ B

**Explanation:** TCP is connection-oriented (3-way handshake), reliable.

---

**Q3.** Which layer handles routing?
- A) Transport
- B) Network
- C) Data Link
- D) Application

**Answer:** ✅ B

**Explanation:** Network layer (Layer 3) handles routing and logical addressing (IP).

---

**Q4.** MAC address is how many bits?
- A) 32
- B) 48
- C) 64
- D) 128

**Answer:** ✅ B

**Explanation:** MAC address is 48 bits (6 bytes), burned into NIC.

---

**Q5.** HTTP uses which port?
- A) 21
- B) 25
- C) 80
- D) 443

**Answer:** ✅ C

**Explanation:** HTTP=80, HTTPS=443, FTP=21, SMTP=25.

---

**Q6.** UDP header size is:
- A) 8 bytes
- B) 20 bytes
- C) 32 bytes
- D) 64 bytes

**Answer:** ✅ A

**Explanation:** UDP header: 8 bytes (simpler than TCP's 20 bytes).

---

**Q7.** CSMA/CD is used in:
- A) WiFi
- B) Ethernet
- C) Bluetooth
- D) Satellite

**Answer:** ✅ B

**Explanation:** CSMA/CD (Collision Detection) for Ethernet. CSMA/CA (Collision Avoidance) for WiFi.

---

**Q8.** DNS resolves:
- A) MAC to IP
- B) IP to MAC
- C) Domain name to IP
- D) Port to IP

**Answer:** ✅ C

**Explanation:** DNS converts domain names (www.google.com) to IP addresses.

---

**Q9.** Which is NOT a network layer protocol?
- A) IP
- B) ICMP
- C) TCP
- D) ARP

**Answer:** ✅ C

**Explanation:** TCP is transport layer. IP, ICMP, ARP are network layer.

---

**Q10.** 3-way handshake is used in:
- A) UDP
- B) TCP
- C) IP
- D) ICMP

**Answer:** ✅ B

**Explanation:** TCP uses SYN → SYN-ACK → ACK for connection establishment.

---

**Q11.** SSL operates at which layer?
- A) Network
- B) Transport
- C) Presentation
- D) Session

**Answer:** ✅ C

**Explanation:** SSL/TLS provides encryption at Presentation layer (Layer 6).

---

**Q12.** Which protocol is connectionless?
- A) TCP
- B) UDP
- C) Both
- D) Neither

**Answer:** ✅ B

**Explanation:** UDP is connectionless (no handshake, no ACK).

---

**Q13.** IPv6 address size is:
- A) 32 bits
- B) 64 bits
- C) 128 bits
- D) 256 bits

**Answer:** ✅ C

**Explanation:** IPv4=32 bits, IPv6=128 bits.

---

**Q14.** Firewall is used for:
- A) Speed up network
- B) Filter traffic
- C) Assign IPs
- D) Routing

**Answer:** ✅ B

**Explanation:** Firewall filters incoming/outgoing traffic based on rules.

---

**Q15.** ARP converts:
- A) Domain to IP
- B) IP to MAC
- C) MAC to IP
- D) Port to IP

**Answer:** ✅ B

**Explanation:** ARP (Address Resolution Protocol): IP → MAC address.

---

**Q16.** Class C IP range is:
- A) 0-127
- B) 128-191
- C) 192-223
- D) 224-239

**Answer:** ✅ C

**Explanation:** Class A: 0-127, B: 128-191, C: 192-223.

---

**Q17.** Which protocol assigns IP addresses dynamically?
- A) DNS
- B) DHCP
- C) FTP
- D) HTTP

**Answer:** ✅ B

**Explanation:** DHCP (Dynamic Host Configuration Protocol) auto-assigns IPs.

---

**Q18.** Port numbers are how many bits?
- A) 8
- B) 16
- C) 32
- D) 64

**Answer:** ✅ B

**Explanation:** 16-bit port numbers (0-65535).

---

**Q19.** Symmetric encryption uses:
- A) Different keys
- B) Same key
- C) No key
- D) Public key only

**Answer:** ✅ B

**Explanation:** Symmetric: same key for encryption and decryption (AES, DES).

---

**Q20.** HTTPS uses port:
- A) 80
- B) 443
- C) 8080
- D) 21

**Answer:** ✅ B

**Explanation:** HTTPS (secure HTTP) uses port 443.

---

**Q21.** Ping uses which protocol?
- A) TCP
- B) UDP
- C) ICMP
- D) ARP

**Answer:** ✅ C

**Explanation:** Ping uses ICMP (Internet Control Message Protocol).

---

**Q22.** Which layer provides end-to-end delivery?
- A) Network
- B) Transport
- C) Data Link
- D) Physical

**Answer:** ✅ B

**Explanation:** Transport layer (Layer 4) provides end-to-end communication.

---

**Q23.** RSA is which type of encryption?
- A) Symmetric
- B) Asymmetric
- C) Hash
- D) None

**Answer:** ✅ B

**Explanation:** RSA uses public + private key pair (asymmetric).

---

**Q24.** Subnet mask is used to:
- A) Encrypt data
- B) Identify network portion
- C) Route packets
- D) Compress data

**Answer:** ✅ B

**Explanation:** Subnet mask separates network bits from host bits.

---

**Q25.** NAT stands for:
- A) Network Address Translation
- B) Network Access Terminal
- C) New Address Transfer
- D) Network Auto Transfer

**Answer:** ✅ A

**Explanation:** NAT converts private IPs to public IPs.

---

**Q26.** Well-known ports range:
- A) 0-1023
- B) 1024-49151
- C) 49152-65535
- D) 0-65535

**Answer:** ✅ A

**Explanation:** Well-known: 0-1023, Registered: 1024-49151, Dynamic: 49152-65535.

---

**Q27.** Which is used for email sending?
- A) FTP
- B) SMTP
- C) HTTP
- D) DNS

**Answer:** ✅ B

**Explanation:** SMTP (Simple Mail Transfer Protocol) sends emails.

---

**Q28.** VPN provides:
- A) Faster internet
- B) Encrypted tunnel
- C) More bandwidth
- D) Free access

**Answer:** ✅ B

**Explanation:** VPN creates secure encrypted tunnel over public network.

---

**Q29.** Stop-and-Wait protocol sends:
- A) Multiple frames
- B) One frame at a time
- C) No frames
- D) Unlimited frames

**Answer:** ✅ B

**Explanation:** Stop-and-Wait: send one frame, wait for ACK before next.

---

**Q30.** Which is NOT a characteristic of HTTP?
- A) Stateless
- B) Connectionless
- C) Reliable
- D) Application layer

**Answer:** ✅ C

**Explanation:** HTTP is stateless and unreliable (uses TCP for reliability below).

---

**Q31.** Bandwidth-delay product equals:
- A) Bandwidth + Delay
- B) Bandwidth × RTT
- C) Bandwidth / Delay
- D) Delay / Bandwidth

**Answer:** ✅ B

**Explanation:** BDP = Bandwidth × Round Trip Time.

---

**Q32.** Which layer handles encryption?
- A) Session
- B) Presentation
- C) Application
- D) Transport

**Answer:** ✅ B

**Explanation:** Presentation layer (Layer 6) handles encryption, compression, translation.

---

**Q33.** TCP header minimum size:
- A) 8 bytes
- B) 20 bytes
- C) 32 bytes
- D) 64 bytes

**Answer:** ✅ B

**Explanation:** TCP header: 20 bytes minimum (can be more with options).

---

**Q34.** Which protocol is used for file transfer?
- A) SMTP
- B) FTP
- C) HTTP
- D) DNS

**Answer:** ✅ B

**Explanation:** FTP (File Transfer Protocol) transfers files.

---

**Q35.** CRC is used for:
- A) Encryption
- B) Error detection
- C) Compression
- D) Routing

**Answer:** ✅ B

**Explanation:** CRC (Cyclic Redundancy Check) detects errors in frames.

---

**Q36.** Link State routing is used in:
- A) RIP
- B) OSPF
- C) BGP
- D) FTP

**Answer:** ✅ B

**Explanation:** OSPF uses Link State. RIP uses Distance Vector.

---

**Q37.** SSH uses port:
- A) 21
- B) 22
- C) 23
- D) 25

**Answer:** ✅ B

**Explanation:** SSH=22, FTP=21, Telnet=23, SMTP=25.

---

**Q38.** Which is NOT a security property?
- A) Confidentiality
- B) Integrity
- C) Availability
- D) Bandwidth

**Answer:** ✅ D

**Explanation:** CIA triad: Confidentiality, Integrity, Availability.

---

**Q39.** Datagram is PDU of:
- A) TCP
- B) UDP
- C) IP
- D) HTTP

**Answer:** ✅ B

**Explanation:** UDP uses datagrams. TCP uses segments.

---

**Q40.** Which device operates at Physical layer?
- A) Router
- B) Switch
- C) Hub
- D) Bridge

**Answer:** ✅ C

**Explanation:** Hub (Layer 1). Switch/Bridge (Layer 2). Router (Layer 3).

---

**Q41.** Flow control prevents:
- A) Deadlock
- B) Overflow at receiver
- C) Collisions
- D) Routing loops

**Answer:** ✅ B

**Explanation:** Flow control: sender doesn't overwhelm receiver.

---

**Q42.** Which uses CSMA/CA?
- A) Ethernet
- B) WiFi
- C) Token Ring
- D) PPP

**Answer:** ✅ B

**Explanation:** WiFi uses CSMA/CA (Collision Avoidance).

---

**Q43.** Fragmentation occurs at which layer?
- A) Transport
- B) Network
- C) Data Link
- D) Physical

**Answer:** ✅ B

**Explanation:** Network layer fragments packets if larger than MTU.

---

**Q44.** Quadruple for socket address:
- A) IP only
- B) IP + Port
- C) Source IP + Source Port + Dest IP + Dest Port
- D) MAC + IP

**Answer:** ✅ C

**Explanation:** Socket identified by 4-tuple: source/dest IP and ports.

---

**Q45.** Which protocol ensures data integrity?
- A) IP
- B) TCP
- C) UDP
- D) ICMP

**Answer:** ✅ B

**Explanation:** TCP provides reliability, error checking, acknowledgment.

---

**Q46.** Traceroute uses:
- A) TCP
- B) UDP
- C) ICMP
- D) ARP

**Answer:** ✅ C

**Explanation:** Traceroute uses ICMP to track route to destination.

---

**Q47.** Private IP address ranges:
- A) 10.x.x.x
- B) 172.16.x.x
- C) 192.168.x.x
- D) All of the above

**Answer:** ✅ D

**Explanation:** All are private ranges (not routable on internet).

---

**Q48.** Which layer establishes session?
- A) Transport
- B) Session
- C) Application
- D) Network

**Answer:** ✅ B

**Explanation:** Session layer (Layer 5) manages dialog/session.

---

**Q49.** MTU stands for:
- A) Maximum Transfer Unit
- B) Maximum Transmission Unit
- C) Minimum Transfer Unit
- D) Medium Transmission Unit

**Answer:** ✅ B

**Explanation:** MTU: Maximum Transmission Unit (max packet size).

---

**Q50.** Which is fastest for error recovery?
- A) Stop-and-Wait
- B) Go-Back-N
- C) Selective Repeat
- D) All equal

**Answer:** ✅ C

**Explanation:** Selective Repeat retransmits only lost frames (most efficient).

---

## 📌 CHAPTER 4: OBJECT-ORIENTED PROGRAMMING (OOP)

### 4.1 OOP Principles

**🔹 Key Concepts:**
- **4 Pillars**: Encapsulation, Inheritance, Polymorphism, Abstraction
- **Class**: Blueprint/template
- **Object**: Instance of class
- **Constructor**: Initializes object (same name as class)
- **Destructor**: Cleans up object

**🧠 Must-Remember:**
- **Encapsulation**: Binding data + methods together
- **Abstraction**: Hiding complexity, showing essentials
- **Polymorphism**: Many forms (compile-time + runtime)
- **Inheritance**: Code reusability

---

### 4.2 Inheritance

**🔹 Key Concepts:**

| Type | Description |
|------|------------|
| **Single** | One child, one parent |
| **Multiple** | One child, multiple parents |
| **Multilevel** | Chain inheritance |
| **Hierarchical** | Multiple children, one parent |
| **Hybrid** | Combination |

**🧠 Must-Remember:**
- **Access Modifiers**: private, protected, public
- **private**: Not inherited
- **protected**: Inherited but not accessible outside
- **public**: Fully accessible
- **Constructor** executes: Parent → Child
- **Destructor** executes: Child → Parent

**⚠️ Trap Concepts:**
- ❌ Private members are inherited → ✅ Inherited but NOT accessible
- ❌ Multiple inheritance supported in Java → ✅ Only through interfaces

---

### 4.3 Polymorphism

**🔹 Key Concepts:**
- **Compile-time**: Method overloading, Operator overloading
- **Runtime**: Method overriding, Virtual functions
- **Overloading**: Same name, different parameters
- **Overriding**: Same name, same parameters (parent vs child)

**🧠 Must-Remember:**
- **Virtual function**: Enables runtime polymorphism
- **Pure virtual function**: `virtual void f() = 0;` (abstract class)
- **Function signature**: Name + parameter types (not return type)

**⚠️ Trap Concepts:**
- ❌ Overloading is runtime → ✅ Compile-time
- ❌ Overriding changes signature → ✅ Must match exactly

---

### 4.4 Encapsulation & Abstraction

**🔹 Key Concepts:**
- **Encapsulation**: Data hiding (private members + public getters/setters)
- **Abstraction**: Abstract classes, Interfaces
- **Information Hiding**: Implementation details hidden

**🧠 Must-Remember:**
- Encapsulation = Data hiding + Bundling
- Abstraction = Hiding complexity
- Getters/Setters control access

---

### 4.5 Interfaces & Abstract Classes

**🔹 Key Concepts:**

| Feature | Abstract Class | Interface |
|---------|---------------|-----------|
| **Methods** | Can have both abstract & concrete | All abstract (Java 8+) |
| **Variables** | Any type | Final, static |
| **Inheritance** | Single | Multiple |
| **Constructor** | Yes | No |
| **Access** | Any | Public only |

**🧠 Must-Remember:**
- Cannot instantiate abstract class or interface
- Abstract class: "is-a" relationship
- Interface: "can-do" relationship

**⚠️ Trap Concepts:**
- ❌ Interface can have constructors → ✅ No constructors
- ❌ Abstract class must have all abstract methods → ✅ Can have concrete methods

---

### 4.6 Exception Handling

**🔹 Key Concepts:**
- **try**: Code that may throw exception
- **catch**: Handle exception
- **finally**: Always executes
- **throw**: Manually throw exception
- **throws**: Declare exception in method signature

**🧠 Must-Remember:**
- **Checked exceptions**: Compile-time (IOException, SQLException)
- **Unchecked exceptions**: Runtime (NullPointerException, ArrayIndexOutOfBounds)
- **finally** block executes even if return in try/catch

**⚠️ Trap Concepts:**
- ❌ finally doesn't execute if exception occurs → ✅ Always executes
- ❌ catch block mandatory → ✅ Can have try-finally only

---

### 4.7 Design Patterns

**🔹 Key Concepts:**
- **Creational**: Singleton, Factory, Abstract Factory, Builder
- **Structural**: Adapter, Decorator, Facade, Proxy
- **Behavioral**: Observer, Strategy, Command, Iterator

**🧠 Must-Remember:**
- **Singleton**: Only one instance (private constructor, static method)
- **Factory**: Creates objects without specifying class
- **Observer**: One-to-many dependency (publish-subscribe)

---

### 4.8 OOAD & Best Practices

**🔹 Key Concepts:**
- **SOLID Principles**:
  - **S**ingle Responsibility
  - **O**pen-Closed
  - **L**iskov Substitution
  - **I**nterface Segregation
  - **D**ependency Inversion
- **DRY**: Don't Repeat Yourself
- **KISS**: Keep It Simple

**🧠 Must-Remember:**
- **Cohesion**: How related responsibilities are (HIGH is good)
- **Coupling**: Dependency between classes (LOW is good)

**⚡ Memory Trick:**
- SOLID: **S-O-L-I-D** (5 principles)

---

## 🧠 CHAPTER 4: OOP - MCQ BANK (50 Questions)

**Q1.** Which is NOT an OOP pillar?
- A) Encapsulation
- B) Inheritance
- C) Compilation
- D) Polymorphism

**Answer:** ✅ C

**Explanation:** 4 pillars: Encapsulation, Inheritance, Polymorphism, Abstraction.

---

**Q2.** Constructor is called:
- A) When object is created
- B) When object is destroyed
- C) Manually
- D) At program end

**Answer:** ✅ A

**Explanation:** Constructor initializes object, called automatically on creation.

---

**Q3.** Method overloading is:
- A) Runtime polymorphism
- B) Compile-time polymorphism
- C) Not polymorphism
- D) Inheritance

**Answer:** ✅ B

**Explanation:** Overloading resolved at compile-time based on parameters.

---

**Q4.** Which access modifier allows inheritance but not outside access?
- A) private
- B) protected
- C) public
- D) default

**Answer:** ✅ B

**Explanation:** protected: accessible in subclass, not outside package/class.

---

**Q5.** Abstract class can have:
- A) Only abstract methods
- B) Only concrete methods
- C) Both
- D) Neither

**Answer:** ✅ C

**Explanation:** Abstract class can have both abstract and concrete methods.

---

**Q6.** Interface variables are:
- A) Private
- B) Protected
- C) Final and static
- D) Volatile

**Answer:** ✅ C

**Explanation:** Interface variables are implicitly final and static (constants).

---

**Q7.** Which block always executes in exception handling?
- A) try
- B) catch
- C) finally
- D) throw

**Answer:** ✅ C

**Explanation:** finally executes regardless of exception occurrence.

---

**Q8.** Singleton pattern ensures:
- A) Multiple instances
- B) One instance
- C) No instance
- D) Dynamic instances

**Answer:** ✅ B

**Explanation:** Singleton restricts to one instance (private constructor, static method).

---

**Q9.** Method overriding requires:
- A) Different name
- B) Same signature
- C) Different parameters
- D) Different return type

**Answer:** ✅ B

**Explanation:** Overriding: same name, same parameters in parent and child.

---

**Q10.** Virtual functions enable:
- A) Compile-time polymorphism
- B) Runtime polymorphism
- C) Overloading
- D) Encapsulation

**Answer:** ✅ B

**Explanation:** Virtual functions resolved at runtime (late binding).

---

**Q11.** Which is an unchecked exception?
- A) IOException
- B) SQLException
- C) NullPointerException
- D) ClassNotFoundException

**Answer:** ✅ C

**Explanation:** NullPointerException is runtime (unchecked). Others are checked.

---

**Q12.** Multiple inheritance is supported in Java through:
- A) Classes
- B) Interfaces
- C) Both
- D) Neither

**Answer:** ✅ B

**Explanation:** Java supports multiple inheritance only via interfaces.

---

**Q13.** Encapsulation means:
- A) Data hiding
- B) Data hiding + bundling
- C) Inheritance
- D) Polymorphism

**Answer:** ✅ B

**Explanation:** Encapsulation: bundling data + methods, hiding internals.

---

**Q14.** Pure virtual function syntax in C++:
- A) virtual void f() {}
- B) virtual void f() = 0;
- C) void f() = 0;
- D) abstract void f();

**Answer:** ✅ B

**Explanation:** = 0 makes it pure virtual (must override in derived class).

---

**Q15.** Destructor executes in order:
- A) Parent to Child
- B) Child to Parent
- C) Random
- D) Simultaneous

**Answer:** ✅ B

**Explanation:** Destructor: Child first, then Parent (reverse of constructor).

---

**Q16.** Which design pattern is creational?
- A) Observer
- B) Singleton
- C) Adapter
- D) Strategy

**Answer:** ✅ B

**Explanation:** Singleton is creational. Observer/Strategy=behavioral, Adapter=structural.

---

**Q17.** 'S' in SOLID stands for:
- A) Simple Responsibility
- B) Single Responsibility
- C) Static Responsibility
- D) Secure Responsibility

**Answer:** ✅ B

**Explanation:** Single Responsibility Principle: one class, one reason to change.

---

**Q18.** High cohesion is:
- A) Good
- B) Bad
- C) Neutral
- D) Irrelevant

**Answer:** ✅ A

**Explanation:** High cohesion = related functionality together (desirable).

---

**Q19.** Function overloading is differentiated by:
- A) Return type
- B) Parameter types
- C) Function name
- D) Access modifier

**Answer:** ✅ B

**Explanation:** Overloading: same name, different parameter types/count.

---

**Q20.** Which cannot be instantiated?
- A) Concrete class
- B) Abstract class
- C) Both
- D) Neither

**Answer:** ✅ B

**Explanation:** Abstract classes cannot be instantiated (only subclassed).

---

**Q21.** throws keyword is used for:
- A) Throwing exception
- B) Declaring exception
- C) Catching exception
- D) Handling exception

**Answer:** ✅ B

**Explanation:** throws declares exception in method signature. throw actually throws.

---

**Q22.** Observer pattern implements:
- A) One-to-one
- B) One-to-many
- C) Many-to-many
- D) None

**Answer:** ✅ B

**Explanation:** Observer: one subject, multiple observers (publish-subscribe).

---

**Q23.** Polymorphism means:
- A) One form
- B) Many forms
- C) No form
- D) Hidden form

**Answer:** ✅ B

**Explanation:** Poly (many) + morph (form) = many forms.

---

**Q24.** In inheritance, constructor order is:
- A) Child to Parent
- B) Parent to Child
- C) Random
- D) Simultaneous

**Answer:** ✅ B

**Explanation:** Parent constructor executes first, then child.

---

**Q25.** Which is NOT a design pattern category?
- A) Creational
- B) Structural
- C) Behavioral
- D) Functional

**Answer:** ✅ D

**Explanation:** 3 categories: Creational, Structural, Behavioral.

---

**Q26.** Abstract class represents:
- A) can-do relationship
- B) is-a relationship
- C) has-a relationship
- D) uses-a relationship

**Answer:** ✅ B

**Explanation:** Abstract class: is-a (specialization). Interface: can-do (capability).

---

**Q27.** Low coupling is:
- A) Good
- B) Bad
- C) Neutral
- D) Irrelevant

**Answer:** ✅ A

**Explanation:** Low coupling = less dependency between classes (desirable).

---

**Q28.** Which exception must be declared or caught?
- A) Unchecked
- B) Checked
- C) Error
- D) Runtime

**Answer:** ✅ B

**Explanation:** Checked exceptions require try-catch or throws declaration.

---

**Q29.** Factory pattern is used to:
- A) Create single instance
- B) Create objects without specifying class
- C) Observe changes
- D) Adapt interfaces

**Answer:** ✅ B

**Explanation:** Factory: creates objects via common interface.

---

**Q30.** DRY principle means:
- A) Do Repeat Yourself
- B) Don't Repeat Yourself
- C) Data Reusability
- D) Dynamic Run Yield

**Answer:** ✅ B

**Explanation:** DRY: Don't Repeat Yourself (avoid duplication).

---

**Q31.** Private members in parent class:
- A) Not inherited
- B) Inherited and accessible
- C) Inherited but not accessible
- D) Deleted

**Answer:** ✅ C

**Explanation:** Private members inherited but NOT directly accessible in child.

---

**Q32.** Operator overloading is:
- A) Runtime polymorphism
- B) Compile-time polymorphism
- C) Not polymorphism
- D) Encapsulation

**Answer:** ✅ B

**Explanation:** Operator overloading resolved at compile-time.

---

**Q33.** Which is true about interfaces?
- A) Can have constructors
- B) Can be instantiated
- C) Support multiple inheritance
- D) Can have private methods

**Answer:** ✅ C

**Explanation:** Interfaces support multiple inheritance (class can implement multiple).

---

**Q34.** try block without catch is:
- A) Invalid
- B) Valid with finally
- C) Always error
- D) Not allowed

**Answer:** ✅ B

**Explanation:** try-finally (without catch) is valid.

---

**Q35.** Liskov Substitution Principle states:
- A) Subclasses replace base class
- B) Base class replaces subclass
- C) No substitution
- D) Only interfaces

**Answer:** ✅ A

**Explanation:** L: Objects of subclass should replace objects of base class.

---

**Q36.** Which pattern adds responsibilities dynamically?
- A) Factory
- B) Decorator
- C) Singleton
- D) Observer

**Answer:** ✅ B

**Explanation:** Decorator pattern adds behavior to objects dynamically.

---

**Q37.** Abstraction focuses on:
- A) Implementation details
- B) Essential features
- C) All details
- D) Data hiding only

**Answer:** ✅ B

**Explanation:** Abstraction: show essentials, hide complexity.

---

**Q38.** Dynamic method dispatch is:
- A) Compile-time
- B) Runtime
- C) Design-time
- D) Load-time

**Answer:** ✅ B

**Explanation:** Runtime polymorphism (virtual functions, overriding).

---

**Q39.** Which is NOT an access modifier?
- A) private
- B) protected
- C) public
- D) abstract

**Answer:** ✅ D

**Explanation:** abstract is a modifier, not access modifier. Access: private, protected, public.

---

**Q40.** Composition represents:
- A) is-a relationship
- B) has-a relationship
- C) can-do relationship
- D) uses-a relationship

**Answer:** ✅ B

**Explanation:** Composition: has-a (strong ownership).

---

**Q41.** NullPointerException occurs when:
- A) Array index out of bounds
- B) Accessing null reference
- C) Division by zero
- D) File not found

**Answer:** ✅ B

**Explanation:** NullPointerException: calling method/field on null object.

---

**Q42.** Adapter pattern is:
- A) Creational
- B) Structural
- C) Behavioral
- D) None

**Answer:** ✅ B

**Explanation:** Adapter: structural pattern (converts interface).

---

**Q43.** Open-Closed Principle means:
- A) Open for modification, closed for extension
- B) Open for extension, closed for modification
- C) Both open
- D) Both closed

**Answer:** ✅ B

**Explanation:** O: Open for extension, closed for modification.

---

**Q44.** this keyword refers to:
- A) Parent class
- B) Current object
- C) Static method
- D) Super class

**Answer:** ✅ B

**Explanation:** this refers to current instance.

---

**Q45.** Which enables data hiding?
- A) public
- B) private
- C) protected
- D) static

**Answer:** ✅ B

**Explanation:** private members hidden from outside (encapsulation).

---

**Q46.** Multiple inheritance can cause:
- A) Polymorphism
- B) Diamond problem
- C) Encapsulation
- D) Abstraction

**Answer:** ✅ B

**Explanation:** Diamond problem: ambiguity when multiple parents have same method.

---

**Q47.** Static methods can:
- A) Access non-static members
- B) Access only static members
- C) Be overridden
- D) Use this keyword

**Answer:** ✅ B

**Explanation:** Static methods can only access static members (no instance).

---

**Q48.** Command pattern is:
- A) Creational
- B) Structural
- C) Behavioral
- D) None

**Answer:** ✅ C

**Explanation:** Command: behavioral (encapsulates request as object).

---

**Q49.** Dependency Inversion Principle states:
- A) Depend on concrete classes
- B) Depend on abstractions
- C) No dependencies
- D) Depend on implementations

**Answer:** ✅ B

**Explanation:** D: High-level modules should not depend on low-level; both depend on abstractions.

---

**Q50.** final keyword in Java means:
- A) Can be changed
- B) Cannot be changed
- C) Static only
- D) Private only

**Answer:** ✅ B

**Explanation:** final: cannot be modified (variable), overridden (method), or extended (class).

---

## 📌 CHAPTER 5: DATA STRUCTURES

### 5.1 Arrays & Linked Lists

**🔹 Key Concepts:**

| Feature | Array | Linked List |
|---------|-------|-------------|
| **Size** | Fixed | Dynamic |
| **Access** | O(1) random | O(n) sequential |
| **Insert/Delete** | O(n) | O(1) at known position |
| **Memory** | Contiguous | Non-contiguous |
| **Cache** | Good | Poor |

**🧠 Must-Remember:**
- **Singly Linked List**: Next pointer only
- **Doubly Linked List**: Next + Prev pointers
- **Circular Linked List**: Last points to first

**⚠️ Trap Concepts:**
- ❌ Array insertion is O(1) → ✅ O(n) (shift elements)
- ❌ Linked List has random access → ✅ Sequential only

---

### 5.2 Stacks & Queues

**🔹 Key Concepts:**
- **Stack**: LIFO (Last In First Out)
  - Operations: push, pop, peek
  - Applications: Function calls, Expression evaluation, Undo
- **Queue**: FIFO (First In First Out)
  - Operations: enqueue, dequeue
  - Applications: BFS, Scheduling, Buffer

**🧠 Must-Remember:**
- **Stack Overflow**: Stack full
- **Stack Underflow**: Stack empty
- **Circular Queue**: Better space utilization
- **Priority Queue**: Elements with priority

**⚡ Memory Trick:**
- Stack: **LIFO** (Last In = First Out)
- Queue: **FIFO** (First In = First Out)

---

### 5.3 Trees

**🔹 Key Concepts:**
- **Binary Tree**: Max 2 children per node
- **BST**: Left < Root < Right
- **AVL Tree**: Self-balancing BST (height diff ≤ 1)
- **Red-Black Tree**: Self-balancing (color property)
- **B-Tree**: Multi-way search tree (databases)
- **B+ Tree**: All data in leaves

**🧠 Must-Remember:**
- **Tree Traversals**:
  - **Inorder**: Left → Root → Right (gives sorted in BST)
  - **Preorder**: Root → Left → Right
  - **Postorder**: Left → Right → Root
- **Max nodes at level l**: 2^l
- **Max nodes in tree height h**: 2^(h+1) - 1
- **Height of BST**: O(log n) balanced, O(n) worst

**⚠️ Trap Concepts:**
- ❌ Inorder gives sorted for all trees → ✅ Only BST
- ❌ AVL is faster than BST → ✅ Better worst case, not always faster

---

### 5.4 Graphs

**🔹 Key Concepts:**
- **Graph**: G = (V, E) vertices + edges
- **Directed/Undirected**
- **Weighted/Unweighted**
- **Representation**: Adjacency Matrix, Adjacency List
- **Traversal**: BFS (queue), DFS (stack)

**🧠 Must-Remember:**
- **BFS**: Shortest path (unweighted), Level order
- **DFS**: Path finding, Cycle detection, Topological sort
- **Space**: Matrix O(V²), List O(V+E)

**⚠️ Trap Concepts:**
- ❌ BFS uses stack → ✅ Queue
- ❌ DFS uses queue → ✅ Stack (recursion)

---

### 5.5 Hashing

**🔹 Key Concepts:**
- **Hash Function**: Key → Index
- **Collision**: Two keys map to same index
- **Collision Resolution**:
  - **Chaining**: Linked list at each index
  - **Open Addressing**: Linear probing, Quadratic probing, Double hashing

**🧠 Must-Remember:**
- **Load Factor** α = n / m (elements / table size)
- **Chaining**: Search O(1+α) average
- **Open Addressing**: Search O(1/(1-α)) average
- **Good hash function**: Uniform distribution

**⚡ Memory Trick:**
- Collision: **C-L-O** (Chaining, Linear, Open addressing)

---

### 5.6 Heaps & Priority Queues

**🔹 Key Concepts:**
- **Min-Heap**: Parent ≤ Children (min at root)
- **Max-Heap**: Parent ≥ Children (max at root)
- **Applications**: Heap sort, Priority queue, Dijkstra

**🧠 Must-Remember:**
- **Array representation**: Parent(i) = i/2, Left = 2i, Right = 2i+1
- **Build Heap**: O(n)
- **Insert**: O(log n)
- **Extract Min/Max**: O(log n)
- **Heap Sort**: O(n log n)

---

### 5.7 Disjoint Set (Union-Find)

**🔹 Key Concepts:**
- **Union**: Merge two sets
- **Find**: Determine which set element belongs to
- **Optimizations**: Path compression, Union by rank

**🧠 Must-Remember:**
- **Time**: O(α(n)) ≈ O(1) with optimizations
- **Applications**: Kruskal's algorithm, Cycle detection

---

### 5.8 Choosing Right Data Structure

**🧠 Quick Reference:**

| Use Case | Best DS |
|----------|--------|
| Fast search | Hash Table, BST |
| Sorted data | BST, Array |
| FIFO | Queue |
| LIFO | Stack |
| Priority | Heap |
| Frequent insert/delete | Linked List |
| Random access | Array |

---

## 🧠 CHAPTER 5: DATA STRUCTURES - MCQ BANK (50 Questions)

**Q1.** Array access time complexity:
- A) O(n)
- B) O(1)
- C) O(log n)
- D) O(n²)

**Answer:** ✅ B

**Explanation:** Arrays support O(1) random access via index.

---

**Q2.** Stack follows:
- A) FIFO
- B) LIFO
- C) Random
- D) Priority

**Answer:** ✅ B

**Explanation:** Stack: Last In First Out.

---

**Q3.** Which traversal gives sorted order in BST?
- A) Preorder
- B) Inorder
- C) Postorder
- D) Level order

**Answer:** ✅ B

**Explanation:** Inorder (Left-Root-Right) gives ascending order in BST.

---

**Q4.** BFS uses which data structure?
- A) Stack
- B) Queue
- C) Array
- D) Tree

**Answer:** ✅ B

**Explanation:** BFS uses Queue (level-order traversal).
---

**Q5.** Hash table search average time:
- A) O(n)
- B) O(1)
- C) O(log n)
- D) O(n log n)

**Answer:** ✅ B

**Explanation:** Hash table: O(1) average case with good hash function.

---

**Q6.** Max-Heap property:
- A) Parent ≤ Children
- B) Parent ≥ Children
- C) Parent = Children
- D) No property

**Answer:** ✅ B

**Explanation:** Max-Heap: parent greater than or equal to children.

---

**Q7.** Linked list insertion at known position:
- A) O(1)
- B) O(n)
- C) O(log n)
- D) O(n²)

**Answer:** ✅ A

**Explanation:** Insertion O(1) if position known (just update pointers).

---

**Q8.** DFS uses:
- A) Queue
- B) Stack
- C) Heap
- D) Array

**Answer:** ✅ B

**Explanation:** DFS uses Stack (or recursion which uses call stack).

---

**Q9.** AVL tree is:
- A) Unbalanced BST
- B) Self-balancing BST
- C) Hash table
- D) Graph

**Answer:** ✅ B

**Explanation:** AVL tree maintains balance (height difference ≤ 1).

---

**Q10.** Collision in hashing occurs when:
- A) Table is full
- B) Two keys map to same index
- C) Hash function fails
- D) Load factor is 0

**Answer:** ✅ B

**Explanation:** Collision: different keys produce same hash value.

---

**Q11.** Queue operation to add element:
- A) push
- B) enqueue
- C) insert
- D) add

**Answer:** ✅ B

**Explanation:** Queue uses enqueue (add) and dequeue (remove).

---

**Q12.** Height of balanced BST with n nodes:
- A) O(n)
- B) O(log n)
- C) O(1)
- D) O(n²)

**Answer:** ✅ B

**Explanation:** Balanced BST height is O(log n).

---

**Q13.** Which is NOT a collision resolution technique?
- A) Chaining
- B) Linear probing
- C) Double hashing
- D) Binary search

**Answer:** ✅ D

**Explanation:** Binary search is searching algorithm, not collision resolution.

---

**Q14.** Postorder traversal order:
- A) Root-Left-Right
- B) Left-Root-Right
- C) Left-Right-Root
- D) Right-Left-Root

**Answer:** ✅ C

**Explanation:** Postorder: Left → Right → Root.

---

**Q15.** Doubly linked list node has:
- A) 1 pointer
- B) 2 pointers
- C) 3 pointers
- D) No pointers

**Answer:** ✅ B

**Explanation:** Next and Previous pointers (2 pointers).

---

**Q16.** Heap sort time complexity:
- A) O(n)
- B) O(n log n)
- C) O(n²)
- D) O(log n)

**Answer:** ✅ B

**Explanation:** Heap sort: O(n log n) in all cases.

---

**Q17.** Load factor α in hashing is:
- A) m/n
- B) n/m
- C) n×m
- D) n+m

**Answer:** ✅ B

**Explanation:** α = n/m (elements / table size).

---

**Q18.** Which data structure uses LIFO?
- A) Queue
- B) Stack
- C) Array
- D) Tree

**Answer:** ✅ B

**Explanation:** Stack: Last In First Out.

---

**Q19.** Adjacency list space complexity:
- A) O(V²)
- B) O(V+E)
- C) O(V)
- D) O(E)

**Answer:** ✅ B

**Explanation:** Adjacency list: O(V+E), Matrix: O(V²).

---

**Q20.** Union-Find with optimizations time:
- A) O(n)
- B) O(log n)
- C) O(α(n)) ≈ O(1)
- D) O(n²)

**Answer:** ✅ C

**Explanation:** Near constant time with path compression + union by rank.

---

**Q21.** Which tree is used in databases?
- A) Binary Tree
- B) AVL Tree
- C) B+ Tree
- D) Heap

**Answer:** ✅ C

**Explanation:** B+ Tree: efficient for disk storage and range queries.

---

**Q22.** Circular queue advantage:
- A) Faster access
- B) Better space utilization
- C) Less memory
- D) Simpler

**Answer:** ✅ B

**Explanation:** Reuses empty spaces (circular wrapping).

---

**Q23.** BST property:
- A) Left > Root > Right
- B) Left < Root < Right
- C) Left = Right
- D) No property

**Answer:** ✅ B

**Explanation:** BST: left subtree < root < right subtree.

---

**Q24.** Chaining collision resolution uses:
- A) Array
- B) Linked list
- C) Stack
- D) Queue

**Answer:** ✅ B

**Explanation:** Each index has linked list for colliding keys.

---

**Q25.** Max nodes at level l in binary tree:
- A) 2l
- B) 2^l
- C) l²
- D) l!

**Answer:** ✅ B

**Explanation:** Level 0: 1, Level 1: 2, Level 2: 4 (powers of 2).

---

**Q26.** Priority queue best implemented with:
- A) Array
- B) Linked List
- C) Heap
- D) Stack

**Answer:** ✅ C

**Explanation:** Heap provides O(log n) extract-max/min.

---

**Q27.** Stack underflow occurs when:
- A) Stack full
- B) Stack empty, pop called
- C) Push on full stack
- D) Pop on non-empty

**Answer:** ✅ B

**Explanation:** Underflow: trying to pop from empty stack.

---

**Q28.** Which is faster for searching?
- A) Linked List
- B) Array (unsorted)
- C) Hash Table
- D) Stack

**Answer:** ✅ C

**Explanation:** Hash Table: O(1) average, Array/Linked List: O(n).

---

**Q29.** Path compression is used in:
- A) Hash tables
- B) Union-Find
- C) Trees
- D) Graphs

**Answer:** ✅ B

**Explanation:** Path compression optimizes Union-Find find operation.

---

**Q30.** Preorder traversal order:
- A) Left-Root-Right
- B) Root-Left-Right
- C) Left-Right-Root
- D) Root-Right-Left

**Answer:** ✅ B

**Explanation:** Preorder: Root → Left → Right.

---

**Q31.** Build Heap time complexity:
- A) O(n log n)
- B) O(n)
- C) O(log n)
- D) O(n²)

**Answer:** ✅ B

**Explanation:** Build heap is O(n), not O(n log n).

---

**Q32.** Which DS has poor cache performance?
- A) Array
- B) Linked List
- C) Matrix
- D) Stack

**Answer:** ✅ B

**Explanation:** Linked List nodes scattered in memory (poor locality).

---

**Q33.** Graph with no cycles:
- A) Complete graph
- B) Tree
- C) Dense graph
- D) Weighted graph

**Answer:** ✅ B

**Explanation:** Tree is acyclic connected graph.

---

**Q34.** Linear probing is:
- A) Collision resolution
- B) Sorting
- C) Searching
- D) Traversal

**Answer:** ✅ A

**Explanation:** Linear probing: check next slot on collision.

---

**Q35.** Which operation is O(1) in stack?
- A) Search
- B) pop
- C) Sort
- D) Delete middle

**Answer:** ✅ B

**Explanation:** Push and pop are O(1) in stack.

---

**Q36.** AVL tree height balance factor:
- A) 0
- B) 1
- C) ≤ 1
- D) ≥ 1

**Answer:** ✅ C

**Explanation:** Height difference between subtrees ≤ 1.

---

**Q37.** Which is NOT a graph representation?
- A) Adjacency Matrix
- B) Adjacency List
- C) Incidence Matrix
- D) Hash Table

**Answer:** ✅ D

**Explanation:** Hash table is not a standard graph representation.

---

**Q38.** Min-Heap root contains:
- A) Maximum element
- B) Minimum element
- C) Median
- D) Random

**Answer:** ✅ B

**Explanation:** Min-Heap: minimum at root.

---

**Q39.** Infix to Postfix conversion uses:
- A) Queue
- B) Stack
- C) Array
- D) Tree

**Answer:** ✅ B

**Explanation:** Stack used for operator precedence handling.

---

**Q40.** Which DS is best for recursion?
- A) Queue
- B) Stack
- C) Array
- D) Graph

**Answer:** ✅ B

**Explanation:** Function call stack manages recursion.

---

**Q41.** Sparse graph better represented with:
- A) Adjacency Matrix
- B) Adjacency List
- C) Both same
- D) Neither

**Answer:** ✅ B

**Explanation:** Adjacency List: O(V+E) vs Matrix O(V²) for sparse.

---

**Q42.** Array insertion requires:
- A) No shifting
- B) Shifting elements
- C) New allocation only
- D) Pointer update

**Answer:** ✅ B

**Explanation:** Elements must shift to make room.

---

**Q43.** Red-Black tree is:
- A) Unbalanced
- B) Self-balancing
- C) Hash-based
- D) Linear

**Answer:** ✅ B

**Explanation:** Red-Black tree maintains balance via coloring.

---

**Q44.** Queue is used in:
- A) DFS
- B) BFS
- C) Recursion
- D) Backtracking

**Answer:** ✅ B

**Explanation:** BFS uses queue for level-order traversal.

---

**Q45.** Perfect binary tree with height h has:
- A) 2^h nodes
- B) 2^(h+1) - 1 nodes
- C) h² nodes
- D) 2h nodes

**Answer:** ✅ B

**Explanation:** Perfect tree: 2^(h+1) - 1 total nodes.

---

**Q46.** Double hashing uses:
- A) One hash function
- B) Two hash functions
- C) No hash function
- D) Three hash functions

**Answer:** ✅ B

**Explanation:** Double hashing: h(key, i) = (h1 + i*h2) mod m.

---

**Q47.** Which is true about linked lists?
- A) Fixed size
- B) Contiguous memory
- C) Dynamic size
- D) Random access

**Answer:** ✅ C

**Explanation:** Linked lists dynamically grow/shrink.

---

**Q48.** Kruskal's algorithm uses:
- A) Stack
- B) Queue
- C) Union-Find
- D) Hash Table

**Answer:** ✅ C

**Explanation:** Union-Find detects cycles in Kruskal's MST.

---

**Q49.** Expression tree leaves contain:
- A) Operators
- B) Operands
- C) Both
- D) Neither

**Answer:** ✅ B

**Explanation:** Leaves are operands, internal nodes are operators.

---

**Q50.** Best case BST search time:
- A) O(1)
- B) O(log n)
- C) O(n)
- D) O(n log n)

**Answer:** ✅ B

**Explanation:** Balanced BST: O(log n). Worst (skewed): O(n).

---

## 📌 CHAPTER 6: ALGORITHMS

### 6.1 Algorithm Analysis

**🔹 Key Concepts:**
- **Time Complexity**: How runtime grows with input
- **Space Complexity**: How memory grows with input
- **Big-O**: Upper bound (worst case)
- **Big-Ω**: Lower bound (best case)
- **Big-Θ**: Tight bound (average)

**🧠 Must-Remember:**
- **O(1)**: Constant
- **O(log n)**: Logarithmic (binary search)
- **O(n)**: Linear (linear search)
- **O(n log n)**: Linearithmic (merge sort, heap sort)
- **O(n²)**: Quadratic (bubble, insertion, selection sort)
- **O(2ⁿ)**: Exponential (recursive Fibonacci)
- **O(n!)**: Factorial (permutations)

**⚡ Memory Trick:**
- Order: **1 < log n < n < n log n < n² < 2ⁿ < n!**

---

### 6.2 Master Theorem

**🔹 Key Concepts:**
- Solves: **T(n) = aT(n/b) + f(n)**
- **Case 1**: f(n) = O(n^(log_b(a)-ε)) → T(n) = Θ(n^log_b(a))
- **Case 2**: f(n) = Θ(n^log_b(a)) → T(n) = Θ(n^log_b(a) × log n)
- **Case 3**: f(n) = Ω(n^(log_b(a)+ε)) → T(n) = Θ(f(n))

**🧠 Must-Remember:**
- **Merge Sort**: T(n) = 2T(n/2) + n → a=2, b=2, f(n)=n → **Θ(n log n)**
- **Binary Search**: T(n) = T(n/2) + 1 → **Θ(log n)**

**⚡ Memory Trick:**
- Compare f(n) with n^log_b(a): smaller → case 1, equal → case 2, larger → case 3

---

### 6.3 Sorting Algorithms

**🔹 Key Concepts:**

| Algorithm | Best | Average | Worst | Space | Stable |
|-----------|------|---------|-------|-------|--------|
| **Bubble** | O(n) | O(n²) | O(n²) | O(1) | Yes |
| **Selection** | O(n²) | O(n²) | O(n²) | O(1) | No |
| **Insertion** | O(n) | O(n²) | O(n²) | O(1) | Yes |
| **Merge** | O(n log n) | O(n log n) | O(n log n) | O(n) | Yes |
| **Quick** | O(n log n) | O(n log n) | O(n²) | O(log n) | No |
| **Heap** | O(n log n) | O(n log n) | O(n log n) | O(1) | No |

**🧠 Must-Remember:**
- **Stable**: Equal elements maintain order
- **In-place**: O(1) extra space
- **Quick Sort**: Worst case when array already sorted (naive pivot)
- **Merge Sort**: Always O(n log n), needs extra space

**⚠️ Trap Concepts:**
- ❌ Quick sort always O(n log n) → ✅ Worst case O(n²)
- ❌ Selection sort is stable → ✅ Not stable

---

### 6.4 Divide and Conquer

**🔹 Key Concepts:**
- **Steps**: Divide → Conquer → Combine
- **Examples**: Merge Sort, Quick Sort, Binary Search, Strassen's Matrix

**🧠 Must-Remember:**
- **Binary Search**: O(log n)
- **Merge Sort**: O(n log n)
- **Strassen's**: O(n^2.81) vs naive O(n³)

---

### 6.5 Dynamic Programming

**🔹 Key Concepts:**
- **Properties**: Optimal substructure + Overlapping subproblems
- **Approaches**: Memoization (top-down), Tabulation (bottom-up)
- **Examples**: Fibonacci, Knapsack, LCS, Matrix Chain, Floyd-Warshall

**🧠 Must-Remember:**
- **0/1 Knapsack**: O(nW) time, O(nW) space
- **LCS**: O(m×n) time
- **Matrix Chain**: O(n³) time
- **Floyd-Warshall**: O(V³) all-pairs shortest path

**⚠️ Trap Concepts:**
- ❌ DP used for greedy problems → ✅ Only when subproblems overlap
- ❌ Memoization = Tabulation → ✅ Memoization=top-down, Tabulation=bottom-up

---

### 6.6 Greedy Algorithms

**🔹 Key Concepts:**
- **Approach**: Make locally optimal choice at each step
- **Examples**: Huffman Coding, Kruskal's, Prim's, Dijkstra, Activity Selection
- **Does NOT guarantee optimal** for all problems

**🧠 Must-Remember:**
- **Huffman Coding**: Lossless compression, variable length
- **Dijkstra**: Single-source shortest path (no negative weights)
- **Kruskal's**: MST (sort edges, add if no cycle)
- **Prim's**: MST (grow from vertex)

**⚠️ Trap Concepts:**
- ❌ Greedy always optimal → ✅ Only for specific problems
- ❌ Dijkstra works with negative weights → ✅ Fails (use Bellman-Ford)

---

### 6.7 Graph Algorithms

**🔹 Key Concepts:**

| Algorithm | Purpose | Time | Type |
|-----------|---------|------|------|
| **BFS** | Shortest path (unweighted) | O(V+E) | Greedy |
| **DFS** | Traversal, cycle detection | O(V+E) | Backtracking |
| **Dijkstra** | Shortest path | O((V+E)log V) | Greedy |
| **Bellman-Ford** | Shortest path (negative) | O(VE) | DP |
| **Floyd-Warshall** | All-pairs shortest | O(V³) | DP |
| **Kruskal's** | MST | O(E log E) | Greedy |
| **Prim's** | MST | O((V+E)log V) | Greedy |
| **Topological Sort** | DAG ordering | O(V+E) | DFS |

**🧠 Must-Remember:**
- **MST**: Minimum Spanning Tree (n-1 edges, no cycles)
- **DAG**: Directed Acyclic Graph
- **Negative cycle**: Bellman-Ford detects

---

### 6.8 String Algorithms

**🔹 Key Concepts:**
- **KMP**: O(n+m) pattern matching
- **Rabin-Karp**: Hash-based, O(n+m) average
- **Naive**: O(n×m)

**🧠 Must-Remember:**
- **KMP**: Uses prefix function (pi array)
- **Z-algorithm**: O(n) pattern matching

---

### 6.9 Important Formulas

**🧠 Must-Remember:**
- **Sum of 1 to n**: n(n+1)/2 → O(n²)
- **Geometric series**: 1 + 2 + 4 + ... + n = 2n - 1 → O(n)
- **Log rules**: log(ab) = log a + log b
- **Recursion tree height**: log n (divide by 2 each time)

---

## 🧠 CHAPTER 6: ALGORITHMS - MCQ BANK (50 Questions)

**Q1.** Binary search time complexity:
- A) O(n)
- B) O(log n)
- C) O(n log n)
- D) O(1)

**Answer:** ✅ B

**Explanation:** Binary search halves search space each step: O(log n).

---

**Q2.** Merge sort worst case:
- A) O(n)
- B) O(n log n)
- C) O(n²)
- D) O(2ⁿ)

**Answer:** ✅ B

**Explanation:** Merge sort always O(n log n) in all cases.

---

**Q3.** Quick sort worst case:
- A) O(n log n)
- B) O(n²)
- C) O(n)
- D) O(log n)

**Answer:** ✅ B

**Explanation:** Worst when array already sorted (naive pivot): O(n²).

---

**Q4.** Which sorting is stable?
- A) Quick Sort
- B) Merge Sort
- C) Heap Sort
- D) Selection Sort

**Answer:** ✅ B

**Explanation:** Merge sort maintains relative order of equal elements.

---

**Q5.** Dynamic programming requires:
- A) Greedy choice
- B) Overlapping subproblems
- C) No recursion
- D) Sorting

**Answer:** ✅ B

**Explanation:** DP: Optimal substructure + Overlapping subproblems.

---

**Q6.** Dijkstra's algorithm fails with:
- A) Positive weights
- B) Negative weights
- C) Unweighted graphs
- D) Cycles

**Answer:** ✅ B

**Explanation:** Dijkstra assumes non-negative edges. Use Bellman-Ford for negative.

---

**Q7.** Kruskal's algorithm finds:
- A) Shortest path
- B) MST
- C) Longest path
- D) Cycle

**Answer:** ✅ B

**Explanation:** Kruskal's finds Minimum Spanning Tree.

---

**Q8.** MST of graph with n vertices has:
- A) n edges
- B) n-1 edges
- C) n+1 edges
- D) 2n edges

**Answer:** ✅ B

**Explanation:** MST: n vertices, n-1 edges, no cycles.

---

**Q9.** Big-O represents:
- A) Best case
- B) Average case
- C) Worst case
- D) Exact case

**Answer:** ✅ C

**Explanation:** Big-O: upper bound (worst case).

---

**Q10.** Master theorem solves:
- A) Loops
- B) Recurrences
- C) Sorting
- D) Graphs

**Answer:** ✅ B

**Explanation:** Master theorem: T(n) = aT(n/b) + f(n).

---

**Q11.** Fibonacci with DP is:
- A) O(2ⁿ)
- B) O(n)
- C) O(n²)
- D) O(log n)

**Answer:** ✅ B

**Explanation:** Naive recursive: O(2ⁿ), DP: O(n).

---

**Q12.** Huffman coding is:
- A) Lossy compression
- B) Lossless compression
- C) Sorting
- D) Encryption

**Answer:** ✅ B

**Explanation:** Huffman: lossless compression using variable-length codes.

---

**Q13.** Which is O(1)?
- A) Linear search
- B) Binary search
- C) Array access
- D) Sorting

**Answer:** ✅ C

**Explanation:** Array access by index is O(1).

---

**Q14.** Bubble sort best case:
- A) O(n²)
- B) O(n log n)
- C) O(n)
- D) O(1)

**Answer:** ✅ C

**Explanation:** Already sorted array: O(n) with flag optimization.

---

**Q15.** Longest Common Subsequence uses:
- A) Greedy
- B) DP
- C) Divide & Conquer
- D) Backtracking

**Answer:** ✅ B

**Explanation:** LCS: classic DP problem.

---

**Q16.** Floyd-Warshall finds:
- A) Single-source shortest path
- B) All-pairs shortest path
- C) MST
- D) Cycle

**Answer:** ✅ B

**Explanation:** Floyd-Warshall: all-pairs shortest paths.

---

**Q17.** Floyd-Warshall time:
- A) O(V²)
- B) O(V³)
- C) O(VE)
- D) O(V log V)

**Answer:** ✅ B

**Explanation:** Three nested loops over vertices: O(V³).

---

**Q18.** Insertion sort is best for:
- A) Large arrays
- B) Small/nearly sorted arrays
- C) Random arrays
- D) Sorted in reverse

**Answer:** ✅ B

**Explanation:** O(n) for nearly sorted, low overhead.

---

**Q19.** T(n) = 2T(n/2) + n solves to:
- A) O(n)
- B) O(n log n)
- C) O(n²)
- D) O(log n)

**Answer:** ✅ B

**Explanation:** Master theorem case 2: Θ(n log n) (Merge Sort).

---

**Q20.** Greedy approach makes:
- A) Globally optimal choice
- B) Locally optimal choice
- C) Random choice
- D) No choice

**Answer:** ✅ B

**Explanation:** Greedy: locally optimal at each step.

---

**Q21.** Bellman-Ford time:
- A) O(V²)
- B) O(VE)
- C) O(V³)
- D) O(E log V)

**Answer:** ✅ B

**Explanation:** V-1 iterations over E edges: O(VE).

---

**Q22.** Which detects negative cycle?
- A) Dijkstra
- B) Bellman-Ford
- C) BFS
- D) DFS

**Answer:** ✅ B

**Explanation:** Bellman-Ford can detect negative weight cycles.

---

**Q23.** 0/1 Knapsack time:
- A) O(n)
- B) O(nW)
- C) O(n²)
- D) O(2ⁿ)

**Answer:** ✅ B

**Explanation:** DP solution: O(nW) where W is capacity.

---

**Q24.** Heap sort space:
- A) O(n)
- B) O(1)
- C) O(log n)
- D) O(n log n)

**Answer:** ✅ B

**Explanation:** Heap sort is in-place: O(1) extra space.

---

**Q25.** Matrix Chain Multiplication uses:
- A) Greedy
- B) DP
- C) Divide & Conquer
- D) Backtracking

**Answer:** ✅ B

**Explanation:** MCM: classic DP problem, O(n³).

---

**Q26.** KMP algorithm time:
- A) O(n×m)
- B) O(n+m)
- C) O(n log n)
- D) O(n²)

**Answer:** ✅ B

**Explanation:** KMP: O(n+m) where n=text, m=pattern.

---

**Q27.** Topological sort works on:
- A) Any graph
- B) DAG only
- C) Trees only
- D) Complete graphs

**Answer:** ✅ B

**Explanation:** Topological sort requires Directed Acyclic Graph.

---

**Q28.** Strassen's algorithm multiplies:
- A) Numbers
- B) Matrices
- C) Strings
- D) Arrays

**Answer:** ✅ B

**Explanation:** Strassen's: O(n^2.81) matrix multiplication.

---

**Q29.** Selection sort is:
- A) Stable
- B) Not stable
- C) Adaptive
- D) O(n log n)

**Answer:** ✅ B

**Explanation:** Selection sort swaps, not stable.

---

**Q30.** Θ notation represents:
- A) Upper bound
- B) Lower bound
- C) Tight bound
- D) Worst case

**Answer:** ✅ C

**Explanation:** Θ: tight bound (both upper and lower).

---

**Q31.** Prim's algorithm uses:
- A) Stack
- B) Priority Queue
- C) Queue
- D) Array

**Answer:** ✅ B

**Explanation:** Prim's uses priority queue (min-heap) for efficiency.

---

**Q32.** Activity Selection uses:
- A) DP
- B) Greedy
- C) Divide & Conquer
- D) Backtracking

**Answer:** ✅ B

**Explanation:** Activity Selection: greedy (sort by finish time).

---

**Q33.** In-place sorting means:
- A) O(1) extra space
- B) O(n) extra space
- C) No sorting
- D) External sorting

**Answer:** ✅ A

**Explanation:** In-place: constant extra space.

---

**Q34.** Binary search requires:
- A) Unsorted array
- B) Sorted array
- C) Linked list
- D) Stack

**Answer:** ✅ B

**Explanation:** Binary search needs sorted array.

---

**Q35.** Quick sort average case:
- A) O(n)
- B) O(n log n)
- C) O(n²)
- D) O(log n)

**Answer:** ✅ B

**Explanation:** Average: O(n log n), worst: O(n²).

---

**Q36.** Memoization is:
- A) Bottom-up
- B) Top-down
- C) Greedy
- D) Iterative

**Answer:** ✅ B

**Explanation:** Memoization: top-down with caching.

---

**Q37.** Tabulation is:
- A) Top-down
- B) Bottom-up
- C) Recursive
- D) Greedy

**Answer:** ✅ B

**Explanation:** Tabulation: bottom-up iterative DP.

---

**Q38.** BFS time complexity:
- A) O(V)
- B) O(E)
- C) O(V+E)
- D) O(V×E)

**Answer:** ✅ C

**Explanation:** BFS visits all vertices and edges: O(V+E).

---

**Q39.** Which has O(n!) complexity?
- A) Binary search
- B) Permutations
- C) Sorting
- D) Hashing

**Answer:** ✅ B

**Explanation:** Generating all permutations: O(n!).

---

**Q40.** Merge sort space:
- A) O(1)
- B) O(n)
- C) O(log n)
- D) O(n²)

**Answer:** ✅ B

**Explanation:** Merge sort needs O(n) auxiliary space.

---

**Q41.** Omega (Ω) notation is:
- A) Upper bound
- B) Lower bound
- C) Tight bound
- D) Average

**Answer:** ✅ B

**Explanation:** Ω: lower bound (best case).

---

**Q42.** Counting sort time:
- A) O(n log n)
- B) O(n+k)
- C) O(n²)
- D) O(n)

**Answer:** ✅ B

**Explanation:** Counting sort: O(n+k) where k is range.

---

**Q43.** Which is NOT comparison-based?
- A) Merge Sort
- B) Quick Sort
- C) Counting Sort
- D) Heap Sort

**Answer:** ✅ C

**Explanation:** Counting sort uses counting, not comparisons.

---

**Q44.** Lower bound for comparison sort:
- A) O(n)
- B) O(n log n)
- C) O(n²)
- D) O(log n)

**Answer:** ✅ B

**Explanation:** Ω(n log n) is lower bound for comparison-based sorting.

---

**Q45.** Rabin-Karp uses:
- A) DP
- B) Hashing
- C) Greedy
- D) Sorting

**Answer:** ✅ B

**Explanation:** Rabin-Karp: hash-based string matching.

---

**Q46.** Recursion tree method solves:
- A) Loops
- B) Recurrences
- C) Graphs
- D) Sorting

**Answer:** ✅ B

**Explanation:** Recursion tree visualizes recurrence expansion.

---

**Q47.** DFS can detect:
- A) Shortest path
- B) Cycles
- C) MST
- D) Hash collisions

**Answer:** ✅ B

**Explanation:** DFS detects cycles in graphs.

---

**Q48.** Adaptive sorting means:
- A) Works on all data
- B) Faster on nearly sorted data
- C) Changes algorithm
- D) Not stable

**Answer:** ✅ B

**Explanation:** Adaptive: O(n) for nearly sorted (e.g., Insertion Sort).

---

**Q49.** Amortized analysis considers:
- A) Single operation
- B) Sequence of operations
- C) Worst case only
- D) Best case only

**Answer:** ✅ B

**Explanation:** Amortized: average cost over sequence.

---

**Q50.** NP-complete problems:
- A) Solvable in polynomial time
- B) No known polynomial solution
- C) Always unsolvable
- D) Trivial

**Answer:** ✅ B

**Explanation:** NP-complete: no known P-time algorithm (e.g., TSP, SAT).

---

## 🔥 TOP 100 MOST IMPORTANT QUESTIONS

### 📚 Operating Systems (Q1-Q17)

1. **SJF gives minimum average waiting time** ✅ (Most asked)
2. **Banker's algorithm for deadlock avoidance** ✅
3. **FIFO suffers from Belady's Anomaly** ✅
4. **Context switch is pure overhead** ✅
5. **4 necessary conditions for deadlock** ✅
6. **Mutex has ownership, Binary Semaphore doesn't** ✅
7. **fork() returns 0 to child, PID to parent** ✅
8. **Paging: internal fragmentation only** ✅
9. **Segmentation: external fragmentation only** ✅
10. **RAID 0 has NO fault tolerance** ✅
11. **SRAM for cache, DRAM for main memory** ✅
12. **Round Robin with large quantum = FCFS** ✅
13. **TLB hit ratio formula** ✅
14. **Starvation in Priority & SJF (solved by Aging)** ✅
15. **Threads share code/data, have own stack/registers** ✅
16. **SCAN = Elevator algorithm** ✅
17. **Peterson's solution for 2 processes only** ✅

### 📊 DBMS (Q18-Q33)

18. **Primary Key: UNIQUE + NOT NULL** ✅
19. **Foreign Key can be NULL and duplicate** ✅
20. **DELETE (DML) vs TRUNCATE (DDL) vs DROP (DDL)** ✅
21. **ACID properties** ✅
22. **2PL ensures serializability, not deadlock-free** ✅
23. **BCNF stricter than 3NF** ✅
24. **Clustered index: only ONE per table** ✅
25. **B+ Tree: all data in leaves** ✅
26. **CAP theorem: choose 2 of 3** ✅
27. **HAVING for groups, WHERE for rows** ✅
28. **Lossless join + Dependency preserving in 3NF** ✅
29. **Super keys max = 2^n** ✅
30. **NoSQL: Key-Value, Document, Column, Graph** ✅
31. **Dense vs Sparse index** ✅
32. **Precedence graph cycle = not conflict serializable** ✅
33. **View serializability weaker than conflict** ✅

### 🌐 Networks (Q34-Q50)

34. **OSI model 7 layers** ✅
35. **TCP connection-oriented, UDP connectionless** ✅
36. **HTTP=80, HTTPS=443, FTP=21, SMTP=25, DNS=53, SSH=22** ✅
37. **MAC address 48 bits** ✅
38. **IPv4=32 bits, IPv6=128 bits** ✅
39. **3-way handshake: SYN, SYN-ACK, ACK** ✅
40. **CSMA/CD for Ethernet, CSMA/CA for WiFi** ✅
41. **Network layer: routing, IP** ✅
42. **Transport layer: end-to-end, TCP/UDP** ✅
43. **DNS: domain to IP** ✅
44. **ARP: IP to MAC** ✅
45. **Class A: 0-127, B: 128-191, C: 192-223** ✅
46. **Subnet mask identifies network portion** ✅
47. **Well-known ports: 0-1023** ✅
48. **Firewall filters traffic** ✅
49. **Symmetric = same key, Asymmetric = public+private** ✅
50. **UDP header 8 bytes, TCP 20 bytes** ✅

### 💻 OOP (Q51-Q67)

51. **4 pillars: Encapsulation, Inheritance, Polymorphism, Abstraction** ✅
52. **Overloading = compile-time, Overriding = runtime** ✅
53. **Private members inherited but not accessible** ✅
54. **Interface: multiple inheritance, no constructors** ✅
55. **Abstract class: is-a, Interface: can-do** ✅
56. **finally always executes** ✅
57. **Virtual functions enable runtime polymorphism** ✅
58. **Singleton: one instance** ✅
59. **SOLID principles** ✅
60. **High cohesion + Low coupling = Good design** ✅
61. **Constructor: Parent→Child, Destructor: Child→Parent** ✅
62. **Protected: inherited, not outside access** ✅
63. **Pure virtual function: = 0** ✅
64. **Checked exceptions: must catch/declare** ✅
65. **Static methods: only static members** ✅
66. **Function signature: name + parameters (not return)** ✅
67. **Diamond problem in multiple inheritance** ✅

### 🌲 Data Structures (Q68-Q83)

68. **Array: O(1) access, Linked List: O(n) access** ✅
69. **Stack: LIFO, Queue: FIFO** ✅
70. **BST: Left < Root < Right** ✅
71. **Inorder traversal gives sorted BST** ✅
72. **BFS uses Queue, DFS uses Stack** ✅
73. **Hash table: O(1) average search** ✅
74. **Max-Heap: Parent ≥ Children** ✅
75. **AVL tree: height diff ≤ 1** ✅
76. **B+ Tree used in databases** ✅
77. **Build Heap: O(n), not O(n log n)** ✅
78. **Adjacency List: O(V+E), Matrix: O(V²)** ✅
79. **MST: n vertices, n-1 edges** ✅
80. **Perfect binary tree: 2^(h+1) - 1 nodes** ✅
81. **Chaining vs Open Addressing** ✅
82. **Linked List: dynamic, non-contiguous** ✅
83. **Union-Find: O(α(n)) ≈ O(1)** ✅

### ⚡ Algorithms (Q84-Q100)

84. **Merge Sort: always O(n log n)** ✅
85. **Quick Sort: worst O(n²), average O(n log n)** ✅
86. **Binary Search: O(log n), needs sorted** ✅
87. **DP: Optimal substructure + Overlapping subproblems** ✅
88. **Dijkstra fails with negative weights** ✅
89. **Bellman-Ford: O(VE), detects negative cycle** ✅
90. **Kruskal's & Prim's: MST** ✅
91. **Floyd-Warshall: O(V³), all-pairs** ✅
92. **Master Theorem: T(n) = aT(n/b) + f(n)** ✅
93. **Big-O: upper bound (worst case)** ✅
94. **Stable sorts: Merge, Bubble, Insertion** ✅
95. **Huffman Coding: lossless compression** ✅
96. **0/1 Knapsack: O(nW) DP** ✅
97. **LCS: O(m×n) DP** ✅
98. **KMP: O(n+m) string matching** ✅
99. **Lower bound for comparison sort: Ω(n log n)** ✅
100. **NP-complete: no known polynomial solution** ✅

---

## ⚡ RAPID REVISION SHEETS

### 📘 OS - One Page Summary

| Topic | Key Point |
|-------|-----------|
| **SJF** | Minimum avg waiting time |
| **Round Robin** | Time quantum, preemptive |
| **Deadlock 4 conditions** | Mutual Exclusion, Hold&Wait, No Preemption, Circular Wait |
| **Banker's** | Deadlock AVOIDANCE |
| **Belady's Anomaly** | FIFO only |
| **Paging** | Internal fragmentation |
| **Segmentation** | External fragmentation |
| **TLB** | Page table cache |
| **RAID 0** | No redundancy |
| **Mutex vs Semaphore** | Mutex has ownership |
| **fork()** | 0 to child, PID to parent |
| **Threads share** | Code, Data, Files |
| **Context Switch** | Pure overhead |
| **Starvation** | Priority, SJF (solve with Aging) |

### 📊 DBMS - One Page Summary

| Topic | Key Point |
|-------|-----------|
| **Primary Key** | UNIQUE + NOT NULL |
| **Foreign Key** | Can be NULL, duplicate |
| **ACID** | Atomicity, Consistency, Isolation, Durability |
| **DELETE** | DML, can rollback |
| **TRUNCATE** | DDL, faster |
| **DROP** | Removes table + data |
| **1NF** | Atomic values |
| **2NF** | No partial dependency |
| **3NF** | No transitive dependency |
| **BCNF** | Determinant = candidate key |
| **Clustered Index** | Only ONE |
| **B+ Tree** | Data in leaves |
| **2PL** | Serializability |
| **CAP** | Consistency, Availability, Partition (choose 2) |
| **NoSQL** | Key-Value, Document, Column, Graph |

### 🌐 Networks - One Page Summary

| Topic | Key Point |
|-------|-----------|
| **OSI Layers** | 7 (A-P-S-T-N-D-P) |
| **TCP** | Connection-oriented, reliable |
| **UDP** | Connectionless, fast |
| **HTTP** | 80 |
| **HTTPS** | 443 |
| **MAC** | 48 bits |
| **IPv4** | 32 bits |
| **IPv6** | 128 bits |
| **CSMA/CD** | Ethernet |
| **CSMA/CA** | WiFi |
| **DNS** | Domain → IP |
| **ARP** | IP → MAC |
| **Ports** | 0-1023 well-known |
| **Firewall** | Filter traffic |
| **3-way handshake** | SYN, SYN-ACK, ACK |

### 💻 OOP - One Page Summary

| Topic | Key Point |
|-------|-----------|
| **4 Pillars** | Encapsulation, Inheritance, Polymorphism, Abstraction |
| **Overloading** | Compile-time |
| **Overriding** | Runtime |
| **Abstract** | is-a relationship |
| **Interface** | can-do, multiple inheritance |
| **finally** | Always executes |
| **Singleton** | One instance |
| **SOLID** | 5 principles |
| **Cohesion** | HIGH = good |
| **Coupling** | LOW = good |
| **Virtual** | Runtime polymorphism |
| **Private** | Inherited, not accessible |

### 🌲 Data Structures - One Page Summary

| Topic | Key Point |
|-------|-----------|
| **Array** | O(1) access, fixed |
| **Linked List** | O(n) access, dynamic |
| **Stack** | LIFO |
| **Queue** | FIFO |
| **BST** | Left < Root < Right |
| **Inorder** | Sorted in BST |
| **BFS** | Queue |
| **DFS** | Stack |
| **Hash Table** | O(1) average |
| **Heap** | Priority queue |
| **AVL** | Balanced BST |
| **B+ Tree** | Databases |
| **MST** | n-1 edges |

### ⚡ Algorithms - One Page Summary

| Topic | Key Point |
|-------|-----------|
| **Merge Sort** | O(n log n) always |
| **Quick Sort** | Worst O(n²) |
| **Binary Search** | O(log n), sorted |
| **DP** | Overlapping + Optimal |
| **Dijkstra** | No negative weights |
| **Bellman-Ford** | O(VE), negative OK |
| **Kruskal/Prim** | MST |
| **Floyd-Warshall** | O(V³) all-pairs |
| **Big-O** | Worst case |
| **Master Theorem** | Recurrences |
| **Huffman** | Lossless compression |
| **KMP** | O(n+m) string |

---

## 🧩 CONCEPT LINKING

### Cross-Chapter Connections

| Concept | Chapter 1 | Chapter 5 | Chapter 6 |
|---------|-----------|-----------|----------|
| **Scheduling** | CPU Scheduling | Priority Queue | Greedy Algorithms |
| **Memory** | Paging/Segmentation | Trees (Page Tables) | Space Complexity |
| **Deadlock** | Resource Allocation | Graphs (Cycle Detection) | DFS |
| **File System** | B+ Tree Indexing | B+ Trees | Database Indexing |

| Concept | Chapter 2 | Chapter 3 | Chapter 4 |
|---------|-----------|-----------|----------|
| **Indexing** | B+ Trees | Routing Tables | Design Patterns |
| **Transactions** | ACID | TCP (Reliable) | Exception Handling |
| **Concurrency** | Locks (2PL) | CSMA/CD/CA | Synchronization |
| **Security** | Access Control | Encryption | Encapsulation |

### High-Yield Connections:
- **OS Scheduling** ↔ **Algorithms (Greedy, Priority Queue)**
- **DBMS Indexing** ↔ **Data Structures (B+ Trees, Hashing)**
- **Network TCP** ↔ **OS (Reliability, Flow Control)**
- **Deadlock Detection** ↔ **Graphs (Cycle Detection)**
- **OOP Encapsulation** ↔ **Security (Information Hiding)**

---

## 🎯 EXAM STRATEGY

### ⏱️ Time Management
- **60 MCQs in 60 minutes** = 1 min per question
- **First pass**: 30 mins (answer easy questions)
- **Second pass**: 20 mins (medium difficulty)
- **Third pass**: 10 mins (hard/guessing)

### 🎯 Elimination Techniques
1. **Absolute words** (always, never) → Usually WRONG
2. **Both A & B** / **All of above** → Often RIGHT
3. **Eliminate extremes** → Pick moderate option
4. **Look for contradictions** → One must be wrong
5. **Similar options** → Answer often between them

### 💡 Smart Guessing Strategy
1. **Don't leave blank** (if no negative marking)
2. **Trust first instinct** (don't overthink)
3. **Pattern recognition**: If seen similar → same answer
4. **Longest option** → Often correct (more precise)
5. **Middle values** in numerical → Usually right

### 🚨 Marking Scheme Optimization
- **No negative marking**: Attempt ALL
- **Negative marking**: Guess only after eliminating 2 options
- **Partial marking**: Answer what you know for sure first

---

## 💡 SUPER SHORTCUTS (VERY IMPORTANT)

### 📘 OS Shortcuts
- Question contains **"minimum waiting time"** → **SJF**
- Question contains **"Belady's Anomaly"** → **FIFO**
- Question contains **"avoidance"** → **Banker's Algorithm**
- Question contains **"ownership"** → **Mutex**
- Question contains **"elevator"** → **SCAN**
- Question contains **"pure overhead"** → **Context Switch**
- Question contains **"thrashing"** → **Excessive paging**
- **Fragmentation in Paging** → **Internal only**
- **Fragmentation in Segmentation** → **External only**

### 📊 DBMS Shortcuts
- Question contains **"all or nothing"** → **Atomicity**
- Question contains **"serializability"** → **2PL**
- Question contains **"determinant"** → **BCNF**
- Question contains **"transitive"** → **3NF**
- Question contains **"partial dependency"** → **2NF**
- Question contains **"atomic values"** → **1NF**
- Question contains **"one per table"** → **Clustered Index**
- Question contains **"CAP"** → **Choose 2 of 3**
- **DELETE vs TRUNCATE** → DELETE=DML, TRUNCATE=DDL

### 🌐 Networks Shortcuts
- Question contains **"connection-oriented"** → **TCP**
- Question contains **"connectionless"** → **UDP**
- Question contains **"routing"** → **Network Layer**
- Question contains **"end-to-end"** → **Transport Layer**
- Question contains **"MAC"** → **48 bits**
- Question contains **"IPv6"** → **128 bits**
- Question contains **"Ethernet"** → **CSMA/CD**
- Question contains **"WiFi"** → **CSMA/CA**
- **Port 80** → HTTP, **443** → HTTPS

### 💻 OOP Shortcuts
- Question contains **"compile-time polymorphism"** → **Overloading**
- Question contains **"runtime polymorphism"** → **Overriding/Virtual**
- Question contains **"always executes"** → **finally**
- Question contains **"one instance"** → **Singleton**
- Question contains **"is-a"** → **Abstract Class**
- Question contains **"can-do"** → **Interface**
- Question contains **"multiple inheritance Java"** → **Interfaces only**
- Question contains **"diamond problem"** → **Multiple inheritance**

### 🌲 DS Shortcuts
- Question contains **"LIFO"** → **Stack**
- Question contains **"FIFO"** → **Queue**
- Question contains **"sorted BST"** → **Inorder**
- Question contains **"shortest path unweighted"** → **BFS**
- Question contains **"cycle detection"** → **DFS**
- Question contains **"priority"** → **Heap**
- Question contains **"fast search"** → **Hash Table**
- Question contains **"database index"** → **B+ Tree**
- **Build Heap** → **O(n)** NOT O(n log n)

### ⚡ Algorithms Shortcuts
- Question contains **"divide and conquer"** → **Merge/Quick Sort**
- Question contains **"overlapping subproblems"** → **DP**
- Question contains **"locally optimal"** → **Greedy**
- Question contains **"negative weights"** → **Bellman-Ford**
- Question contains **"all-pairs shortest"** → **Floyd-Warshall**
- Question contains **"MST"** → **Kruskal's/Prim's**
- Question contains **"worst case Quick Sort"** → **O(n²)**
- Question contains **"stable sort"** → **Merge/Bubble/Insertion**
- Question contains **"lossless compression"** → **Huffman**
- Question contains **"lower bound sorting"** → **Ω(n log n)**

---

## 🎓 FINAL TIPS

1. **Revise this document 2-3 times** before exam
2. **Focus on MCQ Bank** explanations (understand WHY)
3. **Use Rapid Revision Sheets** for last-minute review
4. **Apply shortcuts** during exam for quick answers
5. **Stay calm, read questions carefully**
6. **Mark doubtful questions**, return later
7. **Don't spend >2 mins** on any single question

---

**🎯 BEST OF LUCK! You're now exam-ready!** 🚀

> Remember: This document covers 95%+ of frequently asked MCQs. Trust your preparation!
