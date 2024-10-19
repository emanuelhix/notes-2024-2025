# Triple Integrals (Applications)

## Mass of Rectangular Prism

To calculate the mass of a rectangular prism using a triple integral, you'll first need to define the density function and the dimensions of the prism.

### Example:

Let's say we have a rectangular prism defined by the following bounds:

- \( x \) ranges from \( a \) to \( b \)
- \( y \) ranges from \( c \) to \( d \)
- \( z \) ranges from \( e \) to \( f \)

Assume the density function \( \rho(x, y, z) \) is constant throughout the prism, denoted as \( \rho_0 \).

### Mass Calculation:

The mass \( M \) of the prism can be calculated using the triple integral:

\[
M = \iiint_V \rho(x, y, z) \, dV
\]

For a constant density \( \rho(x, y, z) = \rho_0 \), this simplifies to:

\[
M = \iiint_V \rho_0 \, dV
\]

Now, we can express the volume element \( dV \) as \( dx \, dy \, dz \). Thus, the integral becomes:

\[
M = \rho_0 \iiint_V dV
\]

Substituting the limits for \( x \), \( y \), and \( z \):

\[
M = \rho_0 \int_a^b \int_c^d \int_e^f \, dz \, dy \, dx
\]

### Evaluation:

Evaluating the integral:

1. The innermost integral (with respect to \( z \)):
   \[
   \int_e^f dz = f - e
   \]

2. The next integral (with respect to \( y \)):
   \[
   \int_c^d dy = d - c
   \]

3. The outermost integral (with respect to \( x \)):
   \[
   \int_a^b dx = b - a
   \]

Combining these results:

\[
M = \rho_0 (f - e)(d - c)(b - a)
\]

### Conclusion:

So the mass of the rectangular prism with constant density \( \rho_0 \) is given by:

\[
M = \rho_0 \cdot \text{Volume of the prism} = \rho_0 \cdot (b - a)(d - c)(f - e)
\]

This example illustrates how to set up and evaluate a triple integral to calculate the mass of a rectangular prism in three-dimensional space.
