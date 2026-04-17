# 📘 LPU MCQ Bank — OS, DBMS & Computer Networks
> Style: Sanfoundry | Exam-Ready | All syllabus topics covered

---

## ✅ CHAPTER 1: OPERATING SYSTEMS

---

### 🔷 Topic 1: Operating System, Kernel, System Calls

**Q1.** What is an operating system?
- a) Interface between the hardware and application programs
- b) Collection of programs that manages hardware resources
- c) System service provider to the application programs
- **d) All of the mentioned ✅**

**Q2.** Which of the following is NOT a function of an OS?
- a) Memory management
- b) Process management
- **c) Compiling programs ✅**
- d) File system management

**Q3.** To access the services of the operating system, the interface is provided by the ___________
- a) Library
- **b) System calls ✅**
- c) Assembly instructions
- d) API

**Q4.** Which one of the following is not true about kernel?
- a) Kernel remains in the memory during the entire computer session
- **b) Kernel is made of various modules which cannot be loaded in a running operating system ✅**
- c) Kernel is the first part of the OS to load into memory during booting
- d) Kernel is the program that constitutes the central core of the OS

**Q5.** What does OS X have?
- a) Monolithic kernel with modules
- b) Microkernel
- c) Monolithic kernel
- **d) Hybrid kernel ✅**

**Q6.** Which of the following errors will be handled by the operating system?
- a) Lack of paper in printer
- b) Connection failure in the network
- c) Power failure
- **d) All of the mentioned ✅**

**Q7.** Where is the operating system placed in the memory?
- **a) Either low or high memory (depending on the location of interrupt vector) ✅**
- b) In the low memory
- c) In the high memory
- d) None of the mentioned

**Q8.** What is the main function of the command interpreter?
- a) To provide the interface between the API and application program
- b) To handle the files in the operating system
- **c) To get and execute the next user-specified command ✅**
- d) None of the mentioned

**Q9.** Which principle states that programs, users, and systems be given just enough privileges to perform their task?
- **a) Principle of least privilege ✅**
- b) Principle of process scheduling
- c) Principle of operating system
- d) None of the mentioned

**Q10.** In Unix, which system call creates a new process?
- a) create
- **b) fork ✅**
- c) new
- d) None of the mentioned

---

### 🔷 Topic 2: Process, CPU Scheduling, Thread

**Q11.** CPU scheduling is the basis of ___________
- **a) Multiprogramming operating systems ✅**
- b) Larger memory sized systems
- c) Multiprocessor systems
- d) None of the mentioned

**Q12.** Which of the following is/are CPU scheduling algorithms?
- a) Priority
- b) Round Robin
- c) Shortest Job First
- **d) All of the mentioned ✅**

**Q13.** In operating system, each process has its own __________
- a) Open files
- b) Pending alarms, signals, and signal handlers
- c) Address space and global variables
- **d) All of the mentioned ✅**

**Q14.** In a timeshare OS, when the time slot assigned to a process is completed, the process switches to:
- a) Suspended state
- b) Terminated state
- **c) Ready state ✅**
- d) Blocked state

**Q15.** Cascading termination refers to:
- **a) Termination of all child processes if the parent process terminates normally or abnormally ✅**
- b) Termination only on abnormal parent exit
- c) Termination only on normal parent exit
- d) None of the mentioned

**Q16.** The FCFS algorithm is particularly troublesome for ____________
- a) Operating systems
- b) Multiprocessor systems
- **c) Time sharing systems ✅**
- d) Multiprogramming systems

**Q17.** The portion of the process scheduler that dispatches processes is concerned with:
- a) Assigning ready processes to waiting queue
- b) Assigning running processes to blocked queue
- **c) Assigning ready processes to CPU ✅**
- d) All of the mentioned

**Q18.** When a process is in a "Blocked" state and I/O service is completed, it goes to:
- a) Terminated state
- b) Suspended state
- c) Running state
- **d) Ready state ✅**

**Q19.** Transient operating system code is a code that ____________
- a) Stays in the memory always
- b) Never enters the memory space
- **c) Comes and goes as needed ✅**
- d) Is not easily accessible

**Q20.** Which of the following is NOT true about threads?
- a) Threads share the same process resources
- b) Threads have their own stack
- **c) Threads have separate address spaces ✅**
- d) Threads share code section

---

### 🔷 Topic 3: Synchronization, Semaphores, Mutex

**Q21.** A semaphore is used to:
- a) Allow only one process to run at a time
- **b) Control access to shared resources in concurrent systems ✅**
- c) Manage memory allocation
- d) Schedule CPU processes

**Q22.** A binary semaphore is also known as:
- **a) Mutex ✅**
- b) Spinlock
- c) Monitor
- d) Counting semaphore

**Q23.** Which of the following is NOT a characteristic of a monitor?
- a) It encapsulates the shared data
- b) Only one process can be active in the monitor at a time
- **c) It uses no synchronization primitives ✅**
- d) It has condition variables

**Q24.** What is busy waiting in the context of synchronization?
- **a) A process continuously checks a condition in a loop ✅**
- b) A process waits in a blocked queue
- c) A process is suspended by the OS
- d) None of the mentioned

