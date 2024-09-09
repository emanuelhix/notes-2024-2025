# Chapter 1 Notes

## Notable Questions
  
### 1.3.5: High Level Programming Languages
5. An advantage of a high-level language is that a program <is independent of a particular machine>.
High-level languages are machine independent, but they still have to be converted to a machine dependent (maybe hardware dependent is more accurate) language in order to utilize the hardware in a particular system.

### 

## Notes
### The Big Picture
Every piece of hardware of every computer, past or present, can be placed into one of these categories:
1. Input
writes data to memory
2. Output
displays result of computation to user
3. Memory
the place where instructions and data are retrieved from
3. Datapath
the place where computations happen
4. Control
sends signals that tell the other components how to operate

typically, control and datapth are included together as the "processor".

### the 7 Great Ideas of Computer Science
1. Use abstraction to simplify design
use abstractions to represent the design at different levels; low level details are inaccessible except through things like function calls, which gives a simpler model to work with in higher level code.
2. Make the common case fast
making the common case more quick usually results in a greater improval of performance than optimizing the rare cases.
3. performance via parallelism
splitting a task into subtasks that are completed simultaneously, so that the overall execution time is fractioned.
4. performance via pipelining
multiple operations are moved through different hardware units. these hardware are specialized for that type of operation, sometimes. 
5. peformance via prediction
ues data to look ahead and make predictions. of course, if the prediction is wrong, we need to gracefully handle those cases.
6. hierarchy of memories
the pyramid of different memory hardware. it describes hardware in 3 dimensions: speed, size, and manufacture cost. at the top of the pyramid, memory is the fastest, smallest, and most expensive. at the bottom of the pyramid, memory is the slowest, cheapest, and largest. 
7. dependability via redundancy
design the system in such a way that if one part fails, the system can fallback on another to do the same task. 
this is a type of gracefully failing.

interestingly, this really says a lot about what we strive for when improving computers. 
we care about performance, so we prescribe three solutions: parallelism, prediction, and pipelining.
then, we instruct people to focus on optimizing common cases mainly, instead of edge cases. this is because our improvements will be most seen in those common cases than anywhere else. 
if common cases make up a set of larger cases in part with the rare ones, then we're better off approaching the larger group as that one has a much higher performance improvement potential.
we care in another dimension, too: dependency/reliability. we prescribe redundancy as a good solution for that. abstractly, this should really be about graceful failure.
finally, we care that the systems we design can work easily with eachother. we prescribe abstraction as the solution.

## Hardware
#### DRAM
Large memory where most data is stored. Very dense. 
#### SRAM
Static RAM is less dense than DRAM, but provides faster access times.
  
### Application Binary Interface (ABI)  
The user porti  on of the instruction set plus the operating system interfaces used by application programmers. This provides a standard for binary portability across computers.   
  
### Instruction Set Architecture  
an abstract interface between the hardwaere and the lowest-level software (i.e. the operating system programs) that contains all the information needed to write a machine language program that functions correctly; including instructions, registers, memory access, input/output, and more.  
  
ISAs allow machine language programs to be hardware  implementation independent.  
