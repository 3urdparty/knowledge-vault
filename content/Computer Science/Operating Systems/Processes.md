![[processes-overview.excalidraw|600]]
Processes are programs in **execution** (by CPU, in sequential fashion). They are different from [[Threads|threads]].

Processes can:
- be [[#Creation|created]]
- be [[#Scheduling|scheduled]]
- be [[#Termination|terminated]]
- [[#Commincation|communicate]] with each other

Processes can be [[#Batch|batch]] or [[#Time-Sharing|time-shared]]

![[process.excalidraw]]

**Stack** - stores local variables. Variables are pushed at the start of scope and popped off at end:
```c++
int test(){ \\ <---- start of scope
   int var = 0; \\ <---- Local variable pushed to stack
} \\ <----- Local variable pushed to stack at end of scope
```
**Heap** - dynamic memory allocation. They are managed via calls to `new` , `delete` , `malloc`, `free`
**Data** - global/static variables, initialized before `main`
**Text** - compiled program, loaded from Non-volatile Storage (**NVS**)


# Operations
## Creation
### Child Processes
Processes can [[#Forking|fork]] or [[#Spawning|spawn]] child processes. There are many concerns when it comes to child processes:
- Resource Sharing

#### Resource Sharing
3 Approaches:
1. Parent and children share **all** resources
2. Chidren share **subset** of parents resources
3. Parent and Child share **no** resource

![[resource-sharing.excalidraw|500]]

#### Execution Type
Parent and children execute concurrently
Parent awaits until child terminates (asynchronously)
![[forking.excalidraw]]
#### Address Space
- child duplicate of parent
- child ha a program loaded

## Scheduling
### States
Process can be in any of 5 states:
1. **new** - created
2. **ready** - waiting to be assigned to processor
3. **running** - executing in processor
4. **waiting** - waiting for I/O, [[#IPC]] message, timer or [[#Child Processes|child process]] to finish
5. **terminated** - finished or killed
### Queues
A device can either be I/O bound or CPU bound
**CPU** bound - few long CPU bursts
**I/O** bound - many short CPU bursts
![[cpu-bound-vs-io-bound.excalidraw|300]]

An efficient scheduling system will select a mix of both

**ready** queue - in main memory, waiting for CPU
**device** queue - waiting for I/O

### Schedulers
![[process-state-cycle.excalidraw]]

3 types of schedulers:
- [[#Long-term Schedulers|long-term]] - controls degree of "multiprogramming", moves from memory to ready queue
- [[#Medium-term Schedulers|medium-term]] - swaps out running processes for others (due to [[Round Robic#Timeslice|timeslice]], [[Priority Scheduling#priority|priority]] or otherwise)
- [[#Short-term Schedulers|short-term]] - moves from ready queue to running

### Context Switching
![[context-switch.excalidraw|300]]

### PCB
![[pcb.excalidraw|200]]


## Communication
### IPC
Processes can be:
1. Independent
2. Cooperating

- Information Sharing - access to same resources
- computation speedup - break down problem into subproblems $\rightarrow$ parallel computing
- modularity - efficient OS by breaking down into cooperation
- convenience - user running same process multiple times

Two methods of IPC:
- [[#Shared Memory|shared memory]]
- [[#Message Passing|message passing]]



| Shared Memory                          | Message Passing                                      |
| -------------------------------------- | ---------------------------------------------------- |
| + Faster                               | - system call every transfer $\rightarrow$ slower    |
| - Complicated to setup                 | - simpler to setup (even across different comptuers) |
| - Don't work across multiple computers | = for multiple comptuers / small, infrequent data    |
| = For Large amounts of data            |                                                      |
|                                        |                                                      |

![[in-memory-ipc.excalidraw|300]]
![[message-passing.excalidraw|300]]
#### Message Passing
Messages can be:
- **Blocking** (synchronous) - sender or receiver wait until message has been sent/received
- **Non-blocking** (asynchronous) - sender will send message and continue/receiver receives valid message or null
#### Shared Memory


## Termination
Two methods:
1. Process requests OS to delete it -> output data from child to parent -> process deallocated by OS
2. Parent terminates child (abort), can happen for many reasons:
	1. Child exceeded allocated resource
	2. task assigned no longer needed
	3. parent exiting

Cascading termination - all children terminate