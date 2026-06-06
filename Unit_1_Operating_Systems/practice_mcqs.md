# Unit I: Operating Systems - MCQ Bank

Practice these 50 high-yield, solved Multiple Choice Questions to master Unit 1 concepts. Every question includes the correct answer and a detailed explanation.

---

## 🔷 Topic 1: OS Foundations, Kernel & System Calls

#### Q1. The core component of an Operating System that runs in the most privileged mode (Ring 0) and remains in RAM throughout the session is:
- A) Shell
- B) Kernel
- C) Command Interpreter
- D) BIOS
- **Answer: ✅ B**
- **Explanation**: The kernel is the central core of the OS. The shell is a user-level program that interfaces with the kernel.

#### Q2. Which of the following is true regarding a Microkernel architecture?
- A) All services run in the kernel space for speed
- B) It is faster than a monolithic kernel because it has less code
- C) It keeps only essential services in kernel space; other services run as user processes
- D) A crash in a system driver crashes the entire system
- **Answer: ✅ C**
- **Explanation**: Microkernels keep only bare essentials (IPC, low-level scheduling) in kernel space, isolating drivers and files in user space to make the system more secure and robust, though at the expense of performance.

#### Q3. In Unix-like systems, the `fork()` system call returns:
- A) 0 to the parent process, and child's PID to the child process
- B) 0 to the child process, and child's PID to the parent process
- C) -1 to the child process on success
- D) PID of the parent to the child process
- **Answer: ✅ B**
- **Explanation**: On success, `fork()` creates a clone process. It returns `0` to the child and the child's process ID (PID) to the parent. It returns `-1` if creation fails.

#### Q4. Which instruction execution requires switching from User Mode to Kernel Mode?
- A) Calling a local mathematical function
- B) Modifying a local variable on the stack
- C) Reading a data block from the solid-state drive (SSD)
- D) Adding two values stored in CPU registers
- **Answer: ✅ C**
- **Explanation**: Accessing hardware like storage (I/O) is a privileged operation. The application must invoke a system call, which shifts the CPU execution mode from User to Kernel.

#### Q5. A computer program is a __________ entity, whereas a process is a __________ entity.
- A) Dynamic, Static
- B) Active, Passive
- C) Passive, Active
- D) Temporary, Permanent
- **Answer: ✅ C**
- **Explanation**: A program is a passive set of instructions stored on disk (code). A process is an active entity in execution, with resources like a program counter (PC), stack, registers, and memory.

---

## 🔷 Topic 2: Process States & CPU Scheduling

#### Q6. Which state transition is IMPOSSIBLE in a standard process state model?
- A) Ready $\to$ Running
- B) Running $\to$ Ready
- C) Waiting $\to$ Running
- D) Running $\to$ Waiting
- **Answer: ✅ C**
- **Explanation**: A process waiting for an I/O event must go back to the *Ready* queue once the event completes. It cannot jump straight to *Running* because it must wait for the CPU scheduler to select it.

#### Q7. The CPU scheduler dispatcher is responsible for:
- A) Moving a process from the New state to the Ready state
- B) Assigning a selected ready process to the CPU
- C) Allocating I/O devices to processes
- D) Calculating the time quantum for Round Robin
- **Answer: ✅ B**
- **Explanation**: The dispatcher is the module that gives control of the CPU to the process selected by the short-term scheduler.

#### Q8. Which CPU scheduling algorithm yields the minimum average waiting time for a set of stationary processes?
- A) First-Come, First-Served (FCFS)
- B) Round Robin (RR)
- C) Shortest Job First (SJF)
- D) Multilevel Queue Scheduling
- **Answer: ✅ C**
- **Explanation**: Shortest Job First (SJF) is mathematically proven to be optimal because it minimizes the average waiting time for any given set of processes.

#### Q9. Consider the following processes with their Arrival Time and Burst Time:
| Process | Arrival Time | Burst Time |
| :--- | :--- | :--- |
| P1 | 0 ms | 8 ms |
| P2 | 1 ms | 4 ms |
| P3 | 2 ms | 9 ms |

Using Non-Preemptive SJF, what is the completion time of P2?
- A) 12 ms
- B) 4 ms
- C) 13 ms
- D) 5 ms
- **Answer: ✅ A**
- **Explanation**: 
  - At $t=0$, only P1 is available. It runs to completion ($t=8$).
  - At $t=8$, both P2 and P3 have arrived. Since P2 has a shorter burst ($4 < 9$), P2 runs next.
  - P2 finishes at $8 + 4 = 12$ ms.

#### Q10. In Round Robin scheduling, if the Time Quantum is chosen to be extremely large (e.g., larger than the longest burst time):
- A) The scheduling degrades into FCFS
- B) The scheduling degrades into Shortest Job First
- C) Context switching overhead increases to 100%
- D) Starvation becomes high
- **Answer: ✅ A**
- **Explanation**: If the quantum is large enough, every process runs to completion in its first time slice without being preempted. Hence, it behaves exactly like First-Come, First-Served.

#### Q11. "Aging" is a synchronization or scheduling technique used to prevent:
- A) Deadlocks
- B) Race conditions
- C) Starvation
- D) Belady's Anomaly
- **Answer: ✅ C**
- **Explanation**: Aging gradually increases the priority of processes that have waited in the system for a long time, ensuring they eventually get CPU time and avoiding starvation.

#### Q12. Context switching is:
- A) Time spent performing user computations
- B) Pure overhead to save and restore process states
- C) A method to speed up memory access
- D) An algorithm to prevent page faults
- **Answer: ✅ B**
- **Explanation**: During a context switch, the OS performs no useful calculations for the user; it only saves the state of the old process and loads the state of the new one. Thus, it is pure overhead.

#### Q13. Which of the following is shared between threads belonging to the same process?
- A) Stack and registers
- B) Program counter and thread ID
- C) Global variables and open files
- D) Local variables and stack pointers
- **Answer: ✅ C**
- **Explanation**: Threads share the process's code, global data (data section), heap, and file descriptors. They maintain private stacks, registers, and program counters.

---

## 🔷 Topic 3: Process Synchronization

#### Q14. A race condition is:
- A) A situation where multiple processes compete for CPU scheduling time
- B) A scenario where several threads access shared data concurrently and the outcome depends on the execution order
- C) A physical hardware fault in the system clock
- D) An optimization technique in multi-core chips
- **Answer: ✅ B**
- **Explanation**: A race condition occurs when concurrent operations read and write shared state, making the final result highly dependent on execution scheduling.

#### Q15. Which of the following is NOT a necessary requirement to solve the Critical Section problem?
- A) Mutual Exclusion
- B) Progress
- C) Bounded Waiting
- D) Preemption
- **Answer: ✅ D**
- **Explanation**: The three requirements are Mutual Exclusion, Progress, and Bounded Waiting. Preemption is a design flag, not a correctness condition.

#### Q16. In Peterson's solution for two-process synchronization, process entry is controlled using:
- A) A single counting semaphore
- B) Hardware test-and-set instructions
- C) A flag array and a turn variable
- D) A binary mutex lock
- **Answer: ✅ C**
- **Explanation**: Peterson's is a software-based solution using `bool flag[2]` to show intent and `int turn` to yield priority.

#### Q17. The wait() operation on a semaphore S acts to:
- A) Increment the semaphore value and block if negative
- B) Decrement the semaphore value and block the process if S < 0
- C) Wake up a waiting process from the queue
- D) Release a Mutex lock
- **Answer: ✅ B**
- **Explanation**: `wait(S)` (or $P(S)$) decrements the semaphore value. If the value becomes negative, the executing process is added to the block queue.

#### Q18. What is the fundamental difference between a Mutex and a Binary Semaphore?
- A) A binary semaphore can take values up to $N$
- B) A Mutex has an ownership property: only the thread that locks it can unlock it
- C) Mutexes do not support mutual exclusion
- D) A binary semaphore is faster than a Mutex in user mode
- **Answer: ✅ B**
- **Explanation**: A mutex has ownership. A binary semaphore does not; one thread can wait on the semaphore, and a completely different thread can signal it.

---

## 🔷 Topic 4: Deadlocks

#### Q19. Which of the following is NOT one of the 4 necessary Coffman conditions for a deadlock?
- A) Hold and Wait
- B) Mutual Exclusion
- C) Circular Wait
- D) Resource Preemption
- **Answer: ✅ D**
- **Explanation**: The condition is **No Preemption** (resources cannot be forcibly taken). Preemption would actually *prevent* deadlocks.

