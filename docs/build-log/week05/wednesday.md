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
SPI is a common communication protocol used by many different devices. For example, SD card reader modules, RFID card reader modules, and 2.4 GHz wireless transmitter/receivers all use SPI to communicate with microcontrollers.
### Key lines
```
MOSI - Master out slave in.Line for the master to send data to the slave.
MISO - Master in slave out.Line for the slave to send data to the master.
SCLK - Clock signal from master. 
SS/CS - Slave Select / Chip Select (Master chooses which slave to talk to)
```
## UART(Universal Asynchronous Receiver Transmitter)
A hardware communication module that converts parallel data to serial data and vice versa.It’s not a communication protocol like SPI and I2C, but a physical circuit in a
microcontroller, or a stand-alone IC. A UART’s main purpose is to transmit and receive serial data.
```
Asynchronous communication (no shared clock)
Uses TX (transmit) and RX (receive) pins
Common in serial terminals, debugging, GPS modules, Bluetooth modules
Data is transferred from the data bus to the transmitting UART in parallel form. After the transmitting UART gets the parallel data from the data bus, it adds a start bit, a parity bit, and a stop bit, creating the data packet.
Next, the data packet is output serially, bit by bit at the Tx pin. The receiving UART reads the data packet bit by bit at its Rx pin.
The receiving UART then converts the data back into parallel form and removes the start bit, parity bit, and stop bits. Finally, the receiving UART transfers the data packet in parallel to the data bus on the receiving end.
```

## I2C:Inter-intergrated circuits
A two-wire, synchronous, serial communication protocol used for sensors and IC-to-IC communication.

### Overview
```
I2C is a serial communication protocol, so data is transferred bit by bit along a single wire
(the SDA line).
Like SPI, I2C is synchronous, so the output of bits is synchronized to the sampling of bits by a clock signal shared between the master and the slave. The clock signal is always controlled by the master.

```
### How It Works:
```
Master-Slave Protocol: I2C uses a master-slave architecture where the master (usually the
microcontroller) controls communication with multiple slave devices.
Addressing:
Each I2C device has a unique address, so multiple devices can share the same data and
clock lines.
```

### Wi-Fi(Wireless Fidelity)
A wireless communication technology that connects devices using radio waves.

### How it works:
```
Client and Server Roles: Wi-Fi can be used for
connecting to external networks as a client or
hosting a network as a server.
```
### Protocols
```
Wi-Fi communication with CircuitPython often involves HTTP or MQTT for IoT applications, providing standard ways to send and receive data over the internet.
```
Modules like ESP32 and ESP8266 provide built-in wi-fi capabilities.