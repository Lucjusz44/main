# Investigating the Dynamics of a Forced Damped Pendulum

## Motivation
A pendulum is a simple system, but when you add **damping** (like friction) and an **external force** (like pushing it periodically), things get interesting. This system can show behaviors like:
- **Resonance**: When the pendulum swings wildly because the external force matches its natural rhythm.
- **Chaos**: When the motion becomes unpredictable and highly sensitive to initial conditions.
- **Quasiperiodic Motion**: When the motion seems almost regular but not quite.

These behaviors help us understand real-world systems like:
- **Energy Harvesting Devices**: Turning vibrations into electricity.
- **Suspension Bridges**: How they handle wind or traffic forces.
- **Electrical Circuits**: Like RLC circuits with an AC power source.

---

## Task

### 1. Theoretical Foundation
The motion of a forced damped pendulum is described by this equation:

$$
\frac{d^2\theta}{dt^2} + \gamma \frac{d\theta}{dt} + \omega_0^2 \theta = F \cos(\omega t)
$$

Where:
- $$ \theta $$: Angle of the pendulum.
- $$ \gamma $$: Damping coefficient (how much friction there is).
- $$ \omega_0 $$: Natural frequency of the pendulum (how fast it swings without forcing).
- $$ F $$: Amplitude of the external force.
- $$ \omega $$: Frequency of the external force.

#### Small-Angle Approximation
For small angles, we can simplify the equation by assuming $$ \sin(\theta) \approx \theta $$. This makes the math easier and gives us approximate solutions.

#### Resonance
Resonance happens when the external force frequency $$ \omega $$ matches the pendulum's natural frequency $$ \omega_0 $$. At this point, the pendulum swings with maximum amplitude.

---

### 2. Analysis of Dynamics
We’ll explore how the pendulum behaves under different conditions:
- **Damping Coefficient ($$ \gamma $$)**: More damping means the pendulum stops swinging faster.
- **Driving Amplitude ($$ F $$)**: A stronger force can make the pendulum swing more wildly.
- **Driving Frequency ($$ \omega $$)**: If the force frequency matches the pendulum's natural frequency, resonance occurs.

We’ll also look at:
- **Regular Motion**: Predictable swinging.
- **Chaotic Motion**: Unpredictable and sensitive to initial conditions.

---

### 3. Practical Applications
This model applies to many real-world systems:
- **Energy Harvesting**: Devices that convert vibrations into electricity.
- **Suspension Bridges**: How they handle wind or traffic forces.
- **Electrical Circuits**: Like RLC circuits with an AC power source.

---

### 4. Implementation
We’ll use Python to simulate the pendulum and visualize its behavior. Here’s the plan:
1. Solve the differential equation numerically.
2. Plot the pendulum’s motion for different damping, force, and frequency values.
3. Create phase diagrams and Poincaré sections to analyze chaotic behavior.

---

## Python Simulation

```python
import numpy as np
from scipy.integrate import solve_ivp
import matplotlib.pyplot as plt

# Parameters
gamma = 0.1  # Damping coefficient
omega0 = 1.0  # Natural frequency
F = 0.5  # Amplitude of external force
omega = 1.2  # Frequency of external force

# Differential equation
def forced_pendulum(t, y):
    theta, dtheta_dt = y
    d2theta_dt2 = -gamma * dtheta_dt - omega0**2 * np.sin(theta) + F * np.cos(omega * t)
    return [dtheta_dt, d2theta_dt2]

# Initial conditions
y0 = [0.1, 0]  # Initial angle and angular velocity

# Time span
t_span = (0, 100)
t_eval = np.linspace(0, 100, 1000)

# Solve the equation
sol = solve_ivp(forced_pendulum, t_span, y0, t_eval=t_eval)

# Plot the results
plt.plot(sol.t, sol.y[0], label="Angle (θ)")
plt.title("Forced Damped Pendulum Motion")
plt.xlabel("Time")
plt.ylabel("Angle (θ)")
plt.grid()
plt.legend()
plt.show()
```

---

## Deliverables
1. **Markdown Document**: This document with explanations and code.
2. **Python Script**: The simulation code provided above.
3. **Graphs**:
   - Motion of the pendulum for different damping, force, and frequency values.
   - Phase diagrams and Poincaré sections to show chaotic behavior.
4. **Discussion**:
   - Limitations of the model (e.g., small-angle approximation).
   - Extensions (e.g., nonlinear damping or non-periodic forces).

---

## Hints and Resources
- Use **Runge-Kutta methods** for solving the differential equation numerically.
- Compare the pendulum to **RLC circuits** or **human gait** for analogies.
- Use Python libraries like `numpy`, `scipy`, and `matplotlib` for simulations and visualizations.

