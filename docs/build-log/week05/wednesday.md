# Serial and parallel communication
```
Serial communication transfers data one bit at a time over a single data line. It is slower than parallel in theory but more reliable over long distances and uses fewer wires.

Parallel communication transfers multiple bits simultaneously using multiple data lines. It is faster for short distances but prone to noise and expensive due to many wires.
```

# Communication protocols
```
Communication protocols define rules and standards that devices use to exchange data. They specify data format, timing, clocking, error handling, and how devices synchronize communication.
```
# Synchronous and asynchronous communication
## Synchronous communication
```
Uses a shared clock between sender and receiver.
Data is transmitted with precise timing.
Faster and reliable for continuous data flow.
```
## Asynchronous communication
```
No shared clock; communication depends on start and stop bits.
Simpler, cheaper, but slightly slower.
Used in UART-based communication.
```
## Serial peripheral interface
A high-speed, full-duplex serial communication protocol used between microcontrollers and peripherals.
### Key lines
```
MOSI - Master out slave in.
MISO - Master in slave out.
SCLK - Clock signal from master. 
SS/CS - Slave Select / Chip Select (chooses which slave to talk to)
```
## UART
A hardware communication module that converts parallel data to serial data and vice versa.
```
Asynchronous communication (no shared clock)
Uses TX (transmit) and RX (receive) pins
Common in serial terminals, debugging, GPS modules, Bluetooth modules
```

## I2C:Inter-intergrated circuits
A two-wire, synchronous, serial communication protocol used for sensors and IC-to-IC communication.

### Features
```
Multi-master, multi-slave
Supports many devices using only 2 wires
Slower than SPI but more scalable
```

## Wi-Fi(Wireless Fidelity)
A wireless communication technology that connects devices using radio waves.

### In embedded systems, Wi-Fi is used for:
```
IoT devices
Web servers on microcontrollers
Remote monitoring and control
```
Modules like ESP32 and ESP8266 provide built-in wi-fi capabilities.