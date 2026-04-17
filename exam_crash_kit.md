# 🎯 COMBINATORIAL STUDIES - EXAM CRASH KIT
## Operating Systems | DBMS | Computer Networks (Chapter 1-3)

---

## 📊 STEP 1: SYLLABUS EXTRACTION & ANALYSIS

### **CHAPTER 1: OPERATING SYSTEMS**
1.1 Introduction to OS
1.2 OS Services & Functions
1.3 Process Management
1.4 Process Scheduling
1.5 CPU Scheduling Algorithms
1.6 Process Synchronization
1.7 Deadlock

### **CHAPTER 2: DATABASE MANAGEMENT SYSTEMS**
2.1 Introduction to DBMS
2.2 Data Models
2.3 ER Model & ER Diagrams
2.4 Relational Model
2.5 Relational Algebra
2.6 SQL Basics
2.7 Normalization (1NF, 2NF, 3NF, BCNF)

### **CHAPTER 3: COMPUTER NETWORKS**
3.1 Introduction to Networks
3.2 Network Types (LAN, MAN, WAN)
3.3 OSI Reference Model
3.4 TCP/IP Model
3.5 Transmission Media
3.6 Network Topologies
3.7 Switching Techniques

---

## 📈 WEIGHTAGE ANALYSIS (Predicted)

| Topic | Weightage | Priority |
|-------|-----------|----------|
| CPU Scheduling Algorithms | 15-18% | 🔴 HIGH |
| Normalization | 12-15% | 🔴 HIGH |
| OSI Model | 12-15% | 🔴 HIGH |
| Process Synchronization | 10-12% | 🟡 MEDIUM |
| Deadlock | 10-12% | 🟡 MEDIUM |
| SQL & Relational Algebra | 10-12% | 🟡 MEDIUM |
| DBMS Architecture | 8-10% | 🟡 MEDIUM |
| Network Topologies | 5-8% | 🟢 LOW |
| OS Basics | 5-8% | 🟢 LOW |

---

## 🔥 SECTION 1: HIGH-PROBABILITY MCQs (150 Questions)

### **OPERATING SYSTEMS (50 MCQs)**

#### **OS Basics (Q1-Q10)**

**Q1. What is the main function of an Operating System?**
- A) Compile programs
- B) Manage hardware and software resources ✅
- C) Provide internet connectivity
- D) Create databases

**Q2. Which of the following is NOT an operating system?**
- A) Windows
- B) Linux
- C) Oracle ✅
- D) macOS

**Q3. The kernel is:**
- A) The outer layer of OS
- B) The core component of OS that manages system resources ✅
- C) A type of application software
- D) A database management tool

**Q4. Which interface allows users to interact with the OS?**
- A) API
- B) Shell ✅
- C) Compiler
- D) Linker

**Q5. Batch processing systems:**
- A) Execute jobs one at a time without user interaction ✅
- B) Allow real-time interaction
- C) Process multiple users simultaneously
- D) Are used only in personal computers

**Q6. Time-sharing systems are designed for:**
- A) Batch processing
- B) Multi-user interactive computing ✅
- C) Single-user systems only
- D) Embedded systems only

**Q7. System calls provide:**
- A) Interface between user and applications
- B) Interface between user programs and OS ✅
- C) Interface between hardware and software
- D) Interface between two OS

**Q8. Which is NOT a type of OS?**
- A) Real-time OS
- B) Distributed OS
- C) Sequential OS ✅
- D) Multiprogramming OS

**Q9. Bootstrap program is stored in:**
- A) RAM
- B) ROM ✅
- C) Hard disk
- D) Cache

**Q10. An interrupt is:**
- A) A hardware signal that temporarily stops CPU execution ✅
- B) A software error
- C) A type of virus
- D) A network protocol

#### **Process Management (Q11-Q20)**

**Q11. A process in execution is called:**
- A) Program
- B) Process ✅
- C) Thread
- D) Task

**Q12. Process Control Block (PCB) contains:**
- A) Only process ID
- B) Process state, PC, registers, memory info ✅
- C) Only memory allocation details
- D) Only I/O status

**Q13. Which is NOT a process state?**
- A) New
- B) Running
- C) Compiled ✅
- D) Terminated

**Q14. Context switching involves:**
- A) Creating a new process
- B) Saving state of old process and loading state of new process ✅
- C) Deleting a process
- D) Terminating all processes

**Q15. A thread is:**
- A) A heavy-weight process
- B) A lightweight process ✅
- C) A type of scheduler
- D) A memory management unit

**Q16. Which queue contains processes waiting for CPU?**
- A) Job queue
- B) Ready queue ✅
- C) Device queue
- D) Wait queue

**Q17. Fork() system call:**
- A) Terminates a process
- B) Creates a child process ✅
- C) Allocates memory
- D) Opens a file

**Q18. Zombie process is:**
- A) A running process
- B) A terminated process whose entry is still in PCB ✅
- C) A waiting process
- D) A blocked process

**Q19. Orphan process is:**
- A) Process with no parent ✅
- B) Process with no child
- C) Terminated process
- D) Ready process

**Q20. Daemon process runs:**
- A) In foreground
- B) In background ✅
- C) Only during boot
- D) Only when user logs in

#### **CPU Scheduling (Q21-Q35)**

**Q21. Which scheduler selects processes from ready queue?**
- A) Long-term scheduler
- B) Short-term scheduler ✅
- C) Medium-term scheduler
- D) Job scheduler

**Q22. FCFS scheduling suffers from:**
- A) Starvation
- B) Convoy effect ✅
- C) Aging
- D) Deadlock

**Q23. SJF algorithm selects process with:**
- A) Longest burst time
- B) Shortest burst time ✅
- C) Highest priority
- D) Earliest arrival time

**Q24. Which scheduling algorithm is optimal for minimum average waiting time?**
- A) FCFS
- B) SJF ✅
- C) Round Robin
- D) Priority

**Q25. Round Robin scheduling uses:**
- A) Priority queue
- B) Time quantum ✅
- C) Stack
- D) Tree

**Q26. If time quantum in RR is very large, it behaves like:**
- A) SJF
- B) FCFS ✅
- C) Priority
- D) LRTF

