---

## Topic 2: Introduction to Cryptography
- **Side-Channel Attack**:
  - **Definition**: A side-channel attack exploits additional information obtained from the physical implementation of a cryptographic system, rather than vulnerabilities in the algorithm itself. This can include timing information, power consumption, electromagnetic leaks, or sound.
  - **Simple Explanation**: A side-channel attack uses information gathered from the way a system operates (e.g., timing or power usage) to gain unauthorized access, rather than attacking the theoretical design of the cryptographic algorithm.
  - **Example**: An attacker measures how long it takes to process different inputs and uses this timing information to deduce secret data or cryptographic keys.

### Permutation Ciphers

- **Definition**: A permutation cipher, also known as a transposition cipher, encrypts data by rearranging the positions of characters rather than substituting them.
- **How It Works**: The plaintext is arranged in blocks of columns and rows. The columns are then permuted according to a key.

- **Example**:
  - **Plaintext**: "ATTACK POSTPONED UNTIL TWO AM"
  - **Key**: 4, 3, 1, 2, 5, 7, 8
  - **Block Arrangement**:
    ```
    A T T A C K P
    O S T P O N E
    D U N T I L T
    W O A M
    ```
  - **Permuted Output**: "TTNA APTM TSUO AODW COIX PETZ KNLY"

#### Example: Vigenère Cipher

- **Overview**: The Vigenère cipher improves upon simple substitution ciphers by using a key to determine how much each letter is shifted, thus breaking the direct one-to-one relationship between plaintext and ciphertext characters.
- **Frequency Analysis**: In simple substitution ciphers, character frequencies in the plaintext directly map to frequencies in the ciphertext. The Vigenère cipher disrupts this pattern, making frequency analysis less effective.
Here’s an improved version:
- The Vigenère cipher can be seen as a series of Caesar ciphers, each using a different shift value derived from a repeating key.
- **Encryption Formula**: \( C_i = (P_i + K_i) \mod 26 \)
- **Decryption Formula**: \( P_i = (C_i - K_i + 26) \mod 26 \)
  - **Where**:
    - \( P_i \) is the alphabetical position of the \(i\)-th plaintext character.
    - \( C_i \) is the alphabetical position of the \(i\)-th ciphertext character.
    - \( K_i \) is the alphabetical position of the \(i\)-th key character.

### Perfectly Secure Cipher: One-Time Pads

- **Theorem**: For a cipher to be perfectly secure, it requires:
  1. A key length at least as long as the message.
  2. The key must be used only once.
- **Limitations**: One-time pads are impractical for most applications due to the challenge of generating and securely distributing long, random keys.

### Secret-Key Cryptography

- **Symmetric Cryptography**: Uses the same key for both encryption and decryption.

#### Applications

1. **Transmitting Messages Over Insecure Channels**:
   - **Challenge**: Secure key exchange.

2. **Authentication**:
   - **Challenge-Response**: Proves knowledge of the secret key.
   - **Security**: Must resist chosen plaintext attacks.

3. **Integrity Checks**:
   - **Message Integrity Code (MIC)** or **Message Authentication Code (MAC)**.
   - **Key Types**: Can involve secret keys or public keys.

### Summary / Takeaways

1. **Perfectly Secure Ciphers**: Theoretically possible but impractical due to the difficulties in key management.
2. **Early Ciphers**: Insufficiently secure; modern cryptography has advanced to overcome their weaknesses.
3. **Key Distribution and Management**:
   - **Issues**: Requires a key to distribute another key and the need for secure channels for key communication.

## Topic 3.1: Secret-Key Cryptography Algorithms

### Key Sizes

- **Importance**: Keys should be selected from a large potential set to resist brute force attacks.
- **Example**: For a 3-bit key, there are 2^3 = 8 possible keys. A brute force attack can attempt all possibilities.

#### Adequate Key Size

- **Evolution**: As computational power increases, key sizes must also increase. For example, with a 50% annual increase in computing power, key sizes should increase by 5 bits every decade to maintain security.

### Two Principles for Cipher Design

1. **Confusion**:
   - **Goal**: Make the relationship between plaintext and ciphertext as complex as possible.
   - **Method**: Achieved through substitutions.

2. **Diffusion**:
   - **Goal**: Spread the influence of each input bit across many output bits.
   - **Method**: Achieved through permutations.

- **Implementation**: Use alternating permutations (P) and substitutions (S). Consecutive Ps or Ss do not enhance security.

## Questions
1. How does a permutation cipher work? (Practice encrypt/decrypt once or twice)
2. What's a good example of a perfectly secure cipher?
---