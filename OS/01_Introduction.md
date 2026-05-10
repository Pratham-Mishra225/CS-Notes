
# What is an Operating System?

An Operating System (OS) is system software that acts as an interface between the user and computer hardware.

It manages hardware resources and provides services to application programs.

Without an operating system, users would have to directly interact with hardware components, which is extremely difficult.

## Simple Definition

> An Operating System is software that manages computer hardware and software resources and provides common services for computer programs.

---

# Real Life Analogy

Think of the operating system as a manager in a company.

* Users give instructions.
* The OS manages resources.
* Hardware performs the actual work.

Example:

When you open Chrome:

1. The OS allocates memory.
2. The OS gives CPU time.
3. The OS handles keyboard and mouse input.
4. The OS manages files and internet access.

---

# Functions of an Operating System

## 1. Process Management

The OS manages running programs and processes.

Responsibilities:

* Creating processes
* Scheduling processes
* Terminating processes
* Synchronization
* Communication between processes

---

## 2. Memory Management

The OS manages RAM efficiently.

Responsibilities:

* Allocating memory
* Deallocating memory
* Virtual memory management
* Protection between processes

---

## 3. File Management

The OS manages files and directories.

Responsibilities:

* Creating files
* Deleting files
* Organizing directories
* File permissions

---

## 4. Device Management

The OS controls hardware devices.

Examples:

* Printer
* Keyboard
* Mouse
* Monitor
* Disk drives

---

## 5. Security and Protection

The OS protects data and resources.

Responsibilities:

* Authentication
* Authorization
* Access control
* Malware protection

---

## 6. User Interface

The OS provides ways for users to interact with the system.

Types:

* CLI (Command Line Interface)
* GUI (Graphical User Interface)

---

# Goals of Operating System

The main goals of an operating system are:

---

## 1. Convenience

The OS makes the computer easier to use.

Users do not need to understand hardware details.

---

## 2. Efficiency

The OS uses hardware resources efficiently.

Examples:

* Better CPU utilization
* Efficient memory usage
* Faster response time

---

## 3. Ability to Evolve

The OS should support:

* New hardware
* New software
* New technologies

without major redesign.

---

# Types of Operating Systems

---

# 1. Batch Operating System

In a batch OS, jobs are collected and executed in batches.

There is no direct interaction between user and computer.

## Features

* Jobs processed sequentially
* High turnaround time
* No user interaction during execution

## Advantages

* Efficient for large repetitive tasks
* Reduces setup time

## Disadvantages

* Difficult debugging
* Long waiting time

## Example

Payroll systems in older computers.

---

# 2. Multiprogramming Operating System

Multiple programs are loaded into memory simultaneously.

The CPU switches between them to maximize utilization.

## Goal

Keep CPU busy all the time.

## Advantages

* Better CPU utilization
* Increased throughput

## Disadvantages

* Complex memory management
* Scheduling complexity

---

# 3. Multitasking Operating System

Allows users to run multiple applications simultaneously.

Example:

* Listening to music
* Browsing internet
* Editing documents

at the same time.

## Features

* Time-sharing
* Fast CPU switching
* Interactive system

## Example

Windows, Linux, macOS.

---

# 4. Time Sharing Operating System

CPU time is divided among users/processes.

Each user gets a small time slice.

## Features

* Multi-user environment
* Interactive response
* Quick switching

## Advantages

* Better resource sharing
* Reduced response time

---

# 5. Distributed Operating System

A distributed OS manages multiple computers connected through a network.

Users feel like they are using a single system.

## Features

* Resource sharing
* High reliability
* Parallel processing

## Advantages

* Faster computation
* Fault tolerance

## Disadvantages

* Complex design
* Security issues

---

# 6. Real-Time Operating System (RTOS)

An RTOS provides responses within strict time limits.

Used where timing is extremely important.

## Types

### Hard Real-Time OS

Missing deadlines is unacceptable.

Example:

* Air traffic control
* Medical systems

### Soft Real-Time OS

Occasional deadline misses are acceptable.

Example:

* Multimedia systems

## Features

* Predictable response time
* High reliability
* Minimal delay

---

# Kernel

The kernel is the core part of an operating system.

It directly interacts with hardware.

It manages:

* CPU
* Memory
* Devices
* Processes
* System calls

The kernel loads into memory during booting and remains there until shutdown.

---

# Functions of Kernel

## 1. Process Management

* Process creation
* Scheduling
* Context switching

---

## 2. Memory Management

* Memory allocation
* Virtual memory
* Paging

---

## 3. Device Management

* Device drivers
* Input/output handling

---

## 4. File System Management

* Reading/writing files
* Storage management

---

## 5. System Call Handling

The kernel provides an interface for user programs.

---

# Types of Kernels

---

## 1. Monolithic Kernel

All OS services run inside kernel space.

## Advantages

* High performance
* Fast communication

## Disadvantages

* Large size
* Difficult debugging
* One bug can crash system

## Example

Linux

---

## 2. Microkernel

Only essential services run in kernel mode.

Other services run in user space.

## Advantages

* More secure
* Better stability
* Easier maintenance

## Disadvantages

* Slower performance

## Example

MINIX

---

# User Mode vs Kernel Mode

Modern operating systems operate in two modes.

---

# User Mode

Applications run in user mode.

Examples:

* Chrome
* VS Code
* Games

## Features

* Limited hardware access
* Cannot directly access memory or devices
* Safer environment

If an application crashes, the entire OS usually does not crash.

---

# Kernel Mode

The OS kernel runs in kernel mode.

## Features

