# [Process](Process.md) Management
- Processes need resources: CPU, memory, I/O, files, initialisation data.
- A program is not a process - it’s a passive entity.
- Processes instead are active entities.
- A single-threaded process has one program counter specifying the next instruction to execute.
- Sequential execution: CPU executes instructions one at a time, until the process terminates.
- Two processes can be associated to the same program, but are considered separate entities, separate execution sequences.
- Multi threaded processes have multiple program counters
- Typically many processes exist, some belong to OS executing in kernel mode, some to user, executing in user mode: OS multiplexes between these processes on single or multi-core CPUs.