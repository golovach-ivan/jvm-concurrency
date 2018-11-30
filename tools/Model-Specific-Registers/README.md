> A **model-specific register (MSR)** is any of various control registers in the x86 instruction set used for debugging, program execution tracing, computer performance monitoring, and toggling certain CPU features.

> Reading and writing to these registers is handled by the **rdmsr** and **wrmsr** instructions, respectively. As these are privileged instructions they must be executed by the operating system. Use of the Linux msr kernel module creates a pseudo file **"/dev/cpu/x/msr"** (with a unique x for each processor or processor core). A user with permissions to read and/or write to this file can use the file I/O API to access these registers. 

> The **msr-tools** package provides a reference implementation.

## msr-tools

