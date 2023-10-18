## Main Terms
- CPU: The hardware that executes instructions.
- Process: A physical chip that contains one or more CPUs
- Core: The basic computation unit of the CPU.
- Multicore: Including multiple computing cores on the same CPU.
- Multiprocessor: Including multiple processors
## Single-Processor Systems
- Single processor containing one CPU with a single processing core - many years ago.
- The core is the main piece of hardware within a CPU that executed program instructions and managed register storage locally.
- General purpose or domain specific: can run general programs or can runs a limited set of operations optimised for some task/s.
- A computer system may have one general purpose single-processor CPU and multiple domain-specific processors that accelerate some specific tasks. From the perspective of OS, this system is still a single processor
## Multi-Processor Systems
- THEY DOMINATE
- Two or more processors, each with a single-core CPU
- Increase throughput
- Ideally N processors should result in N times speed up. In reality it is less:there is some overhead in managing multiple processors that cooperate on some task. This overhead does not exist when only one processor is executing

## Multiprogramming
- Single Programs can't keep CPU occupied due to wait times so will switch between programs to keep busy

## Multitasking
- Similar to multiprogramming, but the switches between processes are very frequent to provide users with a fast response time

## Timer: Periodic Interrupts from OS
- For the OS to maintain control over the CPU we need protection against user program getting stuck in infinite loop or similar.
- Timer is set to [[Semester3/COMP2211-OperatingSystems/Interrupts|Interrupt]] the computer after a specified period.
- Period can be fixed or variable.OS sets up the timer before transferring control to user programs. When the timer interrupt occurs OS gets control and can decide whether to abort the program or let it run longer.
- Instructions that set up the timer are privileged instructions—hardware operations that can only be executed in kernel mode

## Processor Management
- Processes need resources: CPU, memory, I/O, files, initialisation data.
- A program is not a process—it’s a passive entity.
- Processes instead are active entities.
- A single-threaded process has one program counter specifying the next instruction to execute.
- Sequential execution: CPU executes instructions one at a time, until the process terminates.
- Two processes can be associated to the same program, but are considered separate entities, separate execution sequences.
- Multi threaded processes have multiple program counters—we will address threads later in the module.
- Typically many processes exist, some belong to OS executing in kernel mode, some to user, executing in user mode: OS multiplexes between these processes on single or multi-core CPUs.