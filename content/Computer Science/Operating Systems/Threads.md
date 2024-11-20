![[threads_concepts.excalidraw]]

Threads are fundamental **units** of CPU utilization
![[process-vs-threads.excalidraw]]

They consist of:
- PC
- Stack
- Set of registers
- Thread ID (**TID**)

Processes have a single thread
Multithreaded processes have multiple threads

Why?
- **Responsive** - threads are not blocked by other threads that take longer
- **Resource Sharing** - creating and managing single address space threads is faster for processes
- **Scalability** - utilization of multiproessor architecture

Challenges:
- **Dividing activity**
- **Balance** - not wasting threads on trivial tasks
- **Data Splitting** - stop threads from interfering
- **Data Dependency** - if one task depends on result of another $\rightarrow$ task needs to be synchronized
- **Testing + Debugging** - harder due to race conditions

Threads can either be:
- User-level
- Kernel-level

## Multithreading Models
![[threading-models.excalidraw]]

Multithreading Models:
- [[#Many-to-one]]
- [[#One-to-one]]
- [[#Many-to-many]]
- [[#Two level]]

### Many-to-one
many user-level threads mapped to one kernel thread:
- efficient
- entire process blocks if blocking system call occurs
- does not allow process to be split across CPUs

![[many-to-one.excalidraw|200]]

### One-to-one
- Each user thread maps to kernel thread
- Not blocked by system call
- More overhead, slow system

![[one-to-one.excalidraw|200]]



### Many-to-many
many user-level threads mapped to many kernel threads
- no limit to number of threads

![[many-to-many-model.excalidraw|200]]

### Two-level
[[#Many-to-one]] + Kernel threads
![[two-level.excalidraw]]

## Thread Cancellation
Asynchronous
- Immediate
Deferred
- Peridically checks if should be cancelled according to flag

## Signal Handling

Deliver signal to thread which it applies
Delivers to every thread
ceertain threads in process
specific thread receiving all signals of process

## Thread pools:
- pool of threads where they await
- number of threads bound to size of pool
- slightly faster