**Q27. Starvation occurs in:**
- A) FCFS
- B) SJF ✅
- C) Round Robin
- D) All of the above

**Q28. Aging technique is used to:**
- A) Increase priority of old processes ✅
- B) Decrease priority
- C) Terminate processes
- D) Create new processes

**Q29. Response ratio in HRRN =**
- A) Burst time / Waiting time
- B) (Waiting time + Burst time) / Burst time ✅
- C) Waiting time / Burst time
- D) Burst time / Turnaround time

**Q30. Turnaround time =**
- A) Completion time - Arrival time ✅
- B) Waiting time + Burst time
- C) Both A and B ✅
- D) None of the above

**Q31. Waiting time =**
- A) Turnaround time - Burst time ✅
- B) Completion time - Burst time
- C) Arrival time - Burst time
- D) None of the above

**Q32. Which scheduling is preemptive?**
- A) FCFS
- B) SJF (non-preemptive)
- C) SRTF ✅
- D) HRRN

**Q33. Priority scheduling can suffer from:**
- A) Convoy effect
- B) Starvation ✅
- C) Deadlock only
- D) No issues

**Q34. Multilevel queue scheduling:**
- A) Has single ready queue
- B) Has multiple ready queues with different priorities ✅
- C) No queue
- D) Only for I/O processes

**Q35. Throughput is:**
- A) Number of processes completed per unit time ✅
- B) Total time taken
- C) Average waiting time
- D) CPU utilization

#### **Process Synchronization (Q36-Q42)**

**Q36. Critical section is:**
- A) Code segment accessing shared resources ✅
- B) Non-shareable code
- C) Error handling code
- D) I/O code

**Q37. Race condition occurs when:**
- A) Processes execute sequentially
- B) Multiple processes access shared data concurrently ✅
- C) Only one process runs
- D) System crashes

**Q38. Mutex stands for:**
- A) Mutual exclusion ✅
- B) Multiple execution
- C) Memory execution
- D) Mutual execution

**Q39. Semaphore is:**
- A) A variable for process synchronization ✅
- B) A scheduling algorithm
- C) A memory management technique
- D) A file system

**Q40. Binary semaphore can have values:**
- A) Any integer
- B) 0 or 1 ✅
- C) -1 to 1
- D) Only positive

**Q41. Producer-Consumer problem is solved using:**
- A) Semaphore ✅
- B) Only mutex
- C) Only locks
- D) Scheduling

**Q42. Dining Philosophers problem demonstrates:**
- A) CPU scheduling
- B) Process synchronization issues ✅
- C) Memory allocation
- D) Deadlock avoidance only

#### **Deadlock (Q43-Q50)**

**Q43. Deadlock occurs when:**
- A) Processes complete execution
- B) Processes wait indefinitely for resources ✅
- C) CPU is idle
- D) Memory is full

**Q44. Which is NOT a necessary condition for deadlock?**
- A) Mutual exclusion
- B) Hold and wait
- C) Preemption ✅
- D) Circular wait

**Q45. Banker's algorithm is used for:**
- A) Deadlock prevention
- B) Deadlock avoidance ✅
- C) Deadlock detection
- D) Deadlock recovery

**Q46. Resource Allocation Graph (RAG) is used for:**
- A) CPU scheduling
- B) Deadlock detection ✅
- C) Memory management
- D) File management

**Q47. If RAG has no cycle:**
- A) Deadlock exists
- B) No deadlock ✅
- C) May or may not have deadlock
- D) System crashes

**Q48. Ostrich algorithm:**
- A) Prevents deadlock
- B) Ignores deadlock ✅
- C) Detects deadlock
- D) Avoids deadlock

**Q49. Safe state means:**
- A) Deadlock exists
- B) System can allocate resources without deadlock ✅
- C) All processes completed
- D) No resources available

**Q50. Which technique breaks circular wait?**
- A) Resource ordering ✅
- B) Preemption
- C) Mutual exclusion
- D) Hold and wait

### **DBMS (50 MCQs)**

#### **DBMS Basics (Q51-Q60)**

**Q51. DBMS stands for:**
- A) Data Base Management System ✅
- B) Database Multiple Systems
- C) Data Binary Management System
- D) Digital Base Management Software

**Q52. Which is NOT a characteristic of DBMS?**
- A) Data redundancy ✅
- B) Data integrity
- C) Data security
- D) Data independence

**Q53. The highest level of data abstraction is:**
- A) Physical level
- B) Logical level
- C) View level ✅
- D) Conceptual level

**Q54. Database schema refers to:**
- A) Overall design of database ✅
- B) Data at a particular time
- C) User interface
- D) Query language

**Q55. Instance is:**
- A) Data in database at a particular moment ✅
- B) Database design
- C) Table structure
- D) Primary key

**Q56. DDL is used for:**
- A) Data manipulation
- B) Defining database structure ✅
- C) Data retrieval
- D) Data deletion

**Q57. DML is used for:**
- A) Creating tables
- B) Manipulating data ✅
- C) Defining constraints
- D) Dropping tables

**Q58. SQL stands for:**
- A) Structured Query Language ✅
- B) Simple Query Language
- C) Standard Query List
- D) System Query Logic

**Q59. Which command is used to remove a table?**
- A) DELETE
- B) DROP ✅
- C) REMOVE
- D) ERASE

**Q60. Which is a DDL command?**
- A) INSERT
- B) UPDATE
- C) CREATE ✅
- D) SELECT

#### **ER Model & Relational Model (Q61-Q70)**

**Q61. Entity in ER diagram is represented by:**
- A) Diamond
- B) Rectangle ✅
- C) Ellipse
- D) Line

**Q62. Relationship in ER diagram is represented by:**
- A) Rectangle
- B) Diamond ✅
- C) Ellipse
- D) Circle

**Q63. Attribute is represented by:**
- A) Rectangle
- B) Diamond
- C) Ellipse ✅
- D) Square

**Q64. Primary key:**
- A) Can be null
- B) Cannot be null ✅
- C) Can have duplicate values
- D) Is always foreign key

**Q65. Foreign key is:**
- A) Primary key of another table ✅
- B) Any attribute
- C) Unique key only
- D) Candidate key

**Q66. A relation is a:**
- A) File
- B) Table ✅
- C) Record
- D) Field