**Q25.** In the wait() operation on a semaphore:
- a) The semaphore value is incremented
- **b) The semaphore value is decremented ✅**
- c) The process is terminated
- d) None of the mentioned

---

### 🔷 Topic 4: Classical Synchronization Problems

**Q26.** The Producer-Consumer problem involves:
- a) A producer and a consumer sharing a CPU
- **b) A bounded buffer shared between producer and consumer processes ✅**
- c) Two producers competing for resources
- d) None of the mentioned

**Q27.** The Readers-Writers problem:
- a) Allows multiple writers simultaneously
- **b) Allows multiple readers but only one writer at a time ✅**
- c) Allows readers and writers simultaneously
- d) None of the mentioned

**Q28.** The Dining Philosophers problem illustrates:
- **a) Deadlock and starvation ✅**
- b) Memory management
- c) CPU scheduling
- d) File management

**Q29.** In the Sleeping Barber problem, the barber sleeps when:
- **a) There are no customers ✅**
- b) There are too many customers
- c) The chair is broken
- d) None of the mentioned

---

### 🔷 Topic 5: Deadlock

**Q30.** For an effective OS, when should deadlock be checked?
- **a) Every time a resource request is made, at fixed time intervals ✅**
- b) At fixed time intervals only
- c) Every time a resource request is made only
- d) None of the mentioned

**Q31.** A deadlock avoidance algorithm dynamically examines the __________ to ensure circular wait cannot exist.
- a) Operating system
- b) Resources
- c) System storage state
- **d) Resource allocation state ✅**

**Q32.** Which of the following is NOT a necessary condition for deadlock?
- a) Mutual exclusion
- b) Hold and wait
- **c) Preemption ✅**
- d) Circular wait

**Q33.** Banker's algorithm is used for:
- a) Deadlock detection
- **b) Deadlock avoidance ✅**
- c) Deadlock prevention
- d) Deadlock recovery

**Q34.** In a resource allocation graph, a cycle indicates:
- **a) Possible deadlock (definite if single instance per resource) ✅**
- b) Always deadlock
- c) No deadlock
- d) None of the mentioned

---

### 🔷 Topic 6: Types of Memory, Memory Management

**Q35.** The main memory accommodates ____________
- a) CPU
- b) User processes
- c) Operating system
- **d) All of the mentioned ✅**

**Q36.** Swapping _______ be done when a process has pending I/O.
- **a) Must never ✅**
- b) Maybe
- c) Can
- d) Must

**Q37.** The OS and other processes are protected from modification because:
- **a) Every address generated by the CPU is checked against relocation and limit registers ✅**
- b) They have a protection algorithm
- c) They are in different memory spaces
- d) They are in different logical addresses

**Q38.** For implementing dynamic loading ____________
- a) Special support from OS is essential
- b) Special support from hardware is required
- **c) User programs can implement dynamic loading without special support ✅**
- d) Special support from both is essential

**Q39.** Using transient code, _______ the size of the operating system during program execution.
- a) Maintains
- **b) Changes ✅**
- c) Increases
- d) Decreases

**Q40.** The OS maintains a ______ table that tracks how many frames are allocated, available, etc.
- a) Memory
- b) Mapping
- c) Page
- **d) Frame ✅**

**Q41.** If the sum of working-set sizes exceeds the total available frames, ____________
- **a) The OS selects a process to suspend ✅**
- b) The system crashes
- c) The process crashes
- d) Memory overflows

---

### 🔷 Topic 7: Secondary Storage, RAID

**Q42.** The two steps the OS takes to use a disk to hold its files are:
- a) Caching & logical formatting
- b) Logical formatting & swap space creation
- c) Swap space creation & caching
- **d) Partitioning & logical formatting ✅**

**Q43.** In SCSI disks, bad blocks are handled during _______ formatting.
- a) Partitioning
- **b) Low-level formatting ✅**
- c) High-level formatting
- d) None of the mentioned

**Q44.** Which RAID level is popular for write performance (log files)?
- **a) RAID level 0 ✅**
- b) RAID level 1
- c) RAID level 5
- d) RAID level 6

**Q45.** RAID level 1 is also known as:
- a) Striping
- **b) Mirroring ✅**
- c) Parity striping
- d) None of the mentioned

**Q46.** Whenever a process needs I/O to or from a disk it issues a:
- **a) System call to the operating system ✅**
- b) A special procedure
- c) System call to the CPU
- d) All of the mentioned

---

### 🔷 Topic 8: File System, Disk Scheduling

**Q47.** The information about all files is kept in ____________
- a) Operating system
- **b) Separate directory structure ✅**
- c) Swap space
- d) None of the mentioned

**Q48.** The OS keeps a small table containing information about all open files called:
- a) File table
- b) Directory table
- **c) Open-file table ✅**
- d) System table

**Q49.** In a single level directory:
- **a) All files are contained in the same directory ✅**
- b) All files are in different directories at the same level
- c) Depends on the OS
- d) None of the mentioned

**Q50.** The OS _______ the links when traversing directory trees to preserve acyclic structure.
- a) Deletes
- b) Considers
- **c) Ignores ✅**
- d) None of the mentioned

**Q51.** Which disk scheduling algorithm services requests in the order they arrive?
- **a) FCFS ✅**
- b) SSTF
- c) SCAN
- d) C-SCAN

