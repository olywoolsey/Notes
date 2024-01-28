# OS Design and Implementation
#COMP2211
- OS have many User and system goals
- Internal structure can vary widely, based on the purpose of OS.
## Policy and Mechanism
Separation of policies (what) and mechanisms (how) is an important concept
- Example policy: interrupt OS regularly; Mechanism: timer [interrupts](Interrupts.md).
- Good approach as we can change policies later and mechanisms are in place: for example,change the timer interrupt frequency
- Example: 
	- Linux CPU scheduler: is specific but we can change it to support a different policy when we want to schedule jobs in a different way
## Languages
OS is a collection of many programs, implemented by many people over years—general statements hard to make but there are some common points
- Kernel: assembly, C, some Rust.
- Higher level routines: C, C++, other.
- For example,  Android is mostly C and some [assembly](../Hardware/COMP1211-ComputerArchitecture/Assembly.md).
- Android system libraries C or C++.
- Android APIs: Java
### Advantages of High Level Languages
Code written faster, more compact, easier to understand and maintain. Compiler improvements easy to integrate by recompiling the OS. Easier to port the whole OS to new architecture