**Q67. Degree of relation is:**
- A) Number of tuples
- B) Number of attributes ✅
- C) Number of keys
- D) Number of rows

**Q68. Cardinality of relation is:**
- A) Number of attributes
- B) Number of tuples ✅
- C) Number of columns
- D) Number of keys

**Q69. Candidate key is:**
- A) Any key
- B) Minimal superkey ✅
- C) Foreign key
- D) Secondary key

**Q70. Superkey is:**
- A) Minimal set of attributes
- B) Set of attributes that uniquely identifies a tuple ✅
- C) Only primary key
- D) Only foreign key

#### **Relational Algebra & SQL (Q71-Q85)**

**Q71. SELECT operation in relational algebra is:**
- A) Projection
- B) Selection ✅
- C) Join
- D) Union

**Q72. PROJECT operation in relational algebra:**
- A) Selects rows
- B) Selects columns ✅
- C) Joins tables
- D) Deletes rows

**Q73. Cartesian product of R(m rows) and S(n rows) has:**
- A) m+n rows
- B) m×n rows ✅
- C) m-n rows
- D) m^n rows

**Q74. Natural Join requires:**
- A) No common attributes
- B) At least one common attribute ✅
- C) Primary keys only
- D) Foreign keys only

**Q75. Which SQL clause filters rows?**
- A) SELECT
- B) WHERE ✅
- C) GROUP BY
- D) ORDER BY

**Q76. Which SQL clause filters groups?**
- A) WHERE
- B) HAVING ✅
- C) GROUP BY
- D) ORDER BY

**Q77. COUNT(*) returns:**
- A) Only non-null values
- B) All rows including nulls ✅
- C) Only null values
- D) Distinct values

**Q78. Aggregate functions ignore:**
- A) All values
- B) NULL values ✅
- C) Zero values
- D) Negative values

**Q79. INNER JOIN returns:**
- A) All rows from both tables
- B) Only matching rows ✅
- C) Only non-matching rows
- D) Cartesian product

**Q80. LEFT OUTER JOIN returns:**
- A) Only matching rows
- B) All rows from left table + matching from right ✅
- C) All rows from right table
- D) No rows

**Q81. GROUP BY is used with:**
- A) Only SELECT
- B) Aggregate functions ✅
- C) Only WHERE
- D) Only INSERT

**Q82. DISTINCT keyword:**
- A) Deletes duplicates
- B) Removes duplicate rows from result ✅
- C) Sorts data
- D) Groups data

**Q83. LIKE operator is used for:**
- A) Exact match
- B) Pattern matching ✅
- C) Numerical comparison
- D) Logical operations

**Q84. BETWEEN operator is:**
- A) Exclusive
- B) Inclusive ✅
- C) Only for dates
- D) Only for strings

**Q85. ORDER BY default sorting is:**
- A) DESC
- B) ASC ✅
- C) Random
- D) No order

#### **Normalization (Q86-Q100)**

**Q86. Normalization is used to:**
- A) Increase redundancy
- B) Reduce redundancy ✅
- C) Increase data size
- D) Delete data

**Q87. 1NF requires:**
- A) No partial dependency
- B) Atomic values ✅
- C) No transitive dependency
- D) BCNF compliance

**Q88. 2NF eliminates:**
- A) Transitive dependency
- B) Partial dependency ✅
- C) All dependencies
- D) Multi-valued dependency

**Q89. 3NF eliminates:**
- A) Partial dependency
- B) Transitive dependency ✅
- C) Multi-valued dependency
- D) Join dependency

**Q90. BCNF is stricter than:**
- A) 1NF
- B) 2NF
- C) 3NF ✅
- D) 4NF

**Q91. A table is in 2NF if it is in 1NF and:**
- A) No transitive dependency
- B) No partial dependency ✅
- C) All attributes atomic
- D) Has primary key

**Q92. Partial dependency occurs when:**
- A) Non-key attribute depends on part of composite key ✅
- B) Non-key depends on entire key
- C) Key depends on non-key
- D) No dependency exists

**Q93. Transitive dependency occurs when:**
- A) A→B and B→C, then A→C ✅
- B) A→B only
- C) No dependency
- D) B→A only

**Q94. Prime attribute is:**
- A) Any attribute
- B) Part of candidate key ✅
- C) Non-key attribute
- D) Foreign key

**Q95. Lossless decomposition ensures:**
- A) Data loss
- B) Original relation can be reconstructed ✅
- C) Redundancy increases
- D) Tables merge

**Q96. Functional dependency A→B means:**
- A) B determines A
- B) A determines B ✅
- C) A and B are independent
- D) A equals B

**Q97. Multivalued dependency is handled in:**
- A) 1NF
- B) 2NF
- C) 4NF ✅
- D) 3NF

**Q98. Which normal form is most practical?**
- A) 1NF
- B) 2NF
- C) 3NF ✅
- D) 5NF

**Q99. Denormalization is:**
- A) Removing normalization
- B) Adding redundancy for performance ✅
- C) Creating more tables
- D) Deleting data

**Q100. A relation with single attribute key is always in:**
- A) 1NF
- B) 2NF ✅
- C) BCNF
- D) 4NF

### **COMPUTER NETWORKS (50 MCQs)**

#### **Network Basics (Q101-Q110)**

**Q101. Computer network is:**
- A) Single computer
- B) Interconnected computers sharing resources ✅
- C) Only internet
- D) Only WiFi

**Q102. LAN stands for:**
- A) Local Area Network ✅
- B) Large Area Network
- C) Long Area Network
- D) Limited Access Network

**Q103. WAN covers:**
- A) Single building
- B) Large geographical area ✅
- C) Only one room
- D) Only campus

**Q104. MAN stands for:**
- A) Multiple Area Network
- B) Metropolitan Area Network ✅
- C) Main Area Network
- D) Medium Access Network

**Q105. Which network covers largest area?**
- A) LAN
- B) MAN
- C) WAN ✅
- D) PAN

**Q106. PAN stands for:**
- A) Personal Area Network ✅
- B) Public Area Network
- C) Primary Access Network
- D) Private Area Network

**Q107. Bandwidth is measured in:**
- A) Meters
- B) Bits per second ✅
- C) Hertz
- D) Bytes

