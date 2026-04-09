# Pulse width modulation
A method of representing a signal as a series of rectangular pulses with a variable duty cycle
Duty cycle specifies how long it is on or off

## Objectives
```
To understand PWM by varying LED brightness

```
## Firmware implementation
```python
import time
import board
import digitalio
import adafruit_hcsr04
import pwmio

# Sensor setup
sonar = adafruit_hcsr04.HCSR04(trigger_pin=board.GP5, echo_pin=board.GP6)

# LED setup
pwm = pwmio.PWMOut(board.GP15)

while True:
    try:
        pwm.duty_cycle = min(65535, int(sonar.distance) * 600)
        print(sonar.distance)
    except RuntimeError:
        print("Missed an echo")
        
        
        
    time.sleep(0.3)

```
