# C# Memory Model — Stack vs Heap

## Level

Beginner

## Priority

🟥 Must Know  
🔥 Frequently Asked

---

## Why memory model matters in interviews

- Directly impacts performance and scalability
- Explains object lifetime and GC behavior
- Prevents subtle bugs related to copying and mutation
- Frequently tested to validate real-world understanding

---

## Stack memory

- Stack is a region of memory used for **method call frames**
- Each method invocation creates a new stack frame
- Stack frame contains:
  - local variables
  - method parameters
  - references to heap objects
- Memory is automatically released when the method exits
- Allocation is extremely fast (simple pointer movement)

---

## Heap memory

- Heap stores **objects and reference-type data**
- Objects are allocated on the heap and accessed via references
- Object lifetime is managed by the garbage collector
- Heap allocation involves:
  - memory reservation
  - object tracking
  - GC bookkeeping
- Slower than stack allocation but necessary for shared lifetime objects

---

## Value types vs reference types

- **Value types** (`struct`, `int`, `bool`):
  - Stored directly in their containing context
  - Copied on assignment and parameter passing
  - Can live on stack or heap depending on usage

- **Reference types** (`class`, `array`, `string`):
  - Object data lives on the heap
  - Variables store only a reference (pointer)
  - Assignment copies the reference, not the object

---

## Boxing and unboxing

- **Boxing**
  - Converts value type into object
  - Allocates memory on heap
  - Creates additional GC pressure

- **Unboxing**
  - Extracts value type from object
  - Requires type safety checks

- Boxing commonly occurs when:
  - value types are treated as `object`
  - interfaces are used

---

## String immutability

- Strings are immutable by design
- Any modification creates a new string object
- Benefits:
  - thread safety
  - safe sharing
  - string interning (pooling)
- Immutability avoids unexpected side effects

---

## Common interview questions from this topic

- What is stack memory?
- What is heap memory?
- Difference between value and reference types?
- What is boxing and unboxing?
- Why are strings immutable?

---

## Common misconceptions

- ❌ Structs always live on stack  
  ✅ Structs live where they are embedded

- ❌ Reference types are stored entirely on heap  
  ✅ Object is on heap; reference lives in stack or object

- ❌ Reference types are passed by reference  
  ✅ Reference is passed by value unless `ref` is used

---

## Summary

- Stack holds method frames and references
- Heap stores objects and shared data
- Value types are copied; reference types copy references
- Boxing allocates on heap and impacts performance
- Strings are immutable and interned
- Incorrect memory assumptions cause real production bugs
- Interviewers use this topic to assess runtime understanding