**Q108. Throughput is:**
- A) Maximum capacity
- B) Actual data transfer rate ✅
- C) Signal frequency
- D) Cable length

**Q109. Delay in network is also called:**
- A) Bandwidth
- B) Latency ✅
- C) Throughput
- D) Jitter

**Q110. Topology refers to:**
- A) Physical or logical arrangement of network ✅
- B) Network speed
- C) Network protocol
- D) Network security

#### **Network Topologies (Q111-Q117)**

**Q111. Bus topology uses:**
- A) Single backbone cable ✅
- B) Central hub
- C) Ring structure
- D) Mesh connections

**Q112. Star topology has:**
- A) Single cable
- B) Central hub/switch ✅
- C) No central device
- D) All nodes connected to each other

**Q113. Ring topology data flows in:**
- A) Both directions
- B) One direction ✅
- C) Random direction
- D) No direction

**Q114. Mesh topology provides:**
- A) Least redundancy
- B) Maximum redundancy ✅
- C) No connections
- D) Single path

**Q115. Most fault-tolerant topology:**
- A) Bus
- B) Star
- C) Mesh ✅
- D) Ring

**Q116. If central hub fails, which topology fails?**
- A) Bus
- B) Star ✅
- C) Mesh
- D) Ring

**Q117. Ethernet commonly uses:**
- A) Ring
- B) Bus/Star ✅
- C) Mesh only
- D) Tree only

#### **OSI Model (Q118-Q135)**

**Q118. OSI model has how many layers?**
- A) 4
- B) 5
- C) 6
- D) 7 ✅

**Q119. Lowest layer of OSI is:**
- A) Application
- B) Physical ✅
- C) Data Link
- D) Network

**Q120. Top layer of OSI is:**
- A) Physical
- B) Transport
- C) Session
- D) Application ✅

**Q121. Which layer provides routing?**
- A) Data Link
- B) Network ✅
- C) Transport
- D) Session

**Q122. TCP operates at which layer?**
- A) Network
- B) Transport ✅
- C) Session
- D) Application

**Q123. IP operates at which layer?**
- A) Data Link
- B) Network ✅
- C) Transport
- D) Physical

**Q124. MAC address works at:**
- A) Physical layer
- B) Data Link layer ✅
- C) Network layer
- D) Transport layer

**Q125. HTTP is a protocol of:**
- A) Transport layer
- B) Application layer ✅
- C) Network layer
- D) Session layer

**Q126. Error detection is done at:**
- A) Physical layer
- B) Data Link layer ✅
- C) Network layer
- D) Session layer

**Q127. Flow control is provided by:**
- A) Only Data Link
- B) Data Link and Transport ✅
- C) Only Network
- D) Only Application

**Q128. Encryption is done at:**
- A) Application layer
- B) Presentation layer ✅
- C) Session layer
- D) Transport layer

**Q129. Dialog control is function of:**
- A) Transport
- B) Session ✅
- C) Presentation
- D) Network

**Q130. Bits are transmitted at:**
- A) Data Link
- B) Physical ✅
- C) Network
- D) Transport

**Q131. Frames are data unit of:**
- A) Physical layer
- B) Data Link layer ✅
- C) Network layer
- D) Transport layer

**Q132. Packets are data unit of:**
- A) Data Link
- B) Network ✅
- C) Transport
- D) Application

**Q133. Segments are data unit of:**
- A) Network
- B) Transport ✅
- C) Session
- D) Application

**Q134. Router works at:**
- A) Data Link
- B) Network ✅
- C) Transport
- D) Physical

**Q135. Switch works at:**
- A) Physical
- B) Data Link ✅
- C) Network
- D) Transport

#### **TCP/IP & Transmission (Q136-Q150)**

**Q136. TCP/IP model has how many layers?**
- A) 3
- B) 4 ✅
- C) 5
- D) 7

**Q137. TCP is:**
- A) Connectionless
- B) Connection-oriented ✅
- C) Unreliable
- D) Fast but unreliable

**Q138. UDP is:**
- A) Connection-oriented
- B) Connectionless ✅
- C) Reliable
- D) Slower than TCP

**Q139. Which is more reliable?**
- A) TCP ✅
- B) UDP
- C) Both same
- D) Neither

**Q140. IP address is:**
- A) 16-bit
- B) 32-bit (IPv4) ✅
- C) 64-bit
- D) 128-bit only

**Q141. Port number identifies:**
- A) Computer
- B) Process/Application ✅
- C) Network
- D) Router

**Q142. HTTP uses port:**
- A) 21
- B) 25
- C) 80 ✅
- D) 443

**Q143. HTTPS uses port:**
- A) 80
- B) 443 ✅
- C) 21
- D) 25

**Q144. FTP uses port:**
- A) 21 ✅
- B) 80
- C) 443
- D) 25

**Q145. Guided media includes:**
- A) Radio waves
- B) Fiber optic cable ✅
- C) Microwaves
- D) Infrared

**Q146. Unguided media includes:**
- A) Twisted pair
- B) Coaxial cable
- C) Radio waves ✅
- D) Fiber optic

**Q147. Fastest transmission media:**
- A) Twisted pair
- B) Coaxial
- C) Fiber optic ✅
- D) Radio waves

**Q148. Circuit switching:**
- A) No dedicated path
- B) Dedicated path established ✅
- C) Packet-based
- D) Store and forward

**Q149. Packet switching:**
- A) Dedicated path
- B) Data divided into packets ✅
- C) Circuit-based
- D) No routing

**Q150. Which switching is used in internet?**
- A) Circuit switching
- B) Packet switching ✅
- C) Message switching
- D) None

---

## ⚡ SECTION 2: RAPID REVISION NOTES

### **OPERATING SYSTEMS**

#### **OS Basics**
- OS = Resource manager + Control program
- **Kernel**: Core of OS, runs in privileged mode
- **Shell**: User interface to kernel
- **System Calls**: Interface between user programs and OS
- **Bootstrap**: Stored in ROM, loads OS at startup

#### **Types of OS**
| Type | Feature |
|------|---------|
| Batch | No user interaction |
| Time-sharing | Multiple users, interactive |
| Real-time | Time-critical applications |
| Distributed | Multiple processors |
| Multiprogramming | Maximize CPU utilization |

