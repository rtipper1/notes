___
## A Circuit is Not in Equilibrium
We have previously seen situations in which the flow of charges in a system lasts a very short time and eventually finds equilibrium. In contrast to this, an electric circuit is a system that does not reach equilibrium.

___
## Current in Different Parts of a Circuit
What happens to the charges that flow through a circuit? 

___
### The Steady State
The steady state is not to be confused with equilibrium. In a circuit the current keeps flowing at about the same rate for a long time. We call this period of time the steady state

___
### Current at a Node
Kirchoff's Current Law tells us that the current flowing into a node $I_{in} = I_{out}$.

___
## Electric Field and Current
Previously we discussed the Drude model for the motion of mobile electron in a metal and the relationship $\vec{v} = uE$. Where the average drift speed of the mobile electrons is proportional to the magnitude of the electric field.

We know that this is not technically accurate because if it were then current would flow forever.

___
### Electric Field and Drift Speed in Circuit
The electric current $i$ depends on the cross-sectional area $A$ of a wire, since $i = nA\vec{v}$ . 

![[Pasted image 20250303235252.png]]


Since the current must be the same in the thick and thin sections we know that

$$

n A_{\text {thin }} \bar{v}_{\text {thin }}=n A_{\text {thick }} \bar{v}_{\text {thick }} 
$$
$$
\bar{v}_{\text {thin }}=\frac{A_{\text {thick }}}{A_{\text {thin }}} \bar{v}_{\text {thick }}
$$
Since the drift speed must  be greater in the thinner wire, the electric field in the thinner wire must also be larger.

![[Pasted image 20250303235440.png]]

___
### Direction of Electric Field in a Wire
The direction of the electric field in a wire points in the direction of the conventional current of the wire

![[Pasted image 20250303235632.png]]

___
## Surface Charge Distributions
We typically model the distribution of charge about complex surfaces as a collection of point charges. The gradient (derivative of the variation of charge in space) is necessary to produce a uniform field inside a wire in a steady-state circuit.

![[Pasted image 20250309180855.png]]

### Two Uniformly-Charged Rings
First we consider two uniformly charged rings. At a location on the axis midway between the rings, the net electric field is zero. No matter how large the charges on these rings are they cannot create an electric field aligned with the wire.

![[Pasted image 20250309181026.png]]

If we plot ta graph of ring charge vs. position, we see that the slope (gradient) of this plot is zero, this shows that no amount of equally charged rings will create a a uniform electric field pointing along the wire.

![[Pasted image 20250309181336.png]]

### A Constant Gradient of Charge
The simplest configuration of charged rings that has a non-zero gradient of charge is two rings with different amounts of charge. Since one ring is more positive the electric field between the rings is non-zero and points roughly along the axis.

![[Pasted image 20250309181534.png]]

The charge gradient is also now non-zero.

![[Pasted image 20250309181554.png]]

Now we extend our model of the charges on the surface of the wire keeping the gradient constant.

![[Pasted image 20250309181633.png]]

The result is widely spaced rings with a lopsided charge distribution, however, the electric field throughout the interior of the wire is uniform.

A constant gradient of charge density on the surface of a wire produces and electric field inside the wire that is uniform in magnitude along and across the wire and points along the wire.

## Surface Charge Distribution on Circuits
The surface charge distribution on even a simple circuit will be far more complex however we can anticipate the following.

* For long straight sections of wire that are far from other circuit elements there may be a nearly constant gradient of surface charge
* The surface charge gradient will be larges in regions of the circuit in which the electric field is the largest

## Connecting a Circuit
When you complete a circuit by making the final connection, feedback forces a rapid rearrangement of surface charges leading to the steady state. This period of adjustment is called the **initial transient**.

## Feedback
Feedback during the initial transient produces surface charge of the right amount to create and maintain the appropriate steady-state electric field.

Feedback ensures that the surface charge will arrange itself in such a way as to ensure that the net electric field everywhere inside the wire points along the wire and has the appropriate magnitude to drive the appropriate amount of steady-state current.

## Surface Charge and Resistors
We have used surface charges and electric fields to analyze a circuit made up of just a battery and a high-resistance Nichrome wire. In this section we will use the surface-charge model to analyze circuits involving resistors.

### Narrow Resistors and Thick Wires
Consider the following example. A circuit including a battery, wires, and a resistor.

![[Pasted image 20250309183723.png]]

Just after connecting the electric field in the narrow resistor will be about the same as in the wire. Because the number of electrons trying to enter the resistor is a large number $nA_{thick}\vec{v}$, whereas the number of electrons per second passing through the resistor is small $nA_{thin}\vec{v}$, so electrons pile up at location 3 and are scarce at location 4.

Once the steady state has been established the currents must have become the same. If not the surface charge would build up on the resistor.

Since the steady-state current is the same in the thick and thin sections, we have the relation.

$$
nA_{thick}uE_{thick} = nA_{thin}uE_{thin}
$$
$$
E_{thin} = (A_{thick}/A_{thin})E_{thick}
$$

### A Good Analysis Strategy
The analysis in the preceding section is an example of a general strategy for understanding the relationship of charge and field in a circuit.

* Based on $i = nAuE$ draw the distribution of the electric field in the wires.
* Draw an approximate charge distribution that is consistent with the distribution of electric field.

The reason for this order is that the distribution of electric field is fairly simple and can be analyzed nearly exactly whereas the details of the patter of surface charge can be complicated.

The feedback will produce an arbitrarily complicated distribution of surface charge appropriate to the steady-state. The pattern of the electric field gives us quantitative information about the electron current.

### A Wide Resistor
Another kind of resistor is wide rather than narrow but has a low mobility such as a piece of carbon.

![[Pasted image 20250309184918.png]]

In the transient leading up to the steady state, electrons pile up not only on the outer surfaces of the copper and carbon but on the interfaces between the copper and carbon. 

## Energy In A Circuit
We know that over any path the round-trip path integral of the electric field must be zero, as long as the current is steady. From this we find the following

$$
\Delta V_1+\Delta V_2+\cdots=0 \quad \text { along any closed path in a circuit }
$$

This is called Kirchoff's loop rule
___

