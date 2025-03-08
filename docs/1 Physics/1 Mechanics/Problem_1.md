# Problem 1
 # Projectile Motion Analysis

## Theoretical Foundation
Projectile motion follows a parabolic trajectory under uniform gravitational acceleration.  
The horizontal range of a projectile launched at an angle $$ \theta $$ with initial velocity $$ v_0 $$ is given by:

$$
R = \frac{v_0^2 \sin(2\theta)}{g}
$$

The range depends on $$ \theta $$, $$ v_0 $$, and $$ g $$, with a maximum at $$ \theta = 45^\circ $$.

---

## Analysis of the Range
- The range increases with $$ \theta $$ up to $$ 45^\circ $$, then decreases symmetrically.  
- Higher $$ v_0 $$ increases the range, while greater $$ g $$ decreases it.  

---

## Practical Applications
- **Sports**: Optimal angles for throwing and shooting.  
- **Engineering**: Ballistics and projectile launch optimization.  

---

## Implementation
Use Python to simulate projectile motion and visualize the range vs. angle relationship. Below is an example code snippet:

```python
import numpy as np
import matplotlib.pyplot as plt

# Constants
g = 9.81  # gravitational acceleration (m/s^2)
v0 = 50   # initial velocity (m/s)
angles = np.linspace(0, 90, 100)  # angles from 0 to 90 degrees

# Calculate range for each angle
theta_rad = np.radians(angles)
R = (v0**2 * np.sin(2 * theta_rad)) / g

# Plot
plt.plot(angles, R)
plt.title("Range vs. Launch Angle")
plt.xlabel("Launch Angle (degrees)")
plt.ylabel("Range (m)")
plt.grid()
plt.show()