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
- Includes anything with one or more multi-core CPU (most modern laptops, phones ..etc)
![](Screenshot_20240510_230408.png)

### Distributed memory architectures
Processing units only access a fraction of total memory available
- Includes High-Performance Computing (HPC) clusters (e.g. supercomputers), and distributed systems (‘cloud computing’)
### Graphics Processing Units (GPUs)
Hardware specifically designed to rapidly perform calculations that arise in the graphical rendering of scenes
- Historically driven by graphics applications, especially video games, but increasing being used for non-graphical applications such as machine learning, cryptocurrencies
- Some devices design for general-purpose calculations
	- Known as GPGPUs for General-Pupose GPUs
- GPU hardware has multiple memory stores, some of which can be viewed as distributed, some shared