#### **Process States**
```
New → Ready → Running → Terminated
         ↓        ↑
         ← Blocked ←
```

#### **Scheduling Algorithms**
| Algorithm | Preemptive? | Formula |
|-----------|-------------|---------|
| FCFS | No | Simple queue |
| SJF | No | Min burst time |
| SRTF | Yes | Shortest remaining |
| Round Robin | Yes | Time quantum |
| Priority | Both | Priority value |
| HRRN | No | (W+S)/S |

**Formulas:**
- Turnaround Time = Completion - Arrival
- Waiting Time = Turnaround - Burst
- Response Time = First execution - Arrival

#### **Synchronization**
- **Critical Section**: Shared resource access code
- **Race Condition**: Concurrent access to shared data
- **Mutex**: Mutual exclusion lock
- **Semaphore**: Integer variable with wait() & signal()
- **Binary Semaphore**: 0 or 1
- **Counting Semaphore**: Any integer value

**Critical Section Requirements:**
1. Mutual Exclusion
2. Progress
3. Bounded Waiting

#### **Deadlock**
**4 Necessary Conditions (All must hold):**
1. Mutual Exclusion
2. Hold and Wait
3. No Preemption
4. Circular Wait

**Deadlock Handling:**
| Method | Technique |
|--------|-----------|
| Prevention | Break one of 4 conditions |
| Avoidance | Banker's Algorithm |
| Detection | Resource Allocation Graph |
| Recovery | Kill process / Resource preemption |

---

### **DBMS**

#### **DBMS vs File System**
| DBMS | File System |
|------|-------------|
| Less redundancy | High redundancy |
| Data integrity | No integrity |
| Concurrent access | Limited |
| Security | Less secure |

#### **Data Abstraction Levels**
1. **Physical**: How data stored
2. **Logical**: What data stored
3. **View**: User perspective

#### **Database Languages**
| Language | Commands |
|----------|----------|
| DDL | CREATE, ALTER, DROP, TRUNCATE |
| DML | INSERT, UPDATE, DELETE, SELECT |
| DCL | GRANT, REVOKE |
| TCL | COMMIT, ROLLBACK, SAVEPOINT |

#### **Keys**
| Key | Definition |
|-----|------------|
| Superkey | Uniquely identifies tuple |
| Candidate Key | Minimal superkey |
| Primary Key | Selected candidate key |
| Foreign Key | References primary key |
| Composite Key | Multiple attributes |

#### **ER Diagram Symbols**
- Rectangle = Entity
- Diamond = Relationship
- Ellipse = Attribute
- Double Ellipse = Multi-valued
- Dashed Ellipse = Derived

#### **Relational Algebra Operations**
| Operation | Symbol | Purpose |
|-----------|--------|---------|
| Select | σ | Filter rows |
| Project | π | Select columns |
| Union | ∪ | Combine rows |
| Intersection | ∩ | Common rows |
| Cartesian Product | × | All combinations |
| Join | ⋈ | Related tuples |

#### **SQL Clauses Order**
```
SELECT → FROM → WHERE → GROUP BY → HAVING → ORDER BY
```

#### **Normalization**
| Normal Form | Eliminates |
|-------------|------------|
| 1NF | Non-atomic values |
| 2NF | Partial dependency |
| 3NF | Transitive dependency |
| BCNF | Strict 3NF |
| 4NF | Multi-valued dependency |

**Dependency Types:**
- **Full**: A→B (entire key determines)
- **Partial**: A→B (part of key determines)
- **Transitive**: A→B, B→C implies A→C

---

### **COMPUTER NETWORKS**

#### **Network Types**
| Type | Coverage | Speed | Example |
|------|----------|-------|---------|
| PAN | 10m | Low | Bluetooth |
| LAN | Building | High | Ethernet |
| MAN | City | Medium | Cable TV |
| WAN | Country | Low | Internet |

#### **OSI Model (7 Layers)**
```
7. Application  - User interface (HTTP, FTP)
6. Presentation - Encryption, compression
5. Session      - Dialog control
4. Transport    - End-to-end (TCP, UDP)
3. Network      - Routing (IP)
2. Data Link    - Framing, MAC
1. Physical     - Bits, cables
```

**Mnemonic**: **A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing

#### **Data Units by Layer**
| Layer | Data Unit |
|-------|-----------|
| Physical | Bits |
| Data Link | Frames |
| Network | Packets |
| Transport | Segments |

#### **TCP/IP Model (4 Layers)**
1. Application (combines OSI 5,6,7)
2. Transport (same as OSI)
3. Internet (same as Network)
4. Network Access (combines OSI 1,2)

#### **TCP vs UDP**
| TCP | UDP |
|-----|-----|
| Connection-oriented | Connectionless |
| Reliable | Unreliable |
| Slower | Faster |
| Flow control | No flow control |
| Used by: HTTP, FTP | Used by: DNS, Streaming |

#### **Common Port Numbers**
| Service | Port |
|---------|------|
| FTP | 21 |
| SSH | 22 |
| SMTP | 25 |
| DNS | 53 |
| HTTP | 80 |
| HTTPS | 443 |

#### **Topologies Comparison**
| Topology | Pros | Cons |
|----------|------|------|
| Bus | Simple | Single point failure |
| Star | Easy to manage | Hub failure kills all |
| Ring | Organized | One failure affects all |
| Mesh | Fault-tolerant | Expensive |

#### **Switching Techniques**
| Type | Feature |
|------|---------|
| Circuit | Dedicated path |
| Packet | Data in packets |
| Message | Store & forward |

---

## 🧠 SECTION 3: MEMORY TRICKS & SHORTCUTS

### **OS Memory Tricks**

#### **1. Scheduling Algorithms**
**"FCF SJF RR P H"** → **F**irst **C**ome **F**irst, **S**hortest **J**ob **F**irst, **R**ound **R**obin, **P**riority, **H**RRN

**Visual Trick:**
- FCFS = Bus ticket queue 🚌
- SJF = Fast food order (quick first) 🍔
- RR = Pizza slices (equal time each) 🍕
- Priority = VIP entry 🎫

