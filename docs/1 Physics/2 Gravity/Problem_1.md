# Problem 1
# Gravity: Orbital Period and Orbital Radius

## Motivation
When objects orbit each other (like planets around the Sun or the Moon around Earth), there’s a special relationship between how long it takes to complete an orbit (**orbital period**) and how far apart they are (**orbital radius**). This relationship is called **Kepler’s Third Law**, and it’s super important for understanding how gravity works in space.

---

## Task

### 1. Derive the Relationship
For circular orbits, Kepler’s Third Law says:
T 2∝R 3
Where:
- $T$ = Orbital period (time to complete one orbit).
- $R$ = Orbital radius (distance between the two objects).

This means:
- If you double the orbital radius, the orbital period increases by a factor of $\sqrt{8}$ (about 2.83).
- If you triple the orbital radius, the orbital period increases by a factor of $\sqrt{27}$ (about 5.2).

This relationship comes from balancing gravity (which pulls objects together) with the centripetal force (which keeps them moving in a circle).

---

### 2. Implications for Astronomy
Kepler’s Third Law is super useful for:
- **Calculating Planetary Masses**: If you know the orbital period and radius of a moon or satellite, you can calculate the mass of the planet it’s orbiting.
- **Determining Distances**: If you know how long it takes a planet to orbit the Sun, you can figure out how far away it is.
- **Satellite Orbits**: Engineers use this law to design orbits for satellites and space stations.

---

### 3. Real-World Examples
- **The Moon’s Orbit**: The Moon takes about 27.3 days to orbit Earth at an average distance of 384,400 km.
- **Earth’s Orbit**: Earth takes about 365.25 days to orbit the Sun at an average distance of 149.6 million km.
- **Satellites**: GPS satellites orbit Earth at a distance of about 20,200 km and take 12 hours to complete one orbit.

---

### 4. Implementation
We’ll use Python to simulate circular orbits and verify Kepler’s Third Law. Here’s the plan:
1. Simulate a circular orbit using Newton’s laws of motion and gravity.
2. Calculate the orbital period and radius.
3. Plot the relationship between $T^2$ and $R^3$ to verify Kepler’s Third Law.

---

## Python Simulation

```python
import numpy as np
import matplotlib.pyplot as plt

# Constants
G = 6.67430e-11  # Gravitational constant (m^3 kg^-1 s^-2)
M = 5.972e24  # Mass of Earth (kg)

# Function to calculate orbital period
def orbital_period(R):
    return 2 * np.pi * np.sqrt(R**3 / (G * M))

# Orbital radii (in meters)
R_values = np.linspace(6.371e6, 4e8, 100)  # From Earth's surface to Moon's orbit

# Calculate orbital periods
T_values = orbital_period(R_values)

# Plot T^2 vs. R^3
plt.plot(R_values**3, T_values**2, label="T² vs. R³")
plt.title("Kepler's Third Law: T² ∝ R³")
plt.xlabel("Orbital Radius Cubed (R³)")
plt.ylabel("Orbital Period Squared (T²)")
plt.grid()
plt.legend()
plt.show()
```

---

## What Will You See?
- The graph will show a straight line, proving that $T^2$ is proportional to $R^3$.
- This confirms Kepler’s Third Law for circular orbits.

---

## Deliverables
1. **This Document**: With explanations and code.
2. **Python Script**: The simulation code above.
3. **Graphs**:
   - A plot of $T^2$ vs. $R^3$ to verify Kepler’s Third Law.
   - A visualization of circular orbits.
4. **Discussion**:
   - How this relationship applies to elliptical orbits (where orbits are oval-shaped).
   - Examples of other celestial bodies, like binary star systems.

---

## Hints and Resources
- Use **Newton’s Law of Gravitation** to derive the relationship.
- For elliptical orbits, Kepler’s Third Law still applies, but you use the **semi-major axis** (half the longest diameter of the ellipse) instead of the radius.
- Use Python libraries like `numpy` and `matplotlib` for calculations and graphs.