**Q52.** The _______ program initializes all aspects of the system and starts the OS.
- **a) Bootstrap ✅**
- b) Main
- c) Bootloader
- d) ROM

**Q53.** On systems with multiple OSes, which decides which OS to load?
- a) Process control block
- b) File control block
- **c) Boot loader ✅**
- d) Bootstrap

---

### 🔷 Topic 9: Linux Commands

**Q54.** Which Linux command lists files in a directory?
- **a) ls ✅**
- b) dir
- c) list
- d) show

**Q55.** Which command is used to change file permissions in Linux?
- **a) chmod ✅**
- b) chown
- c) chgrp
- d) chperm

**Q56.** Which command displays currently running processes in Linux?
- **a) ps ✅**
- b) run
- c) proc
- d) task

**Q57.** Which command is used to find a file in Linux?
- **a) find ✅**
- b) search
- c) scan
- d) grep

**Q58.** Which Linux command displays the first few lines of a file?
- **a) head ✅**
- b) top
- c) first
- d) start

---

### 🔷 Topic 10: Real-Time OS

**Q59.** In a real-time OS:
- a) Process scheduling can be done only once
- b) All processes have the same priority
- c) Kernel is not required
- **d) A task must be serviced by its deadline period ✅**

**Q60.** Hard real-time OS has ______________ jitter than a soft real-time OS.
- a) Equal
- b) More
- **c) Less ✅**
- d) None of the mentioned

**Q61.** For real-time OS, interrupt latency should be ____________
- a) Zero
- **b) Minimal ✅**
- c) Maximum
- d) Dependent on scheduling

**Q62.** Which one of the following is a real-time OS?
- a) Windows CE
- b) RTLinux
- c) VxWorks
- **d) All of the mentioned ✅**

**Q63.** The priority of a process will ______________ if the scheduler assigns it a static priority.
- a) Depends on the OS
- b) Change
- **c) Remain unchanged ✅**
- d) None of the mentioned

---

### 🔷 Topic 11: Network & Distributed OS

**Q64.** Network operating system runs on ___________
- a) Every system in the network
- **b) Server ✅**
- c) Both server and every system
- d) None of the mentioned

**Q65.** What are the types of distributed operating systems?
- a) Zone based OS
- b) Level based OS
- c) Network OS
- **d) All of the mentioned ✅**

**Q66.** To recover from failures in network operations, _____________ information may be maintained.
- a) Operating system
- b) IP address
- c) Stateless
- **d) State ✅**

**Q67.** What are characteristics of Host-based IDS?
- a) Logs are analysed to detect trails of intrusion
- b) The host OS logs audit information
- c) Logs include logins, file opens, program executions
- **d) All of the mentioned ✅**

**Q68.** What are the characteristics of stack-based IDS?
- a) It is programmed to interpret certain packet series
- b) It models normal network usage
- **c) They are integrated closely with TCP/IP stack and watch packets ✅**
- d) The host OS logs audit information

---

## ✅ CHAPTER 2: DATABASE MANAGEMENT SYSTEM (DBMS)

---

### 🔷 Topic 1: Introduction to DBMS

**Q69.** What is the full form of DBMS?
- a) Data of Binary Management System
- **b) Database Management System ✅**
- c) Database Management Service
- d) Data Backup Management System

**Q70.** What is a database?
- a) Organized collection of information that cannot be accessed, updated, and managed
- b) Collection of data without organizing
- **c) Organized collection of data that can be accessed, updated, and managed ✅**
- d) Organized collection of data that cannot be updated

**Q71.** Who created the first DBMS?
- a) Edgar Frank Codd
- **b) Charles Bachman ✅**
- c) Charles Babbage
- d) Sharon B. Codd

**Q72.** Which of the following is not an example of DBMS?
- a) MySQL
- b) Microsoft Access
- c) IBM DB2
- **d) Google ✅**

**Q73.** Which of the following is NOT a feature of DBMS?
- a) Minimum duplication and redundancy
- b) High level of security
- **c) Single-user access only ✅**
- d) Support ACID property

**Q74.** Which of the following is a component of the DBMS?
- a) Data
- b) Data languages
- c) Data manager
- **d) All of the above ✅**

**Q75.** The DBMS acts as an interface between ________________ and ________________
- a) Data and the DBMS
- b) Application and SQL
- **c) Database application and the database ✅**
- d) The user and the software

**Q76.** The oldest DB model is _______________
- a) Network
- b) Physical
- **c) Hierarchical ✅**
- d) Relational

**Q77.** What is information about data called?
- a) Hyper data
- b) Tera data
- **c) Meta data ✅**
- d) Relations

**Q78.** A major goal of the DB system is to minimize block transfers. Which helps achieve this?
- a) Secondary storage
- b) Storage
- c) Catalog
- **d) Buffer ✅**

---

### 🔷 Topic 2: Relational Model

**Q79.** What does an RDBMS consist of?
- a) Collection of records
- b) Collection of keys
- **c) Collection of tables ✅**
- d) Collection of fields

**Q80.** Which of the following is known as a set of entities of the same type sharing same properties?
- a) Relation set
- b) Tuples
- **c) Entity set ✅**
- d) Entity Relation model

