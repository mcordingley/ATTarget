# ATMega328P and ATTiny85 Target Board

This is a dedicated board for programming microcontrollers for use in other circuits, a fixed
realization of the [breadboard circuit](https://www.arduino.cc/en/Tutorial/ArduinoToBreadboard)
[recommended](https://www.arduino.cc/en/Tutorial/ArduinoISP) in the official Arduino tutorials.

## Minimal Components

Minimal operation just requires the socket for the target chip, a power switch or a wire
permanently connecting the leads for SW1, and the ICSP and/or FTDI (serial) headers populated.
These are in headers J1 and J3, respectively. J3 also needs a 100nF capacitor in C4. R1 is a
10K pull-up resistor to prevent accidental signals to the reset pins.

Beyond that, putting a 100nF capacitor into C1 will help programming stability by smoothing
power to the chips.

## Status LEDs

J2 is intended for the various status LEDs from the linked guides. Given a 5v supply and a
2v forward voltage from red LEDs, the resistors should be 220 ohms. Feel free to swap LED
colors and update resistor values to match the changed forward voltages. All are entirely
optional and are mapped thus:

Program
: J2 pin 1, D1, and R2
Error
: J2 pin 2, D2, and R3
Heartbeat
: J2 pin 3, D3, and R5
Power
: V+, D4, and R6

## Clock Circuit

The clock circuit consists of Y1, C2, C3, and R4. This is entirely optional for basic usage,
but necessary if the chip being programmed requires an external clock source. Y1 is a 16MHz
oscillator, C2 and C3 are the pair of 20pf capacitors that most crystal oscillators require,
and R4 is a 1M resistor that is present on the Arduino schematics, but appears to be optional.


