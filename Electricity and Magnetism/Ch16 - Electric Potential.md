## A Review of Potential Energy

The energy of a single particle with charge $q_1$ consists solely of its particle energy.

$$
\text{Particle Energy} = E_{\text{particle}} = mc^2+K
$$
For low speed particles we can approximate the kinetic energy to be
$$
K \approx \frac{1}{2} m v^2 \text { for } v \ll c
$$
---
### Work
Work is a scalar quantity with units of joules. The work done on a particle is the product of the force exerted on the particle times the displacement through which the force acts.
$$
W=\vec{F} \cdot \Delta \vec{l}=\left\langle F_x, F_y, F_z\right\rangle \cdot\left\langle\Delta_x, \Delta_y, \Delta_z\right\rangle=F_x \Delta x+F_y \Delta y+F_z \Delta z
$$
---
### Potential Energy is Associated with Pairs of Interacting Objects
In a system consisting of two or more interacting particles, there can be energy associated with the interactions of particles inside the system. If the rest energy does not change (the particles don't change), then the change in kinetic energy $\triangle K$ can be affected by work done by the surroundings $W_{surr}$ or by work due to interactions between the particles $W_{int}$ 

$$
\Delta K_{\mathrm{sys}}=W_{\mathrm{surr}}+W_{\mathrm{int}}
$$

We can rearrange this equation to put all terms associated only with particles inside the system on the left side of the equation:

$$
\Delta K_{\text {sys }}+\left(-W_{\mathrm{int}}\right)=W_{\text {surr }}
$$

The term $-W_{\text {int }}$, the negative of the work done by internal forces, is called the change in the potential energy $U$ of the system of particles:

**DEFINITION: CHANGE IN POTENTIAL ENERGY OF A SYSTEM**
$$
\Delta U=-W_{\mathrm{int}}
$$


Therefore, the energy principle for a multiparticle system in which the particles do not change identity can be written

**ENERGY PRINCIPLE FOR A MULTIPARTICLE SYSTEM**
$$
\Delta K_{\mathrm{sys}}+\Delta U=W_{\mathrm{surr}}
$$

for a situation in which $\Delta\left(m c^2\right)=0$ and other energy transfers such as $Q$ are zero.

In words, the equation above says that for a system of two or more particles, the change in kinetic energy of the system plus the change in potential of the system is equal to the amount of work done on the system by external forces.

---
## Systems of Charged Objects

In most cases for this course we will neglect the work done by the surroundings $W_{surr}$ and thus the energy principle for systems we are interested in shortens to
$$
\Delta K_{\text {sys }}+\Delta U=0 \quad \text { (zero work done by surroundings) }
$$

### Decrease in U, Increase in K
Consider a system consisting of two uniformly charged plates and a single proton. The proton is initially travelling right and enter the capacitor. While the proton is inside the capacitor an electric force due to the electric field of the capacitor acts on it.

![[Pasted image 20250212190837.png]]

The energy principle applied to this problem is

$$
\Delta K_{\text {proton }}+\Delta U_{\text {electric }}=0
$$
The change in the electric potential energy is equal to the negative of the internal work, the work done on the proton by the electric field of the capacitor.

$$
\begin{aligned}
\Delta U_{\text {electric }} & =-W_{\text {int }}=-\left(F_x \Delta x+F_y \Delta y+F_z \Delta z\right) \\
& =-\left(e E_x \Delta x+e E_y \Delta y+e E_z \Delta z\right)
\end{aligned}
$$
In this case, since $\vec{E} = (E_x, 0, 0)$ and $\triangle \vec{l} = (\triangle x, 0, 0)$

$$
\begin{aligned}
\Delta U_{\text {electric }} & =-\left(e E_x \Delta x+0+0\right) \\
& =-e E_x \Delta x
\end{aligned}
$$
We can see that $\triangle x - x_f - x_i$ is a positive quantity, and $E_x$ is a also positive so the change in the potential energy of the system $-eE_x \triangle x$ is negative.

$$
\Delta K=-\Delta U_{\text {electric }}>0
$$
And the kinetic energy of the proton increases.

---
## Potential Difference In a Uniform Field

As with electric fields it is useful to generalize the potential difference at a given location so that we can determine the change in potential energy independent of the charge of the particle that may move through the region.

To solve this problem we can define $\triangle V$, units joules/coulomb, as the difference in electric potential.
$$
\Delta U_{\text {electric }}=q \Delta V \text { and therefore } \Delta V=\frac{\Delta U_{\text {electric }}}{q}
$$
---
### Path Not Parallel to Electric Field

The path between two locations does not need to be parallel to the electric field.

![[Pasted image 20250212192240.png]]\

We compute the difference in electric potential the same way

$$
\Delta V=-\left(E_x \Delta x+E_y \Delta y+E_z \Delta z\right)\\
$$
$$
\Delta V=-\vec{E} \bullet \Delta \vec{l}=-\left\langle E_x, E_y, E_z\right\rangle \bullet\langle\Delta x, \Delta y, \Delta z\rangle$$
---
### Calculation Field From Potential Difference

We can calculate the electric field from the potential difference. Electric field is simply the negative gradient of the potential
$$
\vec{E}=-\vec{\nabla} V
$$
$$
E_x=-\frac{\partial V}{\partial x}, \quad E_y=-\frac{\partial V}{\partial y}, \quad E_z=-\frac{\partial V}{\partial z}
$$
---
## Sign of Potential Difference

The potential difference $\triangle V$ can be positive or negative, and the sign is extremely important. The sign indicates whether a particular charged particle will gain or lose energy moving from one place to another. 

---
### Direction of Path is Same as Direction of Electric Field
In this case $\triangle V$ is negative. For example
$$
\begin{aligned}
\Delta x & =(0.6-0.4) \mathrm{m}=0.2 \mathrm{~m} \\
\Delta V & =-E_x \Delta x=-\left(200 \frac{\mathrm{~V}}{\mathrm{~m}}\right)(0.2 \mathrm{~m})=-40 \mathrm{~V}
\end{aligned}
$$ As shown in the image below

![[Pasted image 20250212211729.png | center]] 

---
### Direction of Path is Opposite of Electric Field
In this case $\triangle V$ is positive. For example

$$
\Delta V=-E_x \Delta x=-\left(200 \frac{\mathrm{~V}}{\mathrm{~m}}\right)(-0.2 \mathrm{~m})=+40 \mathrm{~V}
$$
As shown in the image below.

![[Pasted image 20250212212429.png]]

---
### Path Perpendicular to Electric Field
In this case $\triangle V$ is 0. For example

$$
\Delta V=-\left(E_x \Delta x+E_y \Delta y\right)=-\left(\left(0 \frac{\mathrm{~V}}{\mathrm{~m}}\right)(-0.2 \mathrm{~m})+\left(300 \frac{\mathrm{~V}}{\mathrm{~m}}\right)(0 \mathrm{~m})\right)=0 \mathrm{~V}
$$

As shown in the image below.

![[Pasted image 20250212212642.png]]

---

## Potential Difference In a Non-Uniform Field

### Two Adjacent Regions with Different Fields

![[Pasted image 20250212215340.png]]


If we have two adjacent regions with different fields all we need to do to calculate $\triangle V$ is divide the path into two pieces. Each displacement vector $\triangle l$ must be small enough that the electric field is uniform in the region it passes. In this case we create a new point C

![[Pasted image 20250212215400.png]]

Now we can calculate the difference in potential along the two segments

$$\Delta V_1=-E_{1 x}\left(x_C-x_A\right)$$
$$\Delta V_2=-E_{2 x}\left(x_B-x_C\right)$$
$$
\Delta V=\Delta V_1+\Delta V_2=-E_{1 x}\left(x_C-x_A\right)-E_{2 x}\left(x_B-x_C\right)
$$
---
### Potential Difference in a Region of Varying Electric Field

The basic idea is to choose a path from the initial location to the final location, break that path into short pieces, evaluate $\triangle V$  for each piece, add up all $\triangle V$'s and check the result;

#### Step 1: Choose a Path and Divide it into Path Vector
* Choose a path from the initial location $i$ to the final location $f$. The potential difference is independent of path but we need to pick one to calculate.

* Divide the path into many short pieces where each is represented as a vector $\triangle \vec{l}$

* At a location near the middle of the path sketch $\vec{E}$ to guide the calculation.

#### Step 2: Write an Expression
* Write an expression for $\triangle V = -\vec{E} \cdot \triangle \vec{l}$

* Each piece of the path contributes an amount $\Delta V=-\vec{E} \bullet \Delta l$ to the potential difference. $\vec{E}$ has a different value at each location on the path. To calculate each $\Delta V=-\vec{E} \bullet \Delta \vec{l}$ we will use the value of $\vec{E}$ midway along $\overrightarrow{\Delta l}$. If we are doing a numerical calculation, we (or a computer) must calculate $\vec{E}$ for each step. If we are setting up an expression that we can try to integrate analytically, our expression for $\vec{E}$ should depend on an integration variable related to position along the path.

#### Step 3: Add Up the Contributions of All the Pieces
- Add up the $\Delta V$ contributions to get $V_f-V_i$. The summation might be done numerically, or in some cases it may be possible to evaluate the summation as the integral $V_f-V_i=-\int_i^f \vec{E} \bullet \overrightarrow{d l}$, where we imagine that each short piece $\overrightarrow{\Delta l}$ becomes an infinitesimal length $\overrightarrow{d l}$.

#### Step 4: Check the Result
* Check that the result makes sense. Most importantly, does the overall sign make physical sense? Does the result have the correct units of volts (joules per coulomb)? Does the result give the right value in special cases where the correct result is known?

---
### Potential Difference Near a Point Charge
Near a point charge the potential difference along a radial path be be written as 

$$
V_f-V_i=\Delta\left(\frac{1}{4 \pi \varepsilon_0} \frac{Q}{r}\right)
$$

See textbook for full proof using steps in section above

---
### General Definition of Potential Difference
The most general definition of potential difference is the integral expression which can be used in any situation is as follows 

$$
\Delta V=-\int_i^f \vec{E} \bullet \overrightarrow{d l}
$$
---
## Path Independence

The potential energy differences depend only on the initial and final states of the system and are independent of path.

---
#### Example
Consider different paths along the capacitor shown below.

![[Pasted image 20250214092733.png]]

We want to calculate the potential difference from point $A$ to point $C$: $\triangle V = V_C - V_A$. Since the electric field has uniform magnitude and direction along the entire path we can write

$$
\begin{aligned}
\Delta V & =\left(-E_x \Delta x+E_y \Delta y+E_z \Delta z\right) \\
& =-E_x\left(x_1-0\right)+0\left(-y_1-0\right)+0.0=-E_x x_1
\end{aligned}
$$
We could just as easily chosen the path shown below.

![[Pasted image 20250214093057.png]]

Which would have given us along the path from $A$ to $B$,

$$
\begin{aligned}
V_B-V_A & =-\left(E_x \Delta x+E_y \Delta y+E_z \Delta z\right) \\
& =-E_x\left(x_1-0\right)+0.0+0.0=-E_x x_1
\end{aligned}
$$

Along the path from $B$ to $C$,

$$
\begin{aligned}
V_C-V_B & =-\left(E_x \Delta x+E_y \Delta y+E_z \Delta z\right) \\
& =-E_x(0)+0\left(-y_1-0\right)+0.0=0
\end{aligned}
$$

Therefore we again find that

$$
V_C-V_A=\left(V_C-V_B\right)+\left(V_B-V_A\right)=-E_x x_1
$$
---
### Two Different Paths Near a Point Charge

Along a path straight away from a stationary charge $Q$ we know

$$
\Delta V=\frac{1}{4 \pi \varepsilon_0} Q\left[\frac{1}{r_f}-\frac{1}{r_i}\right]
$$

Consider the path in the image below study the potential differences of the pieces of the path. Notice that perpendicular to the $\vec E$ or along the radius of the point charge the potential difference is $0$ and otherwise it is described by the equation above.

![[Pasted image 20250214093432.png]]

From $i$ to $$A, \vec{E} \perp \overrightarrow{\Delta l} \rightarrow \Delta V_1=0$$
From $A$ to $B$, $$\Delta V_2=\frac{1}{4 \pi \varepsilon_0} Q\left[\frac{1}{r_3}-\frac{1}{r_1}\right]$$.
From $B$ to $C$, $$\vec{E} \perp \overrightarrow{\Delta l} \rightarrow \Delta V_3=0$$
From $C$ to $f$ ,
$$\Delta V_4=\frac{1}{4 \pi \varepsilon_0} Q\left[\frac{1}{r_2}-\frac{1}{r_3}\right]$$
Adding up these $\Delta V$ 's, we get:

$$
\begin{aligned}
V_f-V_i & =\Delta V_1+\Delta V_2+\Delta V_3+\Delta V_4 \\
& =0+\frac{1}{4 \pi \varepsilon_0} Q\left[\frac{1}{r_3}-\frac{1}{r_1}\right]+0+\frac{1}{4 \pi \varepsilon_0} Q\left[\frac{1}{r_2}-\frac{1}{r_3}\right] \\
& =\frac{1}{4 \pi \varepsilon_0} Q\left[\frac{1}{r_2}-\frac{1}{r_1}\right]
\end{aligned}
$$

Notice that this is the same result as if we had considered the path straight from point $i$ to $f$.

---
### An Arbitrary Path Near a Point Charge

The same is true for any arbitrary path near a point charge as seen in the image below.

![[Pasted image 20250214093947.png]]


All we are concerned with is the initial and final positions

$$
\Delta V=\frac{1}{4 \pi \varepsilon_0} Q\left[\frac{1}{r_f}-\frac{1}{r_i}\right]
$$
---
### Round Trip Potential Difference

This also tells us that a "round trip" as seen in the image below, has a potential difference of $0$

![[Pasted image 20250214094130.png]]

This is fundamentally related to conservation of energy

---
## Potential at One Location
Usually as in previous sections we are interested in the potential difference between two locations. Now we can consider the potential at one location.

The potential at location $A$ is defined as
$$
V_A=V_A-V_{\infty}
$$

By convention the potential at infinity $V_{\infty}$ is defined to be $0$. 

---
### Potential Near a Point Charge
For example, the potential at a location distance $r$ from a single point charge is defined as follows.

$$
V_r=V_r-V_{\infty}=-\int_{\infty}^r \frac{1}{4 \pi \varepsilon_0} \frac{q}{x^2} d x=\left.\frac{1}{4 \pi \varepsilon_0} \frac{q}{x}\right|_{\infty} ^r=\frac{1}{4 \pi \varepsilon_0} \frac{q}{r}
$$

Notice that if $q < 0$, $V_r < 0$, but if $q > 0$, $V_r > 0$ 

![[Pasted image 20250214094758.png]]

---
### Potential and Potential Energy at One Location
Because we know the potential at a location $A$ we can use this to find what the potential energy of a system is at location $A$ 

$$
U_A=q V_A
$$