* Full hardware access
* Can execute privileged instructions
* Controls memory and devices

Errors in kernel mode can crash the system.

---

# Difference Between User Mode and Kernel Mode

| Feature                 | User Mode    | Kernel Mode             |
| ----------------------- | ------------ | ----------------------- |
| Hardware Access         | Limited      | Full                    |
| Privileged Instructions | Not Allowed  | Allowed                 |
| Security                | Safer        | Riskier                 |
| Examples                | Applications | Operating System        |
| Crash Impact            | Small        | Entire system may crash |

---

# Interrupts

An interrupt is a signal that informs the CPU that an event needs immediate attention.

Interrupts temporarily stop the current execution.

The CPU executes a special routine called Interrupt Service Routine (ISR).

---

# Why Interrupts are Needed

Without interrupts, the CPU would constantly check devices.

This wastes CPU time.

Interrupts improve efficiency.

---

# Types of Interrupts

---

## 1. Hardware Interrupts

Generated by hardware devices.

Examples:

* Keyboard input
* Mouse click
* Disk completion

---

## 2. Software Interrupts

Generated by software programs.

Usually used for system calls.

---

## 3. Maskable Interrupts

Can be ignored temporarily.

---

## 4. Non-Maskable Interrupts

Cannot be ignored.

Used for critical events.

Example:

* Hardware failure

---

# Interrupt Handling Steps

1. Device sends interrupt signal.
2. CPU pauses current process.
3. CPU saves current state.
4. ISR executes.
5. CPU restores previous state.
6. Execution resumes.

---

# System Calls

A system call is a request made by a program to the operating system kernel.

Applications use system calls to access hardware resources.

---

# Why System Calls are Needed

Applications running in user mode cannot directly access hardware.

So they request services from the kernel using system calls.

---

# Common System Calls

| System Call | Purpose          |
| ----------- | ---------------- |
| fork()      | Create process   |
| exec()      | Execute program  |
| wait()      | Wait for process |
| open()      | Open file        |
| read()      | Read file        |
| write()     | Write file       |
| close()     | Close file       |

---

# Categories of System Calls

---

## 1. Process Control

Examples:

* fork()
* exec()
* exit()

---

## 2. File Management

Examples:

* open()
* read()
* write()
* close()

---

## 3. Device Management

Examples:

* request device
* release device

---

## 4. Information Maintenance

Examples:

* get time
* get system data

---

## 5. Communication

Examples:

* pipes
* shared memory
* sockets

---

# Flow of a System Call

1. User application requests service.
2. Trap instruction switches CPU to kernel mode.
3. Kernel performs requested operation.
4. Control returns to user mode.

---

# Booting Process

Booting is the process of starting a computer and loading the operating system into memory.

---

# Types of Booting

---

## 1. Cold Booting

Starting the computer from a powered-off state.

---

## 2. Warm Booting

Restarting the computer without turning off power.

Example:

* Restart button

---

# Steps in Booting Process

---

## Step 1: Power On

The computer receives power.

---

## Step 2: BIOS/UEFI Execution

BIOS or UEFI firmware starts.

Responsibilities:

* Hardware initialization
* POST execution

POST = Power-On Self-Test

---

## Step 3: Bootloader Execution

The bootloader loads the operating system kernel.

Examples:

* GRUB
* Windows Boot Manager

---

## Step 4: Kernel Loading

The kernel loads into RAM.

It initializes:

* Memory management
* Process management
* Device drivers

---

## Step 5: System Initialization

System services and background processes start.

---

## Step 6: User Login

The login screen appears.

The system becomes ready for use.

---

# Important Interview Questions

## Basic Questions

1. What is an operating system?
2. What are the goals of an operating system?
3. Difference between kernel and operating system?
4. Difference between multitasking and multiprogramming?
5. What is a real-time operating system?

---

## Kernel Questions

1. What is a kernel?
2. Difference between monolithic kernel and microkernel?
3. What is kernel panic?

---

## User Mode vs Kernel Mode Questions

1. Why are two modes needed?
2. Why can't user programs access hardware directly?
3. What happens during mode switching?

---

## Interrupt Questions

1. What is an interrupt?
2. Difference between hardware and software interrupts?
3. What is ISR?

---

## System Call Questions

1. What is a system call?
2. Difference between function call and system call?
3. Why are system calls slower?

---

## Booting Questions

1. Explain booting process.
2. Difference between BIOS and UEFI?
3. What is POST?
4. What is a bootloader?

---

# Quick Revision Notes

* OS acts as interface between user and hardware.
* Kernel is the core part of OS.
* User mode is restricted and safer.
* Kernel mode has full hardware access.
* Interrupts improve CPU efficiency.
* System calls provide communication with kernel.
* Booting loads OS into RAM.
* RTOS is used where timing is critical.

---

# Key Terms

| Term   | Meaning                               |
| ------ | ------------------------------------- |
| OS     | Operating System                      |
| Kernel | Core part of OS                       |
| PCB    | Process Control Block                 |
| ISR    | Interrupt Service Routine             |
| BIOS   | Basic Input Output System             |
| UEFI   | Unified Extensible Firmware Interface |
| RTOS   | Real-Time Operating System            |
| GUI    | Graphical User Interface              |
| CLI    | Command Line Interface                |

---

# Conclusion

The operating system is one of the most important parts of a computer system.

It manages hardware resources, provides services to applications, ensures security, and enables users to interact with computers efficiently.

Understanding the basics of operating systems is essential for:

* Placements
* Technical interviews
* System design
* Backend development
* Cybersecurity
* Cloud computing
* Computer science fundamentals
