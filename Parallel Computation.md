# Parallel Computation
*Writing software that makes use of hardware capable of performing calculations simultaneously*
## Automated Parallelism
- Don't Scale
**Instruction-level Parallelism (ILP)**
- Pipelining architecture in which each instruction is processed in different stages
- Different stages for subsequent instructions can be performed simultaniously
CPUs also have **multiple functional units**
- E.G. FPUs, ALUs etc that can work independtly
- Superscalar architectures can merge nearby calculations into a single one

## Current Parallel Architectures
Pro: Scales better than automated parallelism
Con: Software must be specifically developed to take into account these processing units
### Shared memory architectures
All processing units access the same memory
- Includes andything with one or more mu
- Distributed memory architectures
- Graphics Processing Units (GPUs)
