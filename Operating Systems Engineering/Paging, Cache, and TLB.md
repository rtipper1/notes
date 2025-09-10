-Make all chunks of memory the same size, called **pages**. Both virtual and physical memory divided into same size chunks.

For each process a **page table** defines the base address of that process' pages along with existence and read/write bits.

## Page Size

If the page is too small it requires a big page table
* 1B -> 4GB
* 4KB -> 4MB
* 4MB -> 4KB
* 1G -> 16B

If the page size is too big, unused memory in pages is wasted.

Consider **memory fragmentation** in this design choice.

## Example

![[Pasted image 20250206110209.png]]

Page tables accomplish the three goals of virtual memory

* **Transparency** - does not need to know system's internal state, Program A is loaded at 0x8048000. Program B can also be loaded at 0x8048000 because the page table maps them to unique physical address.
* **Efficiency** - If program B takes up 288 KB it can be loaded anywhere in which there is 288 KB of free memory, it does not matter where.
* **Protection** - We can prevent Program A from overflowing into Program B's data.

## Page Directory / Table

x86 (32-bit) uses a 2-level page table. Which includes the following.

* 10-bit directory index
* 10-bit page table index
* 12-bit offset

![[Pasted image 20250206110850.png]]

## PDE and PTE Register Structure

![[Pasted image 20250206111013.png]]

## Access Overhead

![[Pasted image 20250206111214.png]]

### Example

```
movl 0x12345678, %eax
```

This instruction will access memory. Now, instead of it taking one memory access, it will take three memory accesses to navigate our page directory and table.

We can fix this with caching

## Caching

The idea is to cache frequently used page table entries and use a TLB (Translation Lookaside Buffer) to translate between the virtual and physical addresses.

### Without TLB

![[Pasted image 20250206112222.png]]
### With TLB
![[Pasted image 20250206112333.png]]
### Populating TLB

The TLB is populated any time you check it and miss as in the example below.

![[Pasted image 20250206112449.png]]