# Chapter 4  

### Purpose of Register Allocation  

Fit as many variables as possible into registers.  

### Managing Resources  

There are a limited number of registers. Sometimes, a program has more variables than available registers.  

#### Interference  

If two or more variables are in use at the same time, they interfere with each other.  
This essentially means they are competing for space in the registers.  

#### Memory Resource Outage  

When the registers are completely full, variables are typically stored on the stack.  
This means they will take longer to access.  

##### Spills  

A variable is spilled if it is moved onto the stack.  

### liveness analysis

the process of determining which variables are being used in different areas of the program
 
#### live location

a memory location that is being used 

### interference graph

the liveness analysis tells us where each location is live.
since we are trying to maximize register usage, we want to know when two memory locations are live at the same time. that is, are two variables being used at the same time? if so, they can't share a register. 

#### purpose

this process is going to enable safely assigning variables to registers.

