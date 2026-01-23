# Senior Interview Questions — CLR, JIT & Execution

---

**Why does .NET use JIT instead of pure AOT?**

- 🟥 Must Know
- Expected depth: Understand trade-offs, runtime optimization, platform independence
- Typical follow-ups: When is AOT better? What are the downsides of JIT?
- Red flags: Only mentions performance, ignores portability or runtime features

---

**How does JIT impact cold-start performance?**

- 🟥 Must Know
- Expected depth: Explain method-level compilation, startup delays, mitigation strategies
- Typical follow-ups: How does ReadyToRun help? What about tiered compilation?
- Red flags: No mention of method-level, assumes JIT is always slow

---

**How does ReadyToRun change execution?**

- 🟨 Should Know
- Expected depth: Precompilation, impact on startup, trade-offs
- Typical follow-ups: When is it used? What are the limitations?
- Red flags: Thinks it's the same as JIT, can't explain trade-offs

---

**Can multiple .NET apps share the CLR?**

- 🟩 Nice to Know
- Expected depth: AppDomain, process isolation, .NET Core vs Framework
- Typical follow-ups: How did this work in .NET Framework? What changed in .NET Core?
- Red flags: Assumes all apps share the same runtime

---

**What is tiered compilation in .NET?**

- 🟨 Should Know
- Expected depth: Explain what it is, why it exists, performance impact
- Typical follow-ups: How does it differ from classic JIT? When is it used?
- Red flags: Can't describe multiple compilation stages

---

**How does the CLR enforce type safety?**

- 🟥 Must Know
- Expected depth: Metadata, verification, runtime checks
- Typical follow-ups: What happens if type safety is violated? How does this differ from C++?
- Red flags: Only mentions compile-time checks

---

**What happens if JIT compilation fails?**

- 🟨 Should Know
- Expected depth: Exception thrown, process termination, error handling
- Typical follow-ups: Can you recover? What causes JIT failures?
- Red flags: Thinks app continues running

---

**How does the CLR manage exceptions across managed/unmanaged boundaries?**

- 🟩 Nice to Know
- Expected depth: Exception marshaling, limitations, best practices
- Typical follow-ups: What are the risks? How to handle?
- Red flags: No awareness of boundary issues

---

**What is the difference between NGEN and JIT?**

- 🟨 Should Know
- Expected depth: Precompilation vs runtime compilation, pros/cons
- Typical follow-ups: Why is NGEN less common now? What replaced it?
- Red flags: Thinks NGEN is still default

---

**How does the CLR provide security for managed code?**

- 🟨 Should Know
- Expected depth: Code access security, sandboxing, verification
- Typical follow-ups: How is this different in .NET Core?
- Red flags: Only mentions OS-level security

---

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

**How does parameter passing differ for value and reference types?**

- 🟨 Should Know
- Expected depth: Value copy vs reference copy, ref/out semantics
- Typical follow-ups: How to force pass by reference? What are the risks?
- Red flags: "No difference"

---

**What is the impact of large object heap (LOH) allocations?**

- 🟩 Nice to Know
- Expected depth: Special GC treatment, fragmentation, performance
- Typical follow-ups: What size triggers LOH? How to avoid LOH issues?
- Red flags: "LOH is just like normal heap"

---

**Why does .NET use generational GC?**

- 🟥 Must Know
- Expected depth: Understands object lifetime patterns, collection efficiency
- Follow-up questions: How do generations reduce pause times? What if all objects lived long?
- Red flags: "Just for performance"; can't explain short-lived vs long-lived objects

---

**What causes GC pauses?**

- 🟥 Must Know
- Expected depth: Mark/sweep, root scanning, large object graph
- Follow-up questions: How to minimize pauses? What is concurrent GC?
- Red flags: "GC never pauses"; can't describe root scanning

---

**Why is LOH fragmentation dangerous?**

- 🟨 Should Know
- Expected depth: Allocation failures, no compaction, memory waste
- Follow-up questions: How to avoid LOH fragmentation? What is the impact on uptime?
- Red flags: "LOH is always compacted"; doesn't know about fragmentation

---

**When are objects promoted to higher generations?**

- 🟨 Should Know
- Expected depth: Survive collection, promotion rules
- Follow-up questions: What triggers promotion? Why not keep everything in Gen 0?
- Red flags: "Promotion is manual"; can't explain survivor concept

---

**How does memory pressure affect GC?**

- 🟨 Should Know
- Expected depth: More frequent collections, possible full GCs
- Follow-up questions: What causes memory pressure? How to monitor?
- Red flags: "GC always runs on schedule"; can't define memory pressure

---

**When would Server GC be preferred?**

- 🟨 Should Know
- Expected depth: High-throughput, multi-core, web servers
- Follow-up questions: How does Server GC differ from Workstation GC? What are the trade-offs?
- Red flags: "Server GC is always better"; can't explain config

---

**Why are finalizers discouraged?**

- 🟨 Should Know
- Expected depth: Delays, overhead, non-determinism
- Follow-up questions: When are finalizers necessary? How to avoid them?
- Red flags: "Finalizers are always needed"; can't explain cost

---

**Why is GC.Collect() considered harmful?**

- 🟨 Should Know
- Expected depth: Application pause, blocking, misuse
- Follow-up questions: When is it ever justified? What are alternatives?
- Red flags: "GC.Collect() is always safe"; can't explain blocking

---

**How does the GC identify unreachable objects?**

- 🟨 Should Know
- Expected depth: Root reference graph, mark/sweep
- Follow-up questions: What are roots? How does GC traverse?
- Red flags: "GC just guesses"; can't define roots

---

**What is the impact of finalization on GC performance?**

- 🟩 Nice to Know
- Expected depth: Delayed reclamation, finalizer queue
- Follow-up questions: How to suppress finalization? What is Dispose pattern?
- Red flags: "No impact"; can't explain finalizer queue
