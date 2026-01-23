# CLR, JIT & Execution Flow

## Level

Beginner

## Priority

🟥 Must Know  
🔥 Frequently Asked

## What happens from .cs file to execution

- Source code (.cs) is compiled by the C# compiler into Intermediate Language (IL).
- IL is stored in an assembly (DLL or EXE).
- At runtime, the CLR loads the assembly.
- The JIT compiler translates IL to native machine code as methods are called.
- Native code is executed by the CPU.

## Role of the CLR

- Manages memory allocation and garbage collection
- Enforces type safety
- Handles exceptions
- Provides security boundaries
- Manages threads and execution context

## What is IL and why it exists

- IL (Intermediate Language) is a CPU-independent set of instructions
- Enables cross-platform execution and runtime optimizations

## JIT compilation explained

- JIT (Just-In-Time) compilation happens when a method is called for the first time
- Compiles IL to native code at method level, not entire assembly at startup
- Allows runtime optimizations based on actual execution

## Managed vs unmanaged code

- Managed code runs under CLR control (memory, safety, exceptions)
- Unmanaged code runs directly on the OS without CLR services

## Common interview questions from this topic

- What is the CLR?
- What is IL?
- What is JIT compilation?
- What happens when you run a .NET application?
- Difference between managed and unmanaged code?

## Common misconceptions

- JIT compiles the whole assembly at startup (it does not)
- IL is the same as machine code (it is not)
- CLR is only for memory management (it does more)

## Summary

- C# code is compiled to IL, then JIT-compiled to native code at runtime
- CLR manages execution, memory, and safety
- IL enables portability and runtime optimization
- JIT compiles methods as needed, not all at once
- Managed code benefits from CLR services
- Understanding execution flow is critical for interviews
- Many interview questions focus on these fundamentals
