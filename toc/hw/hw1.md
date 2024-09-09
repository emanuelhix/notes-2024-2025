
---

# CS 3823 - Theory of Computation: Homework Assignment 1

**Parker Hix**  
**September 6, 2024**

## Set Theory

i. \( A \) is not a subset of \( B \). \( B \) does not contain \( y \) or \( z \).

ii. \(\{y, z\}\)

iii. \(\{(x, a), (x, b), (x, x), (y, a), (y, b), (y, x), (z, a), (z, b), (z, x)\}\)

iv. \(\{\emptyset, \{x, y, z\}, \{x\}, \{y\}, \{z\}, \{x, y\}, \{x, z\}, \{y, z\}\}\)

---
## Induction 

We want to show that \( f(n) = 11^{n+2} + 12^{2n+1} \) is divisible by 133 for all integers \( n \). In other words, we want to show that \( f(n) = 133x \) for some integer \( x \).

**Base Case:**

Let \( n = 0 \). Then

\[
f(0) = 11^{0+2} + 12^{2 \cdot 0 + 1} = 11^2 + 12^1 = 121 + 12 = 133.
\]

Clearly, \( 133 = 133 \cdot 1 \), so \( x = 1 \) is an integer. Therefore, the base case is true.

**Inductive Hypothesis:**

Assume that for some integer \( k \), the statement is true, i.e.,

\[
f(k) = 11^{k+2} + 12^{2k+1} = 133z
\]

for some integer \( z \). This implies

\[
11^{k+2} = 133z - 12^{2k+1}.
\]

**Inductive Step:**

We need to show that

\[
f(k+1) = 11^{(k+1)+2} + 12^{2(k+1)+1}
\]

is also divisible by 133. Simplify \( f(k+1) \):

\[
f(k+1) = 11^{k+3} + 12^{2k+3}.
\]

We can rewrite \( 11^{k+3} \) using the inductive hypothesis:

\[
11^{k+3} = 11 \cdot 11^{k+2}.
\]

Substitute \( 11^{k+2} \) from the inductive hypothesis:

\[
11^{k+3} = 11 \cdot (133z - 12^{2k+1}) = 133 \cdot 11z - 11 \cdot 12^{2k+1}.
\]

Now, add \( 12^{2k+3} \) to this:

\[
f(k+1) = 11^{k+3} + 12^{2k+3} = 133 \cdot 11z - 11 \cdot 12^{2k+1} + 12^{2k+3}.
\]

Notice that

\[
12^{2k+3} = 12^2 \cdot 12^{2k+1} = 144 \cdot 12^{2k+1}.
\]

Thus,

\[
f(k+1) = 133 \cdot 11z - 11 \cdot 12^{2k+1} + 144 \cdot 12^{2k+1} = 133 \cdot 11z + (144 - 11) \cdot 12^{2k+1}.
\]

\[
f(k+1) = 133 \cdot 11z + 133 \cdot 12^{2k+1}.
\]

\[
f(k+1) = 133 (11z + 12^{2k+1}).
\]

Since \( 11z + 12^{2k+1} \) is an integer, \( f(k+1) \) is divisible by 133. Therefore, the inductive step is true.

Thus, by induction, \( f(n) = 11^{n+2} + 12^{2n+1} \) is divisible by 133 for all integers \( n \).


---