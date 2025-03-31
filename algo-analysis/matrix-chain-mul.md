# Matrix Chain Multiplication

### Motivation

Given \( \langle A_{1}, A_{2}, \dots, A_{n} \rangle \),  
compute \( A_{1} \times A_{2} \times \dots \times A_{n} \)  

Using the "standard" algorithm for multiplying matrices while minimizing the number of scalar multiplication operations.

### Parenthesizations

#### Motivation

Resolves all ambiguities in how the matrices are multiplied together.  
We are looking for the parenthesization that leads to the least number of scalar multiplications.

#### Fully Parenthesized

A matrix expression is "fully parenthesized" if every multiplication step is unambiguously defined with parentheses, i.e., the order of multiplication is well-defined.
- A single, standalone matrix is considered fully parenthesized.
- If two matrices are multiplied inside parentheses, then they are considered fully parenthesized. If more than two are multiplied without clear grouping, this introduces ambiguity about which to do first.

##### Example

Given \( \langle A_{1}, A_{2}, A_{3} \rangle \):
- \( (A_{1} \times (A_{2} \times A_{3})) \)
- \( ((A_{1} \times A_{2}) \times A_{3}) \)

Are all examples of unambiguous multiplication.

Given \( \langle A_{1} \rangle \):
- \( (A_{1}) \)

Is considered fully parenthesized.

*The idea here boils down to PEMDAS.*  
We must first resolve the innermost parentheses before others, and the order of operations within those parenthesis are not ambiguous.

##### Ambiguous (Not fully parenthesized)

An expression like \( A_{1} \times A_{2} \times A_{3} \) (without parentheses) is ambiguous because it doesn’t specify whether it’s \( (A_{1} \times A_{2}) \times A_{3} \) or \( A_{1} \times (A_{2} \times A_{3}) \).

#### Properties

- Since matrix multiplication is associative, all possible parenthesizations will yield the same result.
- The cost \( T(n) \) of multiplying the matrices depends on the number of scalar multiplications.

## Example to Illustrate Varying Costs of Different Parenthesizations (Different Multiplication Orders)

```lua
-- where A, B, C are rectangular (not necessarily square) matrices
-- the size of A is p x q
-- the size of B is q x r
-- the size of C is p x r
-- the indices of A, B, C are defined as (i, j)
function rectMatMul(A, B, C, p, q, r)
    for i = 1, p do
        for j = 1, r do 
            for k = 1, q do
                -- computes C = C + A * B
                -- the cost of this line of code is p*q*r scalar multiplications
                C[i][j] = C[i][j] + A[i][k] * B[k][j]
            end
        end
    end
end
```

Suppose we are given \( \langle A_{1}, A_{2}, A_{3} \rangle \) with dimensions \( 10 \times 100 \), \( 100 \times 5 \), and \( 5 \times 50 \), respectively.
- \( ((A_{1} \times A_{2}) \times A_{3}) \)
The cost is [... write later, and explain why]