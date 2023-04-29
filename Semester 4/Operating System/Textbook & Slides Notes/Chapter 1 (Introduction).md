# Chapter 1 : Introduction
## What is an Operating System?
- An **intermediary program** between
	- a user of a computer and
	- the computer hardware.
- **Goals:**
	- *Execute* user programs.
	- Make the computer system *convenient* to use.
	- Use the computer hardware *efficiently*.
- **Definition:**
	- OS is a *resource allocator*:
		- Manages all resources.
		- Decides between conflicting requests for efficient and for resource use.
	- OS is a *control program*:
		- Controls execution of programs to prevent errors and improper use of the computer.
## Computer System Structure:
### Hardware:
- Provides basic computing resources.
- CPU, memory, I/O devices.
### Operating System:
- Controls ad coordinates the use of hardware among various applications and users.
### Application Programs:
- Word processors, compilers, web browsers, database systems, video games.
### Users:
- People, machines, other computers
![[https---s3-us-west-2.amazonaws.com-secure.notion-static.com-72b11ae9-9738-4337-a877-51e2be38655b-Untitled.png]]

## Computer System Organization:
- #### Computer System Operations:
	- One or more CPUs, device controllers connected through a common bus providing access to shared memory.
	- Concurrent execution of CPUs and devices competing for memory cycles
	- ![[https---s3-us-west-2.amazonaws.com-secure.notion-static.com-b72a6486-e487-4cc8-b46f-6b7c871667f6-Untitled.png]]
- *I/O devices* and the *CPU* can *execute concurrently*.
- Each device controller is in charge of a particular device type.
- CPU moves data *from/to main memory to/from local buffers*
- I/O is from the device to local buffer of controller.
- Device controller informs CPU that it has finished its operation by causing an interrupt.
## Interrupts:
- How does the controller inform the device driver that it has finished its operation. This is accomplished via an *interrupt*.
- Hardware may *trigger* an interrupt at any time by sending a *signal* to the CPU, usually by way of the *system bus*.
- #### Functions of Interrupts:
	- The interrupt *transfers* *control* to the *interrupt service routine*, generally *through the interrupt vector*, which contains the addresses of all the service routines.
	- Interrupt architecture must *save* the *address* of the *interrupted instruction*.
	- Incoming interrupts are *disabled* while another interrupt is being processed to prevent a lost interrupt.
	- A ***trap*** is a software-generated interrupt caused either by an error or a user request.
- #### Interrupt Handling:
	- The operating system preserves the state of the CPU by storing registers and the program counter.
	- ***Interrupt Vector:*** holds the addresses of the interrupt service routines.
## Storage Structure:
- #### Direct Memory Access:
	- Used for *high-speed I/O devices* able to transmit information at close to memory speeds.
	- Device controller transfers blocks of data from buffer storage directly to main memory without CPU intervention.
	- Only one interrupt is generate per block, rather than one interrupt per byte.
- **Main Memory:** Only large storage media that the CPU can access directly.
- **Secondary Storage:** Extension of main memory provides large non-volatile storage capacity.
- Storage systems organized in hierarchy
	- Speed
	- Cost
	- Volatility
- #### Caching:
	- Performed at many levels in a computer.
		(in hardware, operating system, software)
	- Information in use copied from slower to faster storage temporarily.
	- Cache checked first to determine if information is there.
		- If it is, information used directly from the cache.
		- If not, data copied to cache and used there.
	- Cache smaller than storage being cached.
		- Cache management important design problem.
		- Cache size and replacement policy.
## Operating System Structure
- #### Multiprogramming
	- Needed for efficiency
	- Single user cannot keep CPU and I/O devices busy at all times.
	- Multiprogramming organizes jobs, so CPU always has one to execute.
	- A subset of total jobs in the system is kept in memory.
	- **How does it work?**
		- The operating system keeps several processes in memory simultaneously.
		- The operating system picks and begins to execute one of the processes.
		- Eventually, the process may have to wait for some task, such as an I/O operation to complete.
		- In a multi-programmed system the operating system simply switches to another process, and so on.
		- Eventually, the first process finishes waiting and gets the CPU back.
		- As long as at least one process needs to execute, the CPU is never idle.
