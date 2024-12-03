# Post Midterm Review 

## Exercise 1 (True or False)
a. epslion \in A*, where A is an arbitrary language
True
b. for every finite language A, we can provide a regular expression that generates A.
True
Justification: We have a finite number of strings, so technically we could just create a string that ORs them all together.
c. Let N = {1,2,3, ...}. Let A = {i | i = m^3 for some m \in N}. Then, let B = N x N x N . Is A = B?
False
Justification: A contains the cube of all natural integers, but `N x N` is a cartesian product.
d. A' = {w in \Sigma* | w \notin A}, True or false: A is regular => A' is also Regular.
True
e. True or False: if A is regular, then any subset of A is also regular. 
False.
Justification: let A = \sigma*. This language is regular. 
One subset of A* is `(0^n)1^n`.
The intuition, I think, behind saying "True" (which is wrong) is that most people think of a regular language as being finite. That is a misconception.
So, they think if they slice a finite language to get a subset of it, that language is finite. That is true, but not all regular languages are finite.

## Exercise 2 
Produce strings that belong and don't belong in the language.

a. ba(ab)*
Belongs = {ba, baab, baabab, ...}

b.  ab + bababa
Belongs = {ab, bababa}
This language is finite.

c. ab(a+b)*ba

Belong = {abba, ababa, abbba, abaaba, abbbba, ...}
Justification: (a+b)* = {a, b, aa, bb, aaa, bbb, aaa, bbb, ...}

## Exercise 3

Draw a truth table for A->B.

| A  |  B | A->B |
|---|---| ---    |
|  F | F  |     T   |
|  F | T  |     T   |
|  T | F  |     F   |
|  T | T  |     T   |

Variation of the cards example:
if under 21, then non-alcoholic drinks. 

`[ 20 ] [ 23 ] [ coke ] [ vodka ]`

which cards do we flip to verify the rule?

flip 20, because that makes "if under 21" true.
flip vodka, because ... 

## Exercise 4 

## Exercise 5

## Exercise 6

\Sigma = {0, 1, +, =}

Add = {a=b+c | a,b,c are unsigned binary integars and a is the sum of b and c}

Proof by contradiction:

Assume ADD is regular with pumping length `p`.
Let s = 1^p = 0^p + 1^p.
s \in ADD, and |s| = 3p+2 >= p.
(*Note: The +2 comes from the equal sign and the plus sign*).

This satisfies the condition for using the pumping lemma, so 
let s = xyz such that |xy| <= p, |y| > 0