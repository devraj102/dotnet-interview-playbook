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