#### Q20. If a Resource Allocation Graph (RAG) contains a cycle and resources have only a single instance:
- A) Deadlock might exist
- B) Deadlock definitely exists
- C) The system is in a safe state
- D) The cycle will resolve automatically
- **Answer: ✅ B**
- **Explanation**: In a single-instance RAG, a cycle is a necessary *and* sufficient condition for deadlock. If multiple instances exist, a cycle only indicates *possible* deadlock.

#### Q21. The Banker's Algorithm is used by an operating system to achieve:
- A) Deadlock Prevention
- B) Deadlock Avoidance
- C) Deadlock Detection
- D) Deadlock Recovery
- **Answer: ✅ B**
- **Explanation**: Banker's algorithm is an avoidance technique. It dynamically checks if allocating resources keeps the system in a "safe state".

#### Q22. To prevent deadlocks, breaking the "Hold and Wait" condition can be achieved by:
- A) Sharing all resources among all processes
- B) Forcing a process to request all its resources at once before execution
- C) Allowing resources to be preempted
- D) Restructuring resources in a strict hierarchy
- **Answer: ✅ B**
- **Explanation**: If a process must allocate all resources at once, it never holds some while waiting for others, thereby breaking Hold and Wait.

---

## 🔷 Topic 5: Memory Management

#### Q23. Paging solves the problem of:
- A) Internal Fragmentation
- B) External Fragmentation
- C) Virtual memory thrashing
- D) CPU starvation
- **Answer: ✅ B**
- **Explanation**: Since paging maps logical pages to non-contiguous physical frames, it eliminates external fragmentation. However, it can suffer from internal fragmentation in the last page.

#### Q24. In a paging system, the CPU generates a logical address containing:
- A) Page number and Page offset
- B) Frame number and Frame offset
- C) Segment table limit and Segment base
- D) Cache block and Tag
- **Answer: ✅ A**
- **Explanation**: The CPU-generated address has a page number ($p$) and page offset ($d$). The page table maps $p$ to a frame number $f$, while the offset $d$ remains unchanged.

#### Q25. What is the purpose of the Translation Lookaside Buffer (TLB)?
- A) To store temporary files during system boot
- B) To act as a fast hardware cache for page table lookups
- C) To replace secondary storage during page faults
- D) To schedule threads
- **Answer: ✅ B**
- **Explanation**: The TLB stores recently accessed page-to-frame translations in hardware, bypassing slow double memory references to the page table in RAM.

#### Q26. Let memory access time be $100\text{ ns}$ and TLB access time be $10\text{ ns}$. If the TLB hit ratio is $90\%$, what is the effective memory access time (EAT)?
- A) $110\text{ ns}$
- B) $120\text{ ns}$
- C) $100\text{ ns}$
- D) $130\text{ ns}$
- **Answer: ✅ B**
- **Explanation**: 
  - $\text{EAT} = h \times (t + m) + (1-h) \times (t + 2m)$
  - $\text{EAT} = 0.90 \times (10 + 100) + 0.10 \times (10 + 200)$
  - $\text{EAT} = 0.90 \times 110 + 0.10 \times 210 = 99 + 21 = 120\text{ ns}$.

#### Q27. Which page replacement algorithm can display Belady's Anomaly?
- A) Least Recently Used (LRU)
- B) First-In, First-Out (FIFO)
- C) Optimal (OPT)
- D) Least Frequently Used (LFU)
- **Answer: ✅ B**
- **Explanation**: Belady's Anomaly (where increasing the physical frame count increases page faults) can occur in FIFO. LRU and OPT do not exhibit this anomaly because they are stack algorithms.

#### Q28. A page fault occurs when:
- A) The page table gets corrupted
- B) The CPU references a page that is not currently loaded in main memory
- C) The program references an out-of-bounds pointer
- D) The TLB cache is full
- **Answer: ✅ B**
- **Explanation**: When a process references a page whose valid/invalid bit in the page table is set to "invalid" (meaning it's not in RAM), a page fault interrupt occurs, triggering the OS to fetch the page from disk.

#### Q29. Thrashing occurs in an operating system when:
- A) The CPU executes instructions too quickly for the system bus
- B) The system spends more time swapping pages in and out of disk than executing processes
- C) A process goes into an infinite loop
- D) Multiple disks in a RAID array crash simultaneously
- **Answer: ✅ B**
- **Explanation**: Thrashing happens when a process doesn't have enough frames allocated to support its active pages, leading to a constant cycle of page faults and page swapping.

#### Q30. Segmentation is a memory management scheme that:
- A) Divides memory into equal-sized pages
- B) Divides memory into variable-sized, logically meaningful segments
- C) Only works on secondary storage
- D) Prevents external fragmentation
- **Answer: ✅ B**
- **Explanation**: Segmentation divides memory into variable-sized blocks corresponding to logical units (like functions, stack, variables). It suffers from external fragmentation.

---

## 🔷 Topic 6: Storage, File Systems & Linux Commands

#### Q31. Which RAID level uses disk mirroring to write identical copies of data to separate drives, achieving 50% storage efficiency?
- A) RAID 0
- B) RAID 1
- C) RAID 5
- D) RAID 6
- **Answer: ✅ B**
- **Explanation**: RAID 1 (mirroring) clones data to two disks. It offers excellent fault tolerance but has a storage overhead of 50%.

#### Q32. In disk scheduling, the Shortest Seek Time First (SSTF) algorithm:
- A) Services requests in the order of their arrival
- B) Services requests closest to the current cylinder position of the disk head
- C) Moves the head from end to end like an elevator
- D) Suffers from no starvation
- **Answer: ✅ B**
- **Explanation**: SSTF selects the request that requires the least movement of the disk arm. It can cause starvation for far-away requests if closer ones keep arriving.

#### Q33. Which disk scheduling algorithm is also known as the "elevator" algorithm?
- A) FCFS
- B) SSTF
- C) SCAN
- D) C-LOOK
- **Answer: ✅ C**
- **Explanation**: SCAN moves the disk head in one direction servicing requests until it hits the end, then reverses direction, acting like an elevator.

#### Q34. An "Inode" in Unix-like file systems:
- A) Stores the actual file content blocks
- B) Is a directory containing user permissions
- C) Contains file metadata and pointers to data blocks
- D) Holds the system boot sector
- **Answer: ✅ C**
- **Explanation**: An inode (index node) contains properties (file size, permissions, owner, timestamps) and direct/indirect block pointers to the file's data blocks.

#### Q35. What does the Linux command `chmod 754 file.txt` do?
- A) Grants Read/Write/Execute to Owner, Read/Execute to Group, and Read to Others
- B) Grants Read/Write to Owner, Execute to Group, and Write to Others
- C) Deletes the file
- D) Changes the ownership of the file
- **Answer: ✅ A**
- **Explanation**: 
  - `7` (owner) = $4+2+1$ (rwx).
  - `5` (group) = $4+0+1$ (r-x).
  - `4` (others) = $4+0+0$ (r--).

#### Q36. Which command is used to display currently running processes in a Linux terminal?
- A) `ls`
- B) `df`
- C) `ps`
- D) `grep`
- **Answer: ✅ C**
- **Explanation**: `ps` (process status) displays active processes. `top` is also used for a real-time view.

#### Q37. To search for a specific text pattern inside files in a Linux system, which tool is used?
- A) `find`
- B) `grep`
- C) `du`
- D) `chmod`
- **Answer: ✅ B**
- **Explanation**: `grep` searches files for matching text lines using regular expressions.

---

## 🔷 Topic 7: Practice Conceptual Checkups

#### Q38. In a timeshare OS, what happens when a process's assigned time slice expires?
- A) It is terminated
- B) It transitions from Running to Ready
- C) It transitions from Running to Waiting
- D) It enters a deadlocked state
- **Answer: ✅ B**
- **Explanation**: When the quantum expires, the OS generates a timer interrupt, preempting the process from the CPU and placing it back in the Ready queue.

#### Q39. What is a system call?
- A) A hardware diagnostic function
- B) A program translation tool like a compiler
- C) The interface used by user-space applications to request services from the kernel
- D) An IPC network protocol
- **Answer: ✅ C**
- **Explanation**: System calls act as API interfaces between user programs and Kernel operations.

#### Q40. Which necessary condition of deadlock is broken if we share access to a database table for reading?
- A) Mutual Exclusion
- B) Hold and Wait
- C) No Preemption
- D) Circular Wait
- **Answer: ✅ A**
- **Explanation**: Read-only databases do not require exclusive lock access, breaking Mutual Exclusion.

