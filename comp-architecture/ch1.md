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

## Vocabulary 
### Hardware
#### DRAM
Large memory where most data is stored. Very dense. (many bits per unit area)
#### SRAM
Static RAM is less dense than DRAM, but provides faster access times.
  
### Application Binary Interface (ABI)  
The user porti  on of the instruction set plus the operating system interfaces used by application programmers. This provides a standard for binary portability across computers.   
  
### Instruction Set Architecture  
an abstract interface between the hardwaere and the lowest-level software (i.e. the operating system programs) that contains all the information needed to write a machine language program that functions correctly; including instructions, registers, memory access, input/output, and more.  
  
ISAs allow machine language programs to be hardware  implementation independent.  
