# Chapter 1 Notes

## Notable Questions

### 1.3.5: High-Level Programming Languages
5. **Advantage of High-Level Languages:**  
   High-level languages are machine-independent, meaning programs written in them are not tied to a specific machine. However, they must be translated into machine-dependent languages to interact with hardware.

## Notes

### The Big Picture
Computer hardware can be categorized into:

1. **Input:**  
   Devices that write data to memory.

2. **Output:**  
   Devices that display computation results to the user.

3. **Memory:**  
   Storage for instructions and data.

4. **Datapath:**  
   Hardware where computations occur.

5. **Control:**  
   Sends signals to direct other components.

   *Control* and *Datapath* are often combined as the "Processor."

### The 7 Great Ideas of Computer Science

1. **Abstraction:**  
   Simplify design by using abstraction at different levels, hiding low-level details behind higher-level constructs.

2. **Optimize Common Cases:**  
   Focus on making the common cases fast, as this yields better overall performance than optimizing rare cases.

3. **Parallelism:**  
   Improve performance by splitting tasks into subtasks that run simultaneously.

4. **Pipelining:**  
   Enhance performance by overlapping multiple operations in specialized hardware units.

5. **Prediction:**  
   Use data to anticipate future events and handle incorrect predictions gracefully.

6. **Memory Hierarchy:**  
   Organize memory by speed, size, and cost. Faster, smaller, and more expensive memories are at the top, while slower, larger, and cheaper ones are at the bottom.

7. **Redundancy:**  
   Design systems with backup components to ensure graceful failure in case of part failure.

   These principles focus on performance (parallelism, prediction, pipelining), reliability (redundancy), and ease of use (abstraction).

#### These principles highlight our goals in computer improvement:

1. **Performance Optimization:**  
   We focus on three key strategies—parallelism, prediction, and pipelining—to enhance performance. The emphasis is on optimizing common cases rather than rare ones, as improvements in common scenarios yield the most significant performance gains. By addressing common cases effectively, we achieve higher overall performance benefits.

2. **Reliability:**  
   To address dependency and reliability, we use redundancy to ensure graceful failure. This approach allows systems to continue functioning even if a component fails, enhancing overall dependability.

3. **System Integration:**  
   We aim for systems that work seamlessly together, which is achieved through abstraction. This ensures that complex systems can be managed and interacted with more easily, facilitating smoother integration and operation.

## Hardware

- **DRAM (Dynamic Random Access Memory):**  
  Large, dense memory used for most data storage.

- **SRAM (Static Random Access Memory):**  
  Faster but less dense than DRAM.

### Application Binary Interface (ABI)  
Defines the interface between the instruction set and the operating system, ensuring binary portability across different computers.

### Instruction Set Architecture (ISA)  
An abstract interface between hardware and low-level software (e.g., operating systems). It includes instructions, registers, memory access, and I/O details, making machine language programs independent of hardware implementations.
