# Unit IV: PL Revision Cheat Sheet

A rapid-revision summary of language fundamentals, pointers, OOP principles, and memory bindings.

---

## ⚡ 1. Memory Layout & Storage Classes Card

### C/C++ Storage Classes Quick Reference
*   **`auto`**: Default. Stack allocation. Destroyed on block exit.
*   **`register`**: Allocated in CPU registers. Faster access, but cannot use reference address-of operator (`&`) in C.
*   **`static`**: Retains value. Initialized once. Stored in data segment, stays active until program termination.
*   **`extern`**: Variable declared elsewhere (global context).

### Stack vs. Heap Memory Allocation
| Attribute | Stack Memory | Heap Memory |
| :--- | :--- | :--- |
| **Allocation** | Automatic (handled by compiler). | Manual (via `new`/`delete` or Jvm GC). |
| **Speed** | Extremely fast (pointer adjustments). | Slower (overhead of search/fragmentation). |
| **Size Limit** | Small, fixed size (leads to `StackOverflow`).| Very large, bounded by system RAM. |
| **Order** | Strict LIFO order. | Arbitrary allocation/free order. |

---

## 📊 2. High-Yield Comparison Tables

### Abstract Class vs. Interface
| Feature | Abstract Class | Interface |
| :--- | :--- | :--- |
| **Inheritance** | Single class inheritance (use `extends`).| Multiple implementations allowed (`implements`). |
| **Methods** | Can contain both abstract & concrete methods.| All abstract (default methods in Java 8+). |
| **Variables** | Any type (instance variables allowed). | Must be `public static final` constants. |
| **Constructor** | Has constructors (called by subclasses). | Does not have constructors. |
| **Speed** | Faster function dispatch. | Slower due to dynamic interface lookup. |

### C++ vs. Java OOP Models
| Feature | C++ | Java |
| :--- | :--- | :--- |
| **Multiple Inheritance**| **Yes** (directly supported). | **No** (Only via interfaces). |
| **Memory Cleanup** | Manual Destructor (`~ClassName()`). | Automatic Garbage Collector. |
| **Pointers** | Supported (`*ptr`, pointer arithmetic). | Hidden references. No pointer arithmetic. |
| **Virtual by Default** | **No** (Must declare functions as `virtual`).| **Yes** (All non-static methods are virtual). |

---

## 🧠 3. Memory Tricks & Mnemonics

*   **OOP 4 Pillars**: **E-A-I-P** (like "Ape")
    *   **E**ncapsulation, **A**bstraction, **I**nheritance, **P**olymorphism.
*   **SOLID Principles**: **S-O-L-I-D**
    *   **S**ingle Responsibility, **O**pen-Closed, **L**iskov Substitution, **I**nterface Segregation, **D**ependency Inversion.
*   **Java Exception Blocks**: **T-C-F** (like "TCF")
    *   **T**ry, **C**atch, **F**inally.

---

## 🚨 4. High-Risk Confusion Zones

### 1. Method Overloading vs. Method Overriding
*   **Overloading**: Compile-time (static) polymorphism. Same function name, different parameter lists. In the same class scope.
*   **Overriding**: Runtime (dynamic) polymorphism. Same function name and same parameters. Occurs in parent and child classes.

### 2. Pointer vs. Reference in C++
*   **Pointer**: A variable holding an address. Can be reassigned, can point to `NULL`, supports pointer arithmetic (`ptr++`).
*   **Reference**: A constant alias. Cannot be reassigned, cannot be `NULL`, initialized upon declaration.

### 3. Struct vs. Class in C++
*   **`struct`**: Default access modifier is `public`.
*   **`class`**: Default access modifier is `private`.

---

## ⚠️ 5. Traps & Mistakes to Avoid in Exams

*   **Finally block execution**: In Java, the `finally` block **always** executes, even if there is a `return` statement inside the `try` or `catch` block. The only exception is if the system exits via `System.exit()`.
*   **Constructor calling order**: During inheritance, base constructors execute **before** derived constructors. However, destructors execute in the **reverse** order: derived destructors execute before base destructors.
*   **Function Signature**: Overloading is resolved based on the parameter list (type, order, and count) and **not** on the return type. Declaring two functions with the same parameters but different return types will fail compilation.
*   **Virtual Destructor Trap**: In C++, if a base class pointer deletes a derived class object, the base class **must** have a `virtual destructor` (`virtual ~Base()`). Otherwise, only the base destructor will be called, causing memory leaks for the derived portion of the object.

