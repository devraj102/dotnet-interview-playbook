# C# Memory Model — Stack vs Heap

## Level

Beginner

## Priority

🟥 Must Know  
🔥 Frequently Asked

## Why memory model matters in interviews

- Directly impacts performance and bug risk
- Explains why some code is fast and some is slow
- Underpins reference semantics and object lifetime
- Many production bugs stem from misunderstanding value vs reference types

## Stack memory

- Stack is a region of memory for method call frames
- Stores local variables and value types
- Each method call gets its own stack frame
- Data is automatically cleaned up when method exits
- Stack allocation is fast due to simple pointer movement

## Heap memory

- Heap is used for objects and reference types
- Objects are allocated on the heap and referenced by pointers
- Lifetime is managed by the garbage collector
- Heap allocation is slower than stack due to bookkeeping

## Value types vs Reference types

- Value types (structs, int, bool) are stored directly in their context (stack or inside objects)
- Reference types (class, string, array) are stored on the heap, variables hold references
- Value types are copied on assignment; reference types copy the reference
- Passing value types copies the value; passing reference types copies the reference
- Conceptual layout:

  Stack: [int x] [struct s] [ref -> Heap]
  Heap: [object data]

## Boxing and unboxing

- Boxing: Value type is wrapped into an object and moved to heap
- Unboxing: Extracting value type from object
- Boxing happens when value type is used as object/interface
- Causes heap allocation and performance hit

## String immutability

- Strings are immutable for safety and performance
- Any change creates a new string object
- Immutability enables string interning (pooling)
- Thread-safe by design

## Common interview questions from this topic

- What is stack memory?
- What is heap memory?
- Difference between value and reference types?
- What is boxing and unboxing?
- Why are strings immutable?

## Common misconceptions

- “Structs always live on stack” (they can be on heap inside objects)
- “Reference types are stored entirely on heap” (reference itself is on stack or in object)
- “Passing reference types means pass by reference” (it’s pass by value of the reference)

## Summary

- Stack: fast, method-local, value types
- Heap: objects, managed by GC, reference types
- Value types: copied, stored directly
- Reference types: referenced, stored on heap
- Boxing moves value types to heap
- Strings are immutable and pooled
- Misunderstanding memory model leads to real bugs
- Interviewers test this to check for real-world readiness