- #### Multitasking (Time-sharing)
	- Logical extension in which CPU switches jobs, so frequently that users can interact with each job while it is running, creating **interactive** computing.
	- **Response time** should be < 1 second.
	- Each user has at least one program in memory→ process.
	- If several jobs are ready to run at the same time→ CPU Scheduling.
	- If processes don’t fit in memory, **swapping** moves them in and out to run.
	- **Virtual Memory** allows the execution of processes not completely in memory.
## Operating System Operations:
- Since the operating system and its users share the hardware and software resources of the computer system, a properly designed operating must ensure that an incorrect (or malicious) program cannot cause other programs - or the operating system itself - to execute incorrectly.
- In order to ensure that proper execution of the system, it must be able to distinguish between the execution of _operating-system code_ and _user-defined code_.
- #### Dual-Mode Operation:
	- **Dual-mode** operation allows OS to protect itself and other system components
    - **User mode** and **kernel mode**.
    - **Mode bit** added to the hardware of the computer to indicate the current mode:
        - kernel(0)
        - user(1)
    - Provides the ability to distinguish when the system is running user code or kernel code
    - Some instructions designated as **privileged,** only executable in kernel mode
    - System call changes the mode to the kernel, return from call rests it to the user.
    - ![[https---s3-us-west-2.amazonaws.com-secure.notion-static.com-cd805448-21e9-47d6-849b-d9602cd4cca6-Untitled.png| 450]]
## Resource Management:
- Operating System is a **resource manager**.
- ### Process Management:
	- A process is a program in execution. It is a unit of work within the system. Program is a **passive entity,** process is an **active entity.**
	- The process needs resources to accomplish its task
		- CPU, Memory, I/O, files
		- Initialization data
	- **Process termination** requires the reclaim of any reusable resources.
	- *Single-threaded process:*
	    - One **program counter** specifies the locations of the next instruction to execute.
	    - The **process** executes instructions sequentially, one at a time, until completion
	- *Multi-threaded process:*
	    - One program counter per thread
	- Typically system has many processes, some users, and some operating systems running concurrently on one or more CPUs.
	    - Concurrency by multiplexing the CPUs among the processes/threads.
	- *Process Management Activities:*
	    - Creating and deleting both user and system processes.
	    - Suspending and resuming processes.
	    - Providing mechanisms for process synchronization.
	    - Providing mechanisms for process communication.
	    - Providing mechanisms for deadlock handling.
- ### Memory Management:
	- All data in memory before processing
	- All instructions in the memory to execute.
	- *Memory management activities:*
	    - Keeping track of which parts of memory are currently being used and by whom
	    - Deciding which processes and data to move into and out of memory
	    - Allocating and deal-locating memory space as needed.
- ### File-System Management:
	- OS provides a uniform, logical view of storage
	    - **File:** abstracts physical properties to the logical storage unit
	    - Each medium is controlled by the device (i.e., disk drive)
	    - Varying properties: access speed, capacity, data transfer rate, access method (sequential or random)
	- File-system management
	    - Files are usually organized into directories
	    - Access control on most systems to determine who can access what
	- OS activities include
	    - Creating and deleting files and directories
	    - Mapping files onto secondary storage
	    - Backup files onto stable (non-volatile) storage media.
- ### Mass-Storage Management:
	- Usually, disks are used to store data that does not fit in the main memory or data that must be kept for a “long” period of time
	- The entire speed of computer operation hinges on the disk subsystem and its algorithms
	- OS activities:
	    - Free-space management
	    - Storage allocation
	    - Disk scheduling
	- Some storage need not be fast
	    - Tertiary storage includes optical storage, magnetic tape
	    - Still must be managed
	    - Varies between WORM (write-once, read-many-times) and RW (read-write)
- ### I/O System Management:
	- One purpose of OS is to hide peculiarities of hardware devices from the user
	- I/O subsystem responsible for
	    - Memory management of I/O includes buffering (storing data temporarily while it is being transferred), caching (storing parts of data in faster storage for performance)
	    - General device-driver interface
	    - Drivers for specific hardware devices.