# [Process](Process.md) Management
#COMP2211
- Processes need resources: CPU, memory, I/O, files, initialisation data.
- A program is not a process - it’s a passive entity.
- Processes instead are active entities.
- A single-threaded process has one program counter specifying the next instruction to execute.
- Sequential execution: CPU executes instructions one at a time, until the process terminates.
- Two processes can be associated to the same program, but are considered separate entities, separate execution sequences.
- Multi threaded processes have multiple program counters
- Typically many processes exist, some belong to OS executing in kernel mode, some to user, executing in user mode: OS multiplexes between these processes on single or multi-core CPUs.
## Process State Transitions
Processes change states during execution
- New: Process has been created
- Running: CPU is reading process' instructions
- Waiting: Waiting for an event (e.g. I/O)
- Ready
- Terminated
![](Images/Pasted%20image%2020240119160536.png)
Only one process can be running on a core; others may be ready or waiting
## Process Control Block (PCB)
- Process state
- Program Counter (PC)
- CPU registers: along with the PC, these have to be saved when process is interrupted
- CPU-scheduling information: priority and other [scheduling](Scheduling.md) parameters
- Memory-management information: Location of various memories assigned to the process
- Accounting information
- I/O status information: I/O devices allocated to the process, open files
## Processes or Threads
