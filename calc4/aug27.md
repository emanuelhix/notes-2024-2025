### Multivariable Limit Laws

**Section 14.2**

Multivariable limit laws closely mirror those of single-variable limits. Here’s how they align:

1. **Single-Variable Limit Laws**:
   - **Sum Law**: \(\lim_{x \to a} [f(x) + g(x)] = \lim_{x \to a} f(x) + \lim_{x \to a} g(x)\)
   - **Product Law**: \(\lim_{x \to a} [f(x) \cdot g(x)] = \lim_{x \to a} f(x) \cdot \lim_{x \to a} g(x)\)
   - **Quotient Law**: \(\lim_{x \to a} \frac{f(x)}{g(x)} = \frac{\lim_{x \to a} f(x)}{\lim_{x \to a} g(x)}\) (provided \(\lim_{x \to a} g(x) \neq 0\))
   - **Composition Law**: \(\lim_{x \to a} f(g(x)) = f(\lim_{x \to a} g(x))\) (if \(f\) is continuous at \(\lim_{x \to a} g(x)\))

2. **Multivariable Limit Laws** (for \((x, y) \to (a, b)\)):
   - **Sum Law**: \(\lim_{(x, y) \to (a, b)} [f(x, y) + g(x, y)] = \lim_{(x, y) \to (a, b)} f(x, y) + \lim_{(x, y) \to (a, b)} g(x, y)\)
   - **Product Law**: \(\lim_{(x, y) \to (a, b)} [f(x, y) \cdot g(x, y)] = \lim_{(x, y) \to (a, b)} f(x, y) \cdot \lim_{(x, y) \to (a, b)} g(x, y)\)
   - **Quotient Law**: \(\lim_{(x, y) \to (a, b)} \frac{f(x, y)}{g(x, y)} = \frac{\lim_{(x, y) \to (a, b)} f(x, y)}{\lim_{(x, y) \to (a, b)} g(x, y)}\) (provided \(\lim_{(x, y) \to (a, b)} g(x, y) \neq 0\))
   - **Composition Law**: \(\lim_{(x, y) \to (a, b)} f(g(x, y)) = f\left(\lim_{(x, y) \to (a, b)} g(x, y)\right)\) (if \(f\) is continuous at \(\lim_{(x, y) \to (a, b)} g(x, y)\))

### Continuity in Multivariable Functions

A function \( f(x, y) \) is said to be **continuous** at a point \((a, b)\) if:

\[ \lim_{(x, y) \to (a, b)} f(x, y) = f(a, b) \]

The function \( f \) is continuous on a domain \( D \) if it is continuous at every point \((a, b)\) within \( D \).

### Partial Derivatives

**Working definition**: A partial derivative is just a derivative for multivariable functions.

**Motivating Example: Ideal Gas Law**

The pressure \( P \) of an ideal gas depends on three variables:
- Volume (\( V \))
- Temperature (\( T \))
- Amount of gas (\( n \))

The ideal gas law is given by:

\[ P(V, T, n) = \frac{nRT}{V} \]

where \( R \) is the ideal gas constant (8.314 J/(mol·K)).

- **If \( n \) is fixed** at \( n = a \), the pressure can be expressed as a function of \( V \) and \( T \):
  \[ P(V, T) = \frac{aRT}{V} \]

- **If \( V \) is also fixed** at \( V = b \), the pressure becomes a function of \( T \):
  \[ P(T) = \frac{aRT}{b} \]

This allows us to apply single-variable calculus techniques to these functions.

**Problem Setup: Partial Derivatives**

Consider a function \( f(x, y) \). To find the partial derivative of \( f \) with respect to \( x \) at the point \((a, b)\):

1. **Fix \( y = b \)**, creating a function of \( x \):
   \[ g(x) = f(x, b) \]

2. **Define the partial derivative** with respect to \( x \) at \((a, b)\) as:
   \[ f_x(a, b) = \lim_{h \to 0} \frac{g(a+h) - g(a)}{h} \]

This definition is similar to the limit definition of a derivative in single-variable calculus but applied to functions of multiple variables.

### Example: Finding Partial Derivatives

**Given**: \( f(x, y) = x^3 + x^2 y^3 - 2y^2 \)

**Objective**: Find the partial derivatives \( f_x(2,1) \) and \( f_y(2,1) \)

1. **Partial Derivative with Respect to \( x \)**:

   To find \( f_x(x, y) \):
   \[ f_x(x, y) = \frac{\partial}{\partial x} \left(x^3 + x^2 y^3 - 2y^2\right) \]
   \[ f_x(x, y) = 3x^2 + 2x y^3 \]

   Evaluate at \( (2, 1) \):
   \[ f_x(2, 1) = 3(2)^2 + 2(2)(1)^3 \]
   \[ f_x(2, 1) = 12 + 4 = 16 \]

2. **Partial Derivative with Respect to \( y \)**:

   To find \( f_y(x, y) \):
   \[ f_y(x, y) = \frac{\partial}{\partial y} \left(x^3 + x^2 y^3 - 2y^2\right) \]
   \[ f_y(x, y) = x^2 \cdot 3y^2 - 4y \]
   \[ f_y(x, y) = 3x^2 y^2 - 4y \]

   Evaluate at \( (2, 1) \):
   \[ f_y(2, 1) = 3(2)^2(1)^2 - 4(1) \]
   \[ f_y(2, 1) = 12 - 4 = 8 \]

### Faster Approach: Treat \( y \) as a Constant

When finding \( f_x \), treat \( y \) as a constant and differentiate \( f(x, y) \) with respect to \( x \). Similarly, for \( f_y \), treat \( x \) as a constant and differentiate \( f(x, y) \) with respect to \( y \).

### Geometric Interpretation of Partial Derivatives

**Section 14.3**

Consider \( z = f(x, y) \). The planes \( y = b \) and \( x = a \) intersect the graph of \( z = f(x, y) \) along curves \( C_1 \) and \( C_2 \), respectively.

- **Partial Derivative \( f_x \)**: Measures the rate of change of \( z \) along the curve \( C_2 \) when \( y \) is held constant.
- **Partial Derivative \( f_y \)**: Measures the rate of change of \( z \) along the curve \( C_1 \) when \( x \) is held constant.

### Derivative of Contour Maps

Contour maps show lines where the function \( z = f(x, y) \) is constant. The contour lines represent levels of \( z \), and the partial derivatives describe how \( z \) changes with respect to \( x \) and \( y \) respectively.

To estimate \( f_y(5, 1) \):

1. Calculate the limit:
   \[ f_y(5, 1) = \lim_{h \to 0} \frac{f(5, 1 + h) - f(5, 1)}{h} \]
   - Evaluate the limit using the function \( f(x, y) \).

2. For example:
   \[ f_y(5, 1) = -2 \]

### Summary of Topics

1. **Partial Derivatives**: Understanding and computing partial derivatives.
2. **Examples and Techniques**: Applying partial derivatives to specific functions.
3. **Geometric Interpretation**: Visualizing partial derivatives through curves and planes.
4. **Contour Maps**: Using contour maps to analyze changes in the function \( f(x, y) \).
5. **Estimating Derivatives on Contour Maps**: Techniques for estimating derivatives from contour maps.

