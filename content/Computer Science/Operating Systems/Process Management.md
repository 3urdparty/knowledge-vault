# Process
Components of a process:
PC - store *memory*

OS uses many techniques to maximize utilization of the CPU

OS is responsible for:
- **Creating** and **deleting** both user and system processes
- **Suspending and Resuming** processes
- **Process Synchronization**
- **Deadlock Handling**


- [[#Multithreading]]
# Multithreading
![[Pasted image 20241115184619.png]]
![[Pasted image 20241115184717.png]]





## Interrupts
1. Interrupt recieved
2. Address for appropriate **ISR** found in **interrupt vector**
3. Save address of interrupted instruction and CPU state in **registers**
4. Incoming interrupts disabled whilst interrupt is being serviced (prevent **lost interrupt**)




## Processor
**Multiprocessors**:
- Increased throughput
- Economy of scale
- Increased reliability

Types of multiprocessing:
1. Asymmetric Multiprocessing
2. Symmetric Multiprocessing

### Symmetric Multiprocessing Architecture
A multiprocessor system where multiple processors share a single main memory and have equal access to all I/O devices

- Processors run same operating system instance
- **peer-level** no master/slave

### Clustered Systems
- multiple computers sharing the same storage
- high-availability, survives system failures

Types:
- Asymmetric Clustering - one machine in hot-standby mode
- Symmetric Clustering - multiple nodes running applications, monitoring each other

OS Tasks:
[[Timesharing]]
[[CPU Scheduling]]
Process Swapping (RAM <-> Secondary Storage)
Virtual Memory



## I/O Structure
**Synchronous I/O** - control returns to user program AFTER I/O completion:
- CPU (using wait instruction) enters a wait loop until the next interrupt
- Only **1** I/O request can be accessed

