---

# Chapter 2

## Store Program Concept

The stored-program concept refers to the idea that instructions and data of many types can be stored in memory as numbers. The interpretation of these numbers helps differentiate between an instruction and actual data.

## Instruction Set

An instruction set consists of low-level commands understood by a computer architecture.

## Operations on the Computer

Every computer should be capable of performing basic arithmetic operations.

### MIPS Instructions

- `add a, b, c` - Computes `b + c` and stores the result in `a`.
- `add a, c, b` - Computes `c + b` and stores the result in `a`.
- `add a, a, b` - Computes `a + b` and overwrites `a` with the result.

## Design Principles

1. **Simplicity Favors Regularity**
   - The "natural" number of operands for addition, subtraction, division, and multiplication is three.
   - Hardware complexity increases with a variable number of operands. Instead, architectures should assume a fixed number of operands for each operation.

2. **Smaller is Faster (Not Absolute)**
   - The clock signal takes time to reach every register.
   - More registers mean more registers to visit before the clock cycle ends.

3. **Good Design Demands Good Compromises**
   - Issues arise when instructions need more bits than available. For example, a 5-bit field can only store up to 32 values.
   - To manage this, MIPS uses different instruction formats (R-type for register operations, I-type for immediate and data transfer operations) while keeping a consistent instruction length of 32 bits.
   - Although this adds some complexity, the uniform instruction length simplifies hardware design.

## Compiling a Complex C Assignment into MIPS

Consider the assignment: `t = (g + h) - (i + j)`

1. Compute `g + h` and store in a temporary variable `t0`:
   ```
   add t0, g, h
   ```

2. Compute `i + j` and store in a temporary variable `t1`:
   ```
   add t1, i, j
   ```

3. Compute `t0 - t1` and store the result in `f`:
   ```
   sub f, t0, t1
   ```

## Misc Notes

### Java

Java was designed to be portable across architectures by using a software interpreter with its own instruction set called Java bytecode. Modern Java systems compile directly to native instruction sets (like MIPS) using Just-In-Time (JIT) compilers during startup.

### MIPS Operations

- **Registers**: 32 registers (e.g., `$zero`, `$at`, `$s[0-7]`, `$t[0-9]`, `$a[0-3]`, `$v[0-1]`, `$gp`, `$fp`, `$sp`, `$ra`).
- **Memory**: 2^30 memory words accessed by data transfer instructions, with byte addresses (8 bits), making sequential word addresses differ by 4 bytes.

## Memory Data and Addresses

- **Load**: A data transfer instruction that copies data from memory to a register.
- **Base Address**: The starting address of an array in memory (e.g., `5000` for `a[0]`).
- **Base Register**: Holds the array's base address.
- **Offset**: A constant value added to the base address to locate a specific array element.
- **Alignment Restriction**: Addresses must be multiples of a specific number due to memory word size. For instance, if the base address is `5000`, `A[1]` would be `5004`.

### Individual Bits Overview

- **Binary Representation**: `11100000 00000000 00000000 00000001`
  - Byte 0: `11100000`
  - Byte 1: `00000000`
  - Byte 2: `00000000`
  - Byte 3: `00000001`
  - If the word starts at address `5000`, then address `5003` holds `00000001`.

## Signed and Unsigned Numbers

- **Number Bases**: In any base, the value of the ith digit `d` is `d * base^i`, where `i` increases from right to left.
- **Least Significant Bit**: The rightmost bit in a MIPS word.
- **Most Significant Bit**: The leftmost bit in a MIPS word.

### Range of MIPS Word

- A MIPS word is 32 bits long, representing `2^32` values.
- **Largest 4-bit Number**: 15 (binary: `1111`)
- **Largest 8-bit Number**: 255 (binary: `11111111`)
- **Largest 32-bit Number**: 4,294,967,295 (binary: `11111111 11111111 11111111 11111111`)

### Overflow

- Occurs when an operation results in a number larger than what can be stored in a register.

### Two's Complement Representation

- For 32-bit numbers, two's complement representation allows for about 4.2 billion values, with roughly half representing negative numbers and half representing positive numbers.
- **Negative Numbers**: A binary number with a leading `1`.
- **Positive Numbers**: A binary number with a leading `0`.
- **Example**: `1111 1111 1111 1111 1111 1111 1111 1100` in binary is `-4` in decimal.

### One's Complement Representation

- Represents the most negative value by `100...00` and the most positive value by `011...11`.
- Zero is represented twice: `111...111` (negative zero) and `000...000` (positive zero).
- **Inversion**: Involves flipping each bit (0 to 1 and vice versa).

### Biased Notation

- Represents the most positive number by `111...111` and the most negative number by `000...000`.
- **Bias**: Adds a fixed value to adjust the number's representation.

### Hexadecimal

- Base-16 number system.

### Sign-Extension

- Sign-extension fills the leftmost bits of a register with the sign of the number to preserve sign and magnitude when storing a smaller number in a larger register.

## Names of MIPS Fields

- **opcode**: Basic operation of the instruction (e.g., addition, subtraction).
- **rs**: First register of the source operand.
- **rt**: Second register of the source operand.
- **shamt**: Shift amount for register operations.
- **funct**: Function code that selects the specific variant of the opcode.

### Fields and Instructions

- **Add Instruction**: 32 bits, 6 fields
  - Format: `6 bits | 5 bits | 5 bits | 5 bits | 5 bits | 6 bits`
  - The first and sixth fields indicate the instruction is addition.
  - The second and third fields are the operands.
  - The fourth field specifies the result's memory location.
  - The fifth field is unused.

## Instructions

- **Representation**: Instructions are represented using numbers, with each part of the instruction mapped to specific numbers.

### Instruction Format

- Represents an instruction with multiple binary fields, segmented into bits.

### Machine Language

- Communications with the computer via binary words.

## Logical Operations

Logical operations simplify bit-level manipulation:

- **Shift Right/Left**: Moves bits left or right, filling emptied bits with 0s.
- **Bitwise AND**: Masks bits to force 0s where the mask has 0s.
- **Bitwise OR**: Combines bits.
- **Bitwise NOT**: Inverts bits.
- **Bitwise NOR**: Composite of NOT and OR.

## Questions

1. **What is a data transfer instruction?**
   - A command that moves data between memory and registers.

2. **What is a spilled register?**

3. **Why distinguish between registers and memory? Are registers considered memory in all architectures?**

4. **Why have alignment restrictions on memory word addresses?**

5. **Is there a difference between computing addresses and accessing/storing data?**

6. **What is a biased number system?**
   - Example: In a 4-bit system with a bias of 7, the largest number is `8` (1111 - 7) and the smallest is `-7` (0000 - 7).

7. **Why use biases?**

8. **What is the difference between R-Type and I-Type instructions?**
   - R-Type: Used for operations without a constant in the instruction.
   - I-Type: Includes a constant, such as in `addi`, where 16 bits represent the constant.

9. **What is a use case for bit masking?**
   - To isolate a specific field in a word.

10. What is the difference between registers and memory?
    In this context, registers prefer to the temporary memory of the CPU.
    Memory itself is an abstract term. It could refer to caches, disks, etc.

## Miscellaneous

- **Add and Sub Opcodes**: The first field is 0; the last field determines whether it is addition or subtraction. This is due to their similar implementation with two source registers and one result register. This follows design principle 2.