**Q81.** _____________ is a set of one or more attributes to uniquely identify a record.
- a) Primary key
- b) Foreign key
- **c) Super key ✅**
- d) Candidate key

**Q82.** Which of the following establishes a top-to-bottom relationship among items?
- a) Relational schema
- b) Network schema
- **c) Hierarchical schema ✅**
- d) All of the mentioned

**Q83.** Referential integrity constraint states:
- **a) Values in referencing relation must appear in referenced relation ✅**
- b) Every table must have a primary key
- c) A foreign key must be null
- d) None of the mentioned

**Q84.** What does a foreign key combined with a primary key create?
- a) Network model between tables
- **b) Parent-child relationship between tables ✅**
- c) One to one relationship
- d) All of the mentioned

**Q85.** The logical design, and the snapshot of data at a given instant in time is known as?
- a) Instance & Relation
- b) Relation & Schema
- c) Domain & Schema
- **d) Schema & Instance ✅**

**Q86.** _______ indicates the maximum number of entities that can be involved in a relationship.
- a) Greater entity count
- b) Minimum cardinality
- **c) Maximum cardinality ✅**
- d) ERD

---

### 🔷 Topic 3: SQL

**Q87.** The ability to query data, insert, delete, and alter tuples is offered by:
- a) TCL
- b) DCL
- c) DDL
- **d) DML ✅**

**Q88.** Which command is used to remove a relation from SQL?
- **a) Drop table ✅**
- b) Delete
- c) Purge
- d) Remove

**Q89.** Which of the following is correct to delete values in the relation teaches?
- **a) Delete from teaches; ✅**
- b) Delete from teaches where Id='Null';
- c) Remove table teaches;
- d) Drop table teaches;

**Q90.** After groups are established, SQL applies predicates in the ___________ clause.
- a) Where
- **b) Having ✅**
- c) Group by
- d) With

**Q91.** Which of the following is the subset of SQL used to manipulate Oracle structures including tables?
- a) Data Described Language
- b) Data Retrieval Language
- c) Data Manipulation Language
- **d) Data Definition Language ✅**

**Q92.** __________ command is used in SQL to issue multiple CREATE TABLE, CREATE VIEW and GRANT in one transaction.
- a) CREATE CLUSTER
- b) CREATE PACKAGE
- **c) CREATE SCHEMA ✅**
- d) All of the mentioned

**Q93.** Why is the following statement erroneous?
`SELECT dept_name, ID, avg(salary) FROM instructor GROUP BY dept_name;`
- a) dept_id should not be in GROUP BY
- b) GROUP BY clause is invalid
- c) avg(salary) should not be selected
- **d) ID is not in GROUP BY nor an aggregate ✅**

**Q94.** ______ resembles Create view.
- **a) Create table . . . as ✅**
- b) Create view as
- c) Create table . . . like
- d) With data

**Q95.** When is an SQL view updatable?
- a) SELECT contains attribute names without expressions, aggregates, or distinct
- b) FROM clause has 1 relation
- c) Query does not have GROUP BY or HAVING
- **d) All of the mentioned ✅**

---

### 🔷 Topic 4: Normalization

**Q96.** Which normal forms have a relation that contains information about a single entity?
- a) 4NF
- b) 2NF
- c) 5NF
- **d) 3NF ✅**

**Q97.** For designing a normal RDBMS, which normal form is considered adequate?
- a) 4NF
- **b) 3NF ✅**
- c) 2NF
- d) 5NF

**Q98.** Which of the following is known as the process of viewing cross-tab with a fixed value of one attribute?
- a) Dicing
- b) Pivoting
- **c) Slicing ✅**
- d) Both Pivoting and Dicing

**Q99.** BCNF (Boyce-Codd Normal Form) is a stronger version of:
- a) 1NF
- **b) 3NF ✅**
- c) 2NF
- d) 4NF

**Q100.** A relation is in 2NF if:
- a) It is in 1NF and has no transitive dependencies
- **b) It is in 1NF and every non-key attribute is fully functionally dependent on the primary key ✅**
- c) It has no repeating groups
- d) None of the mentioned

---

### 🔷 Topic 5: Indexing & Query Optimization

**Q101.** Which of the following functions construct histograms and use buckets for ranking?
- **a) Ntil() ✅**
- b) Newtil()
- c) Rank()
- d) All of the mentioned

**Q102.** Which of the following is the best way to represent attributes in a large DB?
- **a) Dot representation ✅**
- b) Concatenation
- c) Relational-and
- d) All of the mentioned

**Q103.** When is the "ROLLUP" operator used in GROUP BY?
- a) Find groups that make up subtotals
- b) Create group-wise grand totals
- **c) Group expressions from right to left for computing subtotals ✅**
- d) Produce a cross-tabular report in all directions

**Q104.** What type of index is best for range queries?
- **a) B-Tree index ✅**
- b) Hash index
- c) Bitmap index
- d) None of the mentioned

**Q105.** A dense index contains:
- **a) An entry for every search-key value in the file ✅**
- b) Entries for only some records
- c) Entries for block pointers
- d) None of the mentioned

---

### 🔷 Topic 6: Transaction Management (ACID)

