**OS** - intermediary between user and [[Computer Hardware]]
**Kernel** - program running at all times on the computer
**System Programs** - shipped with OS
**Application Programs** - installed by user
**Middleware** - software frameworks that provide essential services for application development not provided by OS (eg. [[ODBC]]). Sits between OS/Database and application
**Firmware** - Microcode embedded into hardware devices
**Concurrent Execution** - I/O devices and CPU can execute tasks simultaneously
**Device Controllers** - manages specific device and has a local buffer for temporary data storage
**I/O Process** - Input/Output operations occur between device and local buffer of its controller
**Process** - program loaded into memory and is executing

**BIOS program** (firmware) loaded at boot, typically stored in ROM/EPROM
- initializes system components (hardware checks)
- loads OS kernel into memory and starts execution

**Interrupts** - signal from hardware/software that notifies CPU and requests immediate action. 
OS is **interrupt driven** (respond to interrupts to manage tasks)
Interrupts transfer control to the appropriate **ISR** (found in the **Interrup Vector**, which holds addresses of all **ISR**s)


**trap/exception** - software generated interrupt (triggered by an error or user request)
**Main Memory** - large storage media that CPU an access directly
**Secondary Storage** - nonvolatile storage capacity
**Disk controller** manages logical interaction between storage device and computer

**Caching** - copying information into faster storage system to speed up access


**Asynchronous I/O** - Control returns after I/O starts without waiting for completion
**System call** - request to OS to allow user to wait for I/O completion if needed

**Device-status table** - contains entry for each I/O device with type, address and state