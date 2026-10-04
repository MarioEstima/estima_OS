# EstimaOS

> A small operating system built from scratch as a learning project.

**EstimaOS** is an experimental operating system that I am building from the ground up to learn how computers work at a low level.

The project starts with almost no prior knowledge of operating-system development. The goal is not to build a production-ready OS, but to understand what happens underneath the software we normally use every day.

From booting a machine to handling memory, interrupts, keyboards, processes, and eventually user programs, everything will be learned and implemented step by step.

---

## Why?

As a software developer, most of the technologies I work with operate far above the hardware.

Frameworks, runtimes, operating systems, APIs, and programming languages hide a huge amount of complexity.

This project is an attempt to go in the opposite direction.

Instead of starting with a framework, I want to start with:

```text
CPU
 ↓
Memory
 ↓
Kernel
 ↓
Hardware
 ↓
Operating System
```

The purpose of EstimaOS is to learn what happens at each layer.

---

## Learning From Zero

I currently don't have a background in C, Assembly, kernel development, or operating-system development.

That is intentional.

This repository will document the learning process rather than pretending that everything was known beforehand.

The project will gradually introduce:

* C programming
* Assembly
* x86_64 architecture
* CPU registers
* memory
* pointers
* stack and heap
* interrupts
* hardware I/O
* device drivers
* processes
* scheduling
* system calls
* filesystems
* user-space programs

Each concept will be introduced only when the project needs it.

---

## Goals

The long-term goal is to build a small operating system capable of:

* Booting on a virtual machine
* Initializing a basic kernel
* Displaying text
* Reading keyboard input
* Managing memory
* Handling interrupts
* Running a simple shell
* Managing processes
* Providing basic system calls
* Reading and writing files
* Running simple user-space programs

The project will start extremely small.

The first goal is simply:

```text
Boot
 ↓
Kernel
 ↓
Hello from EstimaOS
```

Everything else comes later.

---

## Roadmap

### 01 — First Boot

Learn how a computer starts and how control reaches the kernel.

```text
Firmware
   ↓
Bootloader
   ↓
Kernel
   ↓
EstimaOS
```

Initial objectives:

* Understand the boot process
* Set up the development environment
* Create the first bootable image
* Start the kernel
* Print the first message

---

### 02 — Basic Kernel

Build the first minimal kernel.

Learn:

* C fundamentals
* Assembly basics
* Kernel entry points
* Linking
* Memory layout
* Cross-compilation

Target:

```text
EstimaOS v0.1

Kernel initialized.
```

---

### 03 — Terminal

Create a very small text-based interface.

Example:

```text
EstimaOS

estima@os:~$ help

help
clear
echo
reboot
```

---

### 04 — Keyboard

Teach the kernel to communicate with the keyboard.

Learn:

* Hardware input
* Interrupts
* Keyboard scancodes
* Interrupt handlers

Target:

```text
estima@os:~$ hello
hello
```

---

### 05 — Memory Management

Start managing memory instead of relying entirely on fixed memory locations.

Learn:

* Physical memory
* Virtual memory
* Paging
* Stack
* Heap
* Allocators

Eventually:

```c
void *kmalloc(size_t size);
void kfree(void *ptr);
```

---

### 06 — Processes

Introduce the concept of programs running independently.

Learn:

* CPU context
* Process state
* Scheduling
* Context switching

Target:

```text
Kernel
 ├── Shell
 ├── Process 1
 └── Process 2
```

---

### 07 — System Calls

Create the boundary between applications and the kernel.

Examples:

```c
write();
read();
open();
close();
exit();
```

The goal is to understand how user-space software communicates with the kernel.

---

### 08 — Filesystem

Build a very simple filesystem.

Possible structure:

```text
/
├── bin/
├── home/
│   └── estima/
└── hello.txt
```

---

### 09 — User Space

Move programs outside the kernel.

For example:

```text
/bin/sh
/bin/echo
/bin/ls
/bin/cat
/bin/clear
```

The kernel should no longer contain everything.

---

### 10 — EstimaOS v1.0

The first major milestone.

A small operating system capable of:

```text
Booting
   ↓
Kernel
   ↓
Memory
   ↓
Interrupts
   ↓
Keyboard
   ↓
Shell
   ↓
Processes
   ↓
Syscalls
   ↓
Filesystem
   ↓
User programs
```

---

## Technology

The project will initially focus on low-level technologies rather than existing operating-system frameworks.

| Technology           | Purpose                      |
| -------------------- | ---------------------------- |
| C                    | Kernel development           |
| Assembly             | CPU and low-level operations |
| x86_64               | Initial target architecture  |
| QEMU                 | Virtual machine              |
| GCC / cross-compiler | Building the kernel          |
| GNU Binutils         | Linking and binary tools     |
| Make                 | Build automation             |
| Git                  | Version control              |

The exact toolchain may evolve as the project develops.

---

## Development Environment

Development will initially happen inside a virtual machine.

The main testing environment will be:

```text
QEMU
```

This allows the operating system to be developed and tested without installing it directly onto physical hardware.

The project will prioritize safety and reproducibility during development.

---

## Project Structure

The structure will evolve as the operating system grows.

An early version may look like:

```text
estima-os/
│
├── boot/
│   └── ...
│
├── kernel/
│   ├── ...
│
├── drivers/
│   └── ...
│
├── include/
│   └── ...
│
├── user/
│   └── ...
│
├── Makefile
├── linker.ld
└── README.md
```

The structure is not considered final.

It will change as new concepts are introduced.

---

## Learning Philosophy

This project follows a simple rule:

> Understand first. Implement second.

Code will not be added simply because it makes the operating system work.

Whenever possible, each major component will be understood before being implemented.

That means learning things such as:

```text
What is a CPU register?
What happens when the computer boots?
Where does the kernel live in memory?
What is a stack?
What is a pointer?
What is an interrupt?
What happens when a program calls a function?
How does a process run?
How does user-space communicate with the kernel?
```

These questions are part of the project.

---

## Status

**Early development.**

The project is currently focused on learning the fundamentals required to build the first bootable version.

Nothing here should be considered production-ready.

---

## Long-Term Vision

EstimaOS is not intended to compete with Linux, Windows, macOS, or other mature operating systems.

The goal is much simpler:

**Build a small operating system from scratch and understand how it works.**

Every milestone should represent something that was previously unknown.

```text
Learn
 ↓
Build
 ↓
Break
 ↓
Understand
 ↓
Fix
 ↓
Repeat
```

---

## License

This project is open source and intended primarily for educational purposes.
