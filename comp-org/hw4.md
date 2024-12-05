# Sequential Circuits

## Importance

Sequential circuits are foundational to three key devices:

- **Flip-Flops**: These serve as the basic units of memory and are essential building blocks for our studies.
- **Counters**: While their function is straightforward, counters are vital for tracking time or memory locations. For instance, the "program counter" helps indicate which line of code the computer should execute at any given moment. If you’d like a more detailed explanation, feel free to ask, or wait for Professor Atiq's insights!
- **Registers**: Constructed from flip-flops, registers will be discussed in upcoming classes.

## Definition

In contrast to combinational circuits, the output of a sequential circuit depends on two main factors:

1. The past output(s) of that specific circuit.
2. The current input.

To express this in mathematical terms, we typically denote a function as \( f(x) = y \), where \( x \) is the input and \( y \) is the output. In this course, we often consider \( x \) and \( y \) as single bits (0 or 1).

For a sequential circuit, the function can be generalized as follows:  
`f(currentInput, lastOutput, clockInput) = newOutput`.  
Keep in mind that this is a simplified concept; some sequential circuits may involve additional inputs and outputs. For example, the SR latch may have outputs \( Q \) and \( Q' \), represented as:  
`f(currentInput, lastOutput, clockInput) = (newOutput, newOutput')`.

## Flip-Flops

### SR Latch

#### Properties

- **Stores One Bit**: The SR latch can hold a single bit of information.
- **Clock Control**: When the clock is off (0), the stored value remains unchanged.
- **State Changes**: When the clock is on (1), the latch can change states based on specific conditions:
  - **Set Condition**: If the Set (S) input is activated.
  - **Reset Condition**: If the Reset (R) input is activated.  
    These conditions allow the SR latch to function effectively in various applications.
