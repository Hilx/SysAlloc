# SysAlloc 

Last updated by Hilda Xue, 26 Aug 2015

If you have any questions, please do not hesitate to contact me.

My email address: zeping.xue10 AT imperial.ac.uk.


## Overview ##

SysAlloc is a hardware memory allocator for memory-mapped bus connected heterogeneous systems targeting centred memory. It is scalable in terms of having arbitrary number of active clients in the system; it is also flexible in the range of memory to be managed.

The current SysAlloc is based on the idea of binary[ buddy systems](https://en.wikipedia.org/wiki/Buddy_memory_allocation). The allocator searches for the first-fit memory block. Unlike software-implemented allocators where the memory management is done by repeatedly splitting and coalescing memory blocks, our hardware implemented allocator takes a number of continuous base blocks and allocate. In this way we avoid the splitting and coalescing. Apart from that, instead of searching in a list of memory blocks, we use a tree data structure to search for suitable memory blocks. 

You could read my [paper](https://github.com/Hilx/SysAlloc/tree/master/Paper) to better understand SysAlloc.

## Source##

**SysAlloc IP core for Zynq SoC**

The VHDL implementation of SysAlloc IP core can be found [here](https://github.com/Hilx/SysAlloc-AXI-IP).



**Allocator-only source**

 The VHDL implementation of memory allocator can be found [here](https://github.com/Hilx/SysAlloc-VHDL). This is the allocator only code, which means the communication protocol is not included.

**Allocator Algorithm C model**

The allocator algorithm is firstly modelled in C and the C code can be found [here](https://github.com/Hilx/SysAlloc-C-Model).

**Synthetic FPGA implemented client**

Source code for the synthetic hardware clients used in testing SysAlloc can be found [here](https://github.com/Hilx/Dedicated-AXI-IPs/tree/master/FPGA_Client).

**Software Access**

The example code for accessing SysAlloc from software running on processors can be found [here](https://github.com/Hilx/SysAlloc-AXI-IP/tree/master/Software%20Access).

**HLS Access**

SysAlloc can also be accessed from HLS, and the example can be found [here](https://github.com/Hilx/HLS-Access-SysAlloc/tree/master/Hardware%20Malloc()%20Development/Attemp%201%20source).
