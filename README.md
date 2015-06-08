# SysAlloc #

Last updated by Hilda Xue, 08 Jun 2015

**Overview**

SysAlloc is a dynamic memory allocator implemented using FPGA logic. It targets memory mapped bus based heterogeneous systems. It can manage an arbitrary amount of memory with any granularity. SysAlloc can be easily packaged as an IP core/custom component and put on the bus. Clients on the same bus can request memory through memory mapped access to registers in SysAlloc.
