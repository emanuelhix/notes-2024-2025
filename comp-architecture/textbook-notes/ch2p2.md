## Byte Addressing

### Little Endian

In little endian system, the LSB is stored at the lowest memory address.
Thus, bytes are stored in reverse order compared to how they appear in the number.

- Ex: 0xABCDEF12
- Byte0: 0x12 stored at mem address 0
- Byte1: 0xEF stored at mem address 1
- Byte2: 0xCD stored at mem address 2 
- Byte3: 0xAB stored at mem address 3


### Big Endian

In big endian system, the MSB is stored at the lowest memory address.
Thus, bytes are stored in the same order as they appear in the number.

- Ex: 0xABCDEF12
- Byte0: 0xAB stored at mem address 0
- Byte1: 0xCD stored at mem address 1
- Byte2: 0xEF stored at mem address 2
- Byte3: 0x12 stored at mem address 3
