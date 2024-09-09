# Binary Encoding Systems

## Binary Coded Octal
- **Definition**: Representation of any octal digit by its three-bit binary equivalent.

## Binary Coded Hexadecimal
- **Definition**: Representation of any hex digit by its four-bit binary equivalent.

## Binary Coded Decimal (BCD)
- **Definition**: Representation of any decimal digit by a four-bit binary equivalent.
    - `0` - `0000`
    - `1` - `0001`
    - `2` - `0010`
    - ...
    - `8` - `1000`
    - `9` - `1001`

### General Idea of Coded Systems
- **`x` Coded `y`**: Representation of any `y` digit in terms of digits from the `x` number system.

# Complements

## Why Do We Care About Complements?
- **Purpose**: The type of complement used to represent a signed number affects the range of values it can represent. This range can be:
  - **Unbalanced**: Zero may be represented more than once (e.g., negative zero and positive zero).
  - **Balanced**: Zero is represented only once, but this uses one of the positive values, resulting in a larger negative range.

## 10's Complement
- **Example**: Compute the 10's complement of `12390`.
    1. Calculate: `9999 - 12390 = 87609`
    2. Add 1: `87609 + 1 = 87610`
- **Range**: `-10^(n-1) + 10^(n-1) + 1`, where `n` is the number of digits.
- **Why +1?**: The largest possible number in a 10's number system with `n` digits is `10^n - 1`. For `n=3`, the number is `999`, or `10^3 - 1 = 999`.

## 2's Complement
- **Example**: Compute the 2's complement for `11010 - 10000`.
    1. **Find the 2's Complement of `10000`**:
        - Subtract `10000` from `11111`: `11111 - 10000 = 01111` (1's complement)
        - Add 1: `01111 + 00001 = 10000`
    2. **Add Result to Minuend**: `11010 + 10000 = 1[01010] = 01010` (discard carry)

# Code Conversions

## Binary to Gray Code
1. Record the most significant bit (MSB).
2. Add the MSB to the next bit, record the sum, and discard the carry (similar to XOR).
3. Repeat until all bits are processed.
    - **Example**: Convert `01001` to Gray code.
        - MSB: `0`
        - `0 + 1 = 1`
        - `1 + 0 = 1`
        - `0 + 0 = 0`
        - `0 + 1 = 1`
        - **Gray Code**: `01101`

## Hexadecimal to Gray Code
1. Convert hexadecimal to binary.
2. Convert binary to Gray code.

## Octal to Gray Code
1. Convert octal to binary.
2. Convert binary to Gray code.

## Gray Code to Binary
- **Method**: The inverse of XOR is XOR itself. Use the same process as converting binary to Gray code.

## Gray Code to Hexadecimal
1. Convert Gray code to binary.
2. Convert binary to hexadecimal (group digits into sets of 4, then convert each group to hex digits 0-9 and A-F).

## Gray Code to Octal
1. Convert Gray code to binary.
2. Convert binary to octal (group digits into sets of 3, then convert each group to octal digits 0-7).

# Two's Complement Representation

## Two's Complement of Decimal
1. Convert the number to binary.
2. If the number is positive, leave it as is.
3. If the number is negative:
    - Subtract it from `2^n` (e.g., `2^3 = 8`, so `8 - abs(number)`).
    - Add 1 to the result.

## Limitations of Two's Complement
- **Range Example**: Using 8-bit 2's complement, the range is `-128` to `127`. To represent `137`, 9 bits are needed.

## Detecting Overflow in Two's Complement
1. **Adding Two Positive Numbers**: Overflow occurs if the result is negative (e.g., both numbers have leading 0s, but result has a leading 1).
2. **Adding Two Negative Numbers**: Overflow occurs if the result is positive (e.g., both numbers have leading 1s, but result has a leading 0).
3. **Mixed Signs**: Verify if the result's sign makes sense for the operation.
4. **Subtraction**: If subtracting `y` from `x`, where `x > y` gives a positive result and `x < y` gives a negative result. Overflow occurs if the result is not as expected.

## Two's Complement to Decimal Conversion
1. Identify the sign bit: `0` is positive, `1` is negative.
2. If the sign bit is `0`, convert binary to decimal directly.
3. If the sign bit is `1`:
    - Invert the bits.
    - Add 1.
    - Convert the resulting binary number to decimal.
    - Apply a negative sign to the result.

# Fixed-Point Representation

## Definition
- **Fixed-Point Representation**: Numbers are represented with a fixed number of bits for the integer part and a fixed number of bits for the fractional part.
    - **Example**: `Q8.8` means 8 bits for the integer part and 8 bits for the fractional part.

## Fixed-Point Addition
1. Align the numbers (line up the decimal points).
2. Perform bit-wise addition from right to left.

## Overflow in Fixed-Point Addition
- **Condition**: Overflow occurs if the sum exceeds the maximum value representable with the fixed number of bits.
    - **Example**: For format `Qx.Y`, if the result can't be represented with `x` integer bits, overflow has occurred.
--

IEEE 754 floating point representation (32 bits <==> "single precision")

decimal to IEEE754 32-bit floating point notation
    form: [s][eeeeeeee][mmmmmmmmmmmmmmmmmmmmmmm]
          [1bit][8bits][23bits]
          [sign][exponent][mantissa aka fraction bits]
    1. represent the decimal number in binary form (note: be cautious when converting the value after the decimal place to binar
    2. put the decimal number into scientific form. this requires shifting the decimal all the way up to the most significant bit by multiplying by 2 multiple times.
    suppose our binary number was 1010.0101 -- in scientific form, this is 1.0100101 * 2^3, because we shifted 3 decimal places to the left (multiplied by 2 three times)
    3. at this point, identify the sign bit, the exponent bits, and the mantissa bit.
    4. subtract or add the bias.
    5. if we shifted by a positive number, add the bias. in this case, the operation is 127+3=131. otherwise, subtract the bias