---

## ⚡ 6. Supplemental Masterclass Revision Sheets

### 📋 6.1 5-Minute Quick Reference Sheets

#### Classes
*   **Core Concept:** Logical blueprints (Class) vs. physical allocations (Object).
*   **Attributes vs. Methods:** Properties (variables) vs. Behaviors (functions).
*   **Lifecycle:** Dynamic allocation (`new`) $\to$ Constructor runs $\to$ Usage $\to$ Destructor scope clean.
*   **Static vs. Instance:** Static belongs to class (shared); Instance belongs to object (individual copies).

#### OOP Pillars (EIPA)
*   **Encapsulation:** Protect data fields (`private`) with getter/setter filters.
*   **Inheritance:** Base parent code extended by derived children.
*   **Polymorphism:** Method overloading (compile-time) vs. overriding (runtime via Vtables).
*   **Abstraction:** Simple interface masking execution complexity (ATM buttons).

#### Parameter Passing & Binding
*   **Pass by Value:** Copy made in parameter space; caller's variable remains unchanged.
*   **Pass by Reference:** Direct memory alias passes; modification affects caller directly.
*   **Pass by Result:** Write-only output parameter returned at end of function execution.
*   **Pass by Value-Result:** Copies value in at start, copies updated value back out to caller at function exit.
*   **Pass by Name:** Textual argument evaluation whenever referencing parameter.
*   **Binding:** Static compile-time type binding vs. Dynamic runtime lookup (polymorphic overrides).

#### Memory Handling
*   **Stack:** Compiler-managed, LIFO sequence, extremely fast, auto-cleaned block frames.
*   **Heap:** Dynamic custom allocations (`new`/`delete`), slower random access, requires manual/GC cleanup.
*   **Anomalies:** Memory leaks (forgot to free), Dangling pointer (pointing to freed RAM), Double free (releasing heap address twice).

---

### ⏱ 6.2 2-Minute Memory Maps
*   **Class:** Blueprint design drawing.
*   **Object:** Physical built house.
*   **Constructor:** Creator function (Automatic run).
*   **Destructor:** Janitor function (Automatic cleanup).
*   **Encapsulation:** Security code lock on variables.
*   **Inheritance:** Family hierarchy (Animal $\to$ Dog).
*   **Polymorphism:** One button, multiple actions (Shape drawing).
*   **Abstraction:** Simple dashboard, complex engine.
*   **Parameter Passing:** Value = photocopy; Reference = original document.
*   **Binding:** Static = fixed label; Dynamic = swappable pointer tag.
*   **Stack vs. Heap:** Stack = strict box slots; Heap = custom open ground storage.

---

## ⏱ 7. The 60-Second Exam Hall Recall Cards

Keep these 10 core PL rules in mind before entering the exam room:

1.  **Class vs. Object Memory:** A Class consumes no RAM. Only instantiated Objects occupy physical memory space.
2.  **Constructor Rules:** Same name as the class, no return type, runs automatically once per object creation.
3.  **Encapsulation hides data:** Achieve this by declaring variables `private` and exposing `public` accessor methods.
4.  **Abstraction hides detail:** Different from Encapsulation. Abstraction hides implementation detail; Encapsulation hides state data.
5.  **Polymorphism forms:** Overloading is static/compile-time (same class); Overriding is dynamic/runtime (base-derived classes resolved via Vtable).
6.  **Java parameter passing:** Java is strictly **pass-by-value**. Object arguments copy reference pointers by value.
7.  **Binding times:** Static binding happens during compilation; Dynamic binding happens during execution.
8.  **Stack vs. Heap:** Stack manages local variables and stack frames (auto-cleaned). Heap stores dynamic objects (manually or GC cleaned).
9.  **Memory Leak definition:** Losing all pointer addresses to a heap allocation without deallocating it.
10. **Dangling Pointer definition:** Storing the memory address of an object that has already been deleted.