#### Q41. In contiguous file allocation, the biggest drawback is:
- A) No support for direct access
- B) Huge directory structure overhead
- C) External fragmentation and file size growth issues
- D) Slow execution speed
- **Answer: ✅ C**
- **Explanation**: Contiguous allocation requires finding contiguous free blocks. This leads to external fragmentation over time and limits a file's ability to grow if adjacent blocks are occupied.

#### Q42. Which RAID level distributes striping and parity blocks across all disks (requiring at least 3 disks)?
- A) RAID 1
- B) RAID 5
- C) RAID 6
- D) RAID 0
- **Answer: ✅ B**
- **Explanation**: RAID 5 stripes data and distributes parity blocks across all disks, allowing recovery from a single drive crash.

#### Q43. What is the Belady's Anomaly condition?
- A) CPU utilization drops below 50%
- B) Page faults increase as physical frames increase (in FIFO)
- C) Mutex locks are held permanently
- D) Memory leaks crash the system
- **Answer: ✅ B**
- **Explanation**: It describes the anomaly where a larger memory frame pool leads to more page fault interrupts under FIFO.

#### Q44. The logical address space is mapped to physical address space at runtime by which hardware component?
- A) CPU Scheduler
- B) Memory Management Unit (MMU)
- C) Cache controller
- D) Disk Controller
- **Answer: ✅ B**
- **Explanation**: The MMU is the physical hardware circuit that translates virtual/logical addresses to physical RAM addresses.

#### Q45. Which of the following commands is used to display disk usage statistics in human-readable format?
- A) `df -h`
- B) `du -s`
- C) `top`
- D) `free`
- **Answer: ✅ A**
- **Explanation**: `df -h` reports disk space usage for all mounted file systems in human-readable terms (e.g., GB, MB).

#### Q46. What does the system call `exec()` do?
- A) Spawns a child process
- B) Replaces the current process's memory space with a new executable program
- C) Terminates the process
- D) Blocks execution until child finishes
- **Answer: ✅ B**
- **Explanation**: Unlike `fork()`, which creates a new process, `exec()` overwrites the calling process's memory space, registers, and stack with a new program.

#### Q47. The critical section problem is solved by Peterson's solution for how many processes?
- A) Exactly 2
- B) $N$ processes
- C) Infinite processes
- D) 1 process
- **Answer: ✅ A**
- **Explanation**: Peterson's algorithm is restricted to exactly two processes sharing a critical section.

#### Q48. Which memory type has the fastest access time?
- A) Cache memory
- B) Hard Disk
- C) CPU Registers
- D) RAM
- **Answer: ✅ C**
- **Explanation**: Registers are located directly inside the CPU, making their access speeds faster than cache (L1/L2/L3) and main memory.

#### Q49. A scheduler that selects which processes should be brought into the ready queue from disk is called:
- A) Short-term scheduler (CPU Scheduler)
- B) Long-term scheduler (Job Scheduler)
- C) Medium-term scheduler
- D) Dispatcher
- **Answer: ✅ B**
- **Explanation**: The long-term scheduler controls the degree of multiprogramming by loading processes from disk into RAM.

#### Q50. In a Resource Allocation Graph, a directed edge from a Resource ($R$) to a Process ($P$) represents:
- A) Process $P$ requesting Resource $R$
- B) Resource $R$ allocated to Process $P$
- C) Deadlocked resource
- D) Process $P$ releasing Resource $R$
- **Answer: ✅ B**
- **Explanation**: A directed edge from resource to process ($R \to P$) is an **assignment edge**. An edge from process to resource ($P \to R$) is a **request edge**.

---

# 🖥️ Operating System — Complete MCQ Bank
### All Possible MCQs with Answers & Explanations

> 📌 **How to use:** Try answering each question before revealing the answer. Explanations are given for every question so you understand *why*, not just *what*.

---

## 📚 SECTION 1 — FOUNDATIONS OF OPERATING SYSTEMS

---

**Q1.** What is an Operating System?

- A) A hardware component of a computer
- B) System software that acts as an interface between user and hardware
- C) An application program like a browser
- D) A type of RAM

✅ **Answer: B**
> The OS is system software — it manages hardware and provides services for applications. It is neither hardware nor a user application.

---

**Q2.** Which of the following is NOT a function of an Operating System?

- A) Process Management
- B) Memory Management
- C) Compiling source code
- D) Device Management

✅ **Answer: C**
> Compiling source code is the job of a compiler (application software), not the OS. The OS manages processes, memory, devices, and files.

---

**Q3.** The Operating System acts as an interface between:

- A) Hardware and Application Software
- B) User and Application Software
- C) CPU and RAM
- D) Keyboard and Monitor

✅ **Answer: A**
> The OS sits between hardware and application software — it hides hardware complexity from programmers and users.

---

**Q4.** Which of the following is the correct layer order from bottom to top in a computer system?

- A) User → OS → Hardware → Applications
- B) Hardware → OS → Applications → User
- C) Applications → OS → User → Hardware
- D) Hardware → Applications → OS → User

✅ **Answer: B**
> The layered model goes: Hardware → OS → Applications → User. The OS manages hardware and provides services to applications.

---

**Q5.** The three main objectives of an OS are:

- A) Speed, Security, Storage
- B) Ease, Efficiency, Evolution
- C) Portability, Security, Speed
- D) Multitasking, Multiprocessing, Networking

✅ **Answer: B**
> The 3 E's: **Ease** (convenience), **Efficiency** (optimal resource use), **Evolution** (allow updates without breaking old software).

---

**Q6.** Which part of the OS is always loaded in RAM from boot to shutdown?

- A) Device Driver
- B) User Interface
- C) Kernel
- D) File System

✅ **Answer: C**
> The **kernel** is the core of the OS and is always resident in RAM. It runs in privileged mode and manages all critical functions.

---

**Q7.** User Mode (Ring 3) differs from Kernel Mode (Ring 0) because:

- A) User Mode has full hardware access; Kernel Mode is restricted
- B) Kernel Mode has full hardware access; User Mode is restricted
- C) Both have equal access to hardware
- D) User Mode is faster than Kernel Mode

✅ **Answer: B**
> **Kernel Mode (Ring 0)** has full hardware access. **User Mode (Ring 3)** is restricted — applications cannot directly touch hardware.

---

**Q8.** A system call is:

- A) A hardware interrupt
- B) A way for user programs to request OS services
- C) A type of device driver
- D) A method for CPU to access RAM

✅ **Answer: B**
> System calls are the interface between user programs and the OS kernel. They cause a switch from user mode to kernel mode.

---

**Q9.** Which system call is used to create a new process in Unix/Linux?

- A) `exec()`
- B) `kill()`
- C) `fork()`
- D) `wait()`

✅ **Answer: C**
> `fork()` creates a new process (child process) that is a copy of the calling (parent) process. `exec()` replaces the process image.

---

**Q10.** When a system call is made, the CPU switches from:

- A) Kernel Mode to User Mode
- B) User Mode to Kernel Mode
- C) Ring 0 to Ring 3
- D) RAM to Cache

✅ **Answer: B**
> System calls trigger a **User Mode → Kernel Mode** switch (Ring 3 → Ring 0). After the service is done, CPU switches back.

---

**Q11.** Which kernel type runs all OS services in a single large program in kernel space?

- A) Microkernel
- B) Hybrid Kernel
- C) Monolithic Kernel
- D) Exokernel

✅ **Answer: C**
> **Monolithic kernel** has all OS services (memory, file system, device drivers, IPC) in one large kernel-space program. Fast but fragile.

---

**Q12.** In a Microkernel, which services run in User Space?

- A) Only scheduling
- B) File servers, device drivers, and network services
- C) All OS services including scheduling
- D) Only memory management

✅ **Answer: B**
> Microkernel keeps only bare minimum (scheduling, IPC, basic memory) in kernel space. File servers, drivers, and network run as user-space processes.

---

**Q13.** Which of the following is an example of a Monolithic Kernel?

- A) MINIX
- B) QNX
- C) Linux
- D) Windows NT

✅ **Answer: C**
> **Linux** uses a monolithic kernel. MINIX and QNX use microkernels. Windows NT uses a hybrid kernel.

---

**Q14.** Which of the following is an example of a Hybrid Kernel?

- A) Linux
- B) MINIX
- C) macOS (XNU)
- D) FreeRTOS

✅ **Answer: C**
> **macOS** uses the XNU kernel which is a hybrid. Windows NT is also hybrid. Linux is monolithic, MINIX is microkernel.

---

**Q15.** Which system call category includes `open()`, `read()`, `write()`, `close()`?

