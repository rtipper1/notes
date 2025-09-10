### Early Systems

Early on the physical memory of a machine looked something like the image below. The operating system and whatever program had currently been loaded into memory.

![[Pasted image 20250205114135.png]]

This is very inefficient as only one process can run at the same time and you have to manually switch between programs.
### Multiprogramming and Time Sharing

**Multiprogramming** is when multiple programs can be loaded into memory at the same time and the operating system can switch quickly between them. Having multiple programs loaded into memory at the same time makes protection a big issue. 

![[Pasted image 20250205114548.png]]

## The Address Space

The address space is an easy to use abstraction of physical memory. The address space of a process contains all of the memory state of the running program. The address includes the following for an individual process.

* The **code** of the program (instructions) are stored in the address space.
* While the program is running it uses a **stack** to keep track of the function call chain and local variables
* The **heap** is used for dynamically allocated user managed memory such as the memory you allocate in a call to malloc() or new\

The address space is the abstraction that the OS is providing to the running program. The program isn't  really in memory at physical address 0-16 KB.

When the OS does this we say it is **virtualizing memory**. When process A in Figure 13.2 tries to perform a load at address 0, somehow the OS, in tandem with hardware support will have to make sure the load goes to 320 KB to 0.

## Goals of Virtualization

* **Transparency** - The program should not be aware of the fact that its memory is virtualized
* **Efficiency** - Virtualization should not cause the program to run slower and should not have much memory overhead due to the structures need to support virtualization
* **Protection** - Processes should not be able to access the memory of other address spaces.

## Summary 

Virtual Memory is responsible for providing the illusion of a large, consistent, private address space to each program running on the OS.