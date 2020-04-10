# rtems-release-docker

## Dockerfiles for creating RTEMS release toolchain images 

### Overview

This is a series of Dockerfiles to create toolchains and Board Support Packages (BSPs) for the [RTEMS Real Time Operating System](https://www.rtems.org). This repository focuses on the RTEMS 5 pre-release toolchain downloads rather than the git repositories. 

### What is RTEMS?

RTEMS is an Open Source Real Time Operating System. You can read about it here: [https://www.rtems.org](https://www.rtems.org)

### What is Docker?

Docker is a set of tools for managing Linux containers, which can be thought of as lightweight virtual machines, or isolated application runtime environements for Linux applications. You can read all about it here: [https://www.docker.com](https://www.docker.com)

### Why containerize RTEMS Development Environments?

Normally In order to use the RTEMS releases, you have to do the following:
1. Setup your host operating system with the dependencies needed for an RTEMS toolchain.
2. Download the RTEMS Source Builder tool that is used to build the RTEMS cross compiler toolchain.
3. Build one or more RTEMS Cross Compiler toolchains for the required architectures (ARM, SPARC, RISC-V, etc) using the RTEMS Source Builder tool.
4. Download the RTEMS release archive.
5. Comfigure and compile the RTEMS operating system with the selected BSPs (ARM/Beaglebone Black, ARM/Raspberry Pi, SPARC/LEON3, etc)
6. Optionally download and build the rtems-libbsd release which is a port of the FreeBSD network stack and other infrastructure.
6. Compile RTEMS applications that link to the RTEMS Libraries and Board Support Packages.

This Process is documented in the [RTEMS Quick Start](https://docs.rtems.org/branches/master/user/start/index.html) on the [RTEMS Docs website](https://docs.rtems.org). 

With Docker, you can create an isolated runtime environment that has only the software that is needed for a specific RTEMS build environment. The containers can easily be created with the Dockerfiles, and they are portable to any Linux, MacOS, or Windows environment that Docker supports. The containers can also be used for cloud deployments. These container images can be pushed to a docker registry including the public [Docker Hub](https://hub.docker.com). These images can then be pulled to any machine with Docker support including Windows, MacOS, and Linux. On Linux the container runs on the Linux Kernel with an isolated runtime. On Winodws and MacOS, the container actually runs on a lightweight Linux Virtual Machine that hosts the containers.

### How to use these Dockerfiles

(TBD)
