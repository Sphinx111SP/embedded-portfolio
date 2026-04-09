# Raspberry pi pico W initialization
## Objective
```
To provision a new Raspberry Pi Pico W with the CircuitPython firmware and verify its execution environment by flashing the onboard LED.
```
![Raspberry Pi Pico W](../../images/raspberry-pi-pico-w.jpg)

## Set-up pipeline
Microcontrollers don't natively understand Python. To write Python code for the Pico W, we must first install a Python interpreter (CircuitPython) onto the bare metal of the RP2040 chip.

### Step 1: BOOTSEL Mode
1.Press and hold the white BOOTSEL (Boot Select) button on the board.

2.While holding the button, plug the micro-USB cable into the computer.

3.Release the button.

This forces the RP2040 into USB Mass Storage Mode. The computer will now recognize the microcontroller as a standard USB flash drive named RPI-RP2.

### Step 2: Flashing the Firmware (.uf2)
1.Download the specific CircuitPython .uf2 file for the Raspberry Pi Pico W from the official Adafruit website. 

2.Drag and drop the .uf2 file directly into the RPI-RP2 drive.
 The board will automatically disconnect, flash its internal memory, and reboot.
 A new drive named CIRCUITPY will appear on your computer. The installation is complete.

### Firmware implementation :The hardware "HELLO WORLD".
With CircuitPython installed, any code written in the code.py file located on the CIRCUITPY drive will execute automatically as soon as the board powers on.

Here is the implementation to blink the Pico W's onboard LED:
```python
import board
import digitalio
import time

# Initialize the onboard LED
# Note: CircuitPython handles the complex routing to the wireless chip automatically
led = digitalio.DigitalInOut(board.LED)
led.direction = digitalio.Direction.OUTPUT

print("Starting LED sequence...")

# Infinite execution loop
while True:
    led.value = True      # Turn LED ON
    time.sleep(0.5)       # Pause execution for 500 milliseconds

    led.value = False     # Turn LED OFF
    time.sleep(0.5)       # Pause execution for 500 milliseconds


```
