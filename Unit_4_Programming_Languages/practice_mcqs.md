# Unit IV: Programming Languages - MCQ Bank

Test your understanding of pointers, storage classes, OOP paradigms, parameter passing, and memory bindings with these 50 solved, high-probability Multiple Choice Questions.

---

## 🔷 Topic 1: Pointers & Storage Classes

#### Q1. What is a pointer in C/C++?
- A) A data type used to store characters
- B) A variable that stores the memory address of another variable
- C) A keyword used to define classes
- D) A standard library template
- **Answer: ✅ B**
- **Explanation**: A pointer holds the raw physical address of a memory location, allowing direct memory manipulation.

#### Q2. What does the `static` keyword accomplish when applied to a local variable inside a C function?
- A) It makes the variable accessible globally across all files
- B) It stores the variable in a CPU register
- C) It retains the variable's value between multiple function calls, initializing it only once
- D) It prevents the variable from being modified
- **Answer: ✅ C**
- **Explanation**: A static local variable is stored in the data segment of RAM rather than the stack. It persists for the lifetime of the program, retaining its value between function call invocations.

#### Q3. Which storage class in C uses CPU registers instead of RAM to store variables, meaning you cannot take their address with the `&` operator?
- A) `auto`
- B) `static`
- C) `register`
- D) `extern`
- **Answer: ✅ C**
- **Explanation**: The `register` storage class requests that the compiler allocate a CPU register for the variable for high-speed operations. Because CPU registers do not have memory addresses, using the address-of operator `&` on a register variable in C will fail.

#### Q4. What is the output of the following C++ code snippet?
```cpp
int x = 10;
int &ref = x;
ref = 20;
cout << x;
```
- A) 10
- B) 20
- C) Compiler Error
- D) Random address value
- **Answer: ✅ B**
- **Explanation**: `ref` is a reference variable, which acts as an alias for `x`. Modifying `ref` modifies `x` directly.

#### Q5. A pointer that stores the address of another pointer variable is called:
- A) Void Pointer
- B) Null Pointer
- C) Double Pointer (Pointer to Pointer)
- D) Dangling Pointer
- **Answer: ✅ C**
- **Explanation**: A double pointer (e.g., `int **ptr`) stores the memory address of an `int*` pointer variable.

---

## 🔷 Topic 2: OOP Principles & Inheritance

#### Q6. Which pillar of Object-Oriented Programming binds data members and member functions together into a single class unit, controlling access via modifiers?
- A) Abstraction
- B) Polymorphism
- C) Encapsulation
- D) Inheritance
- **Answer: ✅ C**
- **Explanation**: Encapsulation is the process of bundling data and methods together and hiding internal details using access specifiers (`private`, `protected`).

#### Q7. The Diamond Problem in multiple inheritance arises when:
- A) A parent class has two child classes
- B) A child class inherits from two parent classes that both derive from a single grandparent class, creating ambiguity
- C) A class has virtual functions
- D) A constructor calls another constructor
- **Answer: ✅ B**
- **Explanation**: If class $D$ inherits from $B$ and $C$, which both inherit from $A$, class $D$ receives duplicate copies of $A$'s members. This causes ambiguity when calling $A$'s functions from $D$.

#### Q8. In C++, how is the Diamond Problem resolved?
- A) Using multiple interfaces
- B) Using virtual inheritance (`class B : virtual public A`)
- C) Using the `extern` keyword
- D) It cannot be resolved in C++
- **Answer: ✅ B**
- **Explanation**: Declaring base classes as `virtual` during inheritance ensures only a single shared instance of the grandparent class is created in the final derived class.

#### Q9. Java resolves the diamond problem in multiple inheritance by:
- A) Supporting virtual inheritance
- B) Restricting multiple inheritance of classes, allowing multiple inheritance only through interfaces
- C) Ignoring the grandparent class
- D) Allowing multiple constructors
- **Answer: ✅ B**
- **Explanation**: Java disallows multiple inheritance of classes (`extends ClassA, ClassB` is illegal). A class can only extend one parent class, though it can implement multiple interfaces.

#### Q10. A class in C++ that contains at least one pure virtual function (e.g., `virtual void draw() = 0;`) is called:
- A) Concrete Class
- B) Interface
- C) Abstract Class
- D) Static Class
- **Answer: ✅ C**
- **Explanation**: An abstract class in C++ cannot be instantiated directly and serves as a blueprint. It must contain at least one pure virtual function.

---

## 🔷 Topic 3: Polymorphism & Binding

#### Q11. Which of the following is an example of compile-time (static) polymorphism?
- A) Method Overriding
- B) Virtual Functions
- C) Method Overloading
- D) Interface Implementation
- **Answer: ✅ C**
- **Explanation**: Method overloading (same method name, different parameters) is resolved by the compiler at compile time, making it compile-time polymorphism.

#### Q12. Runtime polymorphism (dynamic binding) is implemented in C++ using which mechanism?
- A) Templates
- B) Storage Classes
- C) Virtual Functions
- D) Operator Overloading
- **Answer: ✅ C**
- **Explanation**: Declaring a base class function as `virtual` tells the compiler to perform late binding (dynamic lookup) at runtime using VTABLE structures.

#### Q13. In dynamic binding, which compiler-generated structures map virtual function calls to their actual implementations at runtime?
- A) Page Tables
- B) VTABLE and VPTR (Virtual Table and Virtual Pointer)
- C) Symbol Tables
- D) Stack Frames
- **Answer: ✅ B**
- **Explanation**: When a class contains a virtual function, the compiler inserts a virtual pointer (`vptr`) into the object. This pointer points to a virtual table (`vtable`) containing function pointers for the overridden methods.

