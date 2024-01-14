# Stack

*[:arrow_left: Go back to Memory Management](./MEMORY_MANAGEMENT.md)*

The stack is a region of memory used for storing local variables and managing function calls in a program. It operates on a Last In, First Out (LIFO) basis, meaning that the last item added is the first one to be removed. Each thread in a Java program has its own stack.

## Contents of Stacks:

Stacks contain local variables, including primitive data types and references to objects, associated with a specific method or function call.
They also store control flow information, such as return addresses and function call instructions.

## Thread-Local:
Each thread in a Java program has its own stack. This is known as a thread's "call stack" or "execution stack."
The stack is used to manage the flow of control within the thread, keeping track of method calls, local variables, and other execution-related information.

## Relation with a Thread:
The stack is closely tied to a thread's execution. It represents the thread's current state and provides a space for storing data related to the methods that the thread is currently executing.
Multiple threads in a Java program each have their own separate stacks.

## No Garbage Collection (for Stack Frames):
The contents of the stack frames (local variables, control flow information) are managed explicitly and automatically by the stack mechanism.
There is no need for a garbage collection cycle for stack frames. When a method exits, its frame is popped off the stack, and the associated local variables are automatically discarded.

## Cleanup Process:
The cleanup process is associated with the automatic management of local variables when a method exits.
When a method completes its execution, its frame is popped off the stack, and the space allocated for its local variables is automatically reclaimed. This is part of the natural flow of control in the program.