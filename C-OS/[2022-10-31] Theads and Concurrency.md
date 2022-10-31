### Programs, Processes, and Threads

- The program starts out as a text file of programming code.
- The program is compiled or interpreted into binary form.
- The program is loaded into memory.
- The program becomes one or more running processes.
- Processes are typically independent of each other.
- Threads exist as the subset of a process.
- Threads can communicate with each other more easily than processes can
- Threads are more vulnerable to problems caused by other threads in the same process.


### Concurrency

Concurrency is the occurrence of multiple events within overlapping time frames, but not simultaneously. On a computer system, concurrency is implemented in the paradigm called concurrent computing. The running process threads always communicate with each other through shared memory or message passing. Concurrency results in sharing of resources result in problems like deadlocks and resources starvation. It helps in techniques like coordinating execution of processes, memory allocation and execution scheduling for maximizing throughput. 