- A) Process Control
- B) File Management
- C) Device Management
- D) Communication

✅ **Answer: B**
> `open()`, `read()`, `write()`, `close()` are **File Management** system calls used to work with files on disk.

---

## 📚 SECTION 2 — TYPES OF OPERATING SYSTEMS

---

**Q16.** In a Batch Operating System, jobs are:

- A) Executed one by one with user interaction
- B) Grouped by similarity and executed automatically without user interaction
- C) Executed in real-time with strict deadlines
- D) Distributed across multiple computers

✅ **Answer: B**
> Batch OS groups similar jobs and runs them automatically. No user interaction happens during execution.

---

**Q17.** What is the main disadvantage of a Batch Operating System?

- A) Too expensive to implement
- B) No interactive debugging; slow turnaround time
- C) Requires multiple CPUs
- D) Cannot run multiple programs

✅ **Answer: B**
> In batch OS, you submit a job and wait for results. If there's an error, you only find out after the whole batch runs — no interactive debugging.

---

**Q18.** A Time-Sharing OS allocates CPU using:

- A) Priority values
- B) Job size
- C) Time slices (quanta)
- D) Arrival order only

✅ **Answer: C**
> Time-sharing OS rotates CPU access among processes using fixed **time slices (quanta)**. Each process gets a turn rapidly.

---

**Q19.** Which type of OS is UNIX considered?

- A) Batch OS only
- B) Real-Time OS
- C) Time-Sharing and Multiprogramming OS
- D) Embedded OS

✅ **Answer: C**
> UNIX is a classic example of both **time-sharing** (multiple users share CPU) and **multiprogramming** (multiple programs in RAM simultaneously).

---

**Q20.** Multiprogramming increases CPU utilization by:

- A) Using multiple CPUs simultaneously
- B) Switching CPU to another process when current process waits for I/O
- C) Giving each user a fixed time slice
- D) Running one process at maximum speed

✅ **Answer: B**
> In multiprogramming, when a process is waiting for I/O, the CPU switches to another process — keeping the CPU busy instead of idle.

---

**Q21.** The key difference between Multiprogramming and Multitasking is:

- A) Multiprogramming is for multiple CPUs; Multitasking is for single CPU
- B) Multiprogramming switches on I/O wait; Multitasking switches on time intervals
- C) Multitasking supports more users than multiprogramming
- D) They are exactly the same thing

✅ **Answer: B**
> **Multiprogramming** switches the CPU when a process waits for I/O. **Multitasking (Time-sharing)** switches based on fixed time intervals.

---

**Q22.** In Symmetric Multiprocessing (SMP):

- A) One master CPU controls all other CPUs
- B) All CPUs are equal and share the same memory
- C) Each CPU has its own private memory
- D) One CPU handles I/O; others handle computation

✅ **Answer: B**
> In **SMP**, all processors are equal — they share the same RAM and OS and can run any task. Linux on multi-core uses SMP.

---

**Q23.** A Hard Real-Time OS is used when:

- A) Response time is measured in seconds
- B) Missing a deadline causes degraded performance
- C) Missing a deadline is catastrophic (system failure)
- D) Multiple users share the system

✅ **Answer: C**
> **Hard RTOS**: missing the deadline is unacceptable — like airbag deployment or pacemaker. **Soft RTOS**: missing deadline is OK with degraded quality.

---

**Q24.** Which of the following is an example of a Hard Real-Time OS application?

- A) YouTube video buffering
- B) VoIP phone calls
- C) Airbag deployment system in a car
- D) Online multiplayer game

✅ **Answer: C**
> Airbag deployment **must** happen within milliseconds. Missing the deadline means the airbag fails to deploy — catastrophic. This is Hard RTOS.

---

**Q25.** A Distributed OS makes multiple computers appear as:

- A) Multiple independent systems
- B) A single unified system to the user
- C) A network of virtual machines
- D) Multiple user accounts on one machine

✅ **Answer: B**
> In a **Distributed OS**, multiple independent computers connected via network appear as ONE system to the end user.

---

**Q26.** Which of the following is an advantage of a Distributed OS?

- A) No need for a network
- B) Single point of failure
- C) Fault tolerance — no single point of failure
- D) Runs on a single processor only

✅ **Answer: C**
> Distributed OS provides **fault tolerance** — if one machine fails, others continue working. There is no single point of failure.

---

**Q27.** An Embedded OS is best characterized by:

- A) Supporting multiple users and applications
- B) Being lightweight, dedicated to one specific task, built into the device
- C) Running on high-end server hardware
- D) Providing a full graphical user interface

✅ **Answer: B**
> Embedded OS is **minimal, purpose-built**, and burned into the device's ROM. Examples: microwave firmware, car ECU, printer firmware.

---

**Q28.** Android and iOS are examples of which type of OS?

- A) Batch OS
- B) Distributed OS
- C) Real-Time OS
- D) Mobile OS

✅ **Answer: D**
> Android and iOS are **Mobile Operating Systems**, specifically designed for touchscreen devices with features like battery optimization and mobile apps.

---

**Q29.** Which type of OS uses the concept of "time quantum"?

- A) Batch OS
- B) Time-Sharing OS
- C) Embedded OS
- D) Batch and Embedded OS

✅ **Answer: B**
> **Time-Sharing OS** uses time quanta (slices) to rapidly switch between processes/users, creating the illusion of simultaneous execution.

---

**Q30.** A Network Operating System (NOS) is different from a Distributed OS because:

- A) NOS appears as one system; Distributed OS does not
- B) Distributed OS appears as one system; NOS does not — users are aware of multiple machines
- C) NOS is only for mobile devices
- D) They are identical concepts

✅ **Answer: B**
> In **Distributed OS**, users see one unified system. In **NOS**, users are aware of separate machines — they explicitly log into servers for file sharing etc.

---

## 📚 SECTION 3 — PROCESS MANAGEMENT

---

**Q31.** The difference between a Program and a Process is:

- A) A program is active; a process is passive
- B) A process is a program in execution (active); a program is static code on disk
- C) They are the same thing
- D) A program uses RAM; a process does not

✅ **Answer: B**
> A **program** is static code stored on disk. A **process** is that code actively executing in RAM, with CPU time, memory, and file handles allocated.

---

**Q32.** The data structure that stores all information about a process is called:

- A) Page Table
- B) Segment Table
- C) Process Control Block (PCB)
- D) Ready Queue

✅ **Answer: C**
> The **PCB (Process Control Block)** stores PID, state, program counter, CPU registers, memory limits, open files, and priority — everything the OS needs to manage a process.

---

**Q33.** Which of the following is NOT stored in a PCB?

- A) Process ID (PID)
- B) Program Counter
- C) Source code of the program
- D) CPU Registers

✅ **Answer: C**
> The PCB stores runtime state information (PID, state, PC, registers, memory limits) — NOT the source code. Source code is on disk.

---

**Q34.** In the Process State diagram, which transition happens when the CPU scheduler selects a process from the Ready Queue?

- A) New → Ready
- B) Running → Waiting
- C) Ready → Running (Dispatch)
- D) Waiting → Ready

✅ **Answer: C**
> When the scheduler **dispatches** a process, it moves from **Ready → Running**. This is when the CPU is actually assigned to the process.

---

**Q35.** A process moves from Running to Waiting state when:

- A) Its time quantum expires
- B) It requests I/O or waits for an event
- C) It is first created
- D) It finishes execution

✅ **Answer: B**
> **Running → Waiting** happens when a process makes an I/O request (e.g., reading a file) and must wait for the operation to complete.

---

**Q36.** A process moves from Waiting to Ready state when:

- A) It receives CPU time
- B) Its time quantum expires
- C) Its I/O operation completes
- D) It makes a new I/O request

✅ **Answer: C**
> **Waiting → Ready** happens when the I/O operation (or event) that the process was waiting for **completes**. The process is now ready to use CPU again.

---

**Q37.** During a Context Switch:

- A) Two processes execute simultaneously
- B) The state of the current process is saved and another process's state is loaded
- C) The OS terminates the current process
- D) Memory is reallocated to all processes

✅ **Answer: B**
> A **context switch** saves the current process's state (to PCB) and loads the next process's state. During this switch, no useful work is done — it is pure overhead.

---

**Q38.** Context switching is considered overhead because:

- A) It increases CPU speed
- B) No useful computation is done during the switch
- C) It reduces memory usage
- D) It terminates old processes

✅ **Answer: B**
> During a context switch, the CPU is busy saving and restoring states — it produces no useful output. Too many switches waste CPU time.

---

