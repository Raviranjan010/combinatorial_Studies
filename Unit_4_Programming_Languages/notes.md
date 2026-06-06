# ☕ Programming Languages — Unit IV: Comprehensive Lecture Notes

> **Target Audience:** Students and job candidates preparing for technical interviews. This unit provides rigorous conceptual explanations, concrete code traces, memory diagrams, and "Mistakes to Avoid" sections for C, C++, and Java.

---

## 📌 Table of Contents

1. [C vs. C++ vs. Java: Paradigms & Compilation](#1-c-vs-c-vs-java-paradigms--compilation)
2. [Pointers, Pointer Arithmetic & References](#2-pointers-pointer-arithmetic--references)
3. [Storage Classes: Scope, Lifetime, and Memory Segments](#3-storage-classes-scope-lifetime-and-memory-segments)
4. [Object-Oriented Programming (OOP) Deep Dive](#4-object-oriented-programming-oop-deep-dive)
   - 4.1 Classes, Objects, and Access Specifiers
   - 4.2 The Diamond Problem & Virtual Inheritance
   - 4.3 Runtime Polymorphism: VTABLE & VPTR Mechanics
5. [Parameter Passing Techniques & Binding](#5-parameter-passing-techniques--binding)
6. [Memory Management: C++ Heap vs. JVM Generational Garbage Collection](#6-memory-management-c-heap-vs-jvm-generational-garbage-collection)
7. [Common Pitfalls & Mistakes to Avoid](#7-common-pitfalls--mistakes-to-avoid)

---

## 1. C vs. C++ vs. Java: Paradigms & Compilation

Operating systems, system programs, and business applications are written across procedural and object-oriented languages. Understanding their compilation pipeline and design paradigms is fundamental.

```
+-----------------------------------------------------------------------------+
|                               PARADIGMS                                     |
+------------------------------------+----------------------------------------+
| C: Procedural / Imperative         | - Focus on functions and top-down step-|
|                                    |   by-step execution.                   |
|                                    | - No built-in classes or encapsulation.|
+------------------------------------+----------------------------------------+
| C++: Multi-Paradigm                | - Supports Procedural, OOP (Classes),  |
|                                    |   and Generic Programming (Templates). |
|                                    | - Manual memory control.               |
+------------------------------------+----------------------------------------+
| Java: Pure Object-Oriented (Almost)| - Everything (except primitives) lives |
|                                    |   inside classes.                      |
|                                    | - Runs on a VM with automatic GC.      |
+------------------------------------+----------------------------------------+
```

### ⚙️ Compilation Pipelines

#### C & C++ Compilation (Direct-to-Machine-Code)
C and C++ code is compiled directly into platform-specific machine code.
```
  [Source Files (.c / .cpp)]
             │
             ▼
        [Preprocess] ────► Resolves #include, #define, #ifdef
             │
             ▼
         [Compile]   ────► Translates to Assembly Code (.s)
             │
             ▼
        [Assemble]   ────► Translates to Object Code (.o / .obj)
             │
             ▼
          [Link]     ────► Resolves library symbols, produces Native Binary (.exe / .out)
```
*   **Pros:** ⚡ Maximum execution speed; raw access to hardware instructions.
*   **Cons:** ❌ Platform dependent. A binary compiled for Windows x86-64 will not run on macOS ARM64.

#### Java Compilation (Write Once, Run Anywhere - WORA)
Java compiles source code to an intermediate bytecode representation which runs on the **Java Virtual Machine (JVM)**.
```
  [Source File (.java)]
             │
             ▼  (javac compiler)
     [Bytecode (.class)]
             │
             ▼
      [JVM Classloader]
             │
             ▼
   [JVM Execution Engine] ──► Interprets bytecode OR uses JIT (Just-In-Time) Compiler
                             to translate hot paths to Native Machine Instructions.
```
*   **Pros:** 🌐 Platform independent. The same `.class` file runs on any OS containing a compatible JVM.
*   **Cons:** 🐢 Small startup overhead due to class loading and JIT compilation.

---

## 2. Pointers, Pointer Arithmetic & References

Pointers and references allow variables to refer to memory addresses instead of copying data values.

### 📮 Memory Address Mechanics
A **pointer** is a variable that stores the physical memory address of another variable.

```cpp
int x = 42;
int *ptr = &x;   // ptr stores the address of x
int **dptr = &ptr; // dptr stores the address of ptr
```

Let's map this in RAM:
```
Memory Address:   0x1000                 0x2000                 0x3000
Variable:         [  42  ]  ◄─────────── [0x1000]  ◄─────────── [0x2000]
Name:                x                     ptr                    dptr
Type:               int                   int*                   int**
```

*   **Address-of Operator (`&`):** Retrieves the memory address of a variable.
*   **Dereferencing Operator (`*`):** Reads or writes the value stored at the address contained in the pointer.
    *   `*ptr = 99;` changes `x` to `99`.
    *   `**dptr = 100;` changes `x` to `100`.

### 🧮 Pointer Arithmetic
Pointers are typed so the compiler knows how many bytes to skip when adding or subtracting integers.
*   **Formula:** If `ptr` points to address `A` of type `T`, then:
    $$\text{Address of } (ptr + n) = A + (n \times \text{sizeof}(T))$$

#### Worked Example:
```c
int arr[5] = {10, 20, 30, 40, 50};
int *ptr = arr; // points to arr[0] at address 0x1000 (assuming 4-byte integers)
```
1.  `ptr + 1` resolves to:
    $$0x1000 + (1 \times 4) = 0x1004 \implies \text{points to } arr[1] \text{ (20)}$$
2.  `ptr + 3` resolves to:
    $$0x1000 + (3 \times 4) = 0x100C \implies \text{points to } arr[3] \text{ (40)}$$

### 🔗 References (C++)
A reference is an **alias** (another name) for an existing variable.
```cpp
int x = 10;
int &ref = x; // ref is a reference to x
ref = 20;     // x is now 20
```

#### Key Differences: Pointers vs. References
```
+----------------------------------+------------------------------------+
|            POINTER               |             REFERENCE              |
+----------------------------------+------------------------------------+
| Can point to NULL.               | Cannot be NULL.                    |
+----------------------------------+------------------------------------+
| Can be reassigned to point to    | Must be initialized when declared; |
| different variables.             | cannot be rebound to another var.  |
+----------------------------------+------------------------------------+
| Occupies its own memory space    | Shares the same address space as   |
| (4 or 8 bytes to store address). | the referred variable.             |
+----------------------------------+------------------------------------+
```

---

## 3. Storage Classes: Scope, Lifetime, and Memory Segments

Storage classes specify where a variable is stored in RAM, its initial default value, its visibility (scope), and how long it remains in memory (lifetime).

```
┌─────────────────────────────────────────────────────────────┐
|                     PROCESS RAM LAYOUT                      |
├─────────────────────────────────────────────────────────────┤
| STACK: Local variables, function frames (grows downward)    |
├─────────────────────────────────────────────────────────────┤
| HEAP: Dynamically allocated memory via new/malloc           |
├─────────────────────────────────────────────────────────────┤
| DATA SEGMENT (BSS + Initialized): Global & static variables |
├─────────────────────────────────────────────────────────────┤
| TEXT SEGMENT: Executable binary instructions                |
└─────────────────────────────────────────────────────────────┘
```

### The C/C++ Storage Classes

#### 1. `auto` (default for local variables)
*   **Location:** Stack.
*   **Lifetime:** Deleted when the enclosing execution block `{}` exits.
*   **Scope:** Local.

#### 2. `register`
*   **Location:** CPU Registers (if available, otherwise defaults to stack).
*   **Properties:** Extremely fast access. You **cannot** use the address-of operator `&` on a register variable in C because registers do not have memory addresses.

#### 3. `static`
*   **Location:** Data Segment.
*   **Lifetime:** Persists for the entire duration of the program.
*   **Behavior (Inside a function):** It retains its value between multiple function calls and is initialized **only once**.
*   **Behavior (Global scope):** Limits visibility of the variable to the file it is declared in, preventing linker conflicts.

##### Code Example: Static Variable Trace
```cpp
#include <iostream>
using namespace std;

void counter() {
    static int count = 0; // Initialized only once, stored in Data Segment
    count++;
    cout << count << " ";
}

int main() {
    counter(); // Outputs: 1
    counter(); // Outputs: 2
    counter(); // Outputs: 3
    return 0;
}
```

#### 4. `extern`
*   **Location:** Data Segment.
*   **Purpose:** Declares a variable or function defined in another source file. It informs the compiler of the variable's existence without allocating new memory, leaving symbol resolution to the linker.

---

## 4. Object-Oriented Programming (OOP) Deep Dive

OOP structures code around objects containing data fields (attributes) and methods (functions).

### 4.1 Classes, Objects, and Access Specifiers
*   **Class:** A blueprint or layout. It occupies no physical memory.
*   **Object:** A physical instance of a class. It is created in memory and holds actual data.
*   **Access Specifiers:**
    *   `private`: Accessible only within the class.
    *   `protected`: Accessible within the class and its child subclasses.
    *   `public`: Accessible from anywhere in the application.

---

### 4.2 The Diamond Problem & Virtual Inheritance
In multiple inheritance, the Diamond Problem occurs when a child class inherits from two parent classes that both derive from a single grandparent class.

```
       [ Grandparent: A ]
          /         \
    [ Parent: B ]  [ Parent: C ]
          \         /
         [ Child: D ]
```

#### The Ambiguity Code:
```cpp
class A {
public:
    void show() { cout << "Grandparent A"; }
};

class B : public A {};
class C : public A {};
class D : public B, public C {};

int main() {
    D obj;
    // obj.show(); // ❌ COMPILER ERROR: Ambiguous call! B and C both contain copies of A.
}
```

#### The C++ Solution: Virtual Inheritance
By inheriting the base class as `virtual`, we instruct the compiler to maintain only a single shared instance of the grandparent class.

```cpp
class B : virtual public A {};
class C : virtual public A {};
class D : public B, public C {};

int main() {
    D obj;
    obj.show(); // ✅ Works! Only one copy of A is inherited.
}
```

#### The Java Approach: Interfaces
Java disallows multiple inheritance of classes (`class D extends B, C` is illegal). Instead, a class can implement multiple **interfaces**, which act as absolute contracts without holding member state, preventing resource duplication.

---

### 4.3 Runtime Polymorphism: VTABLE & VPTR Mechanics
Polymorphism allows a single interface to execute different behaviors.
*   **Compile-time Polymorphism:** Overloading functions or operators (resolved at compile time by renaming functions, i.e., name mangling).
*   **Runtime Polymorphism:** Overriding virtual functions, resolved at runtime using **Vtables** (Virtual Function Tables).

#### How Virtual Functions work under the hood:
When a class declares a `virtual` function:
1.  The compiler creates a static **VTABLE** for that class. The VTABLE contains pointers to all virtual methods declared in the class.
2.  Every instance of the class receives a hidden pointer called **VPTR** (`__vptr`).
3.  The `__vptr` is set during object construction to point to the VTABLE of its concrete class.

```
Base Class: Animal { virtual void speak(); }
Derived Class: Dog : Animal { void speak() override; void bark(); }

Object of Dog in Heap:               Dog's VTABLE in Data Segment:
┌───────────────────────┐            ┌────────────────────────────────┐
│   __vptr              ├───────────►│ [0]: &Dog::speak()             │
├───────────────────────┤            └────────────────────────────────┘
│   dog_data_field      │
└───────────────────────┘
```

When calling `animalRef->speak()`, the CPU performs a dereference loop:
$$\text{Object} \longrightarrow \text{VPTR} \longrightarrow \text{VTABLE[index]} \longrightarrow \text{Execution address of Dog::speak()}$$
This lookup adds a tiny pointer dereference overhead but enables dynamic runtime polymorphism.

---

## 5. Parameter Passing Techniques & Binding

How arguments are mapped to parameters during function invocation.

### 5.1 Parameter Passing Methods

#### 1. Pass by Value
*   **Mechanism:** Copies the argument's value into the function's stack parameter.
*   **Safety:** Modifying the parameter inside the function has no effect on the caller's variable.
*   **Cost:** High for large objects because it invokes copy constructors.

#### 2. Pass by Pointer (Address)
*   **Mechanism:** Passes the memory address of the variable.
*   **Safety:** Modifying the dereferenced parameter directly updates the caller's variable.
*   **Cost:** Low (only passes an 8-byte address).

#### 3. Pass by Reference
*   **Mechanism:** Passes a direct alias of the argument variable.
*   **Safety:** Modifying the reference variable updates the caller's variable directly without pointer dereference symbols (`*` or `->`).

#### Code Execution Trace:
Let's trace these three methods in C++:
```cpp
#include <iostream>
using namespace std;

void byValue(int a) { a = 99; }
void byPointer(int *a) { *a = 99; }
void byReference(int &a) { a = 99; }

int main() {
    int x = 10;
    
    byValue(x);
    cout << x << " "; // Outputs: 10 (x is unchanged)
    
    byPointer(&x);
    cout << x << " "; // Outputs: 99 (x is modified)
    
    x = 10; // reset
    byReference(x);
    cout << x << endl; // Outputs: 99 (x is modified)
    
    return 0;
}
```

### 5.2 Binding: Static vs. Dynamic
*   **Static (Early) Binding:** The compiler maps function calls to their code blocks at compile time. This is used for non-virtual functions and overloaded methods. It is resolved based on the **static type (declared type)** of the pointer.
*   **Dynamic (Late) Binding:** The binding is deferred until runtime, mapping calls based on the **dynamic type (actual object type)** using VTABLE lookups.

---

## 6. Memory Management: C++ Heap vs. JVM Generational Garbage Collection

Programs must allocate memory dynamically when size requirements are unknown at compile time.

### 6.1 C++ Manual Heap Management
*   **Keywords:** `new` (allocates heap space, calls constructor), `delete` (calls destructor, releases heap space).
*   **Arrays:** Use `new[]` and `delete[]`. Mismatched delete operations (e.g. `delete` instead of `delete[]` on an array) lead to undefined behavior or memory leaks.

#### Manual Memory Anomalies:
*   **Memory Leak:** Allocating space with `new` but forgetting to release it using `delete`. The memory remains marked as occupied but is unreachable.
*   **Dangling Pointer:** A pointer pointing to a memory address that has already been released via `delete`. Accessing it causes crashes or memory corruption.
*   **Double Free:** Invoking `delete` twice on the same heap address, corrupting the heap manager.

---

### 6.2 JVM Generational Garbage Collection
Java has no explicit `delete` keyword. The **Garbage Collector (GC)** runs in the background to reclaim memory occupied by unreachable objects.

#### The Generational Hypothesis
Most allocated objects have a very short lifetime (e.g., local variables in loops). Thus, the JVM splits the heap into distinct generations to optimize GC sweeps:

```
┌────────────────────────────────────────────────────────────────────────────┐
|                              JVM HEAP MEMORY                               |
├───────────────────────────────────────────────┬────────────────────────────┤
|             YOUNG GENERATION                  |      OLD GENERATION        |
├─────────────────┬──────────────┬──────────────┤      (TENURED)             |
|   Eden Space    | Survivor S0  | Survivor S1  |                            |
| (New objects)   |  (Minor GC)  |  (Minor GC)  | (Long-lived objects)       |
└─────────────────┴──────────────┴──────────────┴────────────────────────────┘
```

1.  **Young Generation:**
    *   **Eden Space:** All new objects are allocated here.
    *   **Survivor Spaces (S0 / S1):** When Eden fills up, a **Minor GC** occurs. Reachable objects are copied to S0 or S1, and Eden is cleared.
    *   At each Minor GC, surviving objects are swapped between S0 and S1, incrementing their **age counter**.
2.  **Old Generation (Tenured):**
    *   If an object survives enough GC rounds (exceeds the age threshold, default is 15), it is promoted to the **Old Generation**.
    *   When the Old Generation fills up, a **Major GC (Full GC)** runs, scanning the entire heap. This is a heavier "Stop-the-World" operation.

#### Mark-and-Sweep Algorithm
GC identifies unreachable objects using **Reachability Analysis**:
1.  **Mark:** Start from **GC Roots** (active thread local variables, static references) and traverse the reference graph. Mark all encountered objects as "reachable".
2.  **Sweep:** Scan the heap and release the memory of all unmarked objects.

---

## 7. Common Pitfalls & Mistakes to Avoid

> [!WARNING]
> ### 1. Pointer to Constant (`const int *ptr`) vs. Constant Pointer (`int *const ptr`)
> *   **The Mistake:** Confusing which element is immutable.
> *   **The Reality:**
>     *   `const int *ptr` (Pointer to constant): You **cannot modify the value** pointed to (`*ptr = 20` is illegal), but you can point to a different address (`ptr = &y` is legal).
>     *   `int *const ptr` (Constant pointer): You **cannot change the address** contained in the pointer (`ptr = &y` is illegal), but you can modify the value at that address (`*ptr = 20` is legal).

> [!WARNING]
> ### 2. Object Slicing in Inheritance
> *   **The Mistake:** Passing a derived object by value to a function accepting a base class parameter.
> *   **The Reality:**
>     ```cpp
>     class Base { int x; };
>     class Derived : public Base { int y; };
>     void print(Base b); // Pass by value
>     ```
>     When you pass a `Derived` object to `print(b)`, the compiler allocates space for `Base` on the stack and copies only the `Base` portion of the object, slicing off the `Derived` specific members (`y` and the Vtable/VPTR). To preserve polymorphism, you must pass arguments by **pointer** or **reference** (`void print(Base &b)`).

> [!WARNING]
> ### 3. Static Method Overriding (Method Hiding)
> *   **The Mistake:** Believing that declaring a static method as overridden in a subclass will result in runtime polymorphism.
> *   **The Reality:** In Java and C++, static methods cannot be overridden. If a subclass declares a static method with the same signature, it **hides** the parent class method. The method called is determined entirely at compile time based on the reference type, not the runtime object type.

> [!WARNING]
> ### 4. Missing Virtual Destructor in Base Classes
> *   **The Mistake:** Omitting `virtual` on the base class destructor when working with polymorphism.
> *   **The Reality:**
>     If you delete a derived class object through a base class pointer:
>     ```cpp
>     Base *ptr = new Derived();
>     delete ptr; // If ~Base() is not virtual, only Base's destructor is called!
>     ```
>     This leaves all resources allocated inside `Derived` unreleased, causing memory leaks. To prevent this, always declare the base destructor as virtual: `virtual ~Base() {}`.