#### Q14. What is the output of the following C++ code?
```cpp
class Base {
public:
    void show() { cout << "Base "; }
};
class Derived : public Base {
public:
    void show() { cout << "Derived "; }
};
int main() {
    Base *ptr = new Derived();
    ptr->show();
    return 0;
}
```
- A) Base
- B) Derived
- C) Compiler Error
- D) Runtime Crash
- **Answer: ✅ A**
- **Explanation**: Because `show()` is not declared as a `virtual` function in the base class, the compiler performs static binding. Since the pointer type is `Base*`, it calls `Base::show()`.

#### Q15. If we modify the previous question and declare the base class function as `virtual void show()`, what is the output?
- A) Base
- B) Derived
- C) Compiler Error
- D) Base Derived
- **Answer: ✅ B**
- **Explanation**: Adding `virtual` triggers dynamic binding, resolving the call at runtime based on the actual object type (`Derived`), not the pointer type (`Base*`).

---

## 🔷 Topic 4: Parameter Passing & Exceptions

#### Q16. Which parameter passing technique creates a copy of the argument on the function's stack frame?
- A) Pass by Reference
- B) Pass by Address
- C) Pass by Value
- D) Pass by Name
- **Answer: ✅ C**
- **Explanation**: Pass by value copies the argument. Modifications inside the function do not affect the caller's variable.

#### Q17. In Java, what is the parameter passing model for primitive data types and object references?
- A) Primitives are passed by reference, objects by value
- B) All parameters (both primitives and object references) are passed by value
- C) All parameters are passed by reference
- D) Objects are passed by reference, primitives by value
- **Answer: ✅ B**
- **Explanation**: Java is strictly **pass-by-value**. For primitives, it passes a copy of the value. For objects, it passes a copy of the reference address (meaning you can modify the object's fields, but you cannot change which object the caller's reference points to).

#### Q18. What is the execution order of `try`, `catch`, and `finally` blocks in Java if an exception occurs?
- A) `try` $\to$ `finally`
- B) `try` $\to$ `catch` $\to$ `finally`
- C) `catch` $\to$ `finally`
- D) `try` $\to$ `catch`
- **Answer: ✅ B**
- **Explanation**: If an exception occurs in the `try` block, execution jumps to the matching `catch` block. Afterward, the `finally` block executes.

#### Q19. In Java, a `finally` block:
- A) Executes only if no exception occurs
- B) Executes only if an exception is caught
- C) Always executes, even if a `return` statement is executed in `try` or `catch`
- D) Replaces the catch block
- **Answer: ✅ C**
- **Explanation**: The `finally` block is guaranteed to execute (to clean up resources) unless `System.exit()` is called.

#### Q20. A checked exception in Java is:
- A) Checked by the runtime environment
- B) Checked at compile-time, requiring a `try-catch` block or a `throws` declaration
- C) A type of NullPointerException
- D) Ignored by the compiler
- **Answer: ✅ B**
- **Explanation**: Checked exceptions (e.g., `IOException`) are checked at compile time. The compiler forces the programmer to handle or declare them.

---

## 🔷 Topic 5: Memory Management & Garbage Collection

#### Q21. Stack memory allocation is characterized by:
- A) Manual allocation using `malloc`
- B) Automatic allocation, high speed, and LIFO lifecycle
- C) Susceptibility to external fragmentation
- D) Garbage collection sweeps
- **Answer: ✅ B**
- **Explanation**: Stack allocations are managed by the compiler for local variables. They are fast because the system only adjusts the stack pointer, following LIFO order.

#### Q22. Heap memory allocation is used for:
- A) Storing local function arguments
- B) Return addresses of subroutines
- C) Dynamic memory allocation at runtime
- D) Constant system macros
- **Answer: ✅ C**
- **Explanation**: Heap memory is used when the size or lifetime of data cannot be determined at compile time (e.g., creating objects dynamically with `new`).

#### Q23. In C++, allocating memory with `new` but failing to deallocate it with `delete` leads to:
- A) Segmentation Fault
- B) Memory Leak
- C) Stack Overflow
- D) Dangling Pointer
- **Answer: ✅ B**
- **Explanation**: If memory is allocated on the heap and not released, it remains reserved and unusable, draining system RAM.

#### Q24. In C++, what happens when a base class pointer deletes a derived class object, but the base class destructor is NOT declared as `virtual`?
- A) Compiler Error
- B) Only the base class destructor is called, causing memory leaks in the derived class
- C) Only the derived class destructor is called
- D) Both destructors are called in the correct order
- **Answer: ✅ B**
- **Explanation**: Without a `virtual` destructor in the base class, the compiler binds the destructor call statically to the pointer type (`Base*`), bypassing the derived class destructor.

#### Q25. The JVM Garbage Collector identifies dead objects using which primary criteria?
- A) If the object has been in memory for over 10 minutes
- B) If the object is no longer reachable from any GC Roots
- C) If the object has large memory footprints
- D) If the object is primitive
- **Answer: ✅ B**
- **Explanation**: Reachability analysis determines if an object can be accessed starting from active references (stack variables, static references). Unreachable objects are marked for collection.

---

## 🔷 Topic 6: Conceptual Review Questions

