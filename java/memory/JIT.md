# Just in Time (JIT) Compiler

## JIT

Is a process that the JVM execute to translate java bytecode into binary code. This process is called Just in Time, because it is executed in runtime.

## Java Program Compilation

All Java Applications are compiled, this means that Java code is translated to a language that CPU can execute. In java, code compilation occurs in two languages level. The java bytecode and binary code.

### Bytecode compilation
The first compilation takes the java code translate it into java bytecode, this is an intermediate representation and implies that this code needs to be interpreted by the JVM instead of been executed directly. This enables the Platform-Independence that allows that java programs can be executed on any device with a JVM. "Write once, run everywhere"

### Binary compilation
The second compilation takes the java bytecode translate it to binary code. This code is compiled through JIT compilation. Binary code is executed directly by the CPU it means that is faster than bytecode execution. 

## JIT Advantages

Compiling Java code into binary code offers some advantages and optimizations.

- Performance: Binary code is faster than bytecode, reducing the overhead of interpretation.
- Runtime adaptability: Compiler can make decisions about which part of code is frequently executed (hot) and apply optimizations.
- Footprint reduction: Compiler can reduce the amount of code compiled, this means that binary code will be smaller because only the frequently executed code will be compiled.
- Hardware Adaptation: Compiler can the advantage of specific hardware features by performing optimizations focus on current hardware.
- Hotspot detection and Profiling: Compiler allows to identify hotspot in the code by focusing on optimizing frequently executed code.


## JIT Optimizations

Some optimizations that a compiler execute are the following:

- Inlining: Reduces the overhead of function calls
- Constant Folding: Reduces the overhead of compute constant expressions
- Register Allocations: Allocates variable into CPU registers to minimize memory access.
- Escape Analysis: Determines if objects can be allocated on the stack rather than the heap.
- Dead Code elimination: Identifies and remove code tht is guaranteed not to be executed. Reducing code size.

## Code Cache

It is a dedicated area of memory used by the JVM to store to code compiled by the JIT compiler. This are is size fixed this means that if code cache area is full, the performance may be affected because some code may not be compiled and optimized.


## Compilation Flavors

Java has some modes to compile code, those are:

- Client
- Server
- Tiered Compilation

### Client

Client compiler also known as C1 compiler focuses on compiling code on startup using a method-at-a-time compilation strategy. This strategy takes de java bytecode and compiles it to native code as they are executed. This improves code performance at the beginning of the application execution but does not performs advanced optimizations.

### Server

Server compiler also known as C2 compiler, is a compiler that focuses on optimizing the performance of native code. C2 compiler has some characteristics to achieve better performance.

- Optimizations: C2 compiler performs more aggressive optimizations compared to C1 compiler.
- Whole-Method compilation: C2 compiler analyzes the entire method and also the relationship between different parts of code, this allows to optimize methods beyond its boundaries.
- Dynamic Compilation: C2 compiler operates dynamically during program execution, optimizing code based on profiling information like hotstop detection.
- Trade-off: C2 compiler focuses on long-running applications, this implies that performance on startup is worse thant C1 compiler, because the optimizations performed by C2 compiler requires more information, like hotspot, runtime conditions, etc.

### Tiered Compilation

This compilation uses a strategy to balance the trade-off between startup and long-term performance. This compilations uses the C1 and C2 compilers to provide this balance.

Following are some steps of how tiered compilation works:
1. Level 1 Compilation:  At initial stages of program execution, the JVM uses a C1 compiler, to take advantage of faster startup.
2. Execution and profiling: As the application runs, the JVM collects information to detect methods that area frequently executed (HotSpot)
3. Level 2 Compilation: Methods identified as HotStop may be subject to recompilation by the C2 compiler. This allows to increase performance by performing optimizations.

#### Levels

There are five different levels of compilation

- Level 0 - Interpreted Code: In this level JVM interprets the java bytecode it means performance is not good compared to compiled code.
- Level 1 - Simple C1 Compiled Code: In this level JVM uses a C1 compiler, compiling methods that are considered trivial. 
- Level 2 - Limited C2 Compiled Code: In this level JVM uses a C1 compiler with light profiling information that allows to generate more optimized code.
-  Level 3 - Full C1 Compiled Code: In this level JVM uses a C1 compiler with full profiling information, generating even more optimized code.
- Level 4 - C2 Compiled Code: In this level JVM uses a C2 compiler to apply advanced optimizations while the application is running. This is where code is considered fully optimized. 
