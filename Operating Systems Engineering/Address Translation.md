Address translation is the process by which the hardware transforms each memory access, changing the virtual address provided by the instruction to a physical address.

## Dynamic (Hardware-based) Relocation

Dynamic relocation is how the hardware and operating system give a process the illusion of a virtual address space starting at 0.

When a program is run the operating system decided where in physical memory to should be loaded and sets the base register to that value.

### Base and Bounds

The base and bounds registers are hardware structures kept on the chip that are used to virtualize memory.

* Base - The base address of a processes address space
* Bounds - The size of the address space

To translate between virtual memory and physical memory for an individual process we simply add its virtual address to its base address.

$$
\text{physical address} = \text{virtual address} + \text{base}
$$
Before running an instruction the processor will first check that the address is within bounds i.e.

$$
\text{base} \geq \text{physical address} \geq \text{base + bounds}
$$
## Hardware Support

* Privileged Mode - The operating system runs in privileged mode where it has access to the entire machine; applications are run in user mode with limited access. Control over modes is implemented in hardware perhaps with a status bit.
* Base and Bounds - The base and bounds registers are part of the MMU (memory management unit) and are hardware implemented. 
* Address Translation - Hardware provides circuitry to translate and check limits

## Operating System Support

* Memory Management - allocates memory for new processes, reclaims memory from terminated process, manages memory via free list
* Base and Bounds Management - sets base and bounds during context switch
* Exception Handling - code to run when exceptions arise, terminates offending process