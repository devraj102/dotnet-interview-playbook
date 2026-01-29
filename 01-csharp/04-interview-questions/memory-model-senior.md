**Are structs always allocated on stack?**

- 🟥 Must Know
- Expected depth: Understands context-based allocation, heap inside objects/arrays
- Typical follow-ups: When does a struct end up on heap? How does this affect performance?
- Red flags: "Structs are always on stack"

---

**Why can large structs hurt performance?**

- 🟨 Should Know
- Expected depth: Copy cost, method parameter passing, cache impact
- Typical follow-ups: When to use class instead? How to optimize?
- Red flags: Ignores copy semantics

---

**What exactly is stored on stack for reference types?**

- 🟥 Must Know
- Expected depth: Reference/pointer only, not the object
- Typical follow-ups: What about arrays? What about nested objects?
- Red flags: "Object is on stack"

---

**How does passing reference types actually work?**

- 🟥 Must Know
- Expected depth: Pass by value of reference, not by reference to object
- Typical follow-ups: How to pass by reference? What changes with ref/out?
- Red flags: "Objects are passed by reference by default"

---

**How does memory pressure affect GC?**

- 🟨 Should Know
- Expected depth: More allocations, more frequent collections, performance impact
- Typical follow-ups: How to reduce memory pressure? What are common sources?
- Red flags: "GC always runs on schedule"

---

**What is the cost of boxing in high-throughput code?**

- 🟨 Should Know
- Expected depth: Heap allocation, GC, CPU cache
- Typical follow-ups: How to avoid boxing? When is it unavoidable?
- Red flags: "Boxing is free"

---

**How does string interning affect memory usage?**

- 🟩 Nice to Know
- Expected depth: String pool, deduplication, memory savings
- Typical follow-ups: When is interning automatic? How to use String.Intern?
- Red flags: "All strings are interned"

---

**What are the risks of mutable structs?**

- 🟨 Should Know
- Expected depth: Copy-on-assignment, unexpected behavior, bugs
- Typical follow-ups: When is it safe? Why are most structs immutable?
- Red flags: "Mutable structs are fine everywhere"

---
