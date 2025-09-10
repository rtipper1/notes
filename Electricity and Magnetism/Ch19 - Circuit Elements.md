___
## Capacitors
In the example below the capacitor is charged. Initially the bulb glows brightly but after some time the bulb goes out.

![[Pasted image 20250310134552.png]]

After the bulb has stopped glowing it you remove the batteries and attach the bulb to the capacitor, the bulb glows again but then gets dimmer and eventually goes out.

![[Pasted image 20250310134634.png]]

Unlike previous circuits there are two different time scales for events in this circuit.

___
## Capacitor Construction
In previous examples we have show a capacitor to be two large metal plates separated by a gap, these capacitors are not practical. Capacitors are typically constructed as shown below.

![[Pasted image 20250310134953.png]]

___
### Discharging a Capacitor
Using what we know we can explain the discharging of a capacitor in terms of the fundamental properties of charge and field.

Consider the circuit below. We will focus on the electric field at a location inside the wire, and the effect it has on the electrons at that location in the wire. Below is the charge and electric field 0.01s after connecting the bulb to the charged capacitor.

![[Pasted image 20250310135311.png]]

Just outside the capacitor we know that the electric field at a location inside the wire points away from the positive plate and toward the negative plate. Electrons will move away from the negative plate and toward the positive plate making them both more neutral.

![[Pasted image 20250310135541.png]]


Eventually the charge distribution will be even across the entire circuit and there will be no electric field to drive current throughout the circuit as shown below.

![[Pasted image 20250310135708.png]]

___
### Charging a Capacitor
We can use a similar reasoning to describe the initial charging of a capacitor in a circuit containing a battery. After about 0.01 seconds the circuit is shown below. Over time the charge will begin to build up on the capacitor plates.

![[Pasted image 20250310135824.png]]

![[Pasted image 20250310140014.png]]
![[Pasted image 20250310140024.png]]

___
### The Effect of the Resistor
The resistance of the resistor determines how quickly the charging or discharging process takes.

___
### Capacitors in Circuits
Capacitors in parallel as shown below can be thought of as one capacitor with plates that have twice the area.

![[Pasted image 20250310140639.png]]


In an isolated bulb as shown below, you can light the bulb despite that fact that there is no conducting path between. Electrons flow from the plate on the right of the capacitor on top through the bulb onto the plate on the right of the capacitor on the bottom.

![[Pasted image 20250310140930.png]]

The circuit shown below is an example of how capacitors can be useful. If you break the connection from the battery to the light bulb the light will remain on for some time due to the capacitor.

![[Pasted image 20250310141059.png]]

___
### Current Node Rule in a Capacitor Circuit
The current node rule applies to capacitors in any state if you consider the capacitor as a whole and not as two separate nodes (plates)

![[Pasted image 20250310141237.png]]

___
### Capacitance
The capacitance $C$ is the proportionality constant between the charge $Q$ and the potential difference $|\triangle V|$ of the capacitor.

$$
Q=C|\Delta V|
$$

___
## Resistors
When looking at the macroscopic picture of circuits we speak less in terms of the fundamental physical mechanisms of circuit behavior. We speak in terms of measurable quantities such as conventional current, resistance, and potential difference.
___
### Conductivity
It is useful to group material properties together and describe the current independent of geometry

$$
\vec{J}=\sigma \vec{E}
$$

The current density $J=(I / A)$; units are $\mathrm{A} / \mathrm{m}^2$.
The conductivity $\sigma=|q| n u$ depends on
- $|q|$, the absolute value of the charge on each carrier;
- $n$, the number of charge carriers per $\mathrm{m}^3$; and
- $u$, the mobility of the charge carriers.

___
### Conductivity With Two Charge Carriers
The conventional current in amperes is the sum of the conventional current due to the positive charges and the conventional current in the same direction due to the negative charges. Therefore the conductivity with two kinds of charge carries is as follows.

$$
\sigma=\left|q_1\right| n_1 u_1+\left|q_2\right| n_2 u_2
$$
___
### Resistance Combines Conductivity and Geometry
It is useful to combine the properties that change the resistance into one quantity. Where resistance $R$ is measured in volts per ampere or ohms $\Omega$ . We have the following

$$
R=\frac{L}{\sigma A}
$$
Note that resistance depends on
- the properties of the material: $\sigma=|q| n u$
- the geometry of the resistor: $L, A$

___
## Conventional Symbols and Terms
### Main Components

![[Pasted image 20250311125700.png]]


![[Pasted image 20250311125712.png]]

___
### Series Resistors
When elements are connected along a single bath with not branches they are in series

![[Pasted image 20250311125758.png]]

The current $I$ is the same everywhere in this series circuit.

$$\mathrm{emf}=\left(R_1+R_2+R_3\right) I=R_{\text {equivalent }} I$$

$$R_{equivalent} = R_1 + R_2 + R_3$$

___
### Parallel Resistors
When resistors are connected via several branches they are said to be connected in parallel.

![[Pasted image 20250311125937.png]]


$$
I=\left(\frac{1}{R_1}+\frac{1}{R_2}+\frac{1}{R_3}\right)(\mathrm{emf})=\frac{\mathrm{emf}}{R_{\text {equivalent }}}
$$

$$
\frac{1}{R_{\text {equivalent }}}=\frac{1}{R_1}+\frac{1}{R_2}+\frac{1}{R_3}
$$
___
## Work and Power in a Circuit