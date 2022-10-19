### What is process?
Process is the execution of a program that performs the actions specified in that program. It can be defined as an execution unit where a program runs. The OS helps you to create, schedule, and terminates the processes which is used by CPU. A process created by the main process is called a child process.

Process operations can be easily controlled with the help of PCB(Process Control Block). You can consider it as the brain of the process, which contains all the crucial information related to processing like process id, priority, state, CPU registers, etc.

### What is Process Management?

#### Concepts
Process management involves various tasks like creation, scheduling, termination of processes, and a dead lock. Process is a program that is under execution, which is an important part of modern-day operating systems. The OS must allocate resources that enable processes to share and exchange information. It also protects the resources of each process from other methods and allows synchronization among processes.

It is the job of OS to manage all the running processes of the system. It handles operations by performing tasks like process scheduling and such as resource allocation.

#### Process Architecture
Process architecture:

![image info](/images/process_architecture.webp)

Here, is an Architecture diagram of the Process

- Stack: The Stack stores temporary data like function parameters, returns addresses, and local variables.	
- Heap Allocates memory, which may be processed during its run time.
- Data: It contains the variable.	
- Text: Text Section includes the current activity, which is represented by the value of the Program Counter.

#### Process Control Blocks
PCB stands for Process Control Block. It is a data structure that is maintained by the Operating System for every process. The PCB should be identified by an integer Process ID (PID). It helps you to store all the information required to keep track of all the running processes.

It is also accountable for storing the contents of processor registers. These are saved when the process moves from the running state and then returns back to it. The information is quickly updated in the PCB by the OS as soon as the process makes the state transition.

##### Process states

![image info](/images/process_architecture.webp)

A process state is a condition of the process at a specific instant of time. It also defines the current position of the process.

There are mainly seven stages of a process which are:

- New: The new process is created when a specific program calls from secondary memory/ hard disk to primary memory/ RAM a
- Ready: In a ready state, the process should be loaded into the primary memory, which is ready for execution.
- Waiting: The process is waiting for the allocation of CPU time and other resources for execution.
- Executing: The process is an execution state.
- Blocked: It is a time interval when a process is waiting for an event like I/O operations to complete.
- Suspended: Suspended state defines the time when a process is ready for execution but has not been placed in the ready queue by OS.
- Terminated: Terminated state specifies the time when a process is terminated

After completing every step, all the resources are used by a process, and memory becomes free.

##### Process Control Block(PCB)
Every process is represented in the operating system by a process control block, which is also called a task control block.

Here, are important components of PCB

![image info](/images/pcb.webp)

- Process state: A process can be new, ready, running, waiting, etc.
- Program counter: The program counter lets you know the address of the next instruction, which should be executed for that process.	
- CPU registers: This component	includes accumulators, index and general-purpose registers, and information of condition code.
- CPU scheduling information: This component	includes a process priority, pointers for scheduling queues, and various other scheduling parameters.
- Accounting and business information: It includes the amount of CPU and time utilities like real time used, job or process numbers, etc.
- Memory-management information: This information includes the value of the base and limit registers, the page, or segment tables. This depends on the memory system, which is used by the operating system.
- I/O status information: This block includes a list of open files, the list of I/O devices that are allocated to the process, etc.

*reference:* https://www.guru99.com/process-management-pcb.html 
