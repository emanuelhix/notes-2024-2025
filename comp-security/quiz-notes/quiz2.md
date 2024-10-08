# Quiz 2 Notes

## Permutation vs. Substitution (Diffusion vs. Confusion)

### Substitution
In substitution ciphers, characters from the plaintext are replaced with other characters from the same alphabet, while retaining the original structure of the plaintext.

#### Examples
- **Caesar Cipher**
- **Vigenère Cipher**

#### Substitution Box (S-Box)
**Definition:** An S-Box is a lookup table used to determine substitution values. 

- **Mechanism:** The value at the intersection of a row and column indicates which plaintext character should be replaced by the corresponding ciphertext character.
- **Variability:** While S-Boxes may differ in implementation, they all share the (row, column) indexing property.
- **Non-linearity:** S-Boxes introduce non-linearity, eliminating linear relationships between plaintext and ciphertext, enhancing security.
- **Vulnerability:** Despite their complexity, S-Boxes retain the plaintext structure in the ciphertext, making frequency analysis a viable attack method.

### Permutation (P-Box)
**Definition:** A P-Box is a lookup table used to determine the permutation of characters in the plaintext.

## DES

## Effective Key Lengths and Subkey Lengths