#### Q26. C is considered what type of language?
- A) Object-Oriented
- B) Procedural / Imperative
- C) Functional
- D) Logic
- **Answer: ✅ B**
- **Explanation**: C focuses on step-by-step procedures and function calls rather than objects.

#### Q27. Java source code is compiled into:
- A) Native machine code binaries
- B) Assembly code
- C) Bytecode (stored in `.class` files)
- D) HTML text
- **Answer: ✅ C**
- **Explanation**: The Java compiler (`javac`) compiles source files into intermediate bytecode, which is run by the JVM on any platform.

#### Q28. A pointer that has been deallocated (freed) but still points to its old memory address is called:
- A) Null Pointer
- B) Void Pointer
- C) Dangling Pointer
- D) Wild Pointer
- **Answer: ✅ C**
- **Explanation**: A dangling pointer points to freed memory. Accessing it causes unpredictable behavior or segmentation faults.

#### Q29. Pointer arithmetic (e.g., `ptr + 1`) increments the address stored in the pointer by:
- A) 1 byte
- B) 1 bit
- C) The size of the data type the pointer points to
- D) 4 bytes
- **Answer: ✅ C**
- **Explanation**: The address increments by `sizeof(type)`. For an `int*` on a 4-byte system, `ptr + 1` increases the address by 4.

#### Q30. Which C++ keyword is used to ensure a base class method must be overridden in subclasses, preventing direct instantiation of the base class?
- A) `const`
- B) `static`
- C) `= 0` (Pure Virtual declaration)
- D) `inline`
- **Answer: ✅ C**
- **Explanation**: Specifying `= 0` on a virtual function makes it pure virtual, turning the class into an abstract class.

#### Q31. In Java, what is the default parent class of all classes?
- A) `Main`
- B) `String`
- C) `Object`
- D) `System`
- **Answer: ✅ C**
- **Explanation**: Every class in Java implicitly extends `java.lang.Object`.

#### Q32. Can static methods be overridden in Java?
- A) Yes, always
- B) No, they can only be hidden (Method Hiding)
- C) Only if declared virtual
- D) Only if public
- **Answer: ✅ B**
- **Explanation**: Overriding relies on runtime dynamic dispatch for instance methods. Because static methods belong to the class rather than an instance, they are bound statically at compile time.

#### Q33. Which parameter passing technique is most efficient for passing large structures/classes in C++?
- A) Pass by Value
- B) Pass by Constant Reference (`const Type&`)
- C) Pass by pointer in register
- D) All have identical performance
- **Answer: ✅ B**
- **Explanation**: Pass by reference passes only a pointer-sized address, avoiding copying the large object. Using `const` prevents the function from modifying the original object.

#### Q34. What is the scope of an `extern` variable?
- A) Local to the function it is declared in
- B) File-scope only
- C) Global across multiple files/modules
- D) Restricted to the heap
- **Answer: ✅ C**
- **Explanation**: `extern` declares a global variable that is defined in another source file or module.

#### Q35. What is the primary drawback of using a Mark-and-Sweep garbage collection algorithm?
- A) It cannot clean heap objects
- B) It causes "Stop-the-World" pauses, halting program execution to scan memory
- C) It requires manual destructors
- D) It causes memory leaks
- **Answer: ✅ B**
- **Explanation**: To identify reachable objects safely, GC algorithms must temporarily freeze user thread execution, causing execution pauses.

#### Q36. What is the difference between `delete` and `delete[]` in C++?
- A) `delete` is for objects, `delete[]` is for primitive arrays
- B) `delete` calls the destructor of a single object, while `delete[]` calls the destructors for all elements in an allocated array
- C) `delete[]` is used in Java
- D) There is no difference
- **Answer: ✅ B**
- **Explanation**: Allocating an array with `new Type[N]` requires using `delete[]` to ensure the destructor is called for all $N$ elements in the array.

#### Q37. What is the output of the expression `sizeof` on an array of 5 integers in C++ (assuming a 4-byte integer size)?
- A) 5 bytes
- B) 20 bytes
- C) 40 bytes
- D) 10 bytes
- **Answer: ✅ B**
- **Explanation**: `sizeof(array)` returns the total bytes occupied: $5 \text{ elements} \times 4 \text{ bytes/element} = 20 \text{ bytes}$.

#### Q38. In C++, static member functions can access:
- A) Only static member variables and static functions of the class
- B) Both static and non-static member variables
- C) The `this` pointer
- D) Private instance variables
- **Answer: ✅ A**
- **Explanation**: Static functions belong to the class, not an object. Because they run without a `this` pointer instance context, they cannot access non-static instance variables.

#### Q39. What is a memory leak?
- A) Unchecked file reads
- B) RAM memory space that was dynamically allocated but is no longer reachable by the program, preventing it from being reused
- C) Stack overflow crash
- D) Hardware capacitor failure
- **Answer: ✅ B**
- **Explanation**: Memory leaks occur when heap memory is allocated but references to it are lost before it is freed.

#### Q40. Which keyword in Java prevents a class from being inherited?
- A) `static`
- B) `final`
- C) `const`
- D) `abstract`
- **Answer: ✅ B**
- **Explanation**: Marking a class as `final` prevents it from being extended. Marking a method as `final` prevents it from being overridden.

#### Q41. In C++, a destructor is:
- A) Used to allocate memory
- B) A special member function called automatically when an object goes out of scope to release resources
- C) A runtime error handler
- D) The main compiler thread
- **Answer: ✅ B**
- **Explanation**: Destructors clean up resources (e.g. closing files, releasing memory) when an object is destroyed.