**Q106.** Which of the following represents ACID properties?
- **a) Atomicity, Consistency, Isolation, Durability ✅**
- b) Availability, Consistency, Isolation, Durability
- c) Atomicity, Concurrency, Integrity, Durability
- d) None of the mentioned

**Q107.** Which ACID property ensures that a transaction either fully completes or is fully rolled back?
- **a) Atomicity ✅**
- b) Consistency
- c) Isolation
- d) Durability

**Q108.** Which technology does DBMS deploy to maintain transactional integrity?
- a) Pointers
- b) Cursors
- **c) Locks ✅**
- d) Triggers

**Q109.** What happens if a piece of data is stored in two places in the DB?
- **a) Storage is wasted & changing data in one spot causes inconsistency ✅**
- b) It can be more easily accessed
- c) Changing data in one spot causes inconsistency only
- d) Storage space is wasted only

**Q110.** Which RAID level is popular for storage of log files due to best write performance?
- **a) RAID level 0 ✅**
- b) RAID level 1
- c) RAID level 2
- d) RAID level 3

---

### 🔷 Topic 7: NoSQL, Big Data, Current Trends

**Q111.** NoSQL stands for:
- a) No Structured Query Language
- **b) Not Only SQL ✅**
- c) Non Operational SQL
- d) None of the mentioned

**Q112.** Which of the following is a NoSQL database?
- a) MySQL
- b) PostgreSQL
- **c) MongoDB ✅**
- d) Oracle

**Q113.** Which of the following is a characteristic of Big Data?
- a) Volume
- b) Velocity
- c) Variety
- **d) All of the mentioned ✅**

**Q114.** Which type of NoSQL database stores data as key-value pairs?
- **a) Redis ✅**
- b) MongoDB
- c) Neo4j
- d) HBase

**Q115.** CAP theorem states that a distributed system can guarantee at most:
- a) All three: Consistency, Availability, Partition Tolerance
- **b) Two out of three: Consistency, Availability, Partition Tolerance ✅**
- c) Only one property
- d) None of the mentioned

---

## ✅ CHAPTER 3: COMPUTER NETWORKS

---

### 🔷 Topic 1: Networking Basics

**Q116.** What is a computer network?
- a) A device used to display information on a computer screen
- **b) A collection of interconnected computers and devices that can communicate and share resources ✅**
- c) A type of software used to create documents
- d) The physical casing that protects a computer's components

**Q117.** What is the internet?
- a) A network of interconnected local area networks
- b) A collection of unrelated computers
- **c) Interconnection of wide area networks ✅**
- d) A single network

**Q118.** What are nodes in a computer network?
- a) The computer that routes the data
- b) The computer that terminates the data
- c) The computer that originates the data
- **d) All of the mentioned ✅**

**Q119.** What was the name of the first network?
- a) ASAPNET
- **b) ARPANET ✅**
- c) CNNET
- d) NSFNET

**Q120.** Which type of network shares a communication channel among all machines?
- a) Anycast network
- b) Multicast network
- c) Unicast network
- **d) Broadcast network ✅**

**Q121.** What is the term for the data communication system within a building or campus?
- a) MAN
- **b) LAN ✅**
- c) PAN
- d) WAN

**Q122.** Which of the following is an example of Bluetooth?
- a) Wide area network
- b) Virtual private network
- c) Local area network
- **d) Personal area network ✅**

**Q123.** Which of the following computer networks is built on top of another network?
- **a) Overlay network ✅**
- b) Prime network
- c) Prior network
- d) Chief network

**Q124.** When a collection of various computers appears as a single coherent system to clients:
- a) Mail system
- b) Networking system
- c) Computer network
- **d) Distributed system ✅**

**Q125.** How do two devices become part of a network?
- a) PIDs of processes on different devices are same
- **b) A process in one device can exchange information with a process in another device ✅**
- c) A process is active and another is inactive
- d) A process is running on both devices

---

### 🔷 Topic 2: TCP/IP

**Q126.** Which of the following is the network layer protocol for the internet?
- a) Hypertext transfer protocol
- b) File transfer protocol
- c) Ethernet
- **d) Internet protocol ✅**

**Q127.** How is a single channel shared by multiple signals?
- **a) Multiplexing ✅**
- b) Phase modulation
- c) Analog modulation
- d) Digital modulation

**Q128.** If a link transmits 4000 frames/sec and each slot has 8 bits, what is the TDM transmission rate?
- a) 500kbps
- **b) 32kbps ✅**
- c) 32bps
- d) 500bps

**Q129.** Which of the following networks extends a private network across public networks?
- **a) Virtual private network ✅**
- b) Local area network
- c) Storage area network
- d) Enterprise private network

**Q130.** Which connection is necessary for a computer to join the internet?
- a) Internet Society
- **b) Internet Service Provider ✅**
- c) Different computer
- d) Internet Architecture Board

---

### 🔷 Topic 3: Data Link Layer

**Q131.** Which layer does the data link layer take packets from and encapsulate into frames?
- a) Transport layer
- b) Application layer
- **c) Network layer ✅**
- d) Physical layer

**Q132.** What type of transmission is involved in communication between a computer and a keyboard?
- a) Half-duplex
- b) Full-duplex
- **c) Simplex ✅**
- d) Automatic