**Q39.** Which process state means the process has been created but not yet admitted to the ready queue?

- A) Ready
- B) Waiting
- C) New
- D) Suspended

✅ **Answer: C**
> The **New** state is when a process is just being created (e.g., OS is allocating PCB and memory). It moves to Ready once admitted.

---

**Q40.** When a process finishes execution, it enters which state?

- A) Waiting
- B) Blocked
- C) Terminated
- D) Suspended

✅ **Answer: C**
> A process enters the **Terminated** state after completing execution (or after an error/abort). The OS then cleans up its resources (PCB, memory, file handles).

---

## 📚 SECTION 4 — CPU SCHEDULING ALGORITHMS

---

**Q41.** TurnAround Time (TAT) is calculated as:

- A) Burst Time − Waiting Time
- B) Completion Time − Arrival Time
- C) Completion Time − Burst Time
- D) Arrival Time + Burst Time

✅ **Answer: B**
> **TAT = CT − AT** (Completion Time minus Arrival Time). It is the total time from when a process arrives to when it finishes.

---

**Q42.** Waiting Time (WT) is calculated as:

- A) TAT + BT
- B) CT − AT
- C) TAT − BT
- D) BT − AT

✅ **Answer: C**
> **WT = TAT − BT**. Since TAT = CT − AT, we get WT = (CT − AT) − BT. It is the time spent waiting in the ready queue.

---

**Q43.** Which scheduling algorithm is Non-Preemptive and executes processes in arrival order?

- A) Round Robin
- B) SRTF
- C) FCFS
- D) Priority (Preemptive)

✅ **Answer: C**
> **FCFS (First Come First Served)** is non-preemptive and strictly follows arrival order. Once started, a process runs until done.

---

**Q44.** The "Convoy Effect" is a problem associated with which scheduling algorithm?

- A) Round Robin
- B) SJF
- C) FCFS
- D) Priority Scheduling

✅ **Answer: C**
> **Convoy Effect** is FCFS's major problem — a long process at the front holds up all short processes behind it, like a slow truck holding up cars.

---

**Q45.** Which scheduling algorithm gives the minimum average waiting time theoretically?

- A) FCFS
- B) Round Robin
- C) SJF (Shortest Job First)
- D) Priority Scheduling

✅ **Answer: C**
> **SJF** is proven to give the **minimum average waiting time** among all non-preemptive algorithms. This is its key advantage.

---

**Q46.** SJF scheduling can lead to which problem?

- A) Convoy Effect
- B) Thrashing
- C) Starvation of long processes
- D) Deadlock

✅ **Answer: C**
> In SJF, if short jobs keep arriving, long jobs may **never get CPU time** — this is called **starvation**. Solution: Aging.

---

**Q47.** SRTF (Shortest Remaining Time First) is the preemptive version of:

- A) FCFS
- B) Priority Scheduling
- C) Round Robin
- D) SJF

✅ **Answer: D**
> **SRTF** is Preemptive SJF. At every moment, if a new process arrives with shorter remaining burst time, it preempts the current process.

---

**Q48.** In Priority Scheduling, starvation is solved by:

- A) Increasing Time Quantum
- B) Aging — gradually increasing priority of waiting processes
- C) Adding more CPUs
- D) Using FCFS instead

✅ **Answer: B**
> **Aging** prevents starvation by increasing a process's priority the longer it waits. Eventually even low-priority processes get high enough priority to run.

---

**Q49.** Round Robin scheduling is:

- A) Non-Preemptive
- B) Preemptive with fixed time quantum
- C) Non-preemptive with priority
- D) Preemptive based on burst time

✅ **Answer: B**
> **Round Robin** is **preemptive** — each process is given a fixed time quantum (Q). When Q expires, the process is preempted and added to the back of the ready queue.

---

**Q50.** If Time Quantum in Round Robin is set very large (approaching infinity), it behaves like:

- A) SJF
- B) SRTF
- C) Priority Scheduling
- D) FCFS

✅ **Answer: D**
> A very large time quantum means each process runs to completion before the next one starts — identical behavior to **FCFS**.

---

**Q51.** If Time Quantum in Round Robin is set very small, the major drawback is:

- A) Starvation of long processes
- B) Excessive context switching overhead
- C) Convoy Effect
- D) No fairness between processes

✅ **Answer: B**
> Very small quantum → too many context switches → CPU wastes most of its time switching rather than doing useful work.

---

**Q52.** Which scheduling algorithm does NOT cause starvation?

- A) SJF
- B) Priority Scheduling
- C) SRTF
- D) Round Robin

✅ **Answer: D**
> **Round Robin** does NOT cause starvation because every process gets CPU time in rotation — no process is permanently skipped.

---

**Q53.** In which scheduling algorithm does a higher-priority process preempt a running lower-priority process immediately?

- A) Non-Preemptive Priority Scheduling
- B) FCFS
- C) Preemptive Priority Scheduling
- D) SJF

✅ **Answer: C**
> In **Preemptive Priority Scheduling**, if a higher-priority process arrives while a lower-priority process is running, the running process is immediately preempted.

---

**Q54.** Multilevel Feedback Queue (MLFQ) differs from Multilevel Queue because:

- A) MLFQ has only one queue
- B) In MLFQ, processes can move between queues based on behavior
- C) MLFQ uses only FCFS
- D) MLFQ does not allow preemption

✅ **Answer: B**
> **MLFQ** allows processes to **move between queues** based on their CPU usage history. CPU-intensive processes move to lower-priority queues; I/O-bound processes stay high.

---

**Q55.** Given P1(AT=0, BT=4), P2(AT=1, BT=3), P3(AT=2, BT=1) under SJF Non-Preemptive, what is the execution order?

- A) P1 → P2 → P3
- B) P3 → P2 → P1
- C) P1 → P3 → P2
- D) P2 → P3 → P1

✅ **Answer: C**
> At t=0, only P1 is available → P1 runs (BT=4, completes at t=4). At t=4, P2(BT=3) and P3(BT=1) available → Shortest first: P3 then P2. Order: P1 → P3 → P2.

---

**Q56.** Response Time is defined as:

- A) Time from arrival to completion
- B) Time spent waiting in ready queue
- C) Time from arrival to FIRST CPU response
- D) Total burst time

✅ **Answer: C**
> **Response Time = time from process arrival to the first time it gets the CPU**. For interactive systems, minimizing response time is critical.

---

**Q57.** Which algorithm has the best (lowest) Response Time in a time-sharing environment?

- A) FCFS
- B) SJF
- C) Round Robin
- D) Priority Scheduling (Non-Preemptive)

✅ **Answer: C**
> **Round Robin** gives the best response time in interactive systems because every process gets CPU time quickly in rotation.

---

**Q58.** Throughput in CPU scheduling is defined as:

- A) CPU utilization percentage
- B) Number of processes completed per unit time
- C) Average waiting time
- D) Total burst time of all processes

✅ **Answer: B**
> **Throughput = Number of processes completed / Total time**. A good scheduler maximizes throughput along with minimizing waiting time.

---

## 📚 SECTION 5 — MEMORY MANAGEMENT

---

**Q59.** The purpose of Memory Management in an OS is:

- A) To increase CPU speed
- B) To allocate, track, and protect memory among processes
- C) To manage files on disk
- D) To handle network communication

✅ **Answer: B**
> Memory Management tracks which parts of RAM are in use, allocates memory to processes, protects processes from each other, and frees memory when processes exit.

---

**Q60.** Internal Fragmentation occurs when:

- A) Free memory is scattered in small non-contiguous chunks
- B) Allocated memory block is larger than what the process actually needs
- C) Memory is divided into variable-sized segments
- D) A process accesses another process's memory

✅ **Answer: B**
> **Internal fragmentation**: wasted space **inside** an allocated block. E.g., process needs 9 KB, gets 12 KB (3 pages of 4 KB each) → 3 KB wasted inside.

---

**Q61.** External Fragmentation occurs when:

- A) Allocated memory is larger than needed
- B) There is enough total free memory but it is scattered in non-contiguous chunks
- C) A process accesses invalid memory
- D) All memory is used by a single process

✅ **Answer: B**
> **External fragmentation**: enough total free memory exists but is in small scattered gaps that can't satisfy a contiguous allocation request.

---

**Q62.** Paging eliminates which type of fragmentation?

- A) Internal Fragmentation
- B) Both Internal and External
- C) External Fragmentation
- D) Neither — paging causes more fragmentation

✅ **Answer: C**
> **Paging eliminates External Fragmentation** because any free frame anywhere in RAM can be used — pages don't need to be contiguous. However, it can cause internal fragmentation in the last page.

