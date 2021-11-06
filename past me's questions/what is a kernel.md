## What is a Linux kernel?

The core of a computer system, which is responsible for managing the hardware and software of the computer.

It is the lowest layer above the CPU/ hardware.

There are two types of kernels: the monolithic kernel and the microkernel.

## Monolithic kernel

All the services etc. are contained in one program that occupy one memory space. Linux uses monolithic kernel.

## Microkernel

The kernel itself occupies one small memory space, and decive drivers, networking, etc. are running on the user-level program. If one of the services crashes, the kernel is safe.
