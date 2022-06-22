# OS Process Management

*[:arrow_left: Go back](../GENERAL.md)*

## What is a process management?

Integral way to manage processes.
Every process needs to be executed, provided with resources and synchronized with others processes, so all this tasks are handle by OS and can be categorized by the following main task: 

- creation: provide resources and memory to create the process 
- scheduling: Scheduled process by priority and handles queues of processes
- termination: terminate the process and release the resources and memory used by the process
- deadlock: Handle synchronization between processed to access shared resources.


## What is a process?

In general terms, a process is a program in execution. So it is an instance of program and contains some sections that allows the process to be executed.

Process sections:

- Stack: Memory used for static and temporary purpose by a process, it has fixed size
- Heap: Memory used for dynamic usage by the process execution, size is larger that stack
- Data: Global and static variables
- Text: Instructions for the process to execute.

Every process is handle by a data structure call PCB that identify every process uniquely.

## Process Control Block (PCB)

PCB is how a process is represented in the OS, it contains all the information required to keep track of all processes. Information such as:

- Process State
- Process ID (PID)
- Program Counter
- Memory Management Information
- etc...