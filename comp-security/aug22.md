### Tradeoff Triangle
- **Concept:** Increasing one element of the triangle usually decreases the other two elements. Typically, this involves trade-offs between security, performance, and usability.

### Security by Obscurity
- **Definition:** Hiding the inner workings of a system to prevent security issues from being discovered.
- **Challenges:** As many applications have made their source code public (e.g., TCP/IP), and computer knowledge has become widespread, this approach alone is less effective.

### Steganography vs. Cryptography
- **Steganography:** 
  - **Purpose:** Conceals the existence of the communication.
  - **Method:** Hides a message within another message or medium. The original content remains visible but is obscured.
  
- **Cryptography:** 
  - **Purpose:** Conceals the content of the communication.
  - **Method:** Transforms the message into an unreadable format, so even if the communication is detected, its content is hidden.
  
### Key Terms
- **Plaintext:** The original, readable form of a message.
- **Ciphertext:** The transformed, unreadable form of a message.
- **Encryption:** The process of converting plaintext into ciphertext.
- **Decryption:** The process of converting ciphertext back into plaintext.
- **Key:** A value used to control the encryption and decryption processes.

### Chosen Plaintext Attacks
- **Definition:** An attacker can choose arbitrary plaintexts for encryption and obtain the corresponding ciphertexts.
- **Example:**
  - **Plaintext:** “sell the business”
  - **Encryption Method:** Shift each letter by 3 positions in the alphabet (Caesar Cipher).
  - **Ciphertext:** “vhoo wkh exvlqhvv”
  - **Decryption Method:** Shift each letter back by 3 positions.
  - **Key:** 3
- **Vulnerability:** With chosen plaintext attacks, attackers can infer details about the encryption method from the ciphertext, making the method easier to break.

### Ciphers
- **Caesar Cipher:** 
  - **Description:** Shifts each letter of the plaintext by a fixed number of positions in the alphabet.
  - **Possibilities:** 26 (one for each shift).

- **Monoalphabetic Cipher:**
  - **Description:** Maps each letter in the alphabet to another letter.
  - **Possibilities:** 26! (factorial of 26), offering many more permutations but still vulnerable to certain attacks.

### Attacking the Monoalphabetic Cipher
- **Frequency Analysis:** 
  - **Concept:** Certain letters appear more frequently in a given language. In English, 'E', 'T', 'A', and 'O' are among the most common.
  - **Strategy:** By analyzing letter frequency in the ciphertext, attackers can make educated guesses about which letters correspond to which, aiding in decryption.

---
