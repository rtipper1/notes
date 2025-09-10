When a compass needle turns and points in a particular direction, we say that there is a "magnetic field" pointing in that direction. 
___
## Electron Current
Magnetic fields are associated with moving charges. A current in a wire provides a convenient source of moving charges.

The electron current $i$ is the number of electrons per second that enter a section of a conductor.

In a circuit with steady current flowing, the current $i$ is the same in every section of a wire of uniform thickness and composition.

![[Pasted image 20250224103645.png]]
---
## Detecting Magnetic Fields
We can use a compass as a detector of magnetic fields in the same way we used a piece of invisible tape to indicate the presence of an electric field.

The vector sum of the Earth's magnetic field $\vec{B}_{Earth}$ plus the magnetic field $\vec{B}_{wire}$ of the current-carrying wire makes a net magnetic field $\vec{B}_{net}$ as show in the image below.

![[Pasted image 20250224104942.png]]

The magnitudes of $\vec{B}_{Earth}$ and $\vec{B}_{wire}$ are similar.
___
## Biot-Savart Law: Single Moving Charge
A moving point charge not only makes an electric field but also makes a magnetic field which curls around the moving charge.

![[Pasted image 20250224105307.png]]

The magnetic field of a moving point charge is described by the Biot-Savart law for a single charge.

$$
\vec{B}=\frac{\mu_0}{4 \pi} \frac{\vec{q} \times \hat{r}}{r^2}
$$
Where
$$
\frac{\mu_0}{4 \pi}=1 \times 10^{-7} \frac{\mathrm{~T} \cdot \mathrm{~m}^2}{\mathrm{C} \cdot \mathrm{~m} / \mathrm{s}} \text { exactly }
$$
___
### Vector Cross Product
The Biot-Savart Law involves a vector cross product $\vec{v} \times \hat{r}$. In vector mathematics the cross product is an operation that combines two vectors to produce a third vector that is perpendicular to the plane defined by the original vectors.

![[Pasted image 20250224105703.png]]

The magnitude of the cross product is defined as show below.
$$
|\vec{A} \times \vec{B}|=|\vec{A}||\vec{B}| \sin \theta
$$
Note that $\theta$ is always between 0 and 180 degrees.
___
### Direction of Cross Product (Right Hand Rule)

1. Draw the vectors $\vec{A}$ and $\vec{B}$ so their tails are in the same location.

2. Point the fingers of your right hand in the direction $\vec{A}$.

![[Pasted image 20250224110238.png]]

1. Fold your fingers through the angle $\theta$ toward $\vec{B}$. 

2. Stick your thumb out, it will point in the direction of the vector $\vec{A} \times \vec{B}$


![[Pasted image 20250224110249.png]]

___
### Formal Definition of  Cross Product
The direction and magnitude of a cross product is given by

$$
\vec{A} \times \vec{B}=\left\langle A_y B_z-A_z B_y, A_z B_x-A_x B_z, A_x B_y-A_y B_x\right\rangle
$$
$$
|\vec{A} \times \vec{B}|=|\vec{A}||\vec{B}| \sin \theta
$$
___
## Relativistic Effects
Consider the following thought experiment, Jack is sitting at a desk with charged pieces of tape attached to the edge of his desk. Jack does not observe a magnetic field due to the take because the charges are not moving.

Jill runs past jacks desk with a sensitive compass and observes a magnetic field. Because we is in motion the charged tape is moving relative to the compass and thus has a velocity.

The important takeaway is the use the velocity of the charges as you observe them in your frame of reference.
___
### Retardation
When you move a charge, the electric field due to that charge does not change immediately. The same is true for a magnetic field. If you suddenly change the current in a wire, the magnetic field at some distance from the source of the magnetic field stays the same for some time.
___
## Electron Current and Conventional Current
In order to apply the Biot-Savart law to predict the magnitude and direction of the magnetic field associated with a current we need to know the number of moving charges making the field and how fast they are moving
___
### Electron Current
The electron current $i$ is rate at which electrons pass through a section of a wire and is described as follows.
$$
i=n A \bar{v}
$$
Where $n$ is the mobile electron density, $A$ is the cross-sectional area of the wire, and $\vec{v}$ is the average drift speed of the electrons. $i$ has units electrons per second.
___
### Conventional Current
Conventional current is defined as the amount of charge in coulombs passing by a point per second and is described as follows.
$$
I=|q| n A \bar{v} \quad \text { (coulombs per second, or amperes) }
$$
Where the charge $|q|$ of a metal is $e$. 
___
### Electric Field and Current
A non-zero electric field is necessary to maintain a current in a conductor. If we know the electric field we can predict the current in a wire.

