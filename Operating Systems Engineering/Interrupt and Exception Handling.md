There are two main types of interrupts that are very different. Hardware and software interrupts
___
## Hardware Interrupts
Hardware interrupts are how hardware interacts with the CPU such as a network device informing the CPU that it has received a packet.

Hardware interrupts are asynchronous meaning that they can happen at any time of execution.
___
## Software Interrupts (Exceptions)
A software interrupt is requesting to run code in ring 0 (kernel).

A software interrupt is synchronous. It is caused by running an instruction.

### Types of Exceptions
Exceptions are classified based on how they are handled.

* **Fault** - a fault indicates that an exception has occurred but it can be fixed. The instruction pointer will point to the current instruction

* **Trap** - a trap indicates that an exception has occurred but the program could continue execution, the instruction pointer will point to the next instruction.

* **Abort** - an abort is an exception that cannot be handled, it indicates that there are hardware failures in the processor
___
## Handling Interrupts
We can handle interrupts using an Interrupt Descriptor Table (IDT). All interrupts have numbers and the IDT maps the interrupt number to the code used to handle the interrupt.

![[Pasted image 20250303201117.png]]

Note that we could get stuck in an infinite loop of interrupts as show below.

![[Pasted image 20250303201149.png]]

For this reason we disable interrupts while handling interrupts.

___
## Execution Context
In order to handle interrupts and resume the program we must handle interrupts as shown in the diagram below.

![[Pasted image 20250303201355.png]]

But if we want to do this we must have a way to store the programs context before handling the interrupt. 

The CPU uses registers and memory for maintaining an execution context.