#### **2. Deadlock Conditions**
**Mnemonic**: **"My Heavy Noisy Cat"**
- **M**utual Exclusion
- **H**old and Wait
- **N**o Preemption
- **C**ircular Wait

#### **3. Process States**
**"N RBRT"** → **N**ew → **R**eady → **B**locked → **R**unning → **T**erminated

**Visual**: Student lifecycle
- New = Admission
- Ready = Waiting for class
- Running = In class
- Blocked = Sick leave
- Terminated = Graduated 🎓

#### **4. Semaphore Operations**
- **Wait (P)**: Decrease (like parking slot occupied 🚗)
- **Signal (V)**: Increase (slot freed ✅)

---

### **DBMS Memory Tricks**

#### **1. Normalization Flow**
**"1A 2P 3T B"** → **1**NF = **A**tomic, **2**NF = **P**artial, **3**NF = **T**ransitive, **B**CNF

**Story**: **A**tom **P**eter **T**akes **B**us
- 1NF: Make atoms (atomic values)
- 2NF: Remove PARTial
- 3NF: Remove TRANSitive

#### **2. SQL Execution Order**
**"SFWGHO"** → **S**elect **F**rom **W**here **G**roup **H**aving **O**rder

**Visual**: Cooking recipe
1. **FROM**: Get ingredients (tables)
2. **WHERE**: Filter bad ones
3. **GROUP BY**: Group similar
4. **HAVING**: Filter groups
5. **SELECT**: Serve dish
6. **ORDER BY**: Plate presentation

#### **3. Keys Hierarchy**
**"SCPF"** (Superman Can't Punch Flash)
- **S**uperkey (largest)
- **C**andidate Key (minimal superkey)
- **P**rimary Key (chosen candidate)
- **F**oreign Key (references primary)

#### **4. ER Diagram**
**"ERA"** → **E**ntity = **R**ectangle, **R**elationship = Diamond, **A**ttribute = Ellipse

**Visual**: **ERA** triangle 📐

#### **5. Relational Algebra**
- **σ (Sigma)** = **S**elect rows (S for Sigma)
- **π (Pi)** = **P**roject columns (P for Pi)

---

### **NETWORKS Memory Tricks**

#### **1. OSI Model (Most Important!)**
**"All People Seem To Need Data Processing"**
- **A**pplication
- **P**resentation
- **S**ession
- **T**ransport
- **N**etwork
- **D**ata Link
- **P**hysical

**Bottom to Top**: **P**lease **D**o **N**ot **T**hrow **S**ausage **P**izza **A**way

#### **2. Layer Functions**
- **Physical**: **P**hysical = **P**hones (cables) 📞
- **Data Link**: **D**ata = **D**elivery (frames) 📦
- **Network**: **N**etwork = **N**avigation (routing) 🧭
- **Transport**: **T**ransport = **T**rucks (end-to-end) 🚚
- **Session**: **S**ession = **S**tart/stop conversations 🗣️
- **Presentation**: **P**resentation = **P**retty (encryption) 🎨
- **Application**: **A**pplication = **A**pps (user) 📱

#### **3. Port Numbers**
- **FTP = 21** → File Transfer **2** (to) **1** (one place)
- **HTTP = 80** → **8** legs on spider, **0** security
- **HTTPS = 443** → **4** secure wheels, **43** times safer

#### **4. TCP vs UDP**
- **TCP** = **T**otally **C**onnected (reliable) 🤝
- **UDP** = **U**nreliable **D**ata **P**rotocol (fast) 💨

#### **5. Topology Fault Tolerance**
**"BSRM"** (Best to Worst)
- **M**esh = Maximum fault tolerance
- **R**ing = Ring breaks, all break
- **S**tar = Star hub fails, all fail
- **B**us = Bus cable breaks, all break

---

## 🚨 SECTION 4: HIGH-RISK CONFUSION ZONES

### **ZONE 1: SJF vs SRTF**
| Aspect | SJF | SRTF |
|--------|-----|------|
| Preemptive | No | Yes |
| Decision | At arrival | At every arrival |
| Better? | Good | Optimal |

**Key**: SJF = **S**tick to job once started; SRTF = **S**witch if new job shorter

---

### **ZONE 2: 2NF vs 3NF**
| Normal Form | Eliminates | Dependency Type |
|-------------|------------|-----------------|
| 2NF | Partial | Part of key → Non-key |
| 3NF | Transitive | Non-key → Non-key |

**Trick**: 2NF = **2** parts (composite key issue); 3NF = **3** attributes (A→B→C)

---

### **ZONE 3: TCP vs UDP**
| Feature | TCP | UDP |
|---------|-----|-----|
| Connection | Yes | No |
| Reliability | High | Low |
| Speed | Slow | Fast |
| Used by | HTTP, FTP | DNS, Video |
| Flow Control | Yes | No |

**Exam Trap**: DNS uses UDP (not TCP)!

---

### **ZONE 4: WHERE vs HAVING**
| Clause | Applies To | Used With |
|--------|------------|-----------|
| WHERE | Individual rows | Before GROUP BY |
| HAVING | Groups | After GROUP BY |

**Rule**: WHERE filters rows, HAVING filters groups

---

### **ZONE 5: Primary Key vs Unique Key**
| Feature | Primary Key | Unique Key |
|---------|-------------|------------|
| NULL | Not allowed | Allowed (one) |
| Per table | Only one | Multiple |
| Index | Clustered | Non-clustered |

---

### **ZONE 6: Process vs Thread**
| Aspect | Process | Thread |
|--------|---------|--------|
| Weight | Heavy | Light |
| Memory | Separate | Shared |
| Creation | Slow | Fast |
| Communication | Slow | Fast |

**Key**: Threads share memory, processes don't

---

### **ZONE 7: Deadlock Prevention vs Avoidance**
| Method | Approach | Example |
|--------|----------|---------|
| Prevention | Break conditions | Resource ordering |
| Avoidance | Check before allocation | Banker's Algorithm |
| Detection | Let it happen, then detect | RAG |

**Trick**: Prevention = Stop it; Avoidance = Check first

---

### **ZONE 8: Router vs Switch vs Hub**
| Device | Layer | Intelligence |
|--------|-------|--------------|
| Hub | Physical (L1) | Dumb (broadcasts) |
| Switch | Data Link (L2) | Smart (MAC address) |
| Router | Network (L3) | Smartest (IP address) |

---

### **ZONE 9: DELETE vs DROP vs TRUNCATE**
| Command | Type | Removes | Rollback? |
|---------|------|---------|-----------|
| DELETE | DML | Rows | Yes |
| TRUNCATE | DDL | All rows | No |
| DROP | DDL | Table structure | No |

**Memory**: DELETE = Careful; TRUNCATE = Empty table; DROP = Destroy table

---

### **ZONE 10: Starvation vs Deadlock**
| Feature | Starvation | Deadlock |
|---------|------------|----------|
| Processes | Waiting indefinitely | Blocked forever |
| Cause | Low priority | Circular wait |
| Resolution | Aging | Prevention/Avoidance |

**Key**: Starvation = Waiting too long; Deadlock = Waiting forever (circular)

---

## 🧪 SECTION 5: MINI MOCK TEST (30 MCQs)

### **Instructions**: Attempt in 30 minutes. Check answers at end.

**Q1. Which scheduling algorithm can cause starvation?**
- A) FCFS
- B) Round Robin
- C) Priority ✅
- D) None

