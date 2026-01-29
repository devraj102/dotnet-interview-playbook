# Garbage Collection (GC) in .NET

---

**Level:** Intermediate  
**Priority:** 🟥 Must Know  
**Interview Frequency:** 🔥 Frequently Asked

---

## What is Garbage Collection (GC)?

- GC is a background, non-deterministic process that automatically cleans unreferenced managed objects from memory.

## How GC Works Internally

- Objects are allocated on the Heap and referenced from the Stack.
- When objects go out of scope and lose all stack references, GC eventually reclaims them.

## Managed vs Unmanaged Memory

- **Managed resources:** Created and controlled by the CLR (GC can clean them).
- **Unmanaged resources:** File handles, database connections, COM objects, native memory (GC cannot clean them automatically).

## GC Generations (GC0, GC1, GC2)

- **GC0:** Short-lived objects
- **GC1:** Intermediate buffer
- **GC2:** Long-lived objects
- Generations exist to improve performance by avoiding repeated scans of long-lived objects.

## Performance Monitoring & Profiling

- Analyze GC behavior using:
  - Performance Counters
  - Visual Studio Performance Profiler
  - GC Heap Size, Working Set, Object Allocation Tracking

## Primitive Types & GC

- Value types (int, double, etc.) are allocated on the stack and are not cleaned by GC.

## Destructors, Finalize, and GC Behavior

- Objects with destructors take longer to be collected, often requiring multiple GC cycles.

## IDisposable Pattern & Best Practices

- Use IDisposable and GC.SuppressFinalize() to improve GC performance
- Avoid empty destructors
- Use the using statement to ensure deterministic cleanup of unmanaged resources

## Forcing GC Execution

- GC.Collect() exists but is not recommended in real-world applications.

## Memory Leaks in .NET

- GC prevents leaks in managed memory, but unmanaged memory leaks are still possible if resources are not properly released.

## Detecting Memory Issues

- Memory leaks are identified through:
  - Linear growth in total memory
  - Objects allocated but never deallocated
  - Profiling allocation hot spots

## Strong vs Weak References

- **Strong reference:** Prevents GC collection
- **Weak reference:** Allows GC collection while still permitting temporary access
- Commonly used in caching and object pooling scenarios
