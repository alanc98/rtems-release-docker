# rtems-release-docker

This is a series of Dockerfiles to create toolchains and Board Support Packages (BSPs) for the [RTEMS Real Time Operating System](https://www.rtems.org). This repository focuses on the RTEMS 5 pre-release toolchain downloads rather than the git repositories. 
Normally In order to use the RTEMS releases, you have to do the following:
1. Setup your host operating system with the dependancies needed for and RTEMS toolchain.
2. Download the RTEMS Source Builder tool that is used to build the RTEMS cross compiler toolchain.
3. Build the RTEMS Cross Compiler for the required architectures (ARM, SPARC, RISC-V, etc) using the RTEMS Source Builder tool.
4. Download the RTEMS pre-release archive.
5. Comfigure and compile the RTEMS operating system with the selected BSPs (ARM/Beaglebone Black, ARM/Raspberry Pi, SPARC/LEON3, etc)
6. Compile RTEMS applications that link to the RTEMS Libraries and Board Support Packages.

 
