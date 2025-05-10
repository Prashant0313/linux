The most effective way to understand how an operating system works is through abstraction, a fancy way of saying that you can ignore most of the details

1.1 levels and layers of abstraction in a linux system

![[Pasted image 20241125214743.png]]
There is a critical difference between the ways that the kernel and user processes run: The kernel runs in ***kernel mode***, and the user processes run in ***user mode***. Code running in kernel mode has unrestricted access to the processor and main memory. This is a powerful but dangerous privilege that allows a kernel process to easily crash the entire system. The area that only the kernel can access is called ***kernel space***.
User mode, in comparison, restricts access to a (usually quite small) subset of memory and safe CPU operations. User space refers to the parts of main memory that the user processes can access. If a process makes a mistake and crashes, the consequences are limited and can be cleaned up by the kernel
In theory, a user process gone haywire can’t cause serious damage to the rest of the system. In reality, it depends on what you consider “serious damage,” as well as the particular privileges of the process, because some processes are allowed to do more than others. For example, can a user process completely wreck the data on a disk? With the correct permissions, yes—and you may consider this to be fairly dangerous. There are safeguards to prevent this, however, and most processes simply aren’t allowed to wreak havoc in this manner.

##### Hardware: understanding main memory
Of all of the hardware on a computer system, main memory is perhaps the most important. In its most raw form, main memory is just a big storage area for a bunch of 0s and 1s. Each 0 or 1 is called a bit. This is where the running kernel and processes reside—they’re just big collections of bits. All input and output from peripheral devices flows through main memory, also as a bunch of bits. A CPU is just an operator on memory; it reads its instructions and data from the memory and writes data back out to the memory. 
You’ll often hear the term state in reference to memory, processes, the kernel, and other parts of a computer system. Strictly speaking, a state is a particular arrangement of bits.

##### The Kernel
Nearly everything that the kernel does revolves around main memory. One of the kernel’s tasks is to split memory into many subdivisions, and it must maintain certain state information about those subdivisions at all times. Each process gets its own share of memory, and the kernel must ensure that each process keeps to its share.

**Processes** The kernel is responsible for determining which processes are allowed to use the CPU.

**Memory** The kernel needs to keep track of all memory—what is currently allocated to a particular process, what might be shared between processes, and what is free.

**Device drivers** The kernel acts as an interface between hardware (such as a disk) and processes. It’s usually the kernel’s job to operate the hardware.

**System calls and support** Processes normally use system calls to communicate with the kernel.