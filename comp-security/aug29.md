# Feistel Cipher

## Key Parts

- **Round Function**
  - In each round, one half of the data block is XOR'ed with the other half.
  - The output is the same size as the input.
  - This process is repeated a fixed number of times (number of "rounds").
  - The final output is the encrypted data.

- **Invertibility**
  - The entire operation is guaranteed to be invertible, meaning the ciphertext can always be reverted to plaintext.

## Parameters

- Block Size
- Key Size
- Number of Rounds
- Subkey Generation Algorithm
- Scrambling Function (also known as the arbitrarily complex function)

# DES Encryption Standard

- **Block Size:** 64 bits (64-bit input, 64-bit output)
- **Number of Rounds:** 16
- **Key Size:** 64 bits (effectively 56 bits, as every 8th bit is a parity bit)
    - Key representation: 0000000x 0000000x 0000000x 000000x 0000000x 0000000x 0000000x 0000000x


- **Encryption Method:** Feistel network
- **Rounds Implementation:**
- Mangler function
- Expansion function (32 bits expanded to 48 bits)
- Substitution
- Permutation

# Principles of Cipher Design

The primary goals are to **confuse** and **diffuse**:
- **Confuse:** Make the relationship between ciphertext and plaintext as complicated as possible.
- **Diffuse:** Spread the influence of an individual bit across multiple bits in the block of data.

## The Avalanche Effect

- **Description:** A small change in input results in a significant change in output.
- **Pros:** Increases the uniqueness of ciphertext, making it difficult to infer details about the output from similar input data. 
- **Cons:** Error propagation. Corruption in data can lead to significant changes in ciphertext, potentially resulting in malformed plaintext upon decryption.

