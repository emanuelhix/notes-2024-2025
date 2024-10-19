Sure! Let's go over the solution step by step.

### Problem Overview:
You are asked to find the **average value** of the function:

\[
f(x, y, z) = 3x^2z + 3y^2z
\]

over the solid region enclosed by the paraboloid:

\[
z = 9 - x^2 - y^2
\]

and the plane \( z = 0 \).

### Step 1: Formula for Average Value
The formula for the average value of a function \( f(x, y, z) \) over a solid region \( E \) is:

\[
f_{\text{ave}} = \frac{1}{V(E)} \int \int \int_E f(x, y, z) \, dV
\]

Where \( V(E) \) is the volume of the region \( E \), and the integral is over the region.

### Step 2: Convert to Cylindrical Coordinates
Since the problem involves circular symmetry due to the paraboloid and the circular base, cylindrical coordinates are more convenient. The cylindrical coordinates are given by:

- \( x = r \cos \theta \)
- \( y = r \sin \theta \)
- \( z = z \)

The equation of the paraboloid becomes:

\[
z = 9 - r^2
\]

The region is enclosed by the paraboloid and the plane \( z = 0 \), so the bounds for \( z \) are from \( 0 \) to \( 9 - r^2 \), and the bounds for \( r \) are from \( 0 \) to \( 3 \) (since \( r = 3 \) corresponds to \( z = 0 \)).

Also, the bounds for \( \theta \) are from \( 0 \) to \( 2\pi \), covering the full rotation around the z-axis.

### Step 3: Set up the Integral
The function \( f(x, y, z) = 3x^2z + 3y^2z \) becomes:

\[
f(r, \theta, z) = 3r^2z
\]

in cylindrical coordinates because \( x^2 + y^2 = r^2 \).

The volume element \( dV \) in cylindrical coordinates is \( r \, dz \, dr \, d\theta \).

Now, we can write the integral for the average value of \( f(r, \theta, z) \):

\[
f_{\text{ave}} = \frac{1}{V(E)} \int_0^{2\pi} \int_0^3 \int_0^{9 - r^2} 3r^2z \cdot r \, dz \, dr \, d\theta
\]

### Step 4: Compute the Volume \( V(E) \)
First, we compute the volume of the region \( E \). The volume is given by:

\[
V(E) = \int_0^{2\pi} \int_0^3 \int_0^{9 - r^2} r \, dz \, dr \, d\theta
\]

The integral for the volume \( V(E) \) evaluates to \( \frac{81\pi}{2} \).

### Step 5: Compute the Integral for the Function
Next, we compute the integral of the function \( 3r^2z \) over the region \( E \). The integral is:

\[
\int_0^{2\pi} \int_0^3 \int_0^{9 - r^2} 3r^2z \cdot r \, dz \, dr \, d\theta
\]

This integral evaluates to \( 81 \).

### Step 6: Calculate the Average Value
Finally, we calculate the average value of the function by dividing the result of the integral by the volume:

\[
f_{\text{ave}} = \frac{81}{\frac{81\pi}{2}} = \frac{81}{4}
\]

### Final Answer:
The average value of the function is:

\[
f_{\text{ave}} = \frac{81}{4}
\]