---

**Q63.** In Paging, the physical memory is divided into fixed-size units called:

- A) Pages
- B) Segments
- C) Frames
- D) Blocks

✅ **Answer: C**
> Physical memory (RAM) is divided into **Frames**. Logical memory (process view) is divided into **Pages**. Both are the same size.

---

**Q64.** In Paging, the logical memory (process view) is divided into fixed-size units called:

- A) Frames
- B) Pages
- C) Segments
- D) Sectors

✅ **Answer: B**
> **Pages** are the fixed-size units of logical (virtual) memory. **Frames** are the fixed-size units of physical RAM. A page maps to a frame via the page table.

---

**Q65.** The Page Table is used to:

- A) Store process priority information
- B) Map logical page numbers to physical frame numbers
- C) Track available disk space
- D) Store process scheduling information

✅ **Answer: B**
> The **Page Table** maps each logical page number (p) to the physical frame number (f) in RAM. The MMU uses this table for every memory access.

---

**Q66.** What is the TLB (Translation Lookaside Buffer)?

- A) A type of secondary storage
- B) A cache for page table entries to speed up address translation
- C) A replacement for the page table
- D) A buffer for disk I/O operations

✅ **Answer: B**
> **TLB** is a small, fast hardware cache that stores recently used page-to-frame mappings. A TLB hit avoids a RAM lookup for the page table — much faster.

---

**Q67.** A TLB miss means:

- A) The requested page is not in RAM (page fault)
- B) The page table entry is not in the TLB, so the page table in RAM must be checked
- C) The frame is full
- D) The process must be terminated

✅ **Answer: B**
> **TLB miss**: the mapping is not in the TLB → must look up the page table in RAM (slower). This is different from a page fault (page not in RAM at all).

---

**Q68.** Segmentation divides memory into:

- A) Fixed-size equal blocks
- B) Variable-size logical units (code, data, stack, heap)
- C) Rows and columns
- D) Fixed-size frames

✅ **Answer: B**
> **Segmentation** divides a program into variable-size **logical segments** based on meaning: code segment, data segment, stack segment, heap segment.

---

**Q69.** Segmentation causes which type of fragmentation?

- A) Internal Fragmentation
- B) Both types
- C) No Fragmentation
- D) External Fragmentation

✅ **Answer: D**
> **Segmentation causes External Fragmentation** because variable-size segments leave scattered holes in memory. It does NOT cause internal fragmentation (segments are exactly as needed).

---

**Q70.** A Segmentation Fault occurs when:

- A) A page is not found in RAM
- B) The offset in an address exceeds the segment's limit
- C) The page table is full
- D) The TLB is empty

✅ **Answer: B**
> **Segmentation Fault**: when the offset `d` ≥ Segment Limit. The OS detects the process is trying to access memory outside its segment and terminates it.

---

**Q71.** Which of the following correctly compares Paging and Segmentation?

| Feature | Paging | Segmentation |
|---|---|---|
| Division | Fixed-size | Variable-size |
| External Fragmentation | None | Yes |
| Internal Fragmentation | Yes (last page) | None |

- A) The table above is correct
- B) Paging has external fragmentation; Segmentation has internal
- C) Both have only external fragmentation
- D) Neither has any fragmentation

✅ **Answer: A**
> This is a frequently asked comparison. Paging: fixed-size pages, no external frag, yes internal frag. Segmentation: variable-size, yes external frag, no internal frag.

---

**Q72.** Virtual Memory allows:

- A) CPU to execute multiple instructions simultaneously
- B) Processes larger than physical RAM to execute by using disk as extension
- C) Multiple CPUs to share one RAM
- D) RAM to be used as a cache for CPU registers

✅ **Answer: B**
> **Virtual Memory** uses disk (swap space) as an extension of RAM, creating the illusion that the system has more memory than physically available.

---

**Q73.** Demand Paging means:

- A) All pages of a process are loaded at startup
- B) Pages are loaded into RAM only when they are actually accessed (demanded)
- C) Pages are loaded based on priority
- D) Pages are loaded from the internet

✅ **Answer: B**
> **Demand Paging**: only load a page when the CPU actually tries to access it. This saves RAM by not loading pages that may never be used.

---

**Q74.** A Page Fault occurs when:

- A) A page in RAM is corrupt
- B) The CPU tries to access a page that is NOT currently in RAM
- C) The page table is full
- D) Two processes access the same page simultaneously

✅ **Answer: B**
> **Page Fault**: CPU references a page, checks the page table, finds the "valid bit" = 0 (page not in RAM), and triggers a page fault interrupt. The OS then loads the page from disk.

---

**Q75.** After a page fault, the OS:

- A) Terminates the process
- B) Loads the missing page from disk into RAM, updates page table, and restarts the instruction
- C) Sends an error to the user
- D) Increases the page size

✅ **Answer: B**
> After a page fault: (1) Find page on disk, (2) Load into a free frame (evict one if needed), (3) Update page table, (4) **Restart** the faulting instruction.

---

**Q76.** The Logical Address in paging is divided into:

- A) Segment number and offset
- B) Frame number and offset
- C) Page number and offset
- D) Block number and sector

✅ **Answer: C**
> In paging, **Logical Address = [Page Number (p)] [Offset (d)]**. The page number is used to look up the frame number in the page table.

---

**Q77.** If page size is 4 KB and a process needs 9 KB, how many pages are allocated and how much internal fragmentation occurs?

- A) 2 pages, 0 KB waste
- B) 3 pages, 3 KB waste
- C) 2 pages, 1 KB waste
- D) 4 pages, 7 KB waste

✅ **Answer: B**
> 9 KB ÷ 4 KB = 2.25 → need **3 pages** = 12 KB allocated. Internal fragmentation = 12 − 9 = **3 KB** wasted in the third page.

---

**Q78.** The MMU (Memory Management Unit) is responsible for:

- A) Managing secondary storage
- B) Translating logical addresses to physical addresses
- C) Scheduling CPU among processes
- D) Managing network packets

✅ **Answer: B**
> The **MMU** is hardware that automatically translates every **logical address** the CPU generates into the corresponding **physical address** in RAM.

---

## 📚 SECTION 6 — PAGE REPLACEMENT ALGORITHMS

---

**Q79.** FIFO Page Replacement Algorithm evicts:

- A) The page used least recently
- B) The page that will not be used for the longest time
- C) The page that has been in RAM the longest (oldest)
- D) The page with the lowest priority

✅ **Answer: C**
> **FIFO** evicts the page that has been in RAM the **longest time** (oldest page), regardless of how recently it was used.

---

**Q80.** Belady's Anomaly states that:

- A) LRU always causes more page faults than FIFO
- B) Adding more frames always reduces page faults for all algorithms
- C) FIFO can have MORE page faults with MORE frames
- D) Optimal algorithm causes more page faults than LRU

✅ **Answer: C**
> **Belady's Anomaly**: in FIFO, increasing the number of frames can sometimes **increase** page faults — counterintuitive! LRU and OPT are immune to this.

---

**Q81.** Which page replacement algorithm is immune to Belady's Anomaly?

- A) FIFO only
- B) LRU and Optimal
- C) FIFO and LRU
- D) All algorithms are immune

✅ **Answer: B**
> **LRU and Optimal** are immune to Belady's Anomaly. Adding more frames will never increase page faults with these algorithms (they belong to the "stack algorithm" family).

---

**Q82.** LRU (Least Recently Used) Page Replacement evicts:

- A) The oldest page in RAM
- B) The page that will not be needed for the longest future time
- C) The page that was used least recently (longest time ago)
- D) The page with the smallest page number

✅ **Answer: C**
> **LRU** evicts the page that was **last used the longest time ago**. It uses past access history as a predictor of future use.

---

**Q83.** The Optimal (OPT) Page Replacement Algorithm:

- A) Uses past access history to make decisions
- B) Evicts the page that will not be used for the longest time in the FUTURE
- C) Is the same as LRU
- D) Can be easily implemented in any OS

✅ **Answer: B**
> **Optimal** evicts the page not needed for the longest time in the **future**. It gives minimum page faults but is **impossible to implement** (requires future knowledge).

---

**Q84.** Why is the Optimal Page Replacement Algorithm impractical?

- A) It causes too many page faults
- B) It requires knowing the future sequence of page references
- C) It is too slow to compute
- D) It only works with 3 or fewer frames

✅ **Answer: B**
> OPT requires knowing which pages will be referenced in the **future** — something an OS cannot know at runtime. It is used only as a theoretical benchmark.