$$
I=|q| n A \bar{v}=|q| n A(u E)
$$

___
## The Biot-Savart Law for Currents
We are often interested in the magnetic field due to a current flowing through a wire therefore we need to adapt the Biot-Savart law. 

$$
\Delta \vec{B}=\frac{\mu_0}{4 \pi} \frac{I \Delta \vec{l} \times \hat{r}}{r^2}
$$

See the textbook for the full derivation.

The key point is that there are $nA\triangle l$ electrons in a short length of wire, each moving with average speed $\vec{v}$ so that the sum of all $q\vec{v}$ contributions is $$
(n A \Delta l)|q| \bar{v}=(|q| n A \bar{v}) \Delta l=I \Delta l
$$___
## The Magnetic Field of Current Distributions
We will use the following four step approach to find the magnetic field of distributions of current in wire.

1. Cut up the current distribution into pieces; draw $\triangle \vec{B}$ for a representative piece.
2. Write an expression for the magnetic field due to one piece.
3. Add up the contributions of all pieces.
4. Check the result.
___
### Applying Biot-Savart: Long Straight Wire
Using the procedure outlined above we can calculate the magnetic field due to a long straight wire

#### Step 1: Cut Up the Distribution into Pieces and Draw $\triangle \vec{B}$
Consider a wire of length $L$. We can cut up the wire into very short sections of length $\triangle y$. We will calculate the magnetic field a perpendicular distance $x$ away form the center.

![[Pasted image 20250224115207.png]]

#### Step 2: Write an Expression for the Magnetic Field Due to One Piece
We will place the origin at the center of the wire.

$$
\begin{aligned}
\vec{r} & =\langle x, 0,0\rangle-\langle 0, y, 0\rangle=\langle x,-y, 0\rangle \\
|\vec{r}| & =\left[x^2+(-y)^2\right]^{1 / 2}=\left[x^2+y^2\right]^{1 / 2} \\
\hat{r} & =\frac{\vec{r}}{r}=\frac{\langle x,-y, 0\rangle}{\left[x^2+y^2\right]^{1 / 2}}
\end{aligned}
$$

Since the location of one piece is specified by $y$, this will be the integration variable. We can express $\Delta \vec{l}$ in terms of $y$ :
$$
\begin{aligned}
\overrightarrow{\Delta l} & =\Delta y(0,1,0) \\
\Delta \vec{B} & =\frac{\mu_0}{4 \pi} \frac{I \Delta \overrightarrow{l \times} \times \hat{r}}{\left(x^2+y^2\right)}=\frac{\mu_0}{4 \pi} \frac{I \Delta y\langle 0,1,0\rangle}{\left(x^2+y^2\right)} \times \frac{\langle x,-y, 0\rangle}{\left[x^2+y^2\right]^{1 / 2}}
\end{aligned}
$$

Evaluating the cross product, we get:

$$
\langle 0,1,0\rangle \times\langle x,-y, 0\rangle=\langle 0,0,-x\rangle
$$

Our final expression for $\Delta \vec{B}$ is:

$$
\Delta \vec{B}=-\frac{\mu_0}{4 \pi} \frac{I x \Delta y}{\left(x^2+y^2\right)^{3 / 2}}\langle 0,0,1\rangle
$$

Every piece of the straight wire contributes some magnetic field in the $-z$ direction, so we need to calculate only the $z$ component.

#### Step 3: Add Up the Contributions of All the Pieces
By letting $\Delta y \rightarrow 0$, we can calculate the magnitude $B$ by writing the sum as an integral:

