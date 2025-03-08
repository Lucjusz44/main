# Problem 2
### Problem 2: Investigating the Dynamics of a Forced Damped Pendulum

#### Theoretical Foundation
- The equation of motion for a forced damped pendulum:
  $$ \ddot{\theta} + b\dot{\theta} + \sin(\theta) = F \cos(\omega t) $$
- Where:
  - $$ b $$ is the damping coefficient.
  - $$ F $$ is the driving force amplitude.
  - $$ \omega $$ is the driving frequency.

#### Analysis of Dynamics
- For small angles, $$ \sin(\theta) \approx \theta $$ simplifies the equation.
- Resonance occurs when $$ \omega $$ matches the system’s natural frequency.
- Chaotic behavior arises for certain parameter values.

#### Practical Applications
- **Suspension bridges**: Avoiding resonance-induced failures.
- **Clocks**: Understanding damping in mechanical oscillators.

#### Implementation
- Use numerical methods to solve the differential equation.
- Generate phase diagrams, Poincaré sections, and bifurcation plots to analyze behavior.