---

**Q85.** In page replacement, given reference string 1,2,3,1,2,3 with 3 frames using FIFO, how many page faults occur?

- A) 3
- B) 4
- C) 6
- D) 0

✅ **Answer: A**
> Ref 1: [1,-,-] FAULT, Ref 2: [1,2,-] FAULT, Ref 3: [1,2,3] FAULT, Ref 1: HIT ✓, Ref 2: HIT ✓, Ref 3: HIT ✓. Total = **3 faults**.

---

**Q86.** Thrashing occurs when:

- A) CPU utilization is at 100%
- B) Processes spend more time waiting for pages than executing
- C) Too many processes are terminated simultaneously
- D) The page table becomes too large

✅ **Answer: B**
> **Thrashing**: each process has too few frames → constant page faults → processes spend more time in I/O wait for pages than doing actual computation → CPU utilization drops drastically.

---

**Q87.** The Working Set Model is used to:

- A) Determine the optimal time quantum for Round Robin
- B) Identify the set of pages a process is actively using and ensure they stay in RAM
- C) Calculate the maximum number of processes in the ready queue
- D) Manage the page table size

✅ **Answer: B**
> **Working Set Model**: the "working set" is the set of pages a process has referenced recently. If all working set pages are in RAM, thrashing is prevented.

---

**Q88.** Which of the following correctly ranks page replacement algorithms by number of page faults (best to worst)?

- A) FIFO < LRU < Optimal
- B) Optimal < LRU < FIFO
- C) LRU < Optimal < FIFO
- D) FIFO < Optimal < LRU

✅ **Answer: B**
> **Optimal** has the fewest faults (theoretical minimum). **LRU** is next best. **FIFO** generally has the most faults. Order: **Optimal < LRU < FIFO**.

---

## 📚 SECTION 7 — PROCESS SYNCHRONIZATION

---

**Q89.** A Race Condition occurs when:

- A) Two processes run on two different CPUs
- B) The output of a program depends on the timing/order of concurrent access to shared data
- C) A process runs faster than another
- D) CPU scheduling is unfair

✅ **Answer: B**
> **Race Condition**: multiple processes access shared data concurrently and the final result depends on who executes last. The result is non-deterministic.

---

**Q90.** The Critical Section of a process is:

- A) The fastest executing part of the code
- B) The section where shared resources are accessed — only one process should be here at a time
- C) The first instruction of a program
- D) Code that handles exceptions

✅ **Answer: B**
> The **Critical Section** is the code segment that accesses shared data (memory, files, etc.). Only ONE process should execute its critical section at any time.

---

**Q91.** Which of the following is NOT a requirement for solving the Critical Section Problem?

- A) Mutual Exclusion
- B) Progress
- C) Bounded Waiting
- D) Fairness in CPU Allocation

✅ **Answer: D**
> The three requirements are **Mutual Exclusion, Progress, and Bounded Waiting**. CPU allocation fairness is a scheduling concern, not a Critical Section requirement.

---

**Q92.** Mutual Exclusion means:

- A) Multiple processes can be in the critical section simultaneously
- B) Only one process can be in the critical section at a time
- C) All processes must wait forever before entering critical section
- D) Processes must enter critical section in arrival order

✅ **Answer: B**
> **Mutual Exclusion**: at most ONE process is allowed inside the critical section at any given time. This prevents race conditions.

---

**Q93.** The Progress requirement for Critical Section solution means:

- A) All processes must make forward progress in their execution
- B) If no process is in CS, a waiting process must be allowed to enter without indefinite postponement
- C) Processes must execute their critical section in a fixed order
- D) CPU must be 100% utilized

✅ **Answer: B**
> **Progress**: if no process is in CS, the decision of who enters next must be made in finite time. An empty CS cannot remain locked — that would be incorrect.

---

**Q94.** Bounded Waiting means:

- A) Wait time is proportional to burst time
- B) A process must get to enter CS within a bounded number of times others enter CS after the request
- C) Only a fixed number of processes can wait at a time
- D) Process priority determines wait time

✅ **Answer: B**
> **Bounded Waiting**: after a process requests to enter CS, there's a limit on how many times other processes can enter CS before it gets its turn. No process waits forever.

---

**Q95.** A Semaphore is:

- A) A hardware component for memory management
- B) An integer variable used for process synchronization via wait() and signal() operations
- C) A type of CPU scheduling algorithm
- D) A method for inter-process communication using sockets

✅ **Answer: B**
> A **semaphore** is an integer variable. Processes use `wait(S)` (decrement, potentially block) and `signal(S)` (increment, potentially wake a process) for synchronization.

---

**Q96.** What does `wait(S)` (P operation) do?

- A) S = S + 1; wake up a waiting process if any
- B) S = S − 1; block the calling process if S < 0
- C) Check if S > 0 and proceed without changing S
- D) Reset S to its initial value

✅ **Answer: B**
> `wait(S)`: **S = S − 1**. If S < 0 after decrement, the calling process is **blocked** and added to the semaphore's waiting queue.

---

**Q97.** What does `signal(S)` (V operation) do?

- A) S = S − 1; block the process
- B) S = S + 1; wake up one waiting process if S ≤ 0 (before increment)
- C) Reset S to 0
- D) Check if S > 0

✅ **Answer: B**
> `signal(S)`: **S = S + 1**. If S ≤ 0 (meaning processes were waiting), wake up one process from the waiting queue.

---

**Q98.** A Binary Semaphore can take values:

- A) Any positive integer
- B) 0 or 1 only
- C) −1, 0, or 1
- D) Any integer from 0 to infinity

✅ **Answer: B**
> A **binary semaphore** is restricted to values **0 or 1**. It acts like a lock (0 = locked, 1 = unlocked) and is used for mutual exclusion.

---

**Q99.** A Counting Semaphore is used for:

- A) Mutual exclusion only
- B) Counting and controlling access to a pool of identical resources
- C) CPU scheduling
- D) Memory allocation

✅ **Answer: B**
> A **counting semaphore** tracks a count of available instances of a resource (e.g., 5 printer slots). Its value can be any non-negative integer.

---

**Q100.** The key difference between a Mutex and a Binary Semaphore is:

- A) Mutex can be 0, 1, or 2; semaphore can only be 0 or 1
- B) Only the process that locked a Mutex can unlock it (ownership); any process can signal a semaphore
- C) Mutex is faster than semaphore in all cases
- D) Semaphore is only for file operations

✅ **Answer: B**
> **Mutex has ownership**: the thread/process that acquires it must be the one to release it. A **binary semaphore** has no ownership — any process can call signal().

---

**Q101.** In the Producer-Consumer Problem, the semaphore `empty` is initialized to:

- A) 0
- B) 1
- C) N (buffer size)
- D) −1

✅ **Answer: C**
> `empty = N` (number of empty buffer slots initially). It counts available slots for the producer. `full = 0` (no items yet). `mutex = 1` (binary semaphore for access).

---

**Q102.** In the Dining Philosophers Problem, if all philosophers pick up their LEFT fork simultaneously, the result is:

- A) All philosophers eat successfully
- B) Deadlock — all wait for right fork which none can get
- C) Starvation of one philosopher
- D) Race condition

✅ **Answer: B**
> If all 5 pick up left fork: each holds 1 fork, needs the right fork, but the right fork is held by the neighbor. Circular wait → **Deadlock**.

---

**Q103.** In the Readers-Writers Problem, which of the following is true?

- A) Multiple writers can write simultaneously
- B) Multiple readers can read simultaneously, but only one writer can write (exclusive)
- C) Only one reader can read at a time
- D) Writers and readers can operate simultaneously

✅ **Answer: B**
> **Readers-Writers**: multiple readers can access the shared database simultaneously (reading doesn't modify data). But a writer needs **exclusive** access — no readers or other writers.

---

**Q104.** A Monitor differs from a Semaphore in that:

- A) A Monitor is slower than a Semaphore
- B) Monitors provide automatic mutual exclusion; only one procedure executes inside the monitor at a time
- C) Semaphores are higher-level than Monitors
- D) Monitors can only be used in Java

✅ **Answer: B**
> A **Monitor** automatically enforces mutual exclusion — the programmer doesn't need to manually call wait/signal for basic mutual exclusion. It's a higher-level construct.

---

**Q105.** A Spin Lock differs from a Semaphore because:

- A) Spin lock blocks the process; semaphore uses busy waiting
- B) Spin lock uses busy waiting (continuously checks); semaphore blocks and queues the process
- C) Spin lock allows multiple processes in CS
- D) Spin lock is used only for memory management