**Q133.** Which of the following are Gigabit Ethernets?
- a) 1000 BASE-LX
- b) 1000 BASE-CX
- c) 1000 BASE-SX
- **d) All of the mentioned ✅**

**Q134.** What does each packet contain in a virtual circuit network?
- a) Only source address
- b) Only destination address
- c) Full source and destination address
- **d) A short VC number ✅**

**Q135.** Which of this is NOT a network edge device?
- **a) Switch ✅**
- b) PC
- c) Smartphones
- d) Servers

---

### 🔷 Topic 4: Network Layer

**Q136.** Which one of the following is NOT a function of the network layer?
- a) Congestion control
- **b) Error control ✅**
- c) Routing
- d) Inter-networking

**Q137.** Which device forwards packets between networks by processing routing information?
- a) Firewall
- b) Bridge
- c) Hub
- **d) Router ✅**

**Q138.** What is the full form of OSI?
- a) Optical Service Implementation
- b) Open Service Internet
- **c) Open System Interconnection ✅**
- d) Operating System Interface

**Q139.** How many layers are there in the ISO OSI reference model?
- **a) 7 ✅**
- b) 5
- c) 4
- d) 6

**Q140.** Which network topology requires a central controller or hub?
- a) Ring
- b) Bus
- **c) Star ✅**
- d) Mesh

**Q141.** Which topology requires a multipoint connection?
- a) Ring
- **b) Bus ✅**
- c) Star
- d) Mesh

**Q142.** Which of the following maintains the Domain Name System?
- a) A single server
- b) A single computer
- **c) Distributed database system ✅**
- d) None of the mentioned

---

### 🔷 Topic 5: Transport Layer

**Q143.** Which layer is responsible for process-to-process delivery?
- a) Session layer
- b) Data link layer
- **c) Transport layer ✅**
- d) Network layer

**Q144.** What is the term for an endpoint of an inter-process communication flow?
- a) Port
- b) Machine
- **c) Socket ✅**
- d) Pipe

**Q145.** Which of the following allows you to connect and login to a remote computer?
- a) SMTP
- b) HTTP
- c) FTP
- **d) Telnet ✅**

**Q146.** TCP provides which of the following services?
- a) Unreliable, connectionless delivery
- **b) Reliable, connection-oriented delivery ✅**
- c) Fast, connectionless delivery
- d) None of the mentioned

**Q147.** UDP is preferred over TCP when:
- a) Reliability is critical
- b) Ordered delivery is needed
- **c) Speed is more important than reliability (e.g., video streaming) ✅**
- d) None of the mentioned

---

### 🔷 Topic 6: Application Layer

**Q148.** Which layer provides services to the user?
- a) Physical layer
- b) Presentation layer
- c) Session layer
- **d) Application layer ✅**

**Q149.** Which of the following allows LAN users to share computer programs and data?
- **a) File server ✅**
- b) Network
- c) Communication server
- d) Print server

**Q150.** HTTP stands for:
- **a) Hypertext Transfer Protocol ✅**
- b) High Transfer Text Protocol
- c) Hypertext Terminal Protocol
- d) None of the mentioned

**Q151.** Which protocol is used for sending emails?
- **a) SMTP ✅**
- b) FTP
- c) HTTP
- d) Telnet

**Q152.** DNS converts:
- **a) Domain names to IP addresses ✅**
- b) IP addresses to MAC addresses
- c) IP addresses to domain names only
- d) None of the mentioned

**Q153.** DHCP is used to:
- **a) Automatically assign IP addresses to devices ✅**
- b) Encrypt network traffic
- c) Route packets between networks
- d) None of the mentioned

---

### 🔷 Topic 7: Wireless Networking

**Q154.** Which of the following is the standard for wireless LAN?
- **a) IEEE 802.11 ✅**
- b) IEEE 802.3
- c) IEEE 802.5
- d) IEEE 802.15

**Q155.** WiMAX stands for:
- **a) Worldwide Interoperability for Microwave Access ✅**
- b) Wireless Maximum Access
- c) Wide Interoperability Mobile Access
- d) None of the mentioned

**Q156.** Which of the following is an ad-hoc wireless network mode?
- **a) IBSS (Independent Basic Service Set) ✅**
- b) BSS (Basic Service Set)
- c) ESS (Extended Service Set)
- d) None of the mentioned

**Q157.** Bluetooth uses which frequency band?
- a) 900 MHz
- **b) 2.4 GHz ✅**
- c) 5 GHz
- d) 60 GHz

**Q158.** The range of Bluetooth (Class 2) is approximately:
- a) 1 meter
- **b) 10 meters ✅**
- c) 100 meters
- d) 1000 meters

---

### 🔷 Topic 8: Network Security

**Q159.** Which of the following is used to render a computer resource unavailable to its intended users?
- a) Botnet process
- b) Worms attack
- c) Virus attack
- **d) Denial-of-service attack ✅**

**Q160.** When discussing IDS/IPS, what is a signature?
- a) Normal baseline network behavior
- b) Used to authorize users
- c) Electronic signature to authenticate identity
- **d) Attack-definition file ✅**

**Q161.** Which of the following is a symmetric key encryption algorithm?
- **a) AES ✅**
- b) RSA
- c) Diffie-Hellman
- d) ECC

