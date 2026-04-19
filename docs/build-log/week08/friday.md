# Real-Time Operating Systems (RTOS) in Embedded Systems

## Overview

An **operating system (OS)** acts as an interface between the user (or application software) and hardware resources such as the CPU, memory, and peripherals.

In embedded systems, operating systems are usually lightweight and optimized for **deterministic behavior**, especially when timing is critical.

---

## System Layers

### 1. User Space Applications
These are the programs written by developers.

- Application-level logic (e.g. sensor reading, motor control)
- Runs in a restricted environment (cannot directly access hardware)
- Examples:
  - RFID access system (like your Pico W project)
  - IoT dashboards
  - Control algorithms

---

### 2. Kernel (Core of the OS)

The **kernel** is the central component of an operating system.

#### Responsibilities:
- Task scheduling
- Memory management
- Hardware abstraction
- Interrupt handling
- Inter-process communication

👉 In RTOS, the kernel is designed to be **small, fast, and predictable**

---

### 3. Shell (Optional in Embedded Systems)

The **shell** is a user interface layer that allows interaction with the system.

- Common in Linux-based embedded systems (e.g. Raspberry Pi OS, Ubuntu)
- Not always present in RTOS environments
- Used for:
  - Running commands
  - Debugging
  - System monitoring

---

## RTOS (Real-Time Operating System)

An RTOS is an operating system designed to guarantee **timing constraints**.

### Key Feature:
> Tasks must complete within a **defined time limit**

---

## Core Concepts of RTOS

### 1. Multitasking and Concurrency

RTOS allows multiple tasks to run "simultaneously".

- Achieved via **task switching**
- Each task gets CPU time in turns
- Gives the illusion of parallel execution on single-core systems

---

### 2. Tasks (Threads)

A **task** (or thread) is a unit of execution.

| Term | Meaning |
|------|--------|
| Core | Physical processing unit |
| Thread | Virtual execution path |
| Task | RTOS-managed unit of work |

👉 On a single core CPU:
- Only one instruction executes at a time
- RTOS switches between tasks very quickly

---

### 3. CPU Execution Cycle

Every instruction follows:

```

Fetch → Decode → Execute → Write Back

```

- Fetch: Get instruction from memory
- Decode: Interpret instruction
- Execute: Perform operation
- Write back: Store result

RTOS does not change this cycle—it manages **which task gets the cycle**

---

## Scheduling in RTOS

Scheduling determines **which task runs and when**.

### Common Scheduling Types:

#### 1. Time Slicing (Round Robin)
- Each task gets equal CPU time
- Simple but not always real-time safe

#### 2. Priority-Based Scheduling
- Higher priority tasks execute first
- Critical for real-time systems

#### 3. Preemptive Scheduling
- Higher priority task interrupts lower priority task
- Ensures fast response to critical events

---

## Bare-Metal Systems

A **bare-metal system** runs without an operating system.

### Characteristics:
- No kernel
- No task scheduler
- Direct hardware control

### Structure:
```

Main loop → direct hardware control

```

### Advantages:
- Very fast
- Minimal overhead
- Full control of hardware

### Disadvantages:
- Difficult to scale
- No multitasking support
- Complex for large systems

👉 Example:
- Simple microcontroller LED blink program
- Basic sensor polling systems

---

## RTOS vs Bare-Metal

| Feature | Bare-Metal | RTOS |
|--------|-----------|------|
| Multitasking | No | Yes |
| Scheduling | Manual | Automatic |
| Complexity | Low | Medium |
| Real-time guarantees | Limited | Strong |
| Scalability | Poor | Good |

---

## Embedded Operating Systems

Embedded OS are full or semi-full operating systems designed for embedded hardware.

### Examples:

#### 1. Linux-based Systems
- Ubuntu (embedded versions)
- Raspberry Pi OS

Features:
- Full multitasking
- File systems
- Networking
- GUI support

#### 2. RTOS Examples
- FreeRTOS
- Zephyr RTOS

---

## FreeRTOS

[FreeRTOS](https://www.freertos.org) is one of the most widely used RTOS platforms.

### Key Features:
- Lightweight kernel
- Task scheduling
- Inter-task communication (queues, semaphores)
- Widely used in IoT and microcontrollers

### Common Use Cases:
- Sensor systems
- Motor control
- IoT devices
- Embedded automation

---

## Zephyr RTOS

Zephyr is a modern open-source RTOS designed for more complex embedded systems.

### Features:
- Modular architecture
- Strong networking support (BLE, WiFi, IPv6)
- Device driver framework
- Scalable from small MCUs to complex systems

### Used In:
- IoT devices
- Smart sensors
- Industrial systems

---

## Cores and Threads

### CPU Cores
A **core** is a physical processing unit inside a CPU.

- Single-core → one task at a time
- Multi-core → multiple tasks simultaneously

---

### Threads
A **thread** is a software-level execution path.

- Managed by OS or RTOS
- Multiple threads can run on one core via time slicing

---

## Summary

- Bare-metal = direct hardware control, no OS
- RTOS = time-controlled multitasking system
- Embedded OS = full OS for embedded devices (Linux-based or RTOS-based)
- Kernel = core of OS managing scheduling and hardware access
- Scheduling = determines task execution order
- Threads allow concurrency even on single-core systems

---

## Tags
`#embedded-systems` `#RTOS` `#freertos` `#zephyr` `#bare-metal` `#microcontrollers` `#real-time-systems` `#operating-systems`

