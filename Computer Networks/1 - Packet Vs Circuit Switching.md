___
## Network Abstraction
Think about a generic computer network such as the one below.
![[Pasted image 20250910181044.png]]

There is too much going on here for us to reason about it. We must abstract the network to its simplest representation. We do this by defining three key components.

1. **End Hosts**: Generate and receive data
2. **Links**: Carry data from one point to another
3. **Routers**: Forward data along a network path

Using these three key components we can abstract any network as a graph

![[Pasted image 20250910181341.png]]

___
## Route Problem
Abstracting the network as a graph reduces the routing problem. How do we find a route from Alice to Netflix? We can simply find a path in the graph from Alice to Netflix using some graph algorithm such as Dijkstra's.
![[Pasted image 20250910181638.png]]

___
## Network Sharing
If more than one user wants to communicate with the same resources at the same time they must share some network resources. 

![[Pasted image 20250910181947.png]]

This is a fundamental problem. How is this handled assuming no coordination and assuming that access is initiated by users.

There are two main ways this is handled.

1. **Reservation** (Circuit Switching)
2. **On-Demand** (Network Switching)

___
## Circuit Switching
