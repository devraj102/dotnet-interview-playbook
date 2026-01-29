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

## Portability of IL and Platform Support

- IL is designed to be portable and CPU-independent, but it requires a compatible runtime (CLR/CoreCLR) to execute.
- **.NET Framework** (before .NET Core) only provided the CLR for Windows, so IL could not run natively on Linux or macOS.
- **.NET Core** and later (.NET 5+) introduced CoreCLR, a cross-platform runtime, enabling IL to be executed on Windows, Linux, and macOS.
- Portability of IL means the same compiled code can run anywhere a compatible runtime exists, not everywhere by default.

## Common interview question: If IL is portable, why was .NET Framework Windows-only?

- IL is portable, but the runtime (CLR) was not. Only with .NET Core/CoreCLR did Microsoft provide official cross-platform support.

**Follow-up:**

- What is required to run IL code on a different OS?
- What changed with .NET Core and ASP.NET Core?

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
- What happens internally from a .cs file to execution on the CPU?
- Why does .NET compile to IL instead of compiling directly to machine code?

## Common misconceptions

- JIT compiles the whole assembly at startup (it does not)
- IL is the same as machine code (it is not)
- CLR is only for memory management (it does more)
- IL is portable everywhere by default (it is only portable where a compatible runtime exists)

## Summary

- C# code is compiled to IL, then JIT-compiled to native code at runtime
- CLR manages execution, memory, and safety
- IL enables portability and runtime optimization
- JIT compiles methods as needed, not all at once
- Managed code benefits from CLR services
- Understanding execution flow is critical for interviews
- Many interview questions focus on these fundamentals

## Sample Q & A

<details>
<summary><strong>What happens internally from a .cs file to execution on the CPU?</strong></summary>

<ul>
	<li>When we write C# code, it’s saved as .cs source files.</li>
	<li>During build, the C# compiler (csc) compiles these files into an assembly — either a .dll or .exe.</li>
	<li>This assembly contains Intermediate Language (IL), metadata about types, methods, references, and a manifest describing dependencies.</li>
	<li>When the application starts, the CLR loads the assembly, verifies the IL, and prepares the runtime environment.</li>
	<li>Execution begins from the entry point (Main method).</li>
	<li>The CLR does not compile the entire application upfront. Instead, when a method is called for the first time, the JIT compiler converts that method’s IL into native machine code specific to the current CPU.</li>
	<li>The compiled native code is stored in memory so subsequent calls reuse it.</li>
	<li>As more methods are invoked, they are JIT-compiled individually and executed directly by the CPU.</li>
	<li>The CLR continues managing memory, exceptions, garbage collection, and threading during execution.</li>
</ul>
</details>

<details>
<summary><strong>Why does .NET compile to IL instead of compiling directly to machine code?</strong></summary>

<ol>
	<li><strong>Platform independence:</strong> IL is CPU-agnostic. The same compiled assembly can run on different architectures (x64, ARM) or operating systems. The JIT compiler generates machine code optimized for the current CPU.</li>
	<li><strong>Runtime optimization:</strong> Because compilation happens at runtime, the JIT can optimize code based on CPU features, instruction sets, and runtime profiling. These optimizations are not possible at compile time.</li>
	<li><strong>Faster startup and efficient memory usage:</strong> JIT compiles methods only when they are actually executed, avoiding compilation of unused code and reducing startup cost and memory consumption.</li>
</ol>
</details>
