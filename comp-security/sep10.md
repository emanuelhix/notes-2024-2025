# Initialization Vectors
- Used along with the key; not secret.

## Triple DES Encryption
- **Why don't we use 3 different keys?**
  - **Man-in-the-Middle Attack:** Triple DES is vulnerable to this attack.
  - **Cost vs. Security:** The cost is high, but the security does not increase proportionally.
  - **Single DES Equivalent:** When `k1 = k2 = key`, Triple DES effectively functions as single DES.
  - **Performance:** One-third as fast as single DES on the same hardware.

## Message Authentication Code (MAC)
- **Definition:**
  - Also known as Media Access Control (not to be confused with MAC address).
  - Unique to the device and persistent (doesn’t change).

## IP Address
- **Characteristics:**
  - Not persistent; can change on the same network and usually changes when switching to a different router.

## Residue
- **Definition:** The last (final) ciphertext output block.

## Message Authentication / Integrity
- **Challenge:**
  - Messages can be intercepted and altered. To verify if a message was manipulated, we use encryption and decryption.

- **Approach 1:**
  - If the plaintext "appears plausible," conclude that the ciphertext was produced exclusively by the key partner.
  - Illegally modified ciphertext or text encrypted with the wrong key will likely look random when decrypted.

- **Approach 2:**
  - Send both plaintext and ciphertext.
  - This confirms message integrity but loses confidentiality.

- **Approach 3: Residue:**
  - Encrypt plaintext using DES in CBC mode, with IV set to zero.
  - Send the residue.
  - Forgeries and modifications are likely to be detected.
  - Note: This approach still loses confidentiality because plaintext must be sent.

## Message Authentication Codes (MAC) - Alternative Definition
- **Definition:**
  - A small fixed-size block, meaning the size of the message or plaintext doesn’t affect this.
  - Generated from a message using secret key cryptography.
  - Also known as a checksum.

### Attempt 1
1. Compute residue (MAC) using key `K`.
2. Attach MAC to the plaintext `P`.
3. Encrypt the concatenated quantity `P | MAC` using the same key `K` to produce `C`.
4. Transmit `C` to the receiver.
5. Receiver decrypts received `C'` with `K` to get `P' | MAC'`.
6. Receiver computes MAC(`P'`) using `K` and compares it to the received MAC'.

note: | symbol means "concatenated"

**Exam Question:** Does this approach work?
No.
The last block is always the encryption of zeroes (because the MAC is passed thru DES twice, then SOR'ed??)

Summary
    ECB mode is not secure
       - cbc most commonly used mode of operation
    triple-DEs with 2 keys is much stroner than DEs
       - usually uses EDE in outer chaining mode


Cryptographic hash functions

message of any length -> hash -> a fixed length short message
  
AKA
- message digest
- one way transformation
- one way function
- hash

length of H(M) much shorter than length of m
usually a fixed length: 128 or 160 bits

what does this imply?
performance: easy to compute H(m) where m is message
given H(m), it is infeasible to find m' such that H(m') = H(m) (we'd have to brute force  A LOTTT of messages to figure out which function output matches the original function output)

weak collision resistance 
strong collision resistance (free) computationlally infeasible to find m1,m2 such that H(m1) = H(m2),

why do we have 128 bits or 160 bits in the output of a hash function? why not something small like 10 or 15?
it would be very easy to brute force (why?)
however, if its too long, the overhead is too high to compute
if its too short, loss of strong collision free property. meaning, multiple hashes might end up being related to the same output.
    exam question: birthday paradox analogy -  only 23 people are needed for for at least two people to have the same birthday. this analogy is useful to remember because the peoples birthdays have a collision associated with them. more people == more collisions. 

explanation:
assume all birthdays are equally weighted in probability.
assume there are 365 days in a year.

[equation here]