#### Q42. In Java, what happens to memory allocation if `System.gc()` is called?
- A) Immediate guaranteed sweep of the heap
- B) Suggests that the JVM run the Garbage Collector, but does not guarantee execution
- C) The JVM exits
- D) Stack is emptied
- **Answer: ✅ B**
- **Explanation**: `System.gc()` suggests that the JVM run the garbage collector, but the JVM can choose to ignore the call.

#### Q43. What does "Write Once, Run Anywhere" (WORA) refer to?
- A) Standard compiled binary files
- B) Platform independence in Java via Bytecode execution on the JVM
- C) C++ template functions
- D) SQL transactions
- **Answer: ✅ B**
- **Explanation**: Java source code compiles to bytecode, which can run on any device that has a compatible Java Virtual Machine (JVM).

#### Q44. In C++, can you overload the scope resolution operator (`::`)?
- A) Yes, always
- B) No, the scope resolution operator (`::`) is one of the operators that cannot be overloaded
- C) Only inside classes
- D) Only in templates
- **Answer: ✅ B**
- **Explanation**: C++ forbids overloading of: `::` (Scope Resolution), `.` (Member Access), `.*` (Pointer-to-Member), and `?:` (Ternary).

#### Q45. Which of the following refers to early binding?
- A) Static Binding, resolved at compile-time
- B) Dynamic Binding, resolved at runtime
- C) Virtual method lookup
- D) Garbage Collection
- **Answer: ✅ A**
- **Explanation**: Early (static) binding maps method calls to their definitions at compile time.

#### Q46. What is a wild pointer?
- A) A pointer pointing to the first index of an array
- B) An uninitialized pointer pointing to an arbitrary memory location
- C) A double pointer
- D) A pointer that points to a function
- **Answer: ✅ B**
- **Explanation**: A wild pointer is uninitialized. It contains garbage data and points to an arbitrary memory location, which can cause crashes if dereferenced.

#### Q47. If a class in Java implements multiple interfaces, how are duplicate default method signatures resolved?
- A) The program crashes during compilation
- B) The class must override the duplicate method to resolve the ambiguity
- C) The first interface listed takes priority
- D) It is ignored
- **Answer: ✅ B**
- **Explanation**: If a class implements two interfaces containing duplicate default method signatures, the compiler throws an error. The class must resolve the ambiguity by overriding the method.

#### Q48. In C++, pointer arithmetic on a pointer of type `void*` is:
- A) Allowed and increments by 1 byte
- B) Disallowed because the compiler does not know the size of the pointed-to type
- C) Allowed and increments by 4 bytes
- D) Handled dynamically
- **Answer: ✅ B**
- **Explanation**: A `void*` pointer represents an untyped memory address. Because its size is undefined, pointer arithmetic cannot be performed on it.

#### Q49. Which modifier in Java makes a class member accessible only within the same package and by subclasses?
- A) `private`
- B) `protected`
- C) `public`
- D) default (package-private)
- **Answer: ✅ B**
- **Explanation**: In Java, `protected` members are accessible within the same package and by subclasses in other packages.

#### Q50. In C++, the `this` pointer:
- A) Points to the base class
- B) Points to the current object instance inside non-static member functions
- C) Is a static global pointer
- D) Is used to delete objects
- **Answer: ✅ B**
- **Explanation**: The `this` pointer is an implicit parameter passed to all non-static member functions, pointing to the calling object instance.

---

## 🔷 Topic 3: Advanced Pointers & Storage Classes

#### Q51. What is the output of the following C code snippet?
```c
int a = 10;
const int *ptr = &a;
*ptr = 20;
printf("%d", a);
```
- A) 10
- B) 20
- C) Compiler Error
- D) Runtime Crash
- **Answer: ✅ C**
- **Explanation**: `const int *ptr` defines a pointer to a constant integer. The value pointed to by `ptr` cannot be changed via `ptr` (i.e., `*ptr = 20` is illegal), causing a compiler error.

#### Q52. What is the output of the following C++ code?
```cpp
int x = 5;
int *const ptr = &x;
int y = 10;
ptr = &y;
cout << x;
```
- A) 5
- B) 10
- C) Compiler Error
- D) Runtime Crash
- **Answer: ✅ C**
- **Explanation**: `int *const ptr` defines a constant pointer. The address stored in `ptr` cannot be changed after initialization (i.e., `ptr = &y` is illegal), causing a compiler error.

#### Q53. What is pointer subtraction in C/C++?
```cpp
int arr[5] = {1, 2, 3, 4, 5};
int *p1 = &arr[1];
int *p2 = &arr[4];
cout << (p2 - p1);
```
- A) 12
- B) 3
- C) 4
- D) Compiler Error
- **Answer: ✅ B**
- **Explanation**: Subtracting two pointers of the same type yields the number of elements between them (of the pointed-to type), not the raw byte difference. Here, `p2 - p1` equals $4 - 1 = 3$.

#### Q54. Which of the following is true about a static global variable in C?
- A) It can be accessed in any other file using the `extern` keyword
- B) It is visible only within the file in which it is declared
- C) It is stored on the stack
- D) Its lifetime is limited to the main function
- **Answer: ✅ B**
- **Explanation**: Applying `static` to a global variable restricts its linkage to internal, meaning it is only visible within the compilation unit (file) where it is defined.