**Q162.** A firewall is used for:
- **a) Preventing unauthorized access to or from a private network ✅**
- b) Speeding up network traffic
- c) Compressing data
- d) None of the mentioned

**Q163.** SSL/TLS operates at which layer?
- a) Network layer
- b) Data link layer
- **c) Transport layer ✅**
- d) Application layer

**Q164.** Which encryption uses the same key for both encryption and decryption?
- **a) Symmetric encryption ✅**
- b) Asymmetric encryption
- c) Public key encryption
- d) None of the mentioned

---

### 🔷 Topic 9: Performance & Troubleshooting

**Q165.** Which command is used to test network connectivity?
- **a) ping ✅**
- b) tracert
- c) ipconfig
- d) nslookup

**Q166.** What does `traceroute` (tracert) do?
- **a) Shows the path packets take to a destination ✅**
- b) Tests port availability
- c) Shows current IP configuration
- d) Queries DNS servers

**Q167.** Throughput is defined as:
- **a) The actual rate of successful data delivery over a communication channel ✅**
- b) The theoretical maximum data rate
- c) The delay in data transmission
- d) None of the mentioned

**Q168.** Latency in a network refers to:
- **a) The time delay for data to travel from source to destination ✅**
- b) The amount of data transmitted per second
- c) The number of hops between devices
- d) None of the mentioned

**Q169.** QoS (Quality of Service) in networking is used for:
- **a) Managing network resources to prioritize certain types of traffic ✅**
- b) Encrypting network packets
- c) Compressing data
- d) None of the mentioned

---

## 🔥 BONUS: MIXED TOPIC QUICK-FIRE MCQs (Q170–Q200)

**Q170.** What is the IPv4 address length?
- a) 16 bits
- **b) 32 bits ✅**
- c) 64 bits
- d) 128 bits

**Q171.** What is the IPv6 address length?
- a) 32 bits
- b) 64 bits
- **c) 128 bits ✅**
- d) 256 bits

**Q172.** Which layer of OSI handles encryption and decryption?
- a) Application layer
- **b) Presentation layer ✅**
- c) Session layer
- d) Transport layer

**Q173.** Which protocol is used to translate IP addresses to MAC addresses?
- **a) ARP ✅**
- b) RARP
- c) ICMP
- d) DHCP

**Q174.** Which SQL command is used to retrieve data?
- **a) SELECT ✅**
- b) GET
- c) FETCH
- d) RETRIEVE

**Q175.** What does RAID stand for?
- **a) Redundant Array of Independent Disks ✅**
- b) Random Access of Independent Data
- c) Redundant Array of Integrated Drives
- d) None of the mentioned

**Q176.** Which scheduling algorithm can cause starvation?
- a) Round Robin
- b) FCFS
- **c) Priority Scheduling ✅**
- d) None of the mentioned

**Q177.** The process of converting ER diagram to relational schema is called:
- a) Normalization
- **b) Reduction to relational schemas ✅**
- c) Decomposition
- d) Mapping

**Q178.** Which of the following is a connectionless protocol?
- a) TCP
- **b) UDP ✅**
- c) FTP
- d) Telnet

**Q179.** A primary key can be:
- a) Null
- b) Duplicate
- **c) Neither null nor duplicate ✅**
- d) Both null and duplicate

**Q180.** What does ICMP stand for?
- **a) Internet Control Message Protocol ✅**
- b) Internet Connection Management Protocol
- c) Internal Control Message Protocol
- d) None of the mentioned

**Q181.** Which join returns all records from both tables?
- a) Inner join
- b) Left join
- c) Right join
- **d) Full outer join ✅**

**Q182.** SONET stands for:
- **a) Synchronous Optical Network ✅**
- b) Serial Optical Network
- c) Synchronous Operating Network
- d) None of the mentioned

**Q183.** In tuple relational calculus, a query is represented as:
- a) { }{P(t) | t }
- **b) {t | P(t)} ✅**
- c) t | P() | t
- d) All of the mentioned

**Q184.** Which of the following provides reliable transmission over an unreliable network?
- a) UDP
- **b) TCP ✅**
- c) IP
- d) ARP

**Q185.** The `fork()` system call returns:
- a) 0 to parent, child PID to child
- **b) Child PID to parent, 0 to child ✅**
- c) Same PID to both
- d) -1 to both

**Q186.** A process in the "zombie" state is:
- **a) A terminated process whose entry still exists in the process table ✅**
- b) A process waiting for I/O
- c) A suspended process
- d) None of the mentioned

**Q187.** Which normal form deals with multivalued dependencies?
- a) 2NF
- b) 3NF
- c) BCNF
- **d) 4NF ✅**

**Q188.** The OSI model was developed by:
- **a) ISO (International Organization for Standardization) ✅**
- b) IEEE
- c) IETF
- d) ITU

**Q189.** Which type of memory is fastest?
- **a) Cache memory ✅**
- b) RAM
- c) ROM
- d) Hard disk

**Q190.** In SQL, `GROUP BY` is used with:
- a) WHERE clause
- **b) Aggregate functions ✅**
- c) ORDER BY clause only
- d) None of the mentioned

