# .NET Garbage Collection

## Level

Beginner

## Priority

🟥 Must Know  
🔥 Frequently Asked

## Why GC matters in real applications

- Directly impacts application performance and latency
- GC pauses can cause unpredictable response times
- Memory pressure can trigger frequent collections
- Balancing throughput and responsiveness is critical in production

## What problem GC solves

- Eliminates manual memory management errors (leaks, double free)
- Simplifies object lifetime management
- Ensures memory safety by reclaiming unreachable objects

## How GC works (high level)

- Objects are allocated on the managed heap
- GC tracks root references (stack, static fields, CPU registers)
- Builds a reachability graph to find live objects
- Mark and sweep: marks reachable, sweeps unreachable

## Generational GC model

- Three generations: Gen 0 (youngest), Gen 1 (short-lived survivors), Gen 2 (long-lived)
- Most objects die young, so Gen 0 is collected most often
- Generations reduce the cost of frequent collections

## Object promotion

- Surviving objects in Gen 0 are promoted to Gen 1, then Gen 2
- Promotion happens after surviving a collection
- Long-lived objects end up in Gen 2

## Large Object Heap (LOH)

- Objects > 85,000 bytes are allocated on LOH
- LOH is not compacted by default, leading to fragmentation
- LOH is collected with Gen 2
- Fragmentation can cause allocation failures

## GC triggers

- Allocation pressure (insufficient free memory)
- Gen 0 fills up
- Explicit call to GC.Collect()
- OS signals low memory

## GC modes

- Workstation GC: optimized for desktop, low-latency
- Server GC: optimized for throughput, multi-core servers
- Mode is chosen based on application type and config

## Finalization

- Objects with finalizers are placed in a special queue
- Finalizers run after object is unreachable, before memory is reclaimed
- Finalizers delay memory reclamation and add overhead

## IDisposable pattern

- Used for deterministic cleanup of unmanaged resources
- Dispose is called explicitly by code
- Finalize is a safety net, not a replacement
- GC.SuppressFinalize() prevents finalizer from running if Dispose was called

## Why GC.Collect() is dangerous

- Forces a full collection, causing application pause
- Can block all threads and degrade performance
- Should be avoided in production code

## Common interview questions from this topic

- What is garbage collection?
- What are GC generations?
- What is the LOH?
- When does GC run?
- What is IDisposable for?
- Difference between Dispose and Finalize?

## Common misconceptions

- "GC runs only when memory is full"
- "GC immediately frees memory"
- "Dispose releases managed memory"
- "Finalizers run as soon as object is unreachable"

## Summary

- GC automates memory management and prevents leaks
- Uses generations to optimize collection frequency
- LOH is for large objects and can fragment
- Finalizers are expensive and should be avoided
- IDisposable enables deterministic cleanup
- GC.Collect() should rarely be used
- Understanding GC is critical for backend interviews
- Many bugs and performance issues are GC-related
