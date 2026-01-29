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
