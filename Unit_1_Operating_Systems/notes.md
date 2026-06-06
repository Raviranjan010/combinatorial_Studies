# 🖥️ Unit I: Operating System Basics — Comprehensive Lecture Notes

> **Target Audience:** Students and interview candidates looking for complete conceptual clarity, formal definitions, and rigorous mathematical and programmatic examples of Operating System fundamentals. No generic explanations; every topic is explained with its underlying technical architecture and concrete examples.

---

## 📌 Table of Contents

1. [Chapter 1: Foundations of Operating Systems](#chapter-1-foundations-of-operating-systems)
   - 1.1 What is an Operating System? (Formal Definition & Goals)
   - 1.2 Computer System Architecture & Layers
   - 1.3 Operating System Operations (Dual-Mode Operation)
   - 1.4 Operating System Structure & Architectures
   - 1.5 System Calls (Mechanism & Categories)
   - 1.6 System Boot Process & Interrupt Handling
2. [Chapter 2: Types of Operating Systems](#chapter-2-types-of-operating-systems)
   - 2.1 Batch Operating Systems
   - 2.2 Multiprogramming Operating Systems
   - 2.3 Time-Sharing (Multitasking) Operating Systems
   - 2.4 Multiprocessing Systems (SMP vs. AMP)
   - 2.5 Distributed Operating Systems
   - 2.6 Real-Time Operating Systems (RTOS - Hard vs. Soft)
   - 2.7 Clustered, Embedded, and Mobile Operating Systems
3. [Chapter 3: Process Management Foundations](#chapter-3-process-management-foundations)
   - 3.1 The Concept of a Process (Program vs. Process)
   - 3.2 Process States & Transition Diagrams (5-State & 7-State Models)
   - 3.3 Process Control Block (PCB) Structure
   - 3.4 Context Switching Mechanism & Overhead
   - 3.5 Schedulers: Long-Term, Medium-Term, and Short-Term
   - 3.6 Thread Concept (Process vs. Thread, User vs. Kernel Threads)
4. [Chapter 4: Processor Scheduling Algorithms](#chapter-4-processor-scheduling-algorithms)
   - 4.1 CPU Scheduling Criteria & Terminology
   - 4.2 Preemptive vs. Non-preemptive Scheduling
   - 4.3 Scheduling Algorithms (FCFS, SJF, SRTF, Priority, RR, MLQ, MLFQ)
   - 4.4 Comprehensive Mathematical Walkthrough

*(Note: Chapters 5 to 8 covering Process Synchronization, IPC, Memory Management, and Cheat Sheets are in the latter half of these notes.)*

---

# Chapter 1: Foundations of Operating Systems

## 1.1 What is an Operating System?

An **Operating System (OS)** is a system software that acts as an intermediary between the computer user and the computer hardware. Its primary purpose is to provide an environment in which a user can execute programs in a convenient and efficient manner.

### The Two Viewpoints of an OS:
1. **User View:** The OS is designed for **convenience** and **ease of use**, with attention paid to performance and usability (e.g., via GUI/CLI) rather than resource utilization.
2. **System View:** The OS is a **resource allocator**. The computer system has many resources (CPU time, memory space, file-storage space, I/O devices) that may be required to solve a problem. The OS acts as a manager of these resources, deciding how to allocate them to specific programs and users to prevent conflicts and ensure efficiency.

### Core Goals of an OS:
*   **Convenience:** Make the computer system convenient and easy to use.
*   **Efficiency:** Allow the computer hardware resources to be used in an efficient manner.
*   **Ability to Evolve:** Construction must allow the effective development, testing, and introduction of new system functions without interfering with service.

---

## 1.2 Computer System Architecture & Layers

A computer system can be divided roughly into four components:
1.  **Hardware:** Provides basic computing resources (CPU, Memory, I/O devices).
2.  **Operating System:** Controls and coordinates the use of hardware among various application programs.
3.  **Application Programs:** Define the ways in which the system resources are used to solve the computing problems of the users (e.g., Word Processors, Web Browsers, Databases, compilers).
4.  **Users:** People, machines, or other computers trying to execute tasks.

```
┌─────────────────────────────────────────────────────────┐
│                       👤 USERS                          │
│        (Users, Remote Systems, Automatic Agents)        │
└───────────────────────────┬─────────────────────────────┘
                            │ Interaction (GUI / CLI)
┌───────────────────────────▼─────────────────────────────┐
│                 📱 APPLICATION SOFTWARE                 │
│         (Compilers, Web Browsers, Databases, Games)      │
└───────────────────────────┬─────────────────────────────┘
                            │ System Calls / APIs
┌───────────────────────────▼─────────────────────────────┐
│                  ⚙️ OPERATING SYSTEM                    │
│    (Kernel, Device Drivers, File System, System Services)│
└───────────────────────────┬─────────────────────────────┘
                            │ Machine Instructions / Signals
┌───────────────────────────▼─────────────────────────────┐
│                      🔩 HARDWARE                        │
│            (CPU, RAM, Hard Disk, I/O Controller)        │
└─────────────────────────────────────────────────────────┘
```

---

## 1.3 Operating System Operations: Dual-Mode Operation

To ensure the proper execution of the operating system, we must be able to distinguish between the execution of operating-system code and user-defined code. Most computer systems provide hardware support that allows us to differentiate among various modes of execution.

### Mode Bit Architecture
At a minimum, the hardware supports two modes of operation:
1.  **User Mode (Mode Bit = 1):** The CPU executes instructions on behalf of user applications. In this mode, execution of **privileged instructions** is blocked. Any attempt to run a privileged instruction causes a hardware trap (exception) to the OS.
2.  **Kernel Mode (Mode Bit = 0):** Also known as Supervisor Mode, System Mode, or Privileged Mode. The CPU has unrestricted access to all hardware resources and can execute any instruction, including privileged ones (like disabling interrupts, modifying page tables, or accessing physical I/O ports).

### Mode Transition Mechanics
When the computer system is executing a user application, the system is in user mode. However, when a user application requests a service from the operating system (via a system call), or when an interrupt or trap occurs, the system must transition from user mode to kernel mode.

```
 USER MODE (Mode Bit = 1)                 KERNEL MODE (Mode Bit = 0)
┌─────────────────────────┐              ┌─────────────────────────┐
│  User process executing │              │                         │
│                         │              │                         │
│  Calls System Call ─────┼─ (Trap/Int) ─┼─► Service System Call   │
│  (e.g., read())         │              │   (Access hardware, etc)│
│                         │              │                         │
│  Resume Execution ◄─────┼─ (Return) ───┼─── Return from call     │
│  (Mode bit set to 1)    │              │   (Mode bit set to 0)   │
└─────────────────────────┘              └─────────────────────────┘
```

1.  **Interrupt/Trap occurs:** Hardware switches the mode bit from 1 to 0.
2.  **Kernel executes:** The OS services the interrupt or system call in Kernel Mode.
3.  **Return to User:** Before returning control to the user program, the OS runs a privileged instruction to change the mode bit back to 1.

> [!IMPORTANT]
> **Privileged Instructions** include:
> *   Modifying the Page Table or memory protection registers.
> *   Turning interrupts on/off.
> *   Directly accessing I/O devices (e.g., IN/OUT assembly instructions).
> *   Halting the CPU (`HLT` instruction).
> If these were allowed in User Mode, a rogue program could corrupt the memory of other programs or halt the entire computer.

---

## 1.4 Operating System Structure & Architectures

The architecture of an OS determines how its components are organized and how they communicate with each other.

### A) Monolithic Kernel Architecture
All operating system services run in the same address space as the kernel. The kernel contains the CPU scheduler, memory manager, file system, network protocols, and device drivers in one giant binary.

*   **Communication:** Components communicate via direct fast function calls.
*   **Pros:** ⚡ Extremely fast execution speed (no address space switching overhead).
*   **Cons:** 😰 Fragile. If a single device driver crashes due to a bug, it corrupts kernel memory, crashing the entire operating system.
*   **Examples:** Linux, Unix, MS-DOS.

### B) Microkernel Architecture
This design removes all non-essential components from the kernel and implements them as system and user-level programs (servers), such as file systems, device drivers, and network servers, running in their own isolated user address spaces.
The kernel's role is reduced to providing basic mechanisms: memory management space, process/thread management, and **Inter-Process Communication (IPC)**.

*   **Communication:** Services communicate via **Message Passing** through the kernel.
*   **Pros:** 
    *   **High Stability:** If a file server crashes, it can be restarted without affecting the rest of the OS.
    *   **Security:** Services have least-privilege access.
*   **Cons:** 🐢 Slower performance because message passing requires context switches and domain transitions.
*   **Examples:** MINIX, QNX, L4.

```
MONOLITHIC KERNEL                          MICROKERNEL
┌───────────────────────────────┐          ┌───────────────────────────────┐
│          USER SPACE           │          │          USER SPACE           │
│  [User Apps]                  │          │  [Apps]  [File Serv] [Drivers]│
├───────────────────────────────┤          ├───────────────────────────────┤
│         KERNEL SPACE          │          │         KERNEL SPACE          │
│  [Scheduler] [File System]    │          │  [Minimal Kernel: IPC, CPU]   │
│  [IPC]       [Drivers]        │          └───────────────────────────────┘
└───────────────────────────────┘
```

### C) Hybrid Kernel Architecture
Combines the speed of monolithic kernels with the modularity of microkernels. Major components run in kernel space for performance, but they are structured as dynamically loaded modules.
*   **Examples:** Windows NT (kernel, file system, graphics run in kernel space for speed), macOS (XNU).

---

## 1.5 System Calls

A **System Call** is the programmatic way in which a user-level program requests a service from the kernel. It is the operational interface between the user program and the OS.

### System Call Execution Mechanism
When a system call is made (e.g., using `printf()` in C which internally calls the `write()` system call):
1.  The library code loads the appropriate **System Call Number** into a specific CPU register (e.g., `rax` in x86-64).
2.  The arguments to the system call are loaded into other registers.
3.  The library executes a software interrupt/trap instruction (e.g., `syscall` or `int 0x80`).
4.  The CPU immediately halts execution, switches mode from User to Kernel (mode bit $\to$ 0), and jumps to a pre-defined address in the **System Call Table** (indexed by the System Call Number).
5.  The Kernel executes the handler, writes the return value to a register, and runs the return instruction (e.g., `sysret`), switching back to User Mode (mode bit $\to$ 1).

### Categories of System Calls (with Unix vs. Windows equivalents)

| Category | Purpose | Unix System Call | Windows API |
|---|---|---|---|
| **Process Control** | Create, terminate, wait for processes | `fork()`, `exec()`, `exit()`, `wait()` | `CreateProcess()`, `ExitProcess()`, `WaitForSingleObject()` |
| **File Management** | Open, read, write, close files | `open()`, `read()`, `write()`, `close()` | `CreateFile()`, `ReadFile()`, `WriteFile()`, `CloseHandle()` |
| **Device Management**| Attach, detach, request devices | `ioctl()`, `read()`, `write()` | `DeviceIoControl()`, `SetConsoleMode()` |
| **Information** | Get/set system date, time, PID | `getpid()`, `time()`, `alarm()` | `GetProcessId()`, `GetSystemTime()` |
| **Communication** | Create network connections, pipes | `pipe()`, `socket()`, `shmget()` | `CreatePipe()`, `socket()`, `CreateFileMapping()` |
| **Protection** | Manage file permissions, users | `chmod()`, `chown()` | `SetFileSecurity()`, `InitializeSecurityDescriptor()` |

---

## 1.6 System Boot Process & Interrupt Handling

### A) The Booting Process
Booting is the process of loading and initializing the operating system kernel into memory when the computer is powered on.

```
┌───────────┐     ┌───────────┐     ┌────────────┐     ┌────────────┐     ┌───────────┐
│ Power On  ├───►│ BIOS/UEFI ├───►│    POST    ├───►│ Bootsector ├───►│  Kernel   │
│  (Reset)  │     │ Execution │     │ (Hardware) │     │ (Mbr/Gpt)  │     │ Loaded    │
└───────────┘     └───────────┘     └────────────┘     └────────────┘     └───────────┘
```

1.  **Power Applied:** CPU executes a hardwired jump instruction to the BIOS/UEFI located in non-volatile ROM/Flash memory.
2.  **POST (Power-On Self-Test):** BIOS checks basic hardware sanity (RAM, CPU registers, keyboard, storage controller).
3.  **Boot Device Selection:** BIOS looks for a bootable device (HDD, SSD, USB) based on configuration.
4.  **MBR/GPT Read:** The BIOS reads the first sector (Sector 0, containing Master Boot Record or GUID Partition Table) of the boot device. This sector contains the primary bootloader.
5.  **Bootloader Execution:** The primary bootloader locates and loads the secondary bootloader (e.g., GRUB for Linux, Windows Boot Manager), which initializes system parameters and loads the operating system kernel into physical RAM.
6.  **Kernel Initialization:** Kernel starts system daemons, mounts the root file system, and spawns the first process (`init` on Linux, `smss.exe` on Windows).

### B) Interrupt Handling
An **Interrupt** is an asynchronous signal sent to the CPU by hardware or software indicating an event needs immediate attention.
*   **Hardware Interrupts:** Sent by hardware devices (e.g., keystroke, mouse movement, network packet arrival, disk read complete).
*   **Software Interrupts (Traps/Exceptions):** Triggered by software, either intentionally (System Calls) or due to errors (e.g., division by zero, page fault, segment violation).

#### Interrupt Processing Sequence:
1.  The CPU completes the execution of the current instruction.
2.  The CPU saves the state of the interrupted program (Program Counter and flags/registers) onto the system stack.
3.  The CPU looks up the interrupt source in the **Interrupt Vector Table (IVT)** to find the address of the corresponding **Interrupt Service Routine (ISR)**.
4.  The CPU jumps to the ISR address and executes the code in Kernel Mode.
5.  Once the ISR finishes, it executes an interrupt return instruction (`iret`), which restores the saved registers and PC, resuming the execution of the interrupted process.

> [!NOTE]
> **Polled vs. Vectored Interrupts:**
> *   **Polled Interrupts:** The CPU queries each device in sequence to determine which one generated the interrupt. (Simple hardware, slow software overhead).
> *   **Vectored Interrupts:** The interrupting device sends a unique hardware interrupt vector number along with the signal. The CPU directly indexes the Interrupt Vector Table using this number. (Complex hardware, fast software execution).

---

# Chapter 2: Types of Operating Systems

Operating systems have evolved through several stages, categorized by how they process jobs and manage the CPU.

## 2.1 Batch Operating Systems

### Mechanism:
In a Batch OS, the user does not interact directly with the computer system. Users prepare their jobs off-line (e.g., on punch cards) and submit them to a computer operator. The operator sorts the jobs into groups (batches) with similar requirements (e.g., all Fortran jobs together) and runs them through the computer as a single batch.

```
 Submissions         Operator's Batch Queue             CPU Execution
┌───────────┐       ┌──────────────────────────┐       ┌───────────────┐
│ User Card ├───┐   │ [Batch 1: Fortran Jobs]  ├──────►│ Executes      │
└───────────┘   │   │  - Job A, Job B, Job C   │       │ without       │
┌───────────┐   ├──►├──────────────────────────┤       │ user          │
│ User Card ├───┘   │ [Batch 2: Cobol Jobs]    │       │ intervention  │
└───────────┘       └──────────────────────────┘       └───────────────┘
```

*   **Key Advantage:** Avoids setup time delays (e.g., loading compilers repeatedly).
*   **Key Disadvantage:** CPU utilization is extremely low because when a job performs I/O, the CPU sits idle. Debugging is painful due to a long turnaround loop.

---

## 2.2 Multiprogramming Operating Systems

### Mechanism:
Multiprogramming increases CPU utilization by organizing jobs so that the CPU always has one job to execute. The system keeps multiple jobs in physical memory (RAM) simultaneously. The OS selects one job and starts executing it. If that job needs to wait for an I/O operation (e.g., loading data from disk), the CPU is switched to another job in memory.

```
Memory Layout
┌─────────────────────────────────┐
│ Operating System                │
├─────────────────────────────────┤
│ Job 1 (Waiting for I/O)         │ ◄── CPU Switches!
├─────────────────────────────────┤
│ Job 2 (Active on CPU)           │ ◄── CPU is here
├─────────────────────────────────┤
│ Job 3 (Ready in Memory)         │
└─────────────────────────────────┘
```

*   **Key Advantage:** High CPU utilization. The CPU rarely sits idle.
*   **Key Disadvantage:** Memory management is complex. Needs job scheduling to load processes into memory.

---

## 2.3 Time-Sharing (Multitasking) Operating Systems

### Mechanism:
Time-sharing (or multitasking) is a logical extension of multiprogramming. The CPU executes multiple jobs by switching among them so frequently that users can interact with each program while it is running. The switch is driven by a timer interrupt that fires at fixed intervals, allocating a specific **Time Quantum (or Time Slice)** to each process.

*   **Key Advantage:** Excellent response time (typically $< 100$ milliseconds). Each user gets the illusion of having a dedicated system.
*   **Key Disadvantage:** Context switching overhead. Needs complex CPU scheduling and memory protection.

---

## 2.4 Multiprocessing Systems

Multiprocessing systems have two or more physical processors (CPUs) in close communication, sharing the computer bus, system clock, memory, and peripheral devices.

### A) Symmetric Multiprocessing (SMP)
Each processor runs an identical copy of the operating system, and these copies communicate with one another as needed. All processors share physical RAM, and any processor can run any process.
*   **Key Aspect:** No master-slave relationship. Load balancing is dynamic but requires strict synchronization to avoid race conditions on shared kernel data structures.

### B) Asymmetric Multiprocessing (AMP)
A master processor controls the system. It schedules and allocates work to slave processors.
*   **Key Aspect:** Simple to design (only the master executes OS code, avoiding synchronization complexity), but the master is a single point of failure and performance bottleneck.

---

## 2.5 Distributed Operating Systems

A distributed operating system manages a group of independent, networked computers and makes them appear to the user as a single, centralized computer system.
*   **Architecture:** Loosely coupled. Each node has its own local memory and CPU, communicating via message-passing interfaces (networks).
*   **Transparency:** Users do not know where a file is stored or where a process is executing.
*   **Benefits:** High reliability (if one node fails, others take over) and resource sharing.

---

## 2.6 Real-Time Operating Systems (RTOS)

Used when there are rigid time requirements on the operation of a processor or the flow of data. An RTOS must guarantee that critical tasks complete within a specified **deadline**.

### A) Hard Real-Time Systems
The deadline is absolute. If a task fails to complete within the deadline, the system has failed, often leading to catastrophic results.
*   **Key characteristics:** No virtual memory (no unpredictable page faults), highly deterministic.
*   **Examples:** Anti-lock Braking Systems (ABS), pacemakers, flight controllers.

### B) Soft Real-Time Systems
The deadline is critical, but missing it occasionally is tolerated. The system will continue to function, but its quality of service decreases.
*   **Key characteristics:** Real-time tasks receive scheduling priority over normal tasks.
*   **Examples:** Video streaming players, online gaming servers, ATM transactions.

---

## 2.7 Clustered, Embedded, and Mobile Operating Systems

*   **Clustered Systems:** Similar to multiprocessing but composed of two or more individual systems (nodes) joined together over a high-speed LAN. They share storage (Storage Area Networks) and provide high availability. If one node fails, another node in the cluster takes over its applications (failover).
*   **Embedded Systems:** Designed to run on small, dedicated hardware devices (microwaves, car ECUs). They have severe constraints: tiny RAM (kilobytes), low power consumption, and minimal user interfaces. Often run specialized microkernels or custom RTOS.
*   **Mobile Systems:** Operating systems designed specifically for mobile devices (smartphones, tablets). They must handle touch interfaces, wireless connectivity (cellular, Wi-Fi, Bluetooth), battery life constraints, and sensor inputs (gyroscopes, GPS). Examples include Android (based on modified Linux kernel) and iOS.

---

# Chapter 3: Process Management Foundations

## 3.1 The Concept of a Process

A **Process** is a program in execution. It is the unit of work in a modern time-sharing system.

### Program vs. Process:
*   A **Program** is a passive entity, such as a file containing a list of instructions stored on disk (an executable like `main.exe`).
*   A **Process** is an active entity, with a program counter specifying the next instruction to execute, along with associated resources (registers, memory blocks).

### Memory Layout of a Process:
When a program is loaded into memory, it is allocated an address space divided into four main segments:

```
Address Space Layout
┌─────────────────────────────────────────┐ ◄── High Memory Addresses
│  STACK                                  │
│  (Local variables, Function parameters, │
│   Return addresses - Grows Downward)    │
├───────────────────┬─────────────────────┤
│                   │                     │
│                   ▼                     │
│                                         │
│                   ▲                     │
│                   │                     │
├───────────────────┴─────────────────────┤
│  HEAP                                   │
│  (Dynamically allocated memory via      │
│   malloc() or new - Grows Upward)       │
├─────────────────────────────────────────┤
│  DATA                                   │
│  (Global and static variables)          │
├─────────────────────────────────────────┤
│  TEXT (Code)                            │
│  (Program binary instructions)          │
└─────────────────────────────────────────┘ ◄── Low Memory Addresses
```

*   **Text Segment:** Contains the executable code.
*   **Data Segment:** Contains global and static variables (initialized and uninitialized).
*   **Heap Segment:** Dynamically allocated memory during runtime (e.g., using `malloc()` in C or `new` in C++).
*   **Stack Segment:** Temporary data storage used for function calls (local variables, function parameters, return addresses).

---

## 3.2 Process States & Transition Diagrams

As a process executes, it changes state. The state of a process is defined in part by that process's current activity.

### The 5-State Process Model
1.  **New:** The process is being created but has not yet been admitted to the ready queue.
2.  **Ready:** The process is in memory, waiting to be allocated to a processor.
3.  **Running:** Instructions are being executed by the CPU.
4.  **Waiting (Blocked):** The process is waiting for some event to occur (such as an I/O completion or reception of a signal).
5.  **Terminated:** The process has finished execution.

```
       Admitted            Scheduler Dispatch
 ┌───┐          ┌─────┐                           ┌───────┐
 │New├─── ───►  │Ready├──────────────────────────►│Running│
 └───┘          └▲───┬┘                           └───┬─┬─┘
                 │   │                                │ │
                 │   │         Interrupt              │ │  Exit
                 │   └◄───────────────────────────────┘ │──► Terminated
                 │                                      │
                 │            I/O or event wait         │
                 └──────────────────────────────────────┘
```

*   **Admitted:** Transition from New to Ready (managed by Long-term Scheduler).
*   **Scheduler Dispatch:** Selects a process from Ready and assigns CPU (managed by Short-term Scheduler).
*   **Interrupt:** CPU preempts the running process (e.g., time slice expired) and places it back in the Ready state.
*   **I/O or Event Wait:** The process requests an I/O resource or waits for a signal, moving from Running to Waiting.
*   **I/O or Event Completion:** The I/O completes, moving the process back to the Ready state.

### The 7-State Process Model (With Swapping)
When memory becomes full, the OS may swap processes out of RAM to the secondary disk storage (backing store). This introduces two new states:
6.  **Suspend Ready:** The process is ready to execute but has been swapped out to disk.
7.  **Suspend Wait (Suspend Blocked):** The process is blocked waiting for an event and has been swapped out to disk.

```
                     ┌───────┐
                     │  New  │
                     └───┬───┘
                         │ Admitted
                         ▼
        ┌───Swap In──────┬─────────────┐
        │                ▼             │
 ┌──────┴────────┐  ┌─────────┐   ┌────┴────┐
 │ Suspend Ready │  │  Ready  ├─► │ Running ├──► Terminated
 └──────▲────────┘  └────▲────┘   └────┬────┘
        │                │             │
        │ Swap Out       │ I/O Done    │ I/O Wait
        │                │             ▼
 ┌──────┴────────┐  ┌────┴────┐   ┌────┴────┐
 │ Suspend Wait  ├──┼─I/O Done┤◄──│ Blocked │
 └───────────────┘  └─────────┘   └─────────┘
```

*   **Suspend:** Moving a process from Ready to Suspend Ready, or Blocked to Suspend Wait (managed by Medium-term Scheduler).
*   **Activate (Swap In):** Moving a process from Suspend Ready to Ready once RAM space is freed.

---

## 3.3 Process Control Block (PCB)

Each process is represented in the operating system by a **Process Control Block (PCB)**, also called a Task Control Block. It is a data structure in kernel memory that contains all information associated with a specific process.

### Major Fields of a PCB:
1.  **Process ID (PID):** A unique integer identifier assigned by the OS.
2.  **Process State:** Current state (New, Ready, Running, etc.).
3.  **Program Counter (PC):** The address of the next instruction to be executed for this process.
4.  **CPU Registers:** Accumulators, index registers, stack pointers, general-purpose registers. These must be saved during interrupts to allow resume.
5.  **CPU-Scheduling Information:** Process priority, pointers to scheduling queues, and other scheduling parameters.
6.  **Memory-Management Information:** Page tables, segment tables, limit registers, depending on the memory system used.
7.  **Accounting Information:** CPU time used, time limits, execution count.
8.  **I/O Status Information:** List of open files, I/O devices allocated to the process.

---

## 3.4 Context Switching

Switching the CPU to another process requires performing a **Context Switch**. This involves saving the state (context) of the current process and loading the saved state of the new process.

### The Context Switch Sequence:

```
  Process P0                                                 Process P1
 ┌──────────┐                                               ┌──────────┐
 │ Running  │                                               │  Ready   │
 └────┬─────┘                                               └──────────┘
      │  (Interrupt or System Call)
      ▼
   [SAVE state into PCB0] ──┐
                            │ (OS Overhead)
   [LOAD state from PCB1] ◄─┘
      │
      │                                                     ▼
      │                                                ┌──────────┐
      │                                                │ Running  │
      │                                                └────┬─────┘
      │                                                     │ (Interrupt)
      │                                                     ▼
      │                                            [SAVE state into PCB1] ──┐
      │                                                                     │
   [LOAD state from PCB0] ◄─────────────────────────────────────────────────┘
      │
      ▼
 ┌──────────┐
 │ Running  │
 └──────────┘
```

1.  **Interrupt triggers:** CPU switches to kernel mode.
2.  **Save Context:** The hardware and OS save the program counter, CPU registers, and status flags of the executing process ($P_0$) into its PCB ($PCB_0$).
3.  **Select Process:** The scheduler selects another process ($P_1$) to run.
4.  **Load Context:** The OS updates the MMU base registers to switch address space, loads the saved registers and program counter from $PCB_1$ into the physical CPU.
5.  **Resume:** The CPU resumes execution of $P_1$.

> [!WARNING]
> **Context Switch Overhead is Pure Waste:**
> During a context switch, the CPU does no useful work; it simply copies registers and swaps memory tables. Context switch times are highly dependent on hardware speed, register count, and page table flushing. Typical context switch times range from 1 to a few microseconds.

---

## 3.5 Schedulers

Operating systems use three distinct types of schedulers to manage processes in queues:

| Feature | Long-Term Scheduler (Job Scheduler) | Medium-Term Scheduler (Swapper) | Short-Term Scheduler (CPU Scheduler) |
|---|---|---|---|
| **Speed / Frequency** | Very slow (invoked every few minutes) | Moderate (invoked on memory pressure) | Ultra-fast (invoked every few milliseconds) |
| **Location** | Controls pool on disk | Controls swap space on disk | Controls Ready Queue in RAM |
| **Function** | Selects jobs from disk and loads them into RAM | Swaps processes out of RAM to disk, and vice versa | Selects process from Ready Queue and assigns CPU |
| **Control** | Controls **Degree of Multiprogramming** | Controls memory footprint balance | Minimal direct control on multiprogramming degree |
| **Selection Type** | Balances CPU-bound and I/O-bound jobs | Manages physical memory capacity | Directly schedules active execution |

*   **Degree of Multiprogramming:** The number of processes residing in memory. If it is kept constant, the system is stable.
*   **Job Types:**
    *   **I/O-Bound Process:** Spends more time doing I/O than computing; has short CPU bursts.
    *   **CPU-Bound Process:** Generates I/O requests infrequently; spends more time doing computations; has long CPU bursts.
    *   *Goal of LTS:* Select a good mix of both so that the CPU scheduler and I/O queues stay balanced.

---

## 3.6 Thread Concept

A **Thread** is a basic unit of CPU utilization (also called a lightweight process). It comprises a thread ID, a program counter, a register set, and a stack. It shares its code section, data section, and operating-system resources (like open files and signals) with other threads belonging to the same process.

```
┌───────────────────────────────────────────────────────────────────┐
│                           PROCESS SPACE                           │
│                                                                   │
│  📁 Code Section           📄 Data Section          🖨️ Resources  │
│                                                                   │
│  ┌──────────────────────┐ ┌──────────────────────┐ ┌────────────┐ │
│  │       THREAD 1       │ │       THREAD 2       │ │  THREAD 3  │ │
│  │                      │ │                      │ │            │ │
│  │  ⚙️ Registers        │ │  ⚙️ Registers        │ │            │ │
│  │  📚 Stack            │ │  📚 Stack            │ │ ...        │ │
│  │  📍 PC               │ │  📍 PC               │ │            │ │
│  └──────────────────────┘ └──────────────────────┘ └────────────┘ │
└───────────────────────────────────────────────────────────────────┘
```

### Process vs. Thread Comparison

| Feature | Process | Thread |
|---|---|---|
| **Definition** | An executing instance of a program. | A subset of a process (unit of CPU execution). |
| **Resource Sharing** | Do not share memory with other processes (isolated). | Share code, data, and files with sibling threads. |
| **Creation Overhead** | High (allocating virtual address space, PCB). | Low (shares existing address space). |
| **Context Switch Time**| High (requires switching page tables, TLB flush). | Low (only switches registers and stack). |
| **Crash Safety** | High (if one process crashes, others run). | Low (if one thread crashes, the parent process dies). |

### User-Level vs. Kernel-Level Threads
1.  **User-Level Threads:** Managed by a user-space threading library (e.g., POSIX Pthreads, Java threads on green JVMs) without kernel support.
    *   *Pros:* Very fast creation and switching (no mode transitions).
    *   *Cons:* If a user-level thread calls a blocking system call (like disk read), the entire parent process blocks, stopping all other threads in that process.
2.  **Kernel-Level Threads:** Supported and managed directly by the operating system kernel.
    *   *Pros:* If one thread blocks, the kernel can schedule another thread of the same process.
    *   *Cons:* Thread operations require transition to kernel mode, adding overhead.

---

# Chapter 4: Processor Scheduling Algorithms

## 4.1 CPU Scheduling Criteria

CPU scheduling algorithms decide which process in the ready queue is allocated the CPU. To compare these algorithms, we use several criteria:

*   **CPU Utilization:** The percentage of time the CPU is busy executing user processes (Target: Maximize, $80\% - 90\%$).
*   **Throughput:** The number of processes completed per unit of time (Target: Maximize).
*   **Turnaround Time ($TAT$):** The interval from the time of submission of a process to the time of completion.
    $$TAT = CT - AT$$
    *(where $CT$ = Completion Time, $AT$ = Arrival Time)* (Target: Minimize).
*   **Waiting Time ($WT$):** The total amount of time a process spends waiting in the ready queue.
    $$WT = TAT - BT$$
    *(where $BT$ = Burst Time required on CPU)* (Target: Minimize).
*   **Response Time ($RT$):** The time from submission (Arrival) to the first response generated by the CPU. Important in interactive systems. (Target: Minimize).

---

## 4.2 Preemptive vs. Non-preemptive Scheduling

CPU scheduling decisions take place under four conditions:
1.  When a process switches from running state to waiting state (e.g., I/O request).
2.  When a process switches from running state to ready state (e.g., timer interrupt).
3.  When a process switches from waiting state to ready state (e.g., I/O completed).
4.  When a process terminates.

*   **Non-Preemptive Scheduling:** Scheduling occurs only under conditions 1 and 4. Once the CPU has been allocated to a process, the process keeps the CPU until it releases it either by terminating or by switching to the waiting state.
*   **Preemptive Scheduling:** Scheduling can occur under all four conditions. The OS can interrupt a running process and reclaim the CPU to assign it to another process. Requires hardware timers and synchronization locks.

---

## 4.3 Scheduling Algorithms

### 1. First-Come, First-Served (FCFS)
*   **Type:** Non-preemptive.
*   **Logic:** The process that requests the CPU first is allocated the CPU first. Managed using a FIFO queue.
*   **Problem - Convoy Effect:** Short processes wait behind a single long process. If a long process runs first, the average waiting time of the system skyrockets.

---

### 2. Shortest Job First (SJF)
*   **Type:** Non-preemptive.
*   **Logic:** Associates with each process the length of its next CPU burst. When the CPU is available, it is assigned to the process with the smallest burst time. If two processes have the same burst time, FCFS is used as a tie-breaker.
*   **Optimality:** SJF is provably optimal because it gives the minimum average waiting time for a given set of processes.
*   **Implementation Challenge:** The difficulty is knowing the length of the next CPU request. In practice, the next burst is predicted using **Exponential Smoothing** of previous bursts:
    $$\tau_{n+1} = \alpha t_n + (1 - \alpha) \tau_n$$
    Where $t_n$ is the actual length of the $n$-th burst, $\tau_n$ is the predicted value, and $\alpha \in [0, 1]$ determines the weight of recent history.

---

### 3. Shortest Remaining Time First (SRTF)
*   **Type:** Preemptive. (Preemptive version of SJF).
*   **Logic:** When a new process arrives in the ready queue, if its burst time is shorter than the remaining burst time of the currently running process, the running process is preempted and the new process is executed.

---

### 4. Priority Scheduling
*   **Type:** Preemptive or Non-preemptive.
*   **Logic:** A priority number (integer) is associated with each process. The CPU is allocated to the process with the highest priority (some systems use low numbers for high priority, e.g., Unix; others use high numbers, e.g., Windows).
*   **Problem - Starvation (Indefinite Blocking):** A low-priority process may wait indefinitely if higher-priority processes keep arriving.
*   **Solution - Aging:** Gradual increase of the priority of processes that wait in the system for a long time. For example, if priority goes from 10 (lowest) to 1 (highest), aging might increment (decrease number) the priority by 1 every 10 seconds of waiting.

---

### 5. Round Robin (RR)
*   **Type:** Preemptive.
*   **Logic:** Designed specifically for time-sharing systems. A small unit of time, called a **Time Quantum** ($Q$, usually $10-100$ milliseconds), is defined. The ready queue is treated as a circular queue. The CPU scheduler goes around the ready queue, allocating the CPU to each process for up to 1 time quantum.
*   **Mechanics:**
    *   If process burst time $< Q$: Process runs, releases CPU voluntarily, and terminates or blocks.
    *   If process burst time $> Q$: The timer interrupt goes off after $Q$. The process is preempted and placed at the tail of the ready queue.
*   **Performance Dependency on $Q$:**
    *   If $Q$ is extremely large: RR degenerates to FCFS.
    *   If $Q$ is extremely small: RR behaves like processor sharing (illusion of $n$ processors running at $1/n$ speed), but context switch overhead dominates, causing CPU wastage.

```
   Quantum Q = 12                      Quantum Q = 2
  ┌──────────────┐                     ┌───┬───┬───┬───┐
  │  Process P1  │                     │P1 │P2 │P1 │P2 │
  └──────────────┘                     └───┴───┴───┴───┘
  0            12                      0   2   4   6   8
  (Context Switch = 0)                 (Context Switch Overhead = High)
```

---

### 6. Multilevel Queue Scheduling (MLQ)
*   **Logic:** Partitions the ready queue into several separate queues based on process properties (e.g., memory size, process priority, process type). For example:
    *   Queue 1: Foreground (Interactive) processes (Scheduled via Round Robin).
    *   Queue 2: Background (Batch) processes (Scheduled via FCFS).
*   **Queue Scheduling:** There must be scheduling between the queues, typically implemented as fixed-priority preemptive scheduling (e.g., run nothing from Queue 2 if Queue 1 has processes). Processes cannot change queues.

---

### 7. Multilevel Feedback Queue Scheduling (MLFQ)
*   **Logic:** Unlike MLQ, MLFQ allows processes to move between queues.
*   **Mechanics:**
    *   If a process uses too much CPU time, it is moved to a lower-priority queue (demoted). This leaves I/O-bound and interactive processes in the high-priority queues.
    *   If a process waits too long in a lower-priority queue, it is moved to a higher-priority queue (promoted). This prevents starvation.
*   **MLFQ Parameters:** Number of queues, scheduling algorithm for each queue, method for demotion, method for promotion, method for entering a queue.

---

## 4.4 Comprehensive Mathematical Walkthrough

Let us evaluate FCFS, SJF, SRTF, Priority (Non-preemptive), and Round Robin ($Q = 2$) on the following set of five processes. Lower priority number indicates higher priority.

| Process | Arrival Time ($AT$) | Burst Time ($BT$) | Priority |
|---|---|---|---|
| **$P_1$** | 0 | 3 | 3 |
| **$P_2$** | 1 | 6 | 1 (Highest) |
| **$P_3$** | 3 | 1 | 4 |
| **$P_4$** | 4 | 2 | 2 |
| **$P_5$** | 6 | 4 | 5 (Lowest) |

---

### A) First-Come, First-Served (FCFS)
Processes are executed in strict order of their arrival.

#### Gantt Chart:
```
  0       3             9    10    12          16
  ┌───────┬─────────────┬────┬─────┬───────────┐
  │  P1   │     P2      │ P3 │ P4  │    P5     │
  └───────┴─────────────┴────┴─────┴───────────┘
```

#### Calculation Table:
*   $TAT = CT - AT$
*   $WT = TAT - BT$

| Process | $AT$ | $BT$ | $CT$ | $TAT$ | $WT$ |
|---|---|---|---|---|---|
| **$P_1$** | 0 | 3 | 3 | $3 - 0 = 3$ | $3 - 3 = 0$ |
| **$P_2$** | 1 | 6 | 9 | $9 - 1 = 8$ | $8 - 6 = 2$ |
| **$P_3$** | 3 | 1 | 10 | $10 - 3 = 7$ | $7 - 1 = 6$ |
| **$P_4$** | 4 | 2 | 12 | $12 - 4 = 8$ | $8 - 2 = 6$ |
| **$P_5$** | 6 | 4 | 16 | $16 - 6 = 10$ | $10 - 4 = 6$ |

*   **Average Turnaround Time:** $\frac{3 + 8 + 7 + 8 + 10}{5} = \frac{36}{5} = 7.2$ time units.
*   **Average Waiting Time:** $\frac{0 + 2 + 6 + 6 + 6}{5} = \frac{20}{5} = 4.0$ time units.

---

### B) Shortest Job First (SJF) - Non-preemptive
When CPU becomes free, pick the process with the shortest burst time currently in the ready queue.

*   **At $t=0$:** Only $P_1$ is in queue. Run $P_1$ until completion ($t=3$).
*   **At $t=3$:** $P_2$ (arrived at 1, $BT=6$) and $P_3$ (arrived at 3, $BT=1$) are waiting. Pick shortest: $P_3$ ($BT=1$). Run $P_3$ until completion ($t=4$).
*   **At $t=4$:** $P_2$ ($BT=6$) and $P_4$ (arrived at 4, $BT=2$) are waiting. Pick shortest: $P_4$ ($BT=2$). Run $P_4$ until completion ($t=6$).
*   **At $t=6$:** $P_2$ ($BT=6$) and $P_5$ (arrived at 6, $BT=4$) are waiting. Pick shortest: $P_5$ ($BT=4$). Run $P_5$ until completion ($t=10$).
*   **At $t=10$:** Only $P_2$ is left. Run $P_2$ until completion ($t=16$).

#### Gantt Chart:
```
  0       3    4     6          10             16
  ┌───────┬────┬─────┬──────────┬──────────────┐
  │  P1   │ P3 │ P4  │    P5    │      P2      │
  └───────┴────┴─────┴──────────┴──────────────┘
```

#### Calculation Table:

| Process | $AT$ | $BT$ | $CT$ | $TAT$ | $WT$ |
|---|---|---|---|---|---|
| **$P_1$** | 0 | 3 | 3 | $3 - 0 = 3$ | $3 - 3 = 0$ |
| **$P_2$** | 1 | 6 | 16 | $16 - 1 = 15$ | $15 - 6 = 9$ |
| **$P_3$** | 3 | 1 | 4 | $4 - 3 = 1$ | $1 - 1 = 0$ |
| **$P_4$** | 4 | 2 | 6 | $6 - 4 = 2$ | $2 - 2 = 0$ |
| **$P_5$** | 6 | 4 | 10 | $10 - 6 = 4$ | $4 - 4 = 0$ |

*   **Average Turnaround Time:** $\frac{3 + 15 + 1 + 2 + 4}{5} = \frac{25}{5} = 5.0$ time units.
*   **Average Waiting Time:** $\frac{0 + 9 + 0 + 0 + 0}{5} = \frac{9}{5} = 1.8$ time units.

---

### C) Shortest Remaining Time First (SRTF) - Preemptive
Check remaining burst times on every arrival.

*   **At $t=0$:** Start $P_1$ (remaining $BT=3$).
*   **At $t=1$:** $P_2$ arrives ($BT=6$). Remaining times: $P_1 = 2$, $P_2 = 6$. $P_1$ continues.
*   **At $t=3$:** $P_1$ finishes. $P_3$ arrives ($BT=1$). Ready queue has $P_2$ ($BT=6$) and $P_3$ ($BT=1$). Run $P_3$.
*   **At $t=4$:** $P_3$ finishes. $P_4$ arrives ($BT=2$). Ready queue has $P_2$ ($BT=6$) and $P_4$ ($BT=2$). Run $P_4$.
*   **At $t=6$:** $P_4$ finishes. $P_5$ arrives ($BT=4$). Ready queue has $P_2$ ($BT=6$) and $P_5$ ($BT=4$). Run $P_5$.
*   **At $t=10$:** $P_5$ finishes. Only $P_2$ is left. Run $P_2$.
*   **At $t=16$:** $P_2$ finishes.

*(Note: In this specific case, the execution sequence is identical to non-preemptive SJF, because arriving processes did not have smaller burst times than the remaining time of the active process at their instants of arrival. E.g., at $t=1$, $P_1$'s remaining time was 2, which is smaller than $P_2$'s burst time of 6. Let's see what happens if we calculate details)*

#### Gantt Chart:
```
  0       3    4     6          10             16
  ┌───────┬────┬─────┬──────────┬──────────────┐
  │  P1   │ P3 │ P4  │    P5    │      P2      │
  └───────┴────┴─────┴──────────┴──────────────┘
```
*   Average WT = $1.8$, Average TAT = $5.0$.

---

### D) Priority Scheduling - Non-preemptive
Pick the process with the highest priority (lowest number value).

*   **At $t=0$:** Only $P_1$ is available. Run $P_1$ until completion ($t=3$).
*   **At $t=3$:** $P_2$ (Priority 1) and $P_3$ (Priority 4) are waiting. Pick highest priority: $P_2$. Run $P_2$ until completion ($t=9$).
*   **At $t=9$:** $P_3$ (Priority 4), $P_4$ (Priority 2), and $P_5$ (Priority 5) are waiting. Pick highest: $P_4$. Run $P_4$ until completion ($t=11$).
*   **At $t=11$:** $P_3$ (Priority 4) and $P_5$ (Priority 5) are waiting. Pick highest: $P_3$. Run $P_3$ until completion ($t=12$).
*   **At $t=12$:** Only $P_5$ is left. Run $P_5$ until completion ($t=16$).

#### Gantt Chart:
```
  0       3             9    11   12           16
  ┌───────┬─────────────┬────┬────┬────────────┐
  │  P1   │     P2      │ P4 │ P3 │     P5     │
  └───────┴─────────────┴────┴────┴────────────┘
```

#### Calculation Table:

| Process | $AT$ | $BT$ | $CT$ | $TAT$ | $WT$ |
|---|---|---|---|---|---|
| **$P_1$** | 0 | 3 | 3 | $3 - 0 = 3$ | $3 - 3 = 0$ |
| **$P_2$** | 1 | 6 | 9 | $9 - 1 = 8$ | $8 - 6 = 2$ |
| **$P_3$** | 3 | 1 | 12 | $12 - 3 = 9$ | $9 - 1 = 8$ |
| **$P_4$** | 4 | 2 | 11 | $11 - 4 = 7$ | $7 - 2 = 5$ |
| **$P_5$** | 6 | 4 | 16 | $16 - 6 = 10$ | $10 - 4 = 6$ |

*   **Average Turnaround Time:** $\frac{3 + 8 + 9 + 7 + 10}{5} = \frac{37}{5} = 7.4$ time units.
*   **Average Waiting Time:** $\frac{0 + 2 + 8 + 5 + 6}{5} = \frac{21}{5} = 4.2$ time units.

---

### E) Round Robin (RR) - Quantum $Q = 2$
Processes are scheduled in arrival order, but can run for at most 2 units.

#### Step-by-Step Execution trace:
*   **Ready Queue Structure:** `[Process]` (represents processes currently in queue).
*   **$t=0$:** $P_1$ arrives. Queue: `[P1]`. Run $P_1$ for 2 units.
*   **$t=1$:** $P_2$ arrives.
*   **$t=2$:** $P_1$ is preempted (remaining $BT=1$). Queue: `[P2]`. (We add the preempted $P_1$ to the tail: `[P2, P1]`). Run $P_2$ for 2 units.
*   **$t=3$:** $P_3$ arrives. Add to queue: `[P1, P3]`.
*   **$t=4$:** $P_2$ is preempted (remaining $BT=4$). $P_4$ arrives. Queue layout after preempted $P_2$ and new $P_4$ join: `[P1, P3, P4, P2]`. Run $P_1$ for 1 unit (finishes).
*   **$t=5$:** $P_1$ terminates. Queue: `[P3, P4, P2]`. Run $P_3$ for 1 unit (finishes).
*   **$t=6$:** $P_3$ terminates. $P_5$ arrives. Queue layout: `[P4, P2, P5]`. Run $P_4$ for 2 units (finishes).
*   **$t=8$:** $P_4$ terminates. Queue: `[P2, P5]`. Run $P_2$ for 2 units (remaining $BT=2$). Queue: `[P5, P2]`.
*   **$t=10$:** Run $P_5$ for 2 units (remaining $BT=2$). Queue: `[P2, P5]`.
*   **$t=12$:** Run $P_2$ for 2 units (finishes). Queue: `[P5]`.
*   **$t=14$:** Run $P_5$ for 2 units (finishes).

#### Gantt Chart:
```
  0    2    4    5    6    8    10   12   14
  ┌────┬────┬────┬────┬────┬────┬────┬────┐
  │ P1 │ P2 │ P1 │ P3 │ P4 │ P2 │ P5 │ P2 │ P5 │
  └────┴────┴────┴────┴────┴────┴────┴────┴────┘
```

#### Calculation Table:

| Process | $AT$ | $BT$ | $CT$ | $TAT$ | $WT$ |
|---|---|---|---|---|---|
| **$P_1$** | 0 | 3 | 5 | $5 - 0 = 5$ | $5 - 3 = 2$ |
| **$P_2$** | 1 | 6 | 12 | $12 - 1 = 11$ | $11 - 6 = 5$ |
| **$P_3$** | 3 | 1 | 6 | $6 - 3 = 3$ | $3 - 1 = 2$ |
| **$P_4$** | 4 | 2 | 8 | $8 - 4 = 4$ | $4 - 2 = 2$ |
| **$P_5$** | 6 | 4 | 14 | $14 - 6 = 8$ | $8 - 4 = 4$ |

*   **Average Turnaround Time:** $\frac{5 + 11 + 3 + 4 + 8}{5} = \frac{31}{5} = 6.2$ time units.
*   **Average Waiting Time:** $\frac{2 + 5 + 2 + 2 + 4}{5} = \frac{15}{5} = 3.0$ time units.

---

| Algorithm | Average Turnaround Time ($TAT$) | Average Waiting Time ($WT$) |
|---|---|---|
| **FCFS** | 7.2 | 4.0 |
| **SJF (Non-preemptive)** | **5.0** | **1.8** |
| **SRTF (Preemptive)** | **5.0** | **1.8** |
| **Priority (Non-preemptive)** | 7.4 | 4.2 |
| **Round Robin (Q=2)** | 6.2 | 3.0 |

---

# Chapter 5: Process Synchronization

Processes that execute concurrently in the operating system may be either independent processes or cooperating processes. Cooperating processes can affect or be affected by other processes. This requires mechanisms to ensure orderly execution to maintain data consistency.

## 5.1 Cooperating Processes & Race Conditions

When multiple processes access and manipulate the same data concurrently, and the outcome of the execution depends on the particular order in which the access takes place, a **Race Condition** exists.

### The Counter Problem Example
Consider a shared variable `counter` initialized to 5.
*   **Producer process** executes: `counter = counter + 1;`
*   **Consumer process** executes: `counter = counter - 1;`

At the machine-language level (assembly), these statements are compiled into:

```assembly
; Producer (counter = counter + 1)
register1 = counter
register1 = register1 + 1
counter = register1

; Consumer (counter = counter - 1)
register2 = counter
register2 = register2 - 1
counter = register2
```

If the producer and consumer execute concurrently, the CPU scheduler can interleave these low-level instructions:

1.  `T0: Producer` executes `register1 = counter` *(register1 = 5)*
2.  `T1: Producer` executes `register1 = register1 + 1` *(register1 = 6)*
3.  `T2: Consumer` executes `register2 = counter` *(register2 = 5)*
4.  `T3: Consumer` executes `register2 = register2 - 1` *(register2 = 4)*
5.  `T4: Producer` executes `counter = register1` *(counter = 6)*
6.  `T5: Consumer` executes `counter = register2` *(counter = 4)*

The final value of counter is 4 (or 6 if producer wrote last), instead of the correct value of 5. This occurs because the write operations overwrite each other's intermediate state.

---

## 5.2 The Critical Section Problem (CSP)

A **Critical Section** is a segment of code in which a process accesses and modifies shared resources (such as a shared variable, table, or file).

```
┌──────────────────────────────────────────────┐
│  ENTRY SECTION                               │
│  (Requests permission to enter CS)           │
├──────────────────────────────────────────────┤
│  CRITICAL SECTION                            │
│  (Accesses/modifies shared data)             │
├──────────────────────────────────────────────┤
│  EXIT SECTION                                │
│  (Cleans up, notifies waiting processes)     │
├──────────────────────────────────────────────┤
│  REMAINDER SECTION                           │
│  (Non-shared local computations)             │
└──────────────────────────────────────────────┘
```

To solve the Critical Section Problem, any solution must satisfy three requirements:

1.  **Mutual Exclusion:** If process $P_i$ is executing in its critical section, then no other processes can execute in their critical sections.
2.  **Progress:** If no process is executing in its critical section and some processes wish to enter their critical sections, only those processes that are not executing in their remainder sections can participate in deciding which process will enter its critical section next, and this selection cannot be postponed indefinitely.
3.  **Bounded Waiting:** There must be a limit (bound) on the number of times that other processes are allowed to enter their critical sections after a process has made a request to enter its critical section and before that request is granted. (Prevents starvation).

---

## 5.3 Peterson's Solution

Peterson's solution is a classic software-based solution to the critical section problem for **two processes** (say, $P_0$ and $P_1$). It assumes that the machine instructions are executed in a sequential and atomic manner (no hardware instruction reordering).

### Shared Variables:
```c
boolean flag[2]; // flag[i] = true implies P_i is ready to enter CS
int turn;        // turn = i implies it is P_i's turn to enter CS
```

### Algorithm for Process $P_i$ ($j$ is the other process, $1 - i$):
```c
do {
    flag[i] = true;                 // State intention to enter
    turn = j;                       // Give turn to the other process
    while (flag[j] && turn == j);   // Busy wait (do nothing)
    
    // CRITICAL SECTION
    
    flag[i] = false;                // Exit critical section
    
    // REMAINDER SECTION
} while (true);
```

### Correctness Proof:
1.  **Mutual Exclusion:** To enter CS, $P_i$ must pass the `while` condition. If both try to enter, `flag[0] = true` and `flag[1] = true`. However, `turn` can only be 0 or 1. If `turn == 1`, $P_0$ busy-waits while $P_1$ enters. If `turn == 0`, $P_1$ busy-waits while $P_0$ enters. Thus, both cannot be in CS simultaneously.
2.  **Progress:** If $P_j$ is not ready to enter CS (`flag[j] == false`), the `while` loop for $P_i$ immediately evaluates to false, allowing $P_i$ to enter. If both are waiting, `turn` will be either 0 or 1, forcing exactly one process to exit the loop.
3.  **Bounded Waiting:** When $P_i$ exits CS, it resets `flag[i] = false`. If $P_j$ is waiting in the `while` loop, it will detect this change and immediately enter its CS. Even if $P_i$ quickly loops back and sets `flag[i] = true`, it must execute `turn = j`, giving $P_j$ the turn. Hence, $P_i$ cannot enter twice in a row while $P_j$ is waiting.

---

## 5.4 Hardware Synchronization

Modern computers provide hardware support to implement critical section solutions.

### A) Disabling Interrupts
On a uniprocessor system, we can disable interrupts while a shared variable is being modified. This prevents preemption, ensuring the current instructions execute without interruption.
*   **Drawback:** Unsafe on multiprocessor systems because disabling interrupts on one CPU does not affect other CPUs executing concurrently. Also, disabling interrupts for too long can freeze system clocks.

### B) Atomic Instructions
Hardware architectures provide special instructions that perform read-modify-write operations **atomically** (non-interruptibly).

#### 1. TestAndSet Instruction
An abstract definition of the instruction (executed atomically by hardware):
```c
boolean TestAndSet(boolean *target) {
    boolean rv = *target;
    *target = true;
    return rv; // returns original value
}
```
**Mutual Exclusion Implementation using TestAndSet:**
```c
boolean lock = false; // Shared lock variable

do {
    while (TestAndSet(&lock)); // Busy wait until lock is false
    
    // CRITICAL SECTION
    
    lock = false; // Release lock
    
    // REMAINDER SECTION
} while (true);
```

#### 2. CompareAndSwap Instruction
An abstract definition (executed atomically):
```c
int CompareAndSwap(int *value, int expected, int new_value) {
    int temp = *value;
    if (*value == expected) {
        *value = new_value;
    }
    return temp; // returns original value
}
```
**Mutual Exclusion Implementation using CompareAndSwap:**
```c
int lock = 0; // Shared lock variable (0 = unlocked, 1 = locked)

do {
    while (CompareAndSwap(&lock, 0, 1) != 0); // Busy wait
    
    // CRITICAL SECTION
    
    lock = 0; // Release lock
    
    // REMAINDER SECTION
} while (true);
```

---

## 5.5 Mutex Locks

A **Mutex** (Mutual Exclusion) lock is a high-level software tool used to protect critical sections. A process must acquire the lock before entering a critical section, and release it upon exiting.

```c
acquire() {
    while (!available); // Busy wait
    available = false;
}

release() {
    available = true;
}
```
*   **Spinlocks:** Mutex locks that require a process to spin (busy wait) in a loop while waiting for the lock.
*   **Pros:** Useful in multiprocessor systems where the wait time is expected to be short (avoids the overhead of context switching the waiting process).
*   **Cons:** Wastes CPU cycles on uniprocessors.

---

## 5.6 Semaphores

A **Semaphore** is an integer variable $S$ that, apart from initialization, is accessed only through two standard atomic operations: `wait()` (also called `P` or `down`) and `signal()` (also called `V` or `up`).

### Classic Definitions (with Busy Waiting):
```c
wait(S) {
    while (S <= 0); // Busy wait
    S--;
}

signal(S) {
    S++;
}
```

### Queue-Based Implementation (No Busy Waiting):
To avoid busy waiting, we can modify the semaphore definition so that when a process executes `wait()` and finds the semaphore value is not positive, it blocks itself and goes to a waiting queue associated with the semaphore.

```c
typedef struct {
    int value;
    struct process *list; // Queue of blocked PCBs
} semaphore;

void wait(semaphore *S) {
    S->value--;
    if (S->value < 0) {
        // add this process to S->list;
        block(); // suspends calling process
    }
}

void signal(semaphore *S) {
    S->value++;
    if (S->value <= 0) {
        // remove a process P from S->list;
        wakeup(P); // resumes execution of process P
    }
}
```
*   If `S->value` is negative, its absolute value is the number of processes waiting in the queue.

### Types of Semaphores:
1.  **Binary Semaphore:** Integer value can range only between 0 and 1. Behaves similarly to a Mutex lock.
2.  **Counting Semaphore:** Integer value can range over an unrestricted domain. Used to control access to a resource with a finite number of identical instances (e.g., $N$ printers).

---

## 5.7 Monitors

A **Monitor** is an abstract data type (high-level synchronization construct) that packages shared variables and the procedures that access them, ensuring that **only one process at a time can be active within the monitor**.

```
┌──────────────────────────────────────────┐
│                 MONITOR                  │
│  ┌────────────────────────────────────┐  │
│  │ Shared Variables                   │  │
│  └────────────────────────────────────┘  │
│  ┌────────────────────────────────────┐  │
│  │ Procedures                         │  │
│  │  - entry procedure 1()             │  │
│  │  - entry procedure 2()             │  │
│  └────────────────────────────────────┘  │
│  ┌────────────────────────────────────┐  │
│  │ Initialization Code                │  │
│  └────────────────────────────────────┘  │
└───────────────────▲──────────────────────┘
                    │ Mutual Exclusion
            [Process Queues] (only 1 inside)
```

### Condition Variables:
To allow custom synchronization, monitors define variables of type `condition`:
```c
condition x, y;
```
*   `x.wait()`: The process calling this operation is suspended and placed on a queue associated with condition `x`.
*   `x.signal()`: Resumes exactly one process suspended on condition `x`. If no process is suspended, the operation has no effect (unlike semaphores where `signal` always increments the value).

---

## 5.8 Classic Synchronization Problems

### A) The Bounded-Buffer (Producer-Consumer) Problem
A shared buffer consists of $N$ slots, each capable of holding one item.
*   `mutex` (Binary Semaphore): Initialized to 1. Protects buffer modifications.
*   `empty` (Counting Semaphore): Initialized to $N$. Tracks empty slots.
*   `full` (Counting Semaphore): Initialized to 0. Tracks full slots containing data.

#### Producer Process:
```c
do {
    // produce an item
    
    wait(&empty);  // Decrement empty slots (wait if 0)
    wait(&mutex);  // Lock buffer
    
    // add item to buffer
    
    signal(&mutex); // Unlock buffer
    signal(&full);  // Increment full slots (notify consumer)
} while (true);
```

#### Consumer Process:
```c
do {
    wait(&full);   // Decrement full slots (wait if 0)
    wait(&mutex);  // Lock buffer
    
    // remove item from buffer
    
    signal(&mutex); // Unlock buffer
    signal(&empty); // Increment empty slots (notify producer)
    
    // consume the item
} while (true);
```

---

### B) The Readers-Writers Problem
Multiple concurrent processes access a shared database.
*   **Readers:** Only read the database (multiple readers can read concurrently).
*   **Writers:** Modify the database (only one writer can access at a time; no readers allowed).

We implement the **First Readers-Writers Problem** (Reader-priority): Readers do not wait unless a writer has already acquired the lock.

#### Shared Variables:
```c
semaphore rw_mutex = 1; // Controls writer access & first/last reader
semaphore mutex = 1;    // Protects read_count
int read_count = 0;     // Tracks active readers
```

#### Writer Process:
```c
do {
    wait(&rw_mutex); // Lock database for writing
    
    // writing is performed
    
    signal(&rw_mutex); // Unlock database
} while (true);
```

#### Reader Process:
```c
do {
    wait(&mutex); // Lock read_count
    read_count++;
    if (read_count == 1) {
        wait(&rw_mutex); // First reader locks database from writers
    }
    signal(&mutex); // Unlock read_count
    
    // reading is performed
    
    wait(&mutex); // Lock read_count
    read_count--;
    if (read_count == 0) {
        signal(&rw_mutex); // Last reader unlocks database for writers
    }
    signal(&mutex); // Unlock read_count
} while (true);
```

---

### C) The Dining Philosophers Problem
Five philosophers sit around a circular table. They spend their lives thinking and eating. There are five chopsticks (represented by semaphores `chopstick[5]`) placed between them. To eat, a philosopher must obtain both their left and right chopsticks.

```c
semaphore chopstick[5]; // all initialized to 1
```

#### Structure of Philosopher $i$:
```c
do {
    wait(&chopstick[i]);          // Pick up left chopstick
    wait(&chopstick[(i + 1) % 5]); // Pick up right chopstick
    
    // eat
    
    signal(&chopstick[i]);          // Put down left chopstick
    signal(&chopstick[(i + 1) % 5]); // Put down right chopstick
    
    // think
} while (true);
```

#### The Deadlock Hazard:
If all five philosophers sit down at the same time and pick up their left chopsticks (`chopstick[i]`), all chopstick semaphore values become 0. When they try to pick up their right chopsticks, they block forever. This is a **Deadlock**.

#### Solutions to Deadlock:
1.  **Limit seating:** Allow at most four philosophers to sit at the table simultaneously.
2.  **Asymmetric Acquisition:** Odd-numbered philosophers pick up the left chopstick first, then the right. Even-numbered philosophers pick up the right chopstick first, then the left.
3.  **State Inspection (Atomic selection):** Allow a philosopher to pick up chopsticks only if both are available (using a monitor or status array).

---

### D) The Sleeping Barber Problem
A barber shop has one barber, one barber chair, and $N$ chairs for waiting customers.
*   If there are no customers, the barber falls asleep in his chair.
*   If a customer arrives and all waiting chairs are full, the customer leaves.
*   If the barber is busy but chairs are available, the customer sits in a waiting chair.
*   If the barber is asleep, the customer wakes him up.

#### Semaphore Solution Variables:
```c
semaphore customers = 0; // Number of waiting customers
semaphore barbers = 0;   // Number of active/free barbers (waiting for customer)
semaphore mutex = 1;     // Mutex lock for shared waiting chair counter
int waiting = 0;         // Number of customers sitting in waiting chairs
```

#### Barber Process:
```c
do {
    wait(&customers);   // Go to sleep if no customers waiting
    wait(&mutex);       // Lock access to waiting count
    waiting--;          // Decrement waiting customers
    signal(&barbers);   // Barber ready to cut hair (notifies customer)
    signal(&mutex);     // Unlock count
    
    // Cut hair (non-critical execution)
} while (true);
```

#### Customer Process:
```c
// Customer arrives
wait(&mutex);           // Lock access to count
if (waiting < N) {
    waiting++;          // Sit in waiting chair
    signal(&customers); // Wake up barber / notify customer ready
    signal(&mutex);     // Unlock count
    wait(&barbers);     // Wait until barber is free
    // Get haircut
} else {
    signal(&mutex);     // Shop full, customer leaves
}
```

---

# Chapter 6: Inter-process Communication (IPC)

Processes executing concurrently may require exchanging data. The OS provides two main architectural models for **Inter-process Communication (IPC)**.

## 6.1 Shared Memory vs. Message Passing

```
SHARED MEMORY MODEL                       MESSAGE PASSING MODEL
┌──────────────────────────────┐          ┌──────────────────────────────┐
│  Process A      Process B    │          │  Process A      Process B    │
│  ┌──────────────┐            │          │  ┌──────────┐  ┌──────────┐  │
│  │ Shared RAM   │            │          │  │ Mailbox  │  │ Mailbox  │  │
│  └──────────────┘            │          └──┴────┬─────┴──┴────▲─────┴──┘
└──────────────────────────────┘                  │   OS Kernel │
                                          ┌───────▼─────────────┴────────┐
                                          │     System Queues            │
                                          └──────────────────────────────┘
```

| Feature | Shared Memory | Message Passing |
|---|---|---|
| **Mechanism** | Multiple processes map a physical memory region into their address spaces. | Processes exchange messages via system calls. |
| **Speed** | ⚡ Extremely fast (RAM speed, direct access). | 🐢 Slower (requires kernel mode transitions for every message). |
| **Data Volume** | Best for large data transfers. | Best for smaller data packets or control signals. |
| **Synchronization**| **Required manually** by programmer (using Mutex/Semaphores). | **Implicitly handled** by the OS message queue. |
| **Location** | Limited to the same machine. | Works across networks (different machines). |

---

## 6.2 Message Passing Details

### A) Communication Link Topologies:
1.  **Direct Communication:** Processes must name each other explicitly:
    *   `send(P, message)`: Send a message to process $P$.
    *   `receive(Q, message)`: Receive a message from process $Q$.
    *   *Properties:* Links are established automatically; exactly one link exists between each pair.
2.  **Indirect Communication:** Messages are sent to and received from mailboxes (ports):
    *   `send(mailbox_A, message)`
    *   `receive(mailbox_A, message)`
    *   *Properties:* Link established only if processes share a common mailbox; multiple links can exist between processes.

### B) Synchronization (Blocking vs. Non-Blocking):
*   **Blocking Send (Synchronous):** The sending process is blocked until the message is received by the receiving process or mailbox. (Rendezvous).
*   **Non-Blocking Send (Asynchronous):** The sending process sends the message and resumes execution immediately.
*   **Blocking Receive:** The receiver blocks until a message is available.
*   **Non-Blocking Receive:** The receiver retrieves either a valid message or a null indicator immediately.

### C) Buffering Capacity:
*   **Zero Capacity (No buffering):** Queue length is 0. Sender must block until receiver performs rendezvous (synchronous).
*   **Bounded Capacity:** Queue length is $N$. If queue is not full, sender resumes immediately. If full, sender blocks.
*   **Unbounded Capacity:** Queue length is infinite. Sender never blocks.

---

## 6.3 Core IPC Mechanisms

### 1. Pipes
A pipe is a unidirectional communication channel. Data written to the write-end of the pipe is read from the read-end (FIFO order).

*   **Ordinary (Anonymous) Pipes:** Unidirectional. Require a parent-child relationship. Created using the `pipe(fd)` system call. They cease to exist once the processes terminate.
    *   *Example (Unix Command Line):* `ls | grep notes.md` (Output of `ls` is piped into input of `grep`).
*   **Named Pipes (FIFOs):** Bidirectional. Do not require parent-child relationship. They exist as files on the disk system filesystem and persist after processes terminate. Created using `mkfifo()`.

---

### 2. Sockets
A **Socket** is defined as an endpoint for communication, identified by an **IP Address concatenated with a Port number**.
*   **Structure:** `192.168.1.10:8080`
*   Two processes communicating over network establish a socket connection.
*   **Types:**
    *   *Connection-Oriented (TCP):* Reliable, ordered delivery.
    *   *Connectionless (UDP):* Unreliable, packets sent individually without connection overhead.

---

### 3. Message Queues
An OS-managed linked list of messages stored within the kernel. Processes can write messages to the queue and read messages from the queue in FIFO or custom priority order. Message boundaries are preserved (unlike pipes which treat data as a continuous stream of bytes).

---

### 4. Signals
A software interrupt mechanism used to notify a process of a specific system event asynchronously.
*   *Mechanism:* The kernel interrupts the target process's execution flow and forces it to jump to a registered **Signal Handler** routine.
*   *Common Unix Signals:*
    *   `SIGINT` (Ctrl+C): Request termination.
    *   `SIGKILL` (kill -9): Force immediate process termination (cannot be caught or ignored).
    *   `SIGSEGV`: Segmentation fault (illegal memory access).

---

### 5. Remote Procedure Calls (RPC)
Allows a process on one machine to call a subroutine/procedure on a remote machine as if it were a local function call.
*   **Stubs:** Client-side stub packages the parameters (marshalling) and sends them over the network. Server-side stub unpacks the parameters (unmarshalling), executes the local function, and returns results.

---

# Chapter 7: Memory Management

The primary purpose of memory management is to bring programs into RAM so they can execute, while protecting memory space and optimizing utilization.

## 7.1 Basic Hardware & Protection

To protect the operating system from modification by user processes, and to protect user processes from one another, we must isolate address spaces.
*   **Base Register:** Holds the smallest legal physical memory address for a process.
*   **Limit Register:** Specifies the size of the range of legal addresses.

```
                  ┌──────────────────┐
                  │ CPU Address (340)│
                  └────────┬─────────┘
                           │
                           ▼
                 /───────────────────\
                <  Address >= Base?   >───No────► [TRAP: Memory Fault]
                 \───────────────────/
                           │ Yes
                           ▼
                 /───────────────────\
                < Address < Base+Limit>───No────► [TRAP: Memory Fault]
                 \───────────────────/
                           │ Yes
                           ▼
                 ┌───────────────────┐
                 │ RAM Address (340) │
                 └───────────────────┘
```

The hardware compares every address generated in user mode against these registers. If a violation occurs, the hardware traps to the OS.

---

## 7.2 Address Binding & Logical vs. Physical Addresses

An address generated by the CPU is a **Logical Address** (or Virtual Address). The actual address loaded into the memory register of the RAM is a **Physical Address**.

### Address Binding Phases:
Address binding is the mapping of program instructions to physical RAM memory addresses. This can occur at three different stages:

1.  **Compile Time:** If you know at compile time where the process will reside in memory, **absolute code** is generated. (E.g., MS-DOS `.COM` files). Any change in starting location requires recompilation.
2.  **Load Time:** If memory location is not known at compile time, the compiler generates **relocatable code**. Binding is delayed until the program is loaded into RAM.
3.  **Execution Time (Runtime):** If the process can be moved during execution from one memory segment to another, binding is delayed until run time. Special hardware, the **Memory Management Unit (MMU)**, translates logical addresses to physical addresses on-the-fly.

```
                      ┌───────────────┐
                      │ CPU (Logical) │
                      └───────┬───────┘
                              │ Logical Address (e.g., 346)
                              ▼
        ┌───────────────────────────────────────────┐
        │ MMU                                       │
        │   ┌───────────────────────────────────┐   │
        │   │ Relocation Register (Value: 14000)│   │
        │   └─────────────────┬─────────────────┘   │
        └─────────────────────┼─────────────────────┘
                              │ Physical Address = 14346
                              ▼
                      ┌───────────────┐
                      │ RAM Memory    │
                      └───────────────┘
```

---

## 7.3 Dynamic Loading vs. Dynamic Linking

*   **Dynamic Loading:** A routine is not loaded into memory until it is called. All routines are kept on disk in a relocatable load format. Particularly useful for handling large amounts of code that are infrequently executed (e.g., error-recovery routines).
*   **Dynamic Linking (Shared Libraries):** Linking of system library routines is postponed until execution time. The compiled code contains a small pointer ("stub") indicating where the library is. When executed, the stub loads the library into RAM (if not already present) and replaces itself with the actual address. This saves disk and RAM space.

---

## 7.4 Swapping

A process can be swapped temporarily out of memory to a **backing store** (SSD/HDD), and then brought back into memory for continued execution. This allows the total physical address space of active processes to exceed the physical RAM size of the computer.

---

## 7.5 Contiguous Memory Allocation

In contiguous allocation, each process is contained in a single contiguous section of memory.

### A) Partition Schemes:
*   **Fixed Partitioning (MFT):** Memory is divided into fixed-size partitions. Each partition can hold exactly one process.
    *   *Problem:* **Internal Fragmentation** occurs if a process is smaller than the partition allocated to it.
*   **Variable Partitioning (MVT):** The OS keeps a table indicating which parts of memory are free (holes) and which are occupied. When a process arrives, it is allocated space from a hole large enough to accommodate it.

### B) Dynamic Allocation Strategies:
When a process needs memory of size $S$, how do we select a hole from a set of free holes?

1.  **First-Fit:** Allocate the *first* hole that is big enough. (Fastest search).
2.  **Best-Fit:** Allocate the *smallest* hole that is big enough. (Must search entire list unless ordered).
    *   *Drawback:* Leaves behind tiny, unusable holes.
3.  **Worst-Fit:** Allocate the *largest* hole that is big enough. (Must search entire list).
    *   *Rationale:* Leaves behind large, useful holes.

#### Numeric Example:
Given free holes in memory: `100 KB`, `500 KB`, `200 KB`, `300 KB`, `600 KB` (in order).
A process requests `212 KB`.
*   **First-Fit** selects: `500 KB` hole (first hole that fits $\ge 212$ KB).
*   **Best-Fit** selects: `300 KB` hole (closest fit $\ge 212$ KB).
*   **Worst-Fit** selects: `600 KB` hole (largest hole).

### C) Fragmentation
*   **Internal Fragmentation:** Allocated memory is slightly larger than requested memory. The unused portion inside the allocated block is wasted.
*   **External Fragmentation:** Total free memory space is large enough to satisfy a request, but it is not contiguous; it is partitioned into small, scattered holes.
*   **Compaction:** A solution to external fragmentation. The OS shifts memory contents to place all free memory together in one large block.
    *   *Requirement:* Relocation must be dynamic and performed at execution time.

---

## 7.6 Paging

Paging is a memory management scheme that eliminates the need for contiguous allocation of physical memory.

### Basic Mechanism:
*   Physical memory is broken into fixed-size blocks called **Frames**.
*   Logical memory is broken into blocks of the same size called **Pages**.
*   When a process is executed, its pages are loaded into any available memory frames.
*   The **Page Table** maps logical pages to physical frames.

```
 Logical Address (from CPU)                   Physical RAM
┌─────────────────────────┐                  ┌────────────┐
│ Page (p)  │ Offset (d)  │                  │ Frame 0    │
└────┬──────┴──────┬──────┘                  ├────────────┤
     │             │                         │ Frame 1    │
     ▼             │                         ├────────────┤
 ┌───────┐         │                         │ Frame 2    │
 │Page   │         │                         ├────────────┤
 │Table  │         │                         │ Frame 3    │
 ├───────┤         │                         └────────────┘
 │p ──► f│         │
 └───┬───┘         │
     ▼             ▼
┌───────────┬─────────────┐
│ Frame (f) │ Offset (d)  │
└───────────┴─────────────┘
 Physical Address (to RAM)
```

### Address Translation Architecture:
The logical address generated by the CPU consists of two parts:
1.  **Page Number ($p$):** Used as an index into the page table.
2.  **Page Offset ($d$):** Combined with the base address of the frame to define the physical memory address.

*   If the page size is $2^n$ bytes, the low-order $n$ bits of a logical address represent the page offset, and the high-order bits represent the page number.

---

### Translation Lookaside Buffer (TLB)
A page table is kept in main memory. Accessing memory requires two operations: one for the page-table lookup and one for the actual data. This slows down the CPU by a factor of 2.
To solve this, we use a small, fast-lookup hardware cache called a **Translation Lookaside Buffer (TLB)**.

```
                    ┌─────────┐
                    │   CPU   │
                    └────┬────┘ Logical Address
                         │
                 ┌───────▼───────┐
                 │   TLB Cache   │
                 └─┬───────────┬─┘
           Hit     │           │ Miss
      ┌────────────┘           └────────────┐
      ▼                                     ▼
[Get Frame Number]                   [Read Page Table in RAM]
                                            │
                                     [Update TLB]
```

#### Effective Access Time ($EAT$) Math:
Let:
*   $t_{TLB}$ = Time to access TLB cache (typically $1$ ns).
*   $t_{RAM}$ = Time to access RAM memory (typically $100$ ns).
*   $\alpha$ = TLB Hit Ratio (percentage of times page number is found in TLB).

$$EAT = \alpha \times (t_{TLB} + t_{RAM}) + (1 - \alpha) \times (t_{TLB} + 2 \times t_{RAM})$$
*(Note: on a TLB miss, we must access TLB, then Page Table in RAM, then the actual memory location in RAM = $t_{TLB} + 2 \times t_{RAM}$)*.

**Example Calculation:**
If TLB hit ratio is $90\%$, TLB lookup is $10$ ns, and memory access is $100$ ns:
$$EAT = 0.90 \times (10 + 100) + 0.10 \times (10 + 200) = 0.90(110) + 0.10(210) = 99 + 21 = 120\text{ ns}$$

---

### Page Table Structures for Large Address Spaces:
1.  **Hierarchical Paging:** The page table itself is paged (e.g., two-level page table where page directory points to page tables).
2.  **Hashed Page Tables:** A hash table is used, where each entry contains a linked list of elements hashing to the same location.
3.  **Inverted Page Tables:** One entry for each real page (frame) of memory. Each entry contains the virtual address of the page stored in that real memory location, along with information about the process that owns it. Saves memory space by tracking physical rather than logical pages.

---

## 7.7 Segmentation

Segmentation is a memory-management scheme that supports the programmer's view of memory. A logical address space is a collection of variable-length segments (e.g., Code, Data, Stack, Heap, Library subroutines).

*   **Logical Address Format:** `<segment-number, offset>`
*   **Segment Table:** Maps segment numbers to physical addresses. Each entry contains:
    *   **Base:** The starting physical address of the segment.
    *   **Limit:** The length of the segment.

```
                   ┌───────────────────┐
                   │CPU: < s (2), d >  │
                   └─────────┬─────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │ Segment Table   │
                    ├─────────────────┤
                    │ s ──► Limit,Base│
                    └────────┬────────┘
                             │
                      /──────▼───────\
                     <   d < Limit?   >───No────► [TRAP: Seg Fault]
                      \──────┬───────/
                             │ Yes
                             ▼
                    Base + d = Physical Address
```

---

## 7.8 Virtual Memory & Demand Paging

**Virtual Memory** is a technique that allows the execution of processes that are not completely in memory. It abstracts main memory into an extremely large, uniform array of storage, separating logical memory from physical memory.

### Demand Paging
Pages are loaded into memory only when they are needed during execution.
*   **Valid-Invalid Bit:** Associated with each page-table entry.
    *   **Valid (1):** The page is in RAM.
    *   **Invalid (0):** The page is not in RAM (either on disk or illegal).

### The Page Fault Handling Sequence:

```
  1. CPU references page
         │
         ▼
  2. Page Table check (Invalid Bit)
         │
         ▼
  3. [TRAP to OS: Page Fault]
         │
         ▼
  4. Find page location on disk
         │
         ▼
  5. Bring page from disk into a free RAM Frame
         │
         ▼
  6. Update Page Table bit to Valid (1)
         │
         ▼
  7. Restart the instruction that caused the trap
```

### Effective Access Time ($EAT$) in Demand Paging
Let:
*   $p$ = Page Fault Probability ($0 \le p \le 1$).
*   $t_{RAM}$ = Memory access time.
*   $t_{fault}$ = Page fault service time (disk read + context switch overhead $\approx 8$ milliseconds).

$$EAT = (1 - p) \times t_{RAM} + p \times t_{fault}$$

Since $t_{fault}$ is in milliseconds ($10^{-3}$ s) and $t_{RAM}$ is in nanoseconds ($10^{-9}$ s), even a tiny page fault rate (e.g., 1 in 1000) can degrade system speed by orders of magnitude.

---

## 7.9 Page Replacement Algorithms

When a page fault occurs and there are no free frames in memory, the OS must evict an existing page to make room.

---

### 1. First-In, First-Out (FIFO)
*   **Logic:** Evict the oldest page (the page that was brought in first).
*   **Belady's Anomaly:** For some page replacement algorithms, the page-fault rate may *increase* as the number of allocated frames increases. FIFO suffers from this anomaly.

#### Mathematical Trace of Belady's Anomaly:
Reference String: `1, 2, 3, 4, 1, 2, 5, 1, 2, 3, 4, 5`

**Case A: 3 Frames**
```
Ref:  1   2   3   4   1   2   5   1   2   3   4   5
F1:  [1] [1] [1] [4] [4] [4] [5] [5] [5] [5] [4] [4]
F2:   -  [2] [2] [2] [1] [1] [1] [1] [2] [2] [2] [5]
F3:   -   -  [3] [3] [3] [2] [2] [2] [3] [3] [3] [3]
Fault:✗   ✗   ✗   ✗   ✗   ✗   ✗   Hit Hit ✗   ✗   ✗  (Total Faults = 9)
```

**Case B: 4 Frames**
```
Ref:  1   2   3   4   1   2   5   1   2   3   4   5
F1:  [1] [1] [1] [1] Hit Hit [5] [5] [5] [5] [4] [4]
F2:   -  [2] [2] [2]          [2] [1] [1] [1] [1] [5]
F3:   -   -  [3] [3]          [3] [3] [2] [2] [2] [2]
F4:   -   -   -  [4]          [4] [4] [4] [3] [3] [3]
Fault:✗   ✗   ✗   ✗           ✗   ✗   ✗   ✗   ✗   ✗  (Total Faults = 10)
```
*Adding memory (from 3 to 4 frames) increased faults from 9 to 10! This is Belady's Anomaly.*

---

### 2. Least Recently Used (LRU)
*   **Logic:** Evicts the page that has not been used for the longest period of time.
*   **Properties:** Immune to Belady's Anomaly (it is a stack algorithm).
*   **Implementation:**
    *   *Counters:* Every page-table entry has a time-of-use register. Evict the smallest counter.
    *   *Stack:* Keep a stack of page numbers. When a page is referenced, move it to the top. The bottom of the stack is the LRU page.

#### LRU Example Trace (3 Frames):
Reference String: `1, 2, 3, 4, 1, 2, 5, 1, 2, 3`

```
Ref:   1     2     3     4     1     2     5     1     2     3
F1:   [1]   [1]   [1]   [4]   [4]   [4]   [5]   [5]   [5]   [3] (evicted 4)
F2:    -    [2]   [2]   [2]   [1]   [1]   [1]   [1]   [2]   [2] (evicted 1)
F3:    -     -    [3]   [3]   [3]   [2]   [2]   [2]   [2]   [2] 
Fault: ✗     ✗     ✗     ✗     ✗     ✗     ✗     Hit   Hit   ✗  (Total Faults = 8)
```

---

### 3. Optimal Page Replacement (OPT)
*   **Logic:** Evict the page that will not be used for the longest period of time in the future.
*   **Optimality:** Guarantees the lowest possible page-fault rate for a fixed number of frames.
*   **Limitation:** Unimplementable because it requires future knowledge. Used as a benchmark.

---

### 4. Second-Chance (Clock) Algorithm
*   **Logic:** A practical approximation of LRU. Uses a circular queue and a **Reference Bit** for each page.
*   **Operation:**
    *   When page is referenced, hardware sets reference bit $\to$ 1.
    *   When eviction is needed, the clock hand sweeps.
    *   If reference bit is 1: clear it to 0, advance clock hand. (Gives page a "second chance").
    *   If reference bit is 0: evict this page.

```
       Clock Hand (Sweeps queue)
            │
            ▼
       ┌──────────┐
       │ Page 2   │ Reference Bit = 1 ──► Clear bit to 0, advance hand
       ├──────────┤
       │ Page 5   │ Reference Bit = 0 ──► EVICT this page!
       └──────────┘
```

---

### 5. LFU and MFU
*   **Least Frequently Used (LFU):** Evicts the page with the smallest reference count.
*   **Most Frequently Used (MFU):** Evicts the page with the largest reference count (argues that the page with the smallest count was probably just brought in and is yet to be used).

---

## 7.10 Thrashing

A process is **Thrashing** if it is spending more time paging (swapping pages in and out of disk) than executing instructions.

```
  CPU Utilization
 100%│        Optimal Point
     │         / \
     │        /   \
     │       /     \
   0%└──────/───────\──────────────
          Degree of Multiprogramming
          ◄─ Stable ─►◄─ Thrashing ─►
```

### Cause of Thrashing:
1.  As the degree of multiprogramming increases, the OS allocates fewer frames to each process.
2.  Eventually, a process does not have enough frames to hold its active working set.
3.  It page-faults. The processes queue up for the disk controller. The CPU utilization drops.
4.  The OS detects the CPU drop and incorrectly attempts to increase CPU utilization by loading *more* processes (increasing multiprogramming), which worsens the page faults until the system locks up.

### Solutions:
1.  **Working-Set Model:** Tracks the set of pages actively referenced by a process in a sliding window of time $\Delta$. Ensure RAM can hold the working sets of all loaded processes; if not, swap out a process.
2.  **Page-Fault Frequency (PFF):** Establish upper and lower bounds on the page-fault rate. If the rate is too high, allocate more frames; if too low, reclaim frames.

---

# Chapter 8: Quick Revision Cheat Sheet

## 8.1 Core Mathematical Formulas

$$\text{Turnaround Time (TAT)} = CT - AT$$
$$\text{Waiting Time (WT)} = TAT - BT$$
$$\text{Response Time (RT)} = \text{Time of first CPU response} - AT$$
$$\text{CPU Utilization} = \frac{\text{CPU Busy Time}}{\text{Total Measurement Time}} \times 100\%$$
$$\text{Effective Access Time (EAT - TLB)} = \alpha \times (t_{TLB} + t_{RAM}) + (1 - \alpha) \times (t_{TLB} + 2 \times t_{RAM})$$
$$\text{Effective Access Time (EAT - Paging)} = (1 - p) \times t_{RAM} + p \times t_{fault}$$

---

## 8.2 Coffman Conditions for Deadlock

All **four** conditions must hold simultaneously for a deadlock to occur:
1.  **Mutual Exclusion:** At least one resource must be held in a non-shareable mode.
2.  **Hold and Wait:** A process must be holding at least one resource and waiting to acquire additional resources held by other processes.
3.  **No Preemption:** Resources cannot be preempted; a resource can be released only voluntarily by the process holding it.
4.  **Circular Wait:** A closed chain of processes exists, such that each process holds one or more resources needed by the next process in the chain.

---

## 8.3 Fragmentation Reference

*   **Internal Fragmentation:** Waste inside allocated partitions. Caused by fixed partition schemes and fixed-size paging.
*   **External Fragmentation:** Scattered free spaces between allocations. Caused by variable partition schemes and segmentation. Resolved by Compaction or Paging.

---

## 8.4 Key Terms Glossary

| Term | Definitive Definition |
|---|---|
| **Kernel** | The central core program of the OS that runs in privileged Mode (Ring 0) and stays permanently in RAM. |
| **System Call** | Software interface allowing user programs to request privileged kernel services. |
| **Process** | A program in execution containing a stack, heap, data, and text segment. |
| **Context Switch** | Storing state of running process into its PCB and loading state of next process from its PCB. |
| **Degree of Multiprogramming**| The number of active processes currently resident in physical memory (RAM). |
| **Race Condition** | Concurrent execution outcome depends on arbitrary instruction interleaving. |
| **Semaphore** | Atomic integer variable S accessed via wait() and signal() for synchronization. |
| **Mutex** | Locking mechanism with thread ownership — only locker thread can unlock. |
| **Paging** | Memory division into equal pages/frames; eliminates external fragmentation. |
| **TLB** | High-speed cache for page table lookups. |
| **Thrashing** | System spends more time page-faulting than executing instructions. |
| **Aging** | Technique to prevent starvation by gradually increasing priority of waiting processes. |

---

## 8.5 Common Misconceptions

| Myth | Correct Concept |
|---|---|
| *"Paging has absolutely no memory waste"* | **False.** Paging has zero external fragmentation, but suffers from internal fragmentation in the last page of a process. |
| *"RTOS is just an ultra-fast OS"* | **False.** RTOS is designed for **determinism and guaranteed deadlines**, not raw processing speed. |
| *"Binary Semaphores and Mutexes are identical"* | **False.** Mutex has **ownership** (only locking thread can unlock); semaphores can be signaled by any thread. |
| *"Adding more RAM always reduces page faults"* | **False.** Under FIFO page replacement, adding more frames can increase page faults (Belady's Anomaly). |

---

## 8.6 Exam Practice Questions

1.  **Logical vs. Physical Address:** Contrast Logical and Physical addresses. At what binding stage do they differ? Explain the role of the Relocation Register in this translation.
2.  **Peterson's Solution correctness:** Write the pseudocode of Peterson's Solution. Prove step-by-step how it satisfies the three requirements of the Critical Section Problem.
3.  **Scheduling calculation:** Given processes $P_1(AT=0, BT=4, Pri=3)$, $P_2(AT=1, BT=3, Pri=1)$, and $P_3(AT=2, BT=2, Pri=2)$. Draw Gantt charts and calculate average WT and TAT using Preemptive Priority Scheduling.
4.  **Belady's Anomaly:** Define Belady's Anomaly. Provide a numeric reference string and trace how it manifests in FIFO but not in LRU.
5.  **Multilevel Feedback Queue:** Explain how a Multilevel Feedback Queue operates. Detail the mechanisms for process promotion and demotion, and explain why it prevents starvation.
6.  **Reader-Priority Readers-Writers:** Write the semaphore implementation of the first Readers-Writers problem. How does it ensure that multiple readers can read concurrently while writer access is strictly exclusive?
7.  **EAT with TLB:** A system has a TLB lookup time of $5$ ns and memory access time of $80$ ns. What is the effective access time (EAT) if the TLB hit ratio is $95\%$?
8.  **Pipes vs. Sockets:** Compare Ordinary Pipes, Named Pipes, and Sockets. Which of these can be used for communication between two independent processes on different machines?
9.  **Thrashing & working set:** Explain the physical cause of thrashing. How does the Working Set Model prevent thrashing by adjusting the degree of multiprogramming?
10. **Dual Mode Transition:** Draw a diagram and explain the exact mechanical steps that occur when a user-space application executes `read()` to load a file, tracing the mode transitions and interrupt handling.

---

*📌 These redesigned notes cover the complete syllabus for Unit I: Foundations, OS Types, Memory Management, CPU Scheduling, Process Synchronization, and IPC. Good luck! 🎓*