**Q191.** The `ping` command uses which protocol?
- **a) ICMP ✅**
- b) TCP
- c) UDP
- d) ARP

**Q192.** Virtual memory allows:
- **a) Execution of processes larger than physical memory ✅**
- b) Faster CPU operations
- c) More CPU cores to be utilized
- d) None of the mentioned

**Q193.** Which protocol is used for secure shell connections?
- a) Telnet
- **b) SSH ✅**
- c) FTP
- d) HTTP

**Q194.** In E-R diagrams, a rectangle represents:
- **a) Entity ✅**
- b) Attribute
- c) Relationship
- d) Primary key

**Q195.** Deadlock recovery can be done by:
- a) Resource preemption
- b) Process rollback
- c) Process termination
- **d) All of the mentioned ✅**

**Q196.** HTTP default port number is:
- **a) 80 ✅**
- b) 21
- c) 22
- d) 443

**Q197.** FTP uses port number:
- **a) 21 ✅**
- b) 22
- c) 23
- d) 25

**Q198.** SMTP uses port number:
- a) 21
- b) 22
- c) 23
- **d) 25 ✅**

**Q199.** HTTPS uses port number:
- a) 80
- b) 21
- **c) 443 ✅**
- d) 8080

**Q200.** SSH uses port number:
- a) 21
- b) 80
- **c) 22 ✅**
- d) 443

---

## 📊 Quick Answer Reference Table

| Q# | Ans | Q# | Ans | Q# | Ans | Q# | Ans |
|-----|-----|----|-----|----|-----|----|-----|
| 1 | d | 51 | a | 101 | a | 151 | a |
| 2 | c | 52 | a | 102 | a | 152 | a |
| 3 | b | 53 | c | 103 | c | 153 | a |
| 4 | b | 54 | a | 104 | a | 154 | a |
| 5 | d | 55 | a | 105 | a | 155 | a |
| 6 | d | 56 | a | 106 | a | 156 | a |
| 7 | a | 57 | a | 107 | a | 157 | b |
| 8 | c | 58 | a | 108 | c | 158 | b |
| 9 | a | 59 | d | 109 | a | 159 | d |
| 10 | b | 60 | c | 110 | a | 160 | d |
| 11 | a | 61 | b | 111 | b | 161 | a |
| 12 | d | 62 | d | 112 | c | 162 | a |
| 13 | d | 63 | c | 113 | d | 163 | c |
| 14 | c | 64 | b | 114 | a | 164 | a |
| 15 | a | 65 | d | 115 | b | 165 | a |
| 16 | c | 66 | d | 116 | b | 166 | a |
| 17 | c | 67 | d | 117 | c | 167 | a |
| 18 | d | 68 | c | 118 | d | 168 | a |
| 19 | c | 69 | b | 119 | b | 169 | a |
| 20 | c | 70 | c | 120 | d | 170 | b |
| 21 | b | 71 | b | 121 | b | 171 | c |
| 22 | a | 72 | d | 122 | d | 172 | b |
| 23 | c | 73 | c | 123 | a | 173 | a |
| 24 | a | 74 | d | 124 | d | 174 | a |
| 25 | b | 75 | c | 125 | b | 175 | a |
| 26 | b | 76 | c | 126 | d | 176 | c |
| 27 | b | 77 | c | 127 | a | 177 | b |
| 28 | a | 78 | d | 128 | b | 178 | b |
| 29 | a | 79 | c | 129 | a | 179 | c |
| 30 | a | 80 | c | 130 | b | 180 | a |
| 31 | d | 81 | c | 131 | c | 181 | d |
| 32 | c | 82 | c | 132 | c | 182 | a |
| 33 | b | 83 | a | 133 | d | 183 | b |
| 34 | a | 84 | b | 134 | d | 184 | b |
| 35 | d | 85 | d | 135 | a | 185 | b |
| 36 | a | 86 | c | 136 | b | 186 | a |
| 37 | a | 87 | d | 137 | d | 187 | d |
| 38 | c | 88 | a | 138 | c | 188 | a |
| 39 | b | 89 | a | 139 | a | 189 | a |
| 40 | d | 90 | b | 140 | c | 190 | b |
| 41 | a | 91 | d | 141 | b | 191 | a |
| 42 | d | 92 | c | 142 | c | 192 | a |
| 43 | b | 93 | d | 143 | c | 193 | b |
| 44 | a | 94 | a | 144 | c | 194 | a |
| 45 | b | 95 | d | 145 | d | 195 | d |
| 46 | a | 96 | d | 146 | b | 196 | a |
| 47 | b | 97 | b | 147 | c | 197 | a |
| 48 | c | 98 | c | 148 | d | 198 | d |
| 49 | a | 99 | b | 149 | a | 199 | c |
| 50 | c | 100 | b | 150 | a | 200 | c |

---

> 📌 **Study Tip:** Focus on Q1–Q100 first (high-frequency exam topics).
> Memorize the well-known port numbers: HTTP=80, HTTPS=443, FTP=21, SSH=22, SMTP=25, DNS=53, Telnet=23.
> For OS: Know the 4 deadlock conditions, Banker's Algorithm, and scheduling algorithms by heart.
> For DBMS: Know ACID, Normal Forms 1NF through BCNF, and SQL aggregate functions.
