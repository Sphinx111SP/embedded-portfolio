# Design and Implementation of a Low-Cost Smart Self-Leveling Platform Using Embedded Control Systems

## Background
Stability and orientation control are fundamental requirements in many modern engineering applications such as drones, camera systems, robotics, and aerospace systems. In dynamic environments, mechanical platforms are often subjected to vibrations, tilting, and external disturbances that affect their performance and accuracy.

To address this challenge, stabilization systems based on embedded sensors and feedback control mechanisms are widely used. These systems continuously monitor orientation and apply corrective actions using actuators to maintain a desired position.

This project proposes the design and implementation of a smart self-leveling platform that uses real-time sensor feedback and control algorithms to maintain a stable horizontal orientation under external disturbances.
## Problem definition
Many portable and mobile systems suffer from instability due to motion, vibration, or uneven surfaces. This instability leads to:

- Poor quality in camera footage
- Inaccurate sensor readings in mobile systems
- Reduced performance in robotic applications
- Inefficiency in precision equipment

Commercial stabilization systems exist; however, they are often expensive and complex, making them less accessible for educational and low-cost applications.

There is therefore a need for a low-cost, simplified, and educational stabilization system that demonstrates the core principles of real-world control systems.
## Objective
### General
To design and implement a low-cost embedded system that maintains a stable platform orientation using real-time feedback control.

### Specific
- To design a tilt detection system using an Inertial Measurement Unit (IMU)
- To develop a real-time feedback control algorithm for stabilization
- To implement actuator-based correction using servo motors
- To achieve stable platform leveling under external disturbances
- To demonstrate applications of control systems in real-world scenarios
## System architecture
### Components
#### Sensor unit
An IMU sensor MPU6050 IMU ( accelerator and gyroscope) is used to measure angular displacement (roll and pitch) of the platform in real time.
#### Control unit
A microcontroller processes sensor data and executes a control algorithm to determine corrective actions ( a raspberry pi pico w)
#### Actuation unit
Servo motors are used to physically adjust the platform angle and counteract disturbances, restoring it to a level position.(SG90)
#### Power supply
The system uses a shared 5V battery power source, with separate power paths for the control unit and actuators to ensure stability and prevent voltage fluctuations

### Block diagram
![Block diagram](images/blockdiagram3.png)

### Hardware implementation
Reference image
![Reference](images/project.png)
```
The system is built using an IMU sensor (MPU6050), a microcontroller such as the Raspberry Pi Pico W, and two servo motors. The IMU measures the platform’s orientation in real time, while the microcontroller processes this data and sends control signals to the servos. The servos then adjust the platform angle to maintain stability.
```
### Control strategy
The system uses a closed-loop feedback control process to maintain a level platform. The logic works as follows:

- The IMU sensor continuously measures the current tilt angle of the platform (roll and pitch).

- The microcontroller compares the measured angle with the desired reference angle (0° level position).

- The difference between these values is calculated as the error signal.

- The controller processes this error and computes a correction value.

- The correction value is converted into a PWM signal that drives the servo motors.

- The servos adjust the platform position to reduce the error.


This process repeats continuously in real time, forming a feedback loop.

### Application
This system can be applied in camera stabilization, drone payload control, robotics, and automotive sensor alignment, where maintaining stability is essential for performance and accuracy.


