## Common Bugs
- Syntax Error
	- Can't understand the code
- Logical errors:
	1. Code isn't what we meant
	2. We meant the wrong thing
- Memory Error
	- We were sloppy
- Performance
	- It was slow
- No Cohesion
	- Too much happening
- Tight Coupling
	- code too dependant on getting something else right

## The Debug Loop
1. TEST
- test everything - all different types of data
- need to know the right answer first to compare test results to
- when you run into the bug reproduce it
- start small as it is easier to find if something is wrong
- try to break the code
2. ISOLATE
- bugs can interact 
- deal one at the time
- bugs may cause others so start with the bug at the top
3. ANALYSE
- What was the code supposed to do?
- What did the code actually do?
- compare 
- make sure its not because of another line somewhere further up
4. Instruction
- what does every single part of the line do
	- read every dot and comma
- check what variables are supposed to change and see if it matches what it actually does
5. Repair
- Once the bug is understood then fix it
- Go back to step one and test again
- can automate the tests

## Execution Traces
Records all:
- input data
- the code
- system state
- sequence of instructions
Have 2 traces them compare them

## Logs, Cores & Crash Reports
- add output statements to the code to log
- the OS saves memory contents on crash, known as a core dump
- print out important variables

## GDB - GNU Debugger
- standard unix debugger