# Beginner Interview Questions — CLR, JIT & Execution

---

**What is the CLR?**

- 🟥 Must Know
- Interviewer expects: Clear definition, role in execution, key responsibilities
- Common wrong answers: "It's just for garbage collection"; "It's the compiler"

---

**What happens when we run a .NET application?**

- 🟥 Must Know
- Interviewer expects: Step-by-step from source to execution
- Common wrong answers: Skipping IL/JIT, confusing compile/run phases

---

**What is IL?**

- 🟥 Must Know
- Interviewer expects: What IL is, why it exists, how it fits in .NET
- Common wrong answers: "It's machine code"; "It's C# code"

---

**What is JIT?**

- 🟥 Must Know
- Interviewer expects: When JIT happens, what it does, why it's used
- Common wrong answers: "JIT runs at compile time"; "JIT is always slow"

---

**What is managed code?**

- 🟨 Should Know
- Interviewer expects: CLR control, memory, safety
- Common wrong answers: "It's just C# code"; "It's code with no bugs"

---

**What is unmanaged code?**

- 🟨 Should Know
- Interviewer expects: No CLR, direct OS interaction
- Common wrong answers: "It's code that can't run in .NET"

---

**Why does .NET use IL instead of compiling directly to machine code?**

- 🟨 Should Know
- Interviewer expects: Portability, runtime optimization
- Common wrong answers: "To make it slower"; "No reason"

---

**Does JIT compile the whole assembly at startup?**

- 🟥 Must Know
- Interviewer expects: Method-level, on-demand compilation
- Common wrong answers: "Yes, everything is compiled at once"

---

**What is the difference between CLR and JIT?**

- 🟥 Must Know
- Interviewer expects: CLR is the runtime, JIT is the compiler
- Common wrong answers: "They are the same thing"

---

**What is an assembly in .NET?**

- 🟨 Should Know
- Interviewer expects: Definition, role, relation to IL
- Common wrong answers: "It's just a DLL"; "It's the source code"

---

**What is stack memory?**

- 🟥 Must Know
- Interviewer expects: Understands method call frames, local variable storage, lifetime
- Common wrong answers: "It's just for value types"; "It's the same as heap"

---

**What is heap memory?**

- 🟥 Must Know
- Interviewer expects: Knows object allocation, reference storage, GC involvement
- Common wrong answers: "Everything is on heap"; "Heap is always slow"

---

**Difference between value and reference types?**

- 🟥 Must Know
- Interviewer expects: Copy behavior, memory location, assignment semantics
- Common wrong answers: "Value types are always on stack"; "Reference types are always passed by reference"

---

**What happens when a method exits?**

- 🟨 Should Know
- Interviewer expects: Stack frame cleanup, local variable lifetime ends
- Common wrong answers: "Heap objects are deleted"; "Nothing happens"

---

**What is boxing?**

- 🟨 Should Know
- Interviewer expects: Value type to object conversion, heap allocation
- Common wrong answers: "It's just casting"; "No performance impact"

---

**What is unboxing?**

- 🟨 Should Know
- Interviewer expects: Extracting value type from object, type safety
- Common wrong answers: "It's automatic"; "No risk of exceptions"

---

**Why are strings immutable?**

- 🟨 Should Know
- Interviewer expects: Thread safety, pooling, memory efficiency
- Common wrong answers: "Just for safety"; "No reason"

---

**What is the impact of boxing on performance?**

- 🟨 Should Know
- Interviewer expects: Heap allocation, GC pressure, avoid in hot paths
- Common wrong answers: "No impact"; "Boxing is always fast"

---

**Can value types be stored on the heap?**

- 🟨 Should Know
- Interviewer expects: Yes, inside objects or arrays
- Common wrong answers: "Never"; "Only on stack"

---

**What is the conceptual memory layout for a reference type variable?**

- 🟨 Should Know
- Interviewer expects: Reference on stack, object on heap
- Common wrong answers: "Everything is on heap"; "Reference types are copied by value"

---

**What is garbage collection?**

- 🟥 Must Know
- Interviewer expects: Understands automatic memory management, reclaiming unused objects
- Common wrong answers: "GC deletes objects immediately"; "GC is manual in .NET"

---

**What are GC generations?**

- 🟥 Must Know
- Interviewer expects: Knows Gen 0, 1, 2, why generations exist
- Common wrong answers: "All objects are collected the same way"; "Generations don't matter"

---

**What is Gen 0, Gen 1, and Gen 2?**

- 🟥 Must Know
- Interviewer expects: Can describe each generation's purpose and collection frequency
- Common wrong answers: "They're just memory regions"; "All objects start in Gen 2"

---

**What is the Large Object Heap (LOH)?**

- 🟨 Should Know
- Interviewer expects: Knows size threshold, fragmentation, collection with Gen 2
- Common wrong answers: "LOH is always compacted"; "LOH is for all objects"

---

**When does GC run?**

- 🟨 Should Know
- Interviewer expects: Allocation pressure, Gen 0 full, explicit calls, OS memory pressure
- Common wrong answers: "Only when memory is full"; "On a fixed schedule"

---

**What is IDisposable?**

- 🟨 Should Know
- Interviewer expects: Deterministic cleanup, unmanaged resources
- Common wrong answers: "It frees managed memory"; "It's the same as Finalize"

---

**Difference between Dispose and Finalize?**

- 🟨 Should Know
- Interviewer expects: Dispose is explicit, Finalize is automatic, timing differences
- Common wrong answers: "They are the same"; "Dispose is called by GC"

---

**Why is GC.Collect() discouraged?**

- 🟨 Should Know
- Interviewer expects: Performance impact, blocking, not for normal use
- Common wrong answers: "It's always safe"; "It improves performance"

---

**What is object promotion in GC?**

- 🟨 Should Know
- Interviewer expects: Surviving objects move to higher generations
- Common wrong answers: "Objects are always collected in Gen 0"; "Promotion is manual"

---

**What is a finalizer and when does it run?**

- 🟨 Should Know
- Interviewer expects: Cleanup before reclaim, runs after unreachable, not deterministic
- Common wrong answers: "Runs immediately"; "Always needed for cleanup"
