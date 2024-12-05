---
---

## De Morgan's Theorem

### Why?
De Morgan's Theorem allows us to easily change a Boolean function from Sum of Products (SOP) form to Product of Sums (POS) form, or vice versa.

### SOP to POS
Suppose we have \( F = A \cdot B + \overline{A} \cdot C \). This function is in SOP form.

To convert it to POS form:
1. **Invert the Function:**
   \[
   F' = (A \cdot B + \overline{A} \cdot C)'
   \]
2. **Apply De Morgan's Laws:**
   \[
   F' = (A' + B') \cdot (A + C')
   \]
   
Now, the function is in POS form. To convert back to SOP form, apply De Morgan's laws again:

1. **Invert the Function:**
   \[
   G = (A' + B') \cdot (A + C')
   \]
   \[
   G' = [(A' + B') \cdot (A + C')]'
   \]
2. **Apply De Morgan's Laws Separately:**
   \[
   G' = (A' + B')' + (A + C')'
   \]
   \[
   = (A \cdot B) + (\overline{A} \cdot C)
   \]

**Note:** K-maps can also be used for this, but they may be slower and take up more space on paper. 😄

## Dual of Functions

Finding the dual of a Boolean function is similar to converting between POS and SOP forms. I recommend using De Morgan's laws, but K-maps are an alternative if you prefer.

### Example
Given \( F = 1 + B \):
1. **Find the Dual:**
   \[
   F' = (1 + B)' = 0 \cdot B' = 0
   \]
   (0 ANDed with anything is always 0. Note that this fact is useful for bit masking, which we might find useful later in the assembly project.)

## Minterms

Minterms are product terms in which each variable appears exactly once, and they represent conditions where the Boolean function is true (output = 1).

### How to Obtain SOM Canonical Form:
1. **Create a Truth Table:** List all possible combinations of input variables and their corresponding output values.
2. **Identify Minterms:** For each row in the truth table where the output is 1, write down the corresponding minterm.
3. **Combine Minterms:** Sum (OR) all the identified minterms to form the canonical expression.

### Example
Given \( F(A, B, C) = 1 \) when \( A = 0, B = 1, C = 0 \). 

- With the given information, one minterm is \( \overline{A} \cdot B \cdot \overline{C} \).
- If given a full truth table, you can find all minterms and implement the function in SOP form.

Thus, a function \( H \) might be represented as:
\[
H = (A \cdot B) + (\overline{B} \cdot A) + \ldots
\]

## Maxterms

Maxterms are sum terms in which each variable appears exactly once, and they represent conditions where the Boolean function is false (output = 0).

### How to Obtain POM Canonical Form:
1. **Create a Truth Table:** List all possible combinations of input variables and their corresponding output values.
2. **Identify Maxterms:** For each row in the truth table where the output is 0, write down the corresponding maxterm.
3. **Combine Maxterms:** Take the product (AND) of all the identified maxterms to form the canonical expression.

### Example
Given \( F(A, B, C) = 1 \) when \( A = 0, B = 1, C = 0 \).

- With the given information, one maxterm is \( A + \overline{B} + C \).
- If given a full truth table, you can find all maxterms and implement the function in POM form.

Thus, a function \( H \) might be represented as:
\[
H = (A + B) \cdot (\overline{B} + A) \cdot \ldots
\]

**Note:** Expressing functions in minterms or maxterms is considered a "canonical" form (standard, but not necessarily simplified).

---