**Q2. Banker's algorithm deals with:**
- A) Deadlock prevention
- B) Deadlock avoidance ✅
- C) Deadlock detection
- D) CPU scheduling

**Q3. A relation is in 3NF if it is in 2NF and:**
- A) No partial dependency
- B) No transitive dependency ✅
- C) All attributes atomic
- D) Has foreign key

**Q4. Which layer of OSI provides encryption?**
- A) Application
- B) Presentation ✅
- C) Session
- D) Transport

**Q5. SQL command to remove all rows but keep structure:**
- A) DELETE
- B) DROP
- C) TRUNCATE ✅
- D) REMOVE

**Q6. TCP is:**
- A) Connectionless
- B) Connection-oriented ✅
- C) Unreliable
- D) Faster than UDP

**Q7. Context switching occurs in:**
- A) CPU scheduling ✅
- B) Memory management
- C) File management
- D) I/O operations

**Q8. Which topology requires n(n-1)/2 links for n nodes?**
- A) Star
- B) Mesh ✅
- C) Bus
- D) Ring

**Q9. Natural join requires:**
- A) No common attributes
- B) Common attributes ✅
- C) Primary keys only
- D) Foreign keys only

**Q10. Binary semaphore values:**
- A) Any integer
- B) 0 or 1 ✅
- C) -1 to 1
- D) Positive only

**Q11. IP address size (IPv4):**
- A) 16 bits
- B) 32 bits ✅
- C) 64 bits
- D) 128 bits

**Q12. Which is DDL command?**
- A) INSERT
- B) UPDATE
- C) ALTER ✅
- D) DELETE

**Q13. Round Robin with large quantum behaves like:**
- A) SJF
- B) FCFS ✅
- C) Priority
- D) SRTF

**Q14. HTTP uses port:**
- A) 21
- B) 25
- C) 80 ✅
- D) 443

**Q15. Foreign key references:**
- A) Any attribute
- B) Primary key ✅
- C) Foreign key
- D) Candidate key only

**Q16. Which is NOT a deadlock condition?**
- A) Mutual exclusion
- B) Preemption ✅
- C) Hold and wait
- D) Circular wait

**Q17. Data Link layer transmits:**
- A) Bits
- B) Frames ✅
- C) Packets
- D) Segments

**Q18. COUNT(*) includes:**
- A) Only non-null
- B) NULL values ✅
- C) Only zeros
- D) Excludes duplicates

**Q19. Fastest transmission media:**
- A) Twisted pair
- B) Coaxial
- C) Fiber optic ✅
- D) Radio

**Q20. Race condition occurs in:**
- A) Single process
- B) Concurrent processes ✅
- C) Sequential execution
- D) Deadlock

**Q21. BCNF is stricter than:**
- A) 1NF
- B) 2NF
- C) 3NF ✅
- D) 4NF

**Q22. Router operates at:**
- A) Data Link
- B) Network ✅
- C) Transport
- D) Physical

**Q23. Turnaround time formula:**
- A) Waiting + Burst ✅
- B) Arrival + Burst
- C) Completion - Waiting
- D) Burst - Waiting

**Q24. Which uses UDP?**
- A) HTTP
- B) FTP
- C) DNS ✅
- D) SMTP

**Q25. Semaphore is used for:**
- A) Scheduling
- B) Synchronization ✅
- C) Memory allocation
- D) Deadlock prevention

**Q26. 1NF requires:**
- A) No partial dependency
- B) Atomic values ✅
- C) No transitive dependency
- D) BCNF

**Q27. Star topology failure point:**
- A) Cable
- B) Central hub ✅
- C) Node
- D) None

**Q28. HAVING clause filters:**
- A) Rows
- B) Groups ✅
- C) Tables
- D) Databases

**Q29. Zombie process is:**
- A) Running
- B) Terminated but PCB exists ✅
- C) Blocked
- D) Ready

**Q30. Packet switching used in:**
- A) Telephone networks
- B) Internet ✅
- C) Telegraph
- D) Radio

---

### **Mock Test Answer Key**
| Q | Ans | Q | Ans | Q | Ans |
|---|-----|---|-----|---|-----|
| 1 | C | 11 | B | 21 | C |
| 2 | B | 12 | C | 22 | B |
| 3 | B | 13 | B | 23 | A |
| 4 | B | 14 | C | 24 | C |
| 5 | C | 15 | B | 25 | B |
| 6 | B | 16 | B | 26 | B |
| 7 | A | 17 | B | 27 | B |
| 8 | B | 18 | B | 28 | B |
| 9 | B | 19 | C | 29 | B |
| 10 | B | 20 | B | 30 | B |

---

## ⚔️ SECTION 6: EXAM STRATEGY & TIPS

### **🎯 MCQ Solving Strategy**

#### **Phase 1: First Pass (Quick Wins) - 60% of time**
1. **Scan all questions** first
2. Answer **direct knowledge** questions immediately
3. Mark uncertain ones for review
4. **Don't spend >1 min** per question

**Target**: Complete 60-70% questions in first pass

---

