
---

# Chapter 3 Review

## Number Systems Overview

In this course, we explore various number systems, each using a base `r` with distinct symbols representing different digit places. The value of a number in any system can be computed using the formula:

\[ \text{value} = x_n \cdot r^n + x_{n-1} \cdot r^{n-1} + \cdots + x_0 \cdot r^0 \]

where \(x_i\) represents the digit at position \(i\) and \(r\) is the base of the system.

### Decimal (Base 10)

The Decimal system is the most commonly used system, employing ten symbols: 0, 1, 2, 3, 4, 5, 6, 7, 8, and 9. Each digit's place value is a power of 10.

**Examples:**

| Decimal | Representation | Value Calculation      |
|---------|----------------|------------------------|
| 345     | \(3 \cdot 10^2 + 4 \cdot 10^1 + 5 \cdot 10^0\) | 300 + 40 + 5 = 345 |
| 78      | \(7 \cdot 10^1 + 8 \cdot 10^0\) | 70 + 8 = 78 |

### Binary (Base 2)

The Binary system uses only two symbols: 0 and 1. Each digit's place value is a power of 2.

**Examples:**

| Binary | Representation | Value Calculation      |
|--------|----------------|------------------------|
| 1011   | \(1 \cdot 2^3 + 0 \cdot 2^2 + 1 \cdot 2^1 + 1 \cdot 2^0\) | 8 + 0 + 2 + 1 = 11 |
| 1100   | \(1 \cdot 2^3 + 1 \cdot 2^2 + 0 \cdot 2^1 + 0 \cdot 2^0\) | 8 + 4 + 0 + 0 = 12 |

### Gray Code

Gray Code is a binary numeral system where two successive values differ in only one bit. It is used in error correction and digital systems.

**Examples:**

| Decimal | Binary | Gray Code | Description              |
|---------|--------|-----------|--------------------------|
| 0       | 0000   | 0000      | No change                |
| 1       | 0001   | 0001      | Single bit change        |
| 2       | 0010   | 0011      | Single bit change        |
| 3       | 0011   | 0010      | Single bit change        |

### BCD (Binary Coded Decimal)

BCD represents each decimal digit with its 4-bit binary equivalent. Each digit in the decimal number is converted separately to binary.

**Examples:**

| Decimal | BCD Representation | Value Calculation         |
|---------|---------------------|---------------------------|
| 5       | 0101                | 5                         |
| 23      | 0010 0011           | 2 (0010) + 3 (0011) = 23  |
| 47      | 0100 0111           | 4 (0100) + 7 (0111) = 47  |

---
---

## Complements

### Definition
Complements are mathematical tools used in various number systems to simplify arithmetic operations and manage negative values.

### Motivation for Using Complements
Complements are used in various contexts, including:
1. **Simplifying subtraction operations**.
2. Error detection and correction.
3. **Representing negative numbers**.
4. Optimizing digital circuits.
5. Facilitating logical operations.

### Types of Complements

#### r's Complement
- **Definition**: The r's complement of a number is obtained by subtracting the number from \( r^n \), where \( r \) is the base of the numeral system and \( n \) is the number of digits.
- **Purpose**: Commonly used to represent negative numbers in positional numeral systems.

#### (r-1)'s Complement
- **Definition**: The (r-1)'s complement of a number is obtained by subtracting the number from \( r^n - 1 \).
- **Purpose**: Used in error detection and correction as well as in certain digital arithmetic operations.

### Examples

#### Base 10 (Decimal Numbers)
- **r's Complement**: For base 10, the r's complement of a number \( N \) is \( 10^n - N \).
- **(r-1)'s Complement**: For base 10, the (r-1)'s complement of a number \( N \) is \( 9^n - N \).

#### Base 2 (Binary Numbers)
- **r's Complement**: For base 2, the r's complement of a number \( N \) is \( 2^n - N \).
- **(r-1)'s Complement**: For base 2, the (r-1)'s complement of a number \( N \) is \( 1^n - N \), which is equivalent to flipping all bits (1's complement).

#### Base 8 (Octal Numbers)
- **r's Complement**: For base 8, the r's complement of a number \( N \) is \( 8^n - N \).
- **(r-1)'s Complement**: For base 8, the (r-1)'s complement of a number \( N \) is \( 7^n - N \).

### Addition Operations

#### Overflow
- **Definition**: Overflow occurs when the result of adding two \( n \)-bit numbers requires \( n+1 \) bits to represent.
- **Importance**: Registers have a finite amount of space. If an extra bit is needed but not accounted for, it can lead to incorrect results.

#### Detecting Overflow
The method for detecting overflow varies based on if the sum is made up of signed numbers or unsigned numbers.
- **Unsigned Overflow**: Detected by the carry-out position. If the carry-out is 1, overflow has occurred.
- **Signed Overflow**: Detected by comparing carry-in and carry-out positions. Overflow occurs if both are 1 or both are 0, indicating that both operands had the same sign.

### Subtraction Operations

#### Definition of the Subtraction Operation
For subtracting \( N \) from \( M \) in base \( r \), where \( N \ne 0 \):
1. Add \( M \) to the r's complement of \( N \):
   \[
   M + (r^n - N) = M - N + r^n
   \]
2. If \( M \geq N \), there will be an end carry. Discard it.
3. If \( M < N \), there will be no end carry.
4. Take the r's complement of the sum and negate the sign to see the actual value of the result.
   
---
