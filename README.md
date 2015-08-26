# SysAlloc 

Last updated by Hilda Xue, 26 Aug 2015

If you have any questions, please do not hesitate to contact me by emailing at *zeping.xue10 AT imperial.ac.uk*.


## Overview ##

SysAlloc is a dynamic memory allocator implemented using FPGA logic. It targets memory mapped bus based heterogeneous systems. It can manage an arbitrary amount of memory with any granularity. SysAlloc can be easily packaged as an IP core/custom component and put on the bus. Clients on the same bus can request memory through memory mapped access to registers in SysAlloc.

## Source##

**SysAlloc IP core for Zynq SoC**

The VHDL implementation of SysAlloc IP core can be found [here](https://github.com/Hilx/Memory-Allocator-IP).

**Allocator-only source**

The VHDL implementation of memory allocator can be found [here](https://github.com/Hilx/RAM-Buddy-VHDL). This is the allocator only code, which means the communication protocol is not included.

**Allocator Algorithm C model**

The allocator algorithm is firstly modelled in C and the C code can be found [here](https://github.com/Hilx/RAM-Buddy-C-model).

**Synthetic FPGA implemented client**

Source code for the synthetic hardware clients used in testing SysAlloc can be found [here](https://github.com/Hilx/AXI-Peripherals/tree/master/FPGA_Client).

## Algorithm, Principle and Strategy ##

The current SysAlloc is based on the idea of binary[ buddy systems](https://en.wikipedia.org/wiki/Buddy_memory_allocation). The allocator searches for the first-fit memory block. Unlike software-implemented allocators where the memory management is done by repeatedly splitting and coalescing memory blocks, our hardware implemented allocator takes a number of continuous base blocks and allocate. In this way we avoid the splitting and coalescing. Apart from that, instead of searching in a list of memory blocks, we use a tree data structure to search for suitable memory blocks. 

You could read my [paper](https://github.com/Hilx/SysAlloc/tree/master/Paper) to better understand SysAlloc.