✅ **Answer: B**
> **Spin Lock**: process loops continuously checking if the lock is free (busy waiting) — wastes CPU. **Semaphore**: process is blocked and queued — doesn't waste CPU while waiting.

---

## 📚 SECTION 8 — INTER-PROCESS COMMUNICATION (IPC)

---

**Q106.** Which IPC method is the FASTEST for processes on the same machine?

- A) Message Passing (sockets)
- B) Pipes
- C) Shared Memory
- D) Signals

✅ **Answer: C**
> **Shared Memory** is the fastest IPC because processes directly read/write a common memory region — no OS involvement needed during data transfer (after initial setup).

---

**Q107.** In Message Passing IPC, every message exchange involves:

- A) Direct memory access between processes
- B) OS system calls (send/receive go through the OS)
- C) Disk I/O operations
- D) Network sockets only

✅ **Answer: B**
> In **Message Passing**, every `send()` and `receive()` is a system call — the OS is the intermediary. This makes it safer but slower than shared memory.

---

**Q108.** Pipes provide:

- A) Bidirectional, asynchronous communication between any processes
- B) Unidirectional communication, typically between parent and child processes
- C) Network communication across machines
- D) Shared memory between unrelated processes

✅ **Answer: B**
> **Ordinary Pipes** are **unidirectional** (data flows one way) and are typically used between parent-child related processes. Data written to one end is read from the other.

---

**Q109.** Named Pipes (FIFOs) differ from ordinary Pipes because:

- A) Named pipes are faster
- B) Named pipes exist as a file in the file system and can be used by unrelated processes
- C) Named pipes are bidirectional; ordinary pipes are unidirectional
- D) Ordinary pipes exist in the file system; named pipes do not

✅ **Answer: B**
> **Named Pipes (FIFOs)** have a name in the file system, so **unrelated processes** (not just parent-child) can communicate through them.

---

**Q110.** Message Queues differ from Pipes because:

- A) Message queues are faster than pipes
- B) Message queues store messages with structure; processes can receive messages selectively and asynchronously
- C) Pipes store messages; queues do not
- D) Message queues require shared memory

✅ **Answer: B**
> **Message Queues**: messages are stored with type/priority; receivers can selectively pick messages; communication is asynchronous. Pipes are simpler byte streams.

---

**Q111.** Sockets are used for IPC when:

- A) Processes are on the same machine only
- B) Processes need to communicate over a network (can also work on same machine)
- C) Communication needs to be one-directional
- D) Shared memory is not available

✅ **Answer: B**
> **Sockets** work both on the same machine (localhost) and across networks. They are the basis of all internet communication (HTTP, email, etc.).

---

**Q112.** Signals in IPC are used to:

- A) Transfer large amounts of data between processes
- B) Notify a process about an event (like Ctrl+C sending SIGINT)
- C) Create shared memory regions
- D) Establish network connections

✅ **Answer: B**
> **Signals** are asynchronous notifications sent to a process to notify it of events. E.g., `SIGINT` (Ctrl+C) to interrupt, `SIGKILL` to force-terminate, `SIGTERM` to request termination.

---

**Q113.** The Linux command `ls | sort` is an example of:

- A) Shared Memory IPC
- B) Socket communication
- C) Pipe IPC — output of `ls` becomes input of `sort`
- D) Message Queue IPC

✅ **Answer: C**
> `|` in Linux is a **pipe** — the output (stdout) of `ls` is connected to the input (stdin) of `sort` through an ordinary pipe.

---

**Q114.** Which IPC method requires explicit synchronization by the programmer?

- A) Message Passing
- B) Pipes
- C) Shared Memory
- D) Sockets

✅ **Answer: C**
> **Shared Memory** is fast but doesn't have built-in synchronization. Programmers must use semaphores or mutexes to prevent race conditions when accessing shared memory.

---

**Q115.** Remote Procedure Call (RPC) allows:

- A) A process to call a function on a REMOTE machine as if it were local
- B) Multiple processes to share the same memory
- C) Real-time video communication between processes
- D) A process to terminate another process remotely

✅ **Answer: A**
> **RPC** abstracts network communication — a process calls a procedure that executes on a different machine. The network communication is hidden. Used in distributed systems and cloud.

---

## 📚 SECTION 9 — DEADLOCK

---

**Q116.** Deadlock is defined as:

- A) A process that uses 100% CPU
- B) A set of processes where each is waiting for a resource held by another process in the set
- C) A process that has been waiting for more than 10 minutes
- D) When available memory is less than required

✅ **Answer: B**
> **Deadlock**: circular wait where each process holds at least one resource and waits for another resource held by another process in the set. Nothing can proceed.

---

**Q117.** How many Coffman conditions must be present simultaneously for deadlock to occur?

- A) Any one of the four
- B) Any two of the four
- C) All four simultaneously
- D) At least three of the four

✅ **Answer: C**
> **All four Coffman conditions** (Mutual Exclusion, Hold and Wait, No Preemption, Circular Wait) must be present simultaneously for deadlock to occur. Remove any one → no deadlock.

---

**Q118.** Which Coffman condition states that a process holds resources while waiting for additional resources?

- A) Mutual Exclusion
- B) No Preemption
- C) Hold and Wait
- D) Circular Wait

✅ **Answer: C**
> **Hold and Wait**: a process holds at least one resource while waiting to acquire additional resources held by other processes.

---

**Q119.** Breaking the Circular Wait condition is done by:

- A) Allowing preemption of resources
- B) Assigning a global ordering to resources and requiring processes to request them in order
- C) Requiring all resources to be requested at the start
- D) Using a binary semaphore

✅ **Answer: B**
> **Breaking Circular Wait**: assign a total ordering to all resources (R1 < R2 < R3). Processes must always request resources in increasing order — circular wait becomes impossible.

---

**Q120.** The Banker's Algorithm is a:

- A) Deadlock Detection algorithm
- B) Deadlock Prevention algorithm (breaks a Coffman condition)
- C) Deadlock Avoidance algorithm (ensures system stays in safe state)
- D) Page Replacement algorithm

✅ **Answer: C**
> **Banker's Algorithm** is a **Deadlock Avoidance** algorithm. It checks if granting a resource request keeps the system in a **safe state** (all processes can finish). If not, the request is denied.

---

**Q121.** A Safe State in Banker's Algorithm means:

- A) No process is currently executing
- B) There exists a sequence in which every process can finish using currently available + eventually freed resources
- C) All resources are currently available
- D) No process is waiting for resources

✅ **Answer: B**
> A state is safe if there exists a **safe sequence** of processes such that resources can still be allocated to each process in the sequence to allow it to finish, preventing any deadlock.

---

**Q122.** If a Resource Allocation Graph (RAG) contains a cycle and resources have only a single instance:

- A) Deadlock might exist
- B) Deadlock definitely exists
- C) The system is in a safe state
- D) The cycle will resolve automatically

✅ **Answer: B**
> In a single-instance RAG, a cycle is a necessary and sufficient condition for deadlock. If multiple instances exist, a cycle only indicates possible deadlock.

---

**Q123.** What is the main difference between Deadlock Prevention and Deadlock Avoidance?

- A) Prevention is dynamic; Avoidance is static
- B) Prevention breaks one of the Coffman conditions; Avoidance uses resource request checks (safe state tracking)
- C) Avoidance is handled by compilers; Prevention is handled by hardware
- D) Prevention causes deadlocks; Avoidance resolves them

✅ **Answer: B**
> **Deadlock Prevention** prevents deadlocks by restructuring the resource request rules so that at least one Coffman condition is broken. **Deadlock Avoidance** dynamically checks requests using safe state tracking (e.g., Banker's Algorithm) to avoid deadlock.

---

**Q124.** Deadlock Detection differs from Deadlock Avoidance because:

- A) Detection prevents the system from entering unsafe states
- B) Detection allows deadlock to occur and periodically checks the system state to recover
- C) Detection does not require resource graphs
- D) Detection is only used in batch systems

✅ **Answer: B**
> **Deadlock Detection** does not block requests; it allows the system to run, periodically executing a cycle-detection algorithm to find deadlocks and applying recovery techniques if a deadlock is found.

---

**Q125.** Which of the following is a standard method for Deadlock Recovery?

- A) Compaction
- B) Process termination and Resource preemption
- C) Page replacement
- D) Thread context switching

✅ **Answer: B**
> **Deadlock Recovery** is achieved by terminating deadlocked processes (either all of them or one-by-one until the cycle breaks) or by preempting resources from processes and rolling them back.