#### **Phase 2: Second Pass (Thinking Required) - 30% of time**
1. Return to marked questions
2. Apply **elimination technique**
3. Use **context clues** from other questions
4. **Logical reasoning**

---

#### **Phase 3: Final Review - 10% of time**
1. Check all answers marked
2. Verify no questions left blank
3. **Don't change answers** unless 100% sure

---

### **🧠 Elimination Technique**

#### **Rule 1: Extreme Words = Usually Wrong**
❌ "Always", "Never", "Only", "Must"
✅ "Usually", "Often", "Can", "May"

**Example:**
- "OS always prevents deadlock" ❌ (False)
- "OS can prevent deadlock" ✅ (True)

---

#### **Rule 2: Similar Options = One is Correct**
If 2 options are very similar, one is likely correct.

**Example:**
- A) 2NF eliminates partial dependency
- B) 2NF eliminates transitive dependency
- C) 2NF deletes data
- D) 2NF creates tables

**Answer**: Between A and B → A ✅

---

#### **Rule 3: Opposite Options = One is Correct**
If 2 options are exact opposites, one is likely correct.

**Example:**
- A) TCP is connection-oriented
- B) TCP is connectionless
- C) TCP is slow
- D) TCP uses UDP

**Answer**: Between A and B → A ✅

---

#### **Rule 4: Longest Option = Often Correct**
Examiners add details to correct answers to make them precise.

---

#### **Rule 5: "All of the Above" = Usually Correct**
- If you can verify 2 options are correct → Select "All of the above"
- Probability: 70-80% correct

---

### **🎲 Smart Guessing Strategy**

#### **When to Guess:**
- Negative marking: Guess only if you can eliminate 2 options
- No negative marking: **Always guess** (25% chance)

---

#### **Guessing Hierarchy:**
1. **Eliminate obviously wrong** options
2. Look for **keywords** from syllabus
3. Choose **middle values** in numerical options
4. Avoid **extreme values**
5. If stuck, pick **B or C** (statistically more common)

---

#### **Numerical Questions:**
- Calculate rough estimate
- Eliminate outliers
- Choose closest reasonable value

---

### **⚡ Time Management**

| Activity | Time Allocation |
|----------|----------------|
| First Pass | 60% |
| Second Pass | 30% |
| Review | 10% |

**Example** (90 min exam):
- First Pass: 54 min (60 questions)
- Second Pass: 27 min (30 questions)
- Review: 9 min

---

### **🔥 High-Yield Topics (Last 30 Min Revision)**

**Focus on these only:**
1. ✅ CPU Scheduling algorithms & formulas
2. ✅ OSI model layers & functions
3. ✅ Normalization (1NF → 3NF)
4. ✅ Deadlock conditions
5. ✅ TCP vs UDP
6. ✅ SQL commands (DDL vs DML)
7. ✅ Port numbers
8. ✅ Topologies

---

### **🚫 Common Mistakes to Avoid**

1. ❌ Reading question too fast
2. ❌ Not reading ALL options
3. ❌ Overthinking simple questions
4. ❌ Changing answers without reason
5. ❌ Spending too much time on one question
6. ❌ Leaving questions blank (if no negative marking)
7. ❌ Confusing WHERE vs HAVING
8. ❌ Mixing up TCP vs UDP
9. ❌ Forgetting SJF is non-preemptive, SRTF is preemptive
10. ❌ Confusing 2NF vs 3NF

---

### **💡 Examiner Psychology**

**What examiners test:**
- **Definitions** (20-25%)
- **Differences** (20-25%)
- **Applications** (15-20%)
- **Formulas/Calculations** (15-20%)
- **Edge cases** (10-15%)

**Trap questions often:**
- "Which is NOT..."
- "Except..."
- "False statement..."

---

### **🎯 Last 10 Minutes Strategy**

1. Check all questions answered
2. Review marked uncertain ones
3. **Don't start new questions**
4. Verify OMR sheet filled correctly
5. Stay calm! ✅

---

## 🏆 FINAL CHECKLIST

### **Before Exam:**
- [ ] Revise memory tricks (15 min)
- [ ] Review confusion zones (10 min)
- [ ] Skim rapid revision notes (10 min)
- [ ] Stay calm & confident

### **During Exam:**
- [ ] Read instructions carefully
- [ ] First pass → Quick wins
- [ ] Second pass → Elimination
- [ ] Review → Check marks
- [ ] No blank answers (if no negative marking)

### **Mindset:**
- ✅ You've prepared well
- ✅ Trust your first instinct
- ✅ Stay positive
- ✅ Give your best shot

---

## 📚 QUICK REFERENCE TABLES

### **Scheduling Comparison**
| Algorithm | Preemptive | Starvation | Optimal? |
|-----------|------------|------------|----------|
| FCFS | No | No | No |
| SJF | No | Yes | Yes (min WT) |
| SRTF | Yes | Yes | Yes |
| RR | Yes | No | No |
| Priority | Both | Yes | No |

---

### **Normalization Checklist**
| NF | Requirement |
|----|-------------|
| 1NF | Atomic values |
| 2NF | 1NF + No partial dependency |
| 3NF | 2NF + No transitive dependency |
| BCNF | 3NF + For every FD X→Y, X is superkey |

---

### **OSI vs TCP/IP**
| OSI | TCP/IP |
|-----|--------|
| 7 layers | 4 layers |
| Theoretical | Practical |
| Clear boundaries | Combined layers |

---

### **Key Devices & Layers**
| Device | Layer |
|--------|-------|
| Hub | Physical (1) |
| Switch | Data Link (2) |
| Router | Network (3) |
| Gateway | All layers (7) |

---

### **Important Ports**
| Service | Port |
|---------|------|
| FTP | 21 |
| SSH | 22 |
| Telnet | 23 |
| SMTP | 25 |
| DNS | 53 |
| HTTP | 80 |
| HTTPS | 443 |

---

# 🎓 GOOD LUCK FOR YOUR EXAM! 🎓

**Remember:**
- Stay calm
- Read carefully
- Eliminate wrong options
- Trust your preparation
- Give your best! 💪

---

*Generated for Exam Crash Preparation*
*Focus on understanding, not just memorizing*
*You've got this! 🚀*
