## Week 2 (Friday): Architecture, Bare Metal, and the Software-Hardware Bridge

## Objective
- Understand the basic architecture of embedded systems, including CPU, memory, and peripherals.
- Explain what bare-metal programming is and why it’s used in embedded systems.
- Describe the software-hardware bridge, i.e., how software interacts directly with hardware components.
- Apply concepts to write simple embedded programs that control hardware directly without an operating system.

## Embedded system architecture
- Embedded system architecture refers to how hardware and software components are organized to perform a dedicated function.

# Core components:
- CPU / MCU: Executes instructions, processes data.

- Memory: ROM/Flash for code, RAM for temporary data.

- Peripherals: Timers, GPIO, ADC/DAC, communication interfaces (SPI, I²C, UART).

- Bus system: Connects CPU, memory, and peripherals.

# Bare metal programming.
Bare-metal means programming directly on the hardware without an operating system.

# Characteristics.
- You write firmware that interacts directly with hardware registers.

- The code has full control over CPU, memory, and peripherals.

- Timing and resource management are your responsibility (no OS scheduler).

# Software-Hardware bridge.
The software-hardware bridge describes how software communicates with and controls hardware in embedded systems.

# Mechanisms include:
- Registers:
Small memory locations inside peripherals/CPU that control behavior or store status.

Example: Writing 1 to a GPIO output register turns on an LED.

- Memory-Mapped I/O (MMIO):
Hardware peripherals are assigned addresses in the system memory map.

Reading/writing these addresses is equivalent to interacting with hardware.

- Interrupts:
Hardware signals that notify the CPU of an event (like a timer overflow or button press).

The CPU can pause current execution, run an interrupt service routine (ISR), and resume.