#### Q55. In C, what is the default value of an uninitialized static variable?
- A) Garbage value
- B) 0
- C) NULL
- D) Compilation Error
- **Answer: ✅ B**
- **Explanation**: Variables in the data segment (global and static variables) are automatically initialized to 0 (or NULL for pointers) if not explicitly initialized by the programmer.

#### Q56. What happens if you try to take the address of a register variable in C?
- A) You get the CPU register address
- B) It causes a compiler error
- C) It defaults to a stack address
- D) It runs slowly
- **Answer: ✅ B**
- **Explanation**: CPU registers do not have memory addresses. Therefore, applying the address-of operator `&` to a variable declared with the `register` storage class is illegal in C.

#### Q57. What is the linkage of a variable declared with the `extern` keyword?
- A) No linkage
- B) Internal linkage
- C) External linkage
- D) Static linkage
- **Answer: ✅ C**
- **Explanation**: The `extern` keyword gives a variable external linkage, meaning it can be shared and referenced across multiple source files during the linking phase.

#### Q58. In C++, a reference variable:
- A) Can be changed to refer to another variable after initialization
- B) Must be initialized at the time of declaration
- C) Can be a NULL reference
- D) Takes 4 bytes of storage that you can access with the `&` operator
- **Answer: ✅ B**
- **Explanation**: A C++ reference is an alias. It must be bound to a variable at the time of creation and cannot be rebound or set to NULL.

#### Q59. What is a dangling pointer?
- A) A pointer that has not been initialized
- B) A pointer pointing to a memory location that has been deallocated (freed)
- C) A pointer pointing to NULL
- D) A pointer that points to another pointer
- **Answer: ✅ B**
- **Explanation**: A dangling pointer points to a memory location that was deleted or freed. Accessing it leads to undefined behavior.

#### Q60. How can you prevent dangling pointers?
- A) By reinitializing the pointer to NULL immediately after freeing the memory
- B) By using the `static` keyword
- C) By avoiding the use of pointers
- D) By compiling with optimization flags
- **Answer: ✅ A**
- **Explanation**: Setting a pointer to `NULL` (or `nullptr` in C++) immediately after freeing ensures that any future access can be checked against NULL.

---

## 🔷 Topic 4: Advanced OOP, Inheritance & Polymorphism

#### Q61. What is the output of the following C++ program?
```cpp
class Base {
public:
    virtual void print() { cout << "Base "; }
};
class Derived : public Base {
public:
    void print() override { cout << "Derived "; }
};
int main() {
    Base *ptr = new Derived();
    ptr->print();
    delete ptr;
}
```
- A) Base
- B) Derived
- C) Compiler Error
- D) Runtime Crash
- **Answer: ✅ B**
- **Explanation**: `print` is declared as virtual in `Base` and overridden in `Derived`. At runtime, the call `ptr->print()` is dynamically bound to the actual object type, which is `Derived`.

#### Q62. What is the output of the program in Q61 if `virtual` is removed from the `Base` class `print` declaration?
- A) Base
- B) Derived
- C) Compiler Error
- D) Runtime Crash
- **Answer: ✅ A**
- **Explanation**: Without the `virtual` keyword, the function call is bound statically at compile time based on the pointer's declared type, which is `Base*`.

#### Q63. In C++, what is a pure virtual function?
- A) A function that is defined inside an interface
- B) A virtual function with no implementation, declared with `virtual void func() = 0;`
- C) A function that cannot be overridden
- D) A constructor that has no parameters
- **Answer: ✅ B**
- **Explanation**: A pure virtual function is declared with `= 0` and has no definition in the base class. Any class containing a pure virtual function is an abstract class and cannot be instantiated.

#### Q64. What is "Object Slicing" in C++?
- A) Splitting an array of objects
- B) The truncation of derived class members when a derived object is passed by value to a base class parameter
- C) Dynamic casting failure
- D) Deallocating a portion of an object from the heap
- **Answer: ✅ B**
- **Explanation**: Passing a derived object by value forces the compiler to copy only the base portion into the base object, slicing off the derived class properties and Vtable pointers.

#### Q65. How can you prevent Object Slicing in C++?
- A) By passing objects by reference or pointer
- B) By declaring the base class as virtual
- C) By using the `static` keyword on members
- D) By disabling inheritance
- **Answer: ✅ A**
- **Explanation**: Passing by reference (`Base &b`) or pointer (`Base *b`) preserves the derived object's memory layout and dynamic Vtable pointers.

#### Q66. Why should destructors in a base class be declared as `virtual`?
- A) To allow the base class to access derived class variables
- B) To ensure that the derived class destructor is called when deleting a derived object through a base class pointer
- C) To speed up program execution
- D) To prevent class copying
- **Answer: ✅ B**
- **Explanation**: If a base class pointer deletes a derived object and the base destructor is not virtual, only the base destructor executes, causing memory leaks of derived-class resources.

#### Q67. What is the size of an object of a class in C++ containing only virtual functions and no data members?
- A) 0 bytes
- B) 1 byte
- C) Size of a pointer (4 bytes on 32-bit, 8 bytes on 64-bit platforms)
- D) Size of the Vtable
- **Answer: ✅ C**
- **Explanation**: Any object containing virtual functions must store an implicit pointer (`__vptr`) to its class's Vtable. The object size is the size of this pointer.

#### Q68. Can a constructor be declared as `virtual` in C++?
- A) Yes, always
- B) No, constructors cannot be virtual because an object must exist in memory before its Vtable can be accessed
- C) Only in abstract classes
- D) Only in multiple inheritance
- **Answer: ✅ B**
- **Explanation**: Constructors cannot be virtual. To construct an object, the compiler needs to know the exact concrete type at compile time to allocate stack/heap frames. Vtable pointers are set during constructor execution.

#### Q69. Can a static method be virtual in C++?
- A) Yes, to allow static polymorphism
- B) No, static methods belong to the class scope and run without an object instance or a `this` pointer, meaning they cannot access a VPTR
- C) Only if declared public
- D) Only in templates
- **Answer: ✅ B**
- **Explanation**: Virtual calls require an object instance to lookup the VPTR. Because static methods have no instance context, they cannot be virtual.

#### Q70. What is the function of `dynamic_cast` in C++?
- A) To convert a constant variable to non-constant
- B) To perform safe downcasting of polymorphic class pointers, returning `nullptr` (or throwing an exception for references) if the cast is invalid
- C) To cast pointers of unrelated classes
- D) To speed up compilation
- **Answer: ✅ B**
- **Explanation**: `dynamic_cast` uses Runtime Type Information (RTTI) to safely cast a base pointer down to a derived type. It verifies the validity of the cast at runtime.

#### Q71. What does the `final` keyword accomplish when applied to a method in Java?
- A) It prevents the class from being instantiated
- B) It prevents the method from being overridden by subclasses
- C) It makes the method run in a separate thread
- D) It makes the method static
- **Answer: ✅ B**
- **Explanation**: In Java, marking a method as `final` forbids subclasses from overriding its definition, protecting core class logic.

#### Q72. Which of the following is true about Java interfaces?
- A) They can contain instance fields
- B) They can contain constructors
- C) A class can implement multiple interfaces but extend only one class
- D) They support virtual base class inheritance
- **Answer: ✅ C**
- **Explanation**: Java disallows multiple class inheritance to prevent the Diamond problem. It permits classes to implement multiple interfaces, which contain no instance fields or state.

#### Q73. In C++, how is a "friend" function utilized?
- A) It is a member function that can be accessed without an object
- B) It is a non-member function granted access to the private and protected members of a class
- C) It is used to copy classes
- D) It is a function that can only be called from main
- **Answer: ✅ B**
- **Explanation**: Declaring a function as a `friend` of a class allows that function to access all private and protected members of the class, bypass public access limits.

#### Q74. In Java, what is the output of overriding a static method?
- A) Dynamic polymorphism at runtime
- B) Compile-time error
- C) Method Hiding; the method called is determined by the reference type at compile-time
- D) The program throws a NullPointerException
- **Answer: ✅ C**
- **Explanation**: Java static methods cannot be overridden. Defining a static method with the same signature in a subclass hides the parent version. The resolution is static, based on the reference type.

#### Q75. What is the difference between Method Overloading and Method Overriding?
- A) Overloading is runtime polymorphism; Overriding is compile-time polymorphism
- B) Overloading occurs within the same class with different parameters; Overriding occurs in child classes with the same signature
- C) Overloading requires the virtual keyword
- D) Overriding does not require inheritance
- **Answer: ✅ B**
- **Explanation**: Method overloading (compile-time) defines functions with the same name but different parameter list signatures. Overriding (runtime) redefines a parent method in a subclass using the exact same signature.

---

## 🔷 Topic 5: Parameter Passing & Memory Binding

#### Q76. In C++, what happens when a parameter is passed by reference?
- A) A copy of the object is created on the stack
- B) An alias for the argument is created, allowing direct modification without pointer dereferencing
- C) A constant pointer is created
- D) The parameter is allocated on the heap
- **Answer: ✅ B**
- **Explanation**: Reference parameters pass an alias of the caller's variable. Any modification to the parameter directly alters the caller's variable without copies.

#### Q77. What is the output of the following C++ code snippet?
```cpp
void swap(int &x, int &y) {
    int temp = x;
    x = y;
    y = temp;
}
int main() {
    int a = 5, b = 10;
    swap(a, b);
    cout << a << "," << b;
}
```
- A) 5,10
- B) 10,5
- C) 5,5
- D) Compiler Error
- **Answer: ✅ B**
- **Explanation**: Because parameters are passed by reference (`int &x, int &y`), changes made inside `swap` exchange the actual values of `a` and `b`.

#### Q78. In Java, how are objects passed to methods?
- A) Pass-by-value, where the value passed is the copy of the object reference
- B) Pass-by-reference
- C) Pass-by-address
- D) Pass-by-name
- **Answer: ✅ A**
- **Explanation**: Java is strictly **pass-by-value**. For objects, the value passed is a copy of the reference pointer. This means you can modify object fields, but you cannot change the caller's reference to point to a new object.

#### Q79. What is the output of the following Java program?
```java
class Test {
    int value = 10;
}
public class Main {
    static void modify(Test t) {
        t.value = 20;
        t = new Test();
        t.value = 30;
    }
    public static void main(String[] args) {
        Test obj = new Test();
        modify(obj);
        System.out.println(obj.value);
    }
}
```
- A) 10
- B) 20
- C) 30
- D) Compiler Error
- **Answer: ✅ B**
- **Explanation**: `obj`'s reference copy is passed. `t.value = 20` modifies the original object. Reassigning `t = new Test()` changes the local copy of the reference to point to a new object, leaving the caller's reference `obj` pointing to the original object (whose value is now 20).

