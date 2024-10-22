# Finding Theta

![alt](./find-theta.png)

If we want to find theta, we need some information about the projection onto the XY axis.
From the integrand, we can see that the upper bound of Y is sqrt(25-x^2).
So,

Set 0  = sqrt(25-x^2)
-> -1 = cos(theta) (by subtituting rcos(t) into x^2, then simplifying)
we'll find that when cos(theta) = -1, theta = pi. thus, the upper limit of theta is pi.
Here’s an improved and clearer version of your notes, focusing on clarity, accurate mathematical notation, and structure:

---

# Finding \( \theta \)

![Projection of region](./find-theta.png)

To find \( \theta \) (the angular bounds in cylindrical coordinates), we need to analyze the projection of the region onto the \( xy \)-plane.

From the integrand and the setup, we know that the upper bound of \( y \) is \( \sqrt{25 - x^2} \). This represents the top half of a circle with radius 5, which corresponds to the equation of a circle in Cartesian coordinates: \( x^2 + y^2 = 25 \).

### Step-by-Step Process:

1. **Set \( y = 0 \)** to find the angle at the boundary:
   \[
   y = \sqrt{25 - x^2} \quad \Rightarrow \quad x = \pm 5.
   \]

2. **Substitute \( x = r \cos(\theta) \) into the equation:**
   \[
   x = 5 \cos(\theta).
   \]

   This gives us the relationship between \( \theta \) and the \( x \)-coordinate.

3. **Find the limits of \( \theta \):**

   - When \( x = -5 \), we get:
     \[
     5 \cos(\theta) = -5 \quad \Rightarrow \quad \cos(\theta) = -1 \quad \Rightarrow \quad \theta = \pi.
     \]
   
   - When \( x = 5 \), we get:
     \[
     5 \cos(\theta) = 5 \quad \Rightarrow \quad \cos(\theta) = 1 \quad \Rightarrow \quad \theta = 0.
     \]

Thus, the angular limits for \( \theta \) range from \( 0 \) to \( \pi \).

---

### Summary:
By analyzing the projection of the region onto the \( xy \)-plane and using trigonometric relationships, we found that the angular bounds for \( \theta \) are from \( 0 \) to \( \pi \).
