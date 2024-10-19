# Introduction to Cryptography


**plaintext**
- a message in its original, unaltered form
** ciphertext ** 
- the "mangled," unintelligible text
** encryption **
- the process of changing plaintext to ciphertext
** decryption ** 
- the process of changing ciphertext to plaintext

## Computational Difficulty

- Cryptographic algorithms must be computationally efficien to compute, while also be computationally infeasible to crack.
That is, an encryption can be reversed without a key, so long as the "bad guys" guess every possible key.
If we make the number of feasible keys sufficiently large, it will take too long to crack by means of brute force.

### Combination lock example
<embed image with path ./combo-lock.png>
A combination lock typically has 40 digits on it, and the combination can be any 3 of those digits.
So, there are 40^3 possible combinations.
If it takes 10 seconds to try one combination, it will take 10*40^3=640000 seconds to try every combination.
This is equivalent to ~1 week.
Thus, in the worst case scenario, it would take about a week to crack a combination by brute force alone. However, most of the time, the combination is found somewhere around guessing 1/2th of the possible combinations.