#### Q80. What is "Late Binding" (Dynamic Binding)?
- A) Resolving variables to register addresses during compilation
- B) Binding function calls to their definitions at runtime based on the object type
- C) Linking external library binary files
- D) Loading classes dynamically
- **Answer: ✅ B**
- **Explanation**: Late binding occurs at runtime. The JVM or CPU inspects the concrete object and uses a Vtable lookup to route the function call to the correct overridden method.

#### Q81. Which cast in C++ is used to perform low-level, unsafe pointer conversions (like casting an `int*` to a `char*`)?
- A) `static_cast`
- B) `dynamic_cast`
- C) `reinterpret_cast`
- D) `const_cast`
- **Answer: ✅ C**
- **Explanation**: `reinterpret_cast` instructs the compiler to treat a binary pattern as another type without safety checks. Used for low-level system programming.

#### Q82. In C++, which cast must be used to remove the `const` qualifier from a variable?
- A) `static_cast`
- B) `const_cast`
- C) `reinterpret_cast`
- D) `dynamic_cast`
- **Answer: ✅ B**
- **Explanation**: `const_cast` is the only cast in C++ designed to add or remove `const` (or `volatile`) attributes from a variable.

#### Q83. What is static binding resolved by?
- A) The linker at runtime
- B) The compiler at compile-time
- C) The virtual tables
- D) The operating system loader
- **Answer: ✅ B**
- **Explanation**: Static binding maps calls based on static declarations at compile time, eliminating runtime lookup overhead.

#### Q84. What is a "pure OOP" language constraint?
- A) Supports primitive data types directly
- B) Every component must be defined within a class, and all values are objects
- C) Does not support inheritance
- D) Must contain static methods only
- **Answer: ✅ B**
- **Explanation**: In pure OOP, primitives are absent (all values are objects) and all execution is class-scoped. Java is not pure OOP because it supports primitive types (`int`, `char`, etc.) for performance.

#### Q85. In C++, can you overload member functions based only on their return type?
- A) Yes, always
- B) No, overloading requires different parameter lists. Return types alone are not part of the function signature
- C) Only if the return type is virtual
- D) Only in classes
- **Answer: ✅ B**
- **Explanation**: C++ overload resolution is based on function name and parameter types. The return type is not checked during resolution, making overloading by return type alone a compiler error.

---

## 🔷 Topic 6: Memory Handling & Garbage Collection

#### Q86. What is the difference between `new` and `malloc` in C++?
- A) `new` is a function, `malloc` is an operator
- B) `new` allocates memory and calls constructors; `malloc` only allocates raw byte memory
- C) `malloc` returns a typed pointer
- D) `new` requires the size of memory in bytes
- **Answer: ✅ B**
- **Explanation**: `new` is an operator that allocates heap memory and initializes constructors. `malloc` is a standard C function that allocates a raw block of bytes, returning a `void*` pointer.

#### Q87. What happens if you allocate memory with `new[]` but release it with `delete` (without brackets)?
- A) Safe deallocation
- B) Undefined behavior, which can cause memory leaks or heap corruption because individual destructors for array elements are not called
- C) Immediate compile error
- D) The stack overflows
- **Answer: ✅ B**
- **Explanation**: Arrays allocated with `new[]` must be released with `delete[]`. Using `delete` skips destructors for all elements beyond the first, leading to memory leaks and heap table corruption.

#### Q88. What is the role of the JVM garbage collector?
- A) Defragmenting the hard drive
- B) Automatically identifying and reclaiming heap memory occupied by unreachable objects
- C) Compiling bytecode
- D) Catching exceptions
- **Answer: ✅ B**
- **Explanation**: The GC automatically frees memory occupied by objects that have no active references, preventing manual memory leaks.

#### Q89. In JVM Generational Garbage Collection, where are new objects allocated?
- A) Old Generation
- B) Eden Space
- C) Survivor Space S0/S1
- D) Method Area
- **Answer: ✅ B**
- **Explanation**: All newly instantiated objects are allocated in the Eden space of the Young Generation.

#### Q90. What is a Minor GC in the JVM?
- A) Cleaning the entire heap
- B) Scanning and reclaiming memory in the Young Generation (Eden and Survivor spaces)
- C) Deleting static variables
- D) Compiling code
- **Answer: ✅ B**
- **Explanation**: Minor GC is a fast garbage collection process that cleans only the Young Generation, promoting surviving objects to Survivor spaces.

#### Q91. When is an object promoted to the Old (Tenured) Generation in the JVM?
- A) Immediately after instantiation
- B) When it survives a specific number of Minor GC cycles (exceeds age threshold)
- C) When it is larger than 1 MB
- D) When the program terminates
- **Answer: ✅ B**
- **Explanation**: Objects that survive multiple Minor GC sweeps increment their age counter. When it exceeds the age threshold (default 15), they are moved to the Old Generation.

#### Q92. What are "GC Roots" in reachability analysis?
- A) Objects that have been deleted
- B) Active references that are immediately accessible (like local stack variables, active thread references, static variables) from which all references are traced
- C) The root directory of the JVM
- D) Constructors
- **Answer: ✅ B**
- **Explanation**: Reachability analysis starts at GC Roots. If an object cannot be reached by traversing references starting from any GC Root, it is declared dead and swept.

#### Q93. What is the "Stop-the-World" phase in garbage collection?
- A) The program crashes
- B) The JVM halts all application execution threads while GC processes reclaim memory
- C) Network packets are dropped
- D) The OS halts
- **Answer: ✅ B**
- **Explanation**: Stop-the-world pauses all active application threads to prevent the application from modifying the object reference graph while GC is sorting memory.

