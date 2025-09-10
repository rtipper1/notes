## Electric Charge and Force

### Point Charges

Object which may be positive or negatively charged whose radius is so small relative to the other objects that it interacts with that it can be mathematically represented by a single mathematical point in space such as electrons and protons.
### The Coulomb Force Law for Point Particles

Describes the magnitude of the electric force between two point-like charged objects.
$$ |\vec{F}| = F = \frac{1}{4\pi \epsilon_0}\frac{|Q_{1}Q_{2}|}{r^{2}}$$
Where $Q_1$ and $Q_2$ are the magnitudes of the charges and $r$ is the distance between them
* The force acts along a line between the two objects.
* Like charges repel; unlike charges attract.

### Units and Constants

![[Pasted image 20250120213836.png]]

* Oofpez - $\frac{1}{4\pi\epsilon_0}$ = $9 \times 10^{9}\space N \times m^{2}/C^2$

## Electric Fields

$$ \vec{F_{2}}= q_2\vec{E_1}$$
This says that the force on particle 2 is determined by the charge of particle 2 and the electric field $\vec{E_{1}}$ made by all other charged particles in the vicinity.

![[Pasted image 20250120215046.png]]

How can we find the electric field at a given charge?
$$ \vec{E} = \vec{F}/q$$
says that we can find the magnitude and direction of $\vec{E}$ by measuring the force on a known charge $q$. Note that a positive charge experiences a force in the direction of the electric field at its location, a negative charge experiences a force in the opposite direction as shown below.

![[Pasted image 20250120215702.png]]

### No "Self Force"

A point charge is not affected by its own electric field. A point charge does not exert a force on itself.

### Physical Concept of "Field"

A field is a physical quantity that has a value at every location in space, its value can be a scalar or a vector such as.

* Heat map - Scalar temperature value at every location in space.
* Airflow map - Vector air direction at every location in space.

### Electric Field of a Point Charge

The electric field at the observation location marked by "x" is:
$$ \vec{E_{1}}= \frac{1}{4\pi\epsilon_0}\frac{q_1}{|\vec{r}|^{2}}\hat{r}$$
* $q_1$ - source charge
* $\vec{r}$ - vector from source charge to observation location
* $\hat{r}$ - unit vector from source charge to observation location
* $|\vec{r}|$ - distance between source charge and observation location
![[Pasted image 20250120221141.png]]

Note that if the charge of the source charge is negative then the electric field is in the direction of $-\hat{r}$.
![[Pasted image 20250120221213.png]]
### Electric Field of a Uniformly Charged Sphere

A spherical object of radius $R$ with charge $Q$ uniformly spread out over its surface produces and electric field with the following properties similar to point charges.

$$
\vec{E_{sphere}}= \frac{1}{4\pi\epsilon_0}\frac{Q}{r^{2}}\hat{r} \enspace \text{  for } r > R \text{ (outside the sphere)}
$$
$$
\vec{E_{sphere}}= \vec{0} \enspace \text{  for } r < R \text{ (inside the sphere)}
$$
![[Pasted image 20250120223030.png]]


## Superposition of Electric Fields

The net electric field at a location in space is the vector sum of the individual electric fields contributed by all charged particles located elsewhere.

![[Pasted image 20250120223351.png]]

Above we could have calculated the force on $q_3$ by using Coulomb's law directly, however, it is advantageous to use the concept of Electric field because once we calculate the field $\vec{E_{net}}$ due to $q_1$ and $q_2$ you can calculate the force $Q\vec{E_{net}}$ on any amount of charge $Q$.

## Electric Field of a Dipole

An electric dipole consists of two equally but oppositely charged point-like objects, separated by a distance $S$.

![[Pasted image 20250120225824.png]]

With the superposition principle we can calculate the electric field due to a dipole at any location in space. In particular we are interested in two locations, along the axis and perpendicular to the axis of the dipole.

![[Pasted image 20250120225939.png]]


![[Pasted image 20250120230000.png]]
### Approximation Far from Dipole

The equation for the electric field of a dipole along the axis of the dipole and perpendicular to it can be simplified using the following approximation.

$$\text{if } r >> s \text{, then   } (r - \frac{s}{2})^{2} \approx (r + \frac{s}{2})^{2}\approx r^2$$
Therefore...

$$
|\vec{E_{axis}}| \approx \frac{1}{4\pi\epsilon_0}\frac{2qsr}{r^{4}}= \frac{1}{4\pi\epsilon_{0}}\frac{2qs}{r^3}
$$
$$
|\vec{E_{\perp}}| \approx \frac{1}{4\pi\epsilon_0}\frac{2qsr}{r^{4}}= \frac{1}{4\pi\epsilon_{0}}\frac{qs}{r^3}
$$


In general the electric field of a dipole looks as follows.

![[Pasted image 20250120230035.png]]

### Electric Dipole Moment

The electric field of a dipole is proportional to the product $qs$, called the "electric dipole moment" denoted $p$.

$$
p = qs \enspace \text{(electric dipole moment)}
$$
We can rewrite the expressions for the electric field of a dipole using the approximation shown above and in terms of the dipole moment.

$$
|\vec{E_{axis}}| = \frac{1}{4\pi\epsilon_{0}} \frac{2p}{r^{3}} \enspace \text{at a location on the dipole axis, if } r >> s
$$
$$
|\vec{E_{\perp}}| = \frac{1}{4\pi\epsilon_{0}} \frac{2p}{r^{3}} \enspace \text{at a location perpendicular to the dipole axis, if } r >> s
$$
### Dipole Moment as a Vector

The dipole moment can be defined as a vector $\vec{p}$ that points from the negative charge to the positive charge, with magnitude $p=qs$. 