$$
B=\frac{\mu_0}{4 \pi} I x \int_{y=-L / 2}^{y=+L / 2} \frac{d y}{\left(x^2+y^2\right)^{3 / 2}}
$$

Fortunately, this integral can be found in standard tables of integrals:

$$
\begin{aligned}
B & =\frac{\mu_0}{4 \pi} I x\left[\frac{y}{x^2 \sqrt{x^2+y^2}}\right]_{y=-L / 2}^{y=+L / 2} \\
B & =\frac{\mu_0}{4 \pi} I x\left[\frac{L / 2}{x^2 \sqrt{x^2+(L / 2)^2}}-\frac{-L / 2}{x^2 \sqrt{x^2+(L / 2)^2}}\right] \\
B & =\frac{\mu_0}{4 \pi} \frac{L I}{x \sqrt{x^2+(L / 2)^2}}
\end{aligned}
$$

An extremely important case is that of a very long wire $(L \gg x)$ or, equivalently, the magnetic field very near a short wire $(x \ll L)$.

In the case where $L$ is much larger then $x$.
$$
B \approx \frac{\mu_0}{4 \pi} \frac{2 I}{x} \quad \text { if } L>x
$$
#### Summary
The magnetic field due to a long straight wire is 
$$
B_{\text {wire }}=\frac{\mu_0}{4 \pi} \frac{L I}{r \sqrt{r^2+(L / 2)^2}}
$$

for length $L$, conventional current $I$, a perpendicular distance $r$ from the center of the wire.
$$
B_{\text {wire }} \approx \frac{\mu_0}{4 \pi} \frac{2 I}{r} \quad \text { if } L \gg r
$$

#### Step 4: Check the Result
See textbook

---
## Magnetic Field of Circular Loop of Wire
Here we calculate the magnetic field of a circular loop of wire that carries current $I$. We only do the easiest case, the magnetic field along the axis of the loop.

![[Pasted image 20250303230012.png]]

The magnetic field of the loop along the axis is

$$
B_{\text {loop }}=\frac{\mu_0}{4 \pi} \frac{2 \pi R^2 I}{\left(z^2+R^2\right)^{3 / 2}}
$$

See the textbook for the full calculation.

___
### Qualitative Features of Mag Field of Loop of Wire
Very far from the loop the magnetic field due to the loop can be described by the following equation.

$$
\frac{\mu_0}{4 \pi} \frac{2 \pi R^2 I}{z^3}
$$

The following shows the magnetic field due to a loop of wire along the axis and perpendicular to the axis.

![[Pasted image 20250303230426.png]]

___
### Special Right-Hand Rule for Current Loops
There is another “right-hand rule” that is often used to get the direction of the magnetic field along the axis of a loop. Let the fingers of your right hand curl around in the direction of the conventional current, and your thumb will point in the direction of the magnetic field at any location on the axis.

___
## Magnetic Dipole Moment
Similar to the electric dipole moment we can define a magnetic dipole moment for the magnetic field due to a loop along the axis. 

$$
B_{\text {axis }} \approx \frac{\mu_0}{4 \pi} \frac{2 \mu}{r^3}
$$
Where the magnetic dipole moment $\mu = IA$ or $\mu = NIA$ if there are $N$ loops. The magnetic dipole moment $\vec{\mu}$ is considered to be a vector pointing in the direction of the magnetic field along the axis.

![[Pasted image 20250303230823.png]]

___
## Magnetic Field of a Bar Magnet
___
### A Magnet is a Magnetic Dipole
The pattern of directions of magnetic field around a bar magnet is very similar to the patter of directions of the magnetic field around a current loop, and to the pattern of the electric field around a dipole.

![[Pasted image 20250303231122.png]]


___ 
### Magnetic Filed of Earth
The magnetic field of the Earth has a pattern that looks like that of a bar magnet. 

![[Pasted image 20250303231403.png]]

___
### Dependence on Distance
The horizontal component of the earths magnetic field which is the component that affects a horizontally held compass is different at different latitudes depending on the distance from the poles.

![[Pasted image 20250303231511.png]]

___