#### Q94. What is a memory leak in Java?
- A) A physical RAM failure
- B) Objects that are no longer needed by the program but remain reachable via active reference chains, preventing GC from reclaiming them
- C) A stack overflow error
- D) Modifying private fields
- **Answer: ✅ B**
- **Explanation**: Even with GC, if a program maintains references to unused objects (e.g. in static lists), the GC cannot delete them, resulting in a memory leak.

#### Q95. Which of the following is NOT a GC Root?
- A) Local variables in the active stack frame
- B) Static variables inside loaded classes
- C) An object on the heap that has no references pointing to it
- D) Active thread instances
- **Answer: ✅ C**
- **Explanation**: Unreferenced heap objects are targets for sweep collection, not starting roots.

---

## 🔷 Topic 7: Advanced Coding Mechanics & Exceptions

#### Q96. In C++, what is the purpose of the `copy constructor`?
- A) To copy a class definition to another file
- B) To initialize a new object as a copy of an existing object of the same class
- C) To delete duplicate objects
- D) To print object fields
- **Answer: ✅ B**
- **Explanation**: A copy constructor is declared as `ClassName(const ClassName &src)`. It initializes an object using the values of another object of the same class.

#### Q97. What is the difference between a Shallow Copy and a Deep Copy?
- A) Shallow copy copies all data including heap pointers; Deep copy allocates new heap space and copies the actual pointed-to values
- B) Deep copy is faster
- C) Shallow copy is illegal in C++
- D) There is no difference
- **Answer: ✅ A**
- **Explanation**: A shallow copy duplicates pointer addresses, meaning both objects share the same heap resources (causing double free crashes on destruction). A deep copy allocates new memory blocks and copies the actual values, ensuring isolation.

#### Q98. What is the rule of three in C++?
- A) Keep code under three functions
- B) If a class defines a destructor, it should also define a copy constructor and copy assignment operator to manage resources safely
- C) Classes must contain at most three member variables
- D) Compile with three optimization flags
- **Answer: ✅ B**
- **Explanation**: If a class manages dynamic resources, defining a custom destructor implies you also need to manage copying behavior (copy constructor and assignment operator) to prevent shallow copy issues.

#### Q99. In Java, what is the difference between Checked and Unchecked Exceptions?
- A) Checked exceptions are checked by the programmer; Unchecked are checked by the compiler
- B) Checked exceptions are verified at compile-time (must be declared/caught); Unchecked are verified at runtime (descend from RuntimeException)
- C) Checked exceptions do not cause program termination
- D) Unchecked exceptions cannot be caught
- **Answer: ✅ B**
- **Explanation**: Checked exceptions (e.g., `IOException`) must be handled using try-catch blocks or declared in the method signature using `throws`. Unchecked exceptions (e.g., `NullPointerException`) do not have this restriction.

#### Q100. In Java, does the `finally` block always execute?
- A) Yes, except in cases of JVM crash or calling `System.exit(0)`
- B) Only if an exception occurs
- C) Only if no exception occurs
- D) No, it must be called manually
- **Answer: ✅ A**
- **Explanation**: The `finally` block is guaranteed to run after try-catch statements, ensuring resources (e.g., database connections, file streams) are closed even if an exception is thrown.

#### Q101. What is the output of the following C++ code snippet?
```cpp
class A {
public:
    A() { cout << "A"; }
    ~A() { cout << "~A"; }
};
class B : public A {
public:
    B() { cout << "B"; }
    ~B() { cout << "~B"; }
};
int main() {
    B obj;
}
```
- A) AB~B~A
- B) BA~A~B
- C) AB~A~B
- D) Compiler Error
- **Answer: ✅ A**
- **Explanation**: Constructing a child class object calls constructors from parent to child (A then B). Destructors run in reverse order, from child to parent (~B then ~A). Thus, output is `AB~B~A`.

#### Q102. In Java, the `finalize()` method is:
- A) Called manually to release heap memory
- B) Deprecated, but historically called by the Garbage Collector before reclaiming an object's memory
- C) A constructor modifier
- D) Used to lock classes
- **Answer: ✅ B**
- **Explanation**: The `finalize()` method is called by the GC before deleting an object. Because its execution is non-deterministic and can cause resource leaks, it is deprecated in modern Java.

#### Q103. What does the `finally` block solve?
- A) Speeds up compilation
- B) Ensures cleanup code runs regardless of exceptions
- C) Catches all unchecked exceptions
- D) Compiles native code
- **Answer: ✅ B**
- **Explanation**: `finally` guarantees resource release (like closing file handles) even if control flows out of the method due to exceptions or return statements.

#### Q104. In C++, can you catch an integer value in exception handling?
- A) No, you can only catch classes inheriting from `std::exception`
- B) Yes, you can throw and catch any data type in C++ (e.g., `throw 404;`)
- C) Only in template classes
- D) Only using dynamic cast
- **Answer: ✅ B**
- **Explanation**: Unlike Java, where you can only throw objects that inherit from `Throwable`, C++ allows throwing and catching any primitive or user-defined type (e.g., `throw 10;`, `throw "Error";`).

#### Q105. What is the memory area in the JVM where class structures, method data, and static fields are stored?
- A) Stack
- B) Heap
- C) Method Area
- D) PC Register
- **Answer: ✅ C**
- **Explanation**: The Method Area (historically PermGen, now Metaspace) stores class-level data, constants, static variables, and method codes.
