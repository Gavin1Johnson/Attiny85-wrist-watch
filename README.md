# Attiny85-wrist-watch
This project serves as an introduction to using specific ICs rather than relying on Arduinos. This project also serves as an introduction to using SMD packages. 

The goal:

Create a simple wristwatch circuit using specific 0805 SMD components and IC's, a custom circuit board, and 3D model a watch housing to be 3D printed. 


Requirements:

* The watch should be easy and convenient to use
* Must keep a small and discreet shape and form
* Must have a glass face
* Must get at least one year of battery life
* Battery must be easily replaceable
* Must not use any glue and must be easily serviceable
* All PWM signals must be reasonably clean with little crosstalk and interference
* Watch must keep accurate time over the course of a year (+/- 3 min per month)
* All 3D printed parts must have excellent tolerances with no exes play or slop in the wrist band mounting points
* All components should be sourced with price in mind to achieve the lowest production cost while still meeting all requirements.


Procedure:

* Create a very simple block diagram circuit 
* Find parts - Research parts and read datasheets of components
* Create a circuit schematic in fushion360 Eagle 
* Layout PCB and create a 3d PCB model
* Design a watch housing around the custom PCB
* Use an Arduino Uno to burn the bootloader and flash the microcontroller
* Populate the PCB and assemble watch


Components Used in this project:

* AtTiny85 (x1  Microcontroller) - (This is an 8-bit Microcontroller and was picked for its small formfactor, 4 I/O pins, sleep mode)
* DS2417P (x1  1-Wire Time chip with interrupt) - (This is a Timer IC that can keep track of time very accurately, has a sleep mode, communicated over 1-Wire interface)
* ECS-.327-6-13FLX-TR (32.768KHz Crystal) - (This is used to set the clock frequency for the time chip. 32.768KHz is used because it is a power of 2(2^15) and can get precise 1 second period at 1Hz
* IN-S85AT5UW (x12  White LED) - (This was chosen because of its voltage range matching well with the 2016-coin cell battery / AtTiny voltage range)
* CRGH0805F100R (x4  100 Ohms Resistor) - (Four 100 Ohms Resistors are needed for the I/O pins of the AtTiny)
* RTAN0805BKE4K70 (x1  4.7K Ohms Resistor) - (One 4.7K Resistor is needed to pull up the Data pin on the DS2417p)
* C0805C474K4RAC7025 (x1  0.47uF Cap) - (One 0.47uF Cap is needed as a decoupling capacitor to reduce high frequency noise on the power rails)
* BAT-HLD-002-SMT (x1  2016 Battery retainer) - (This is the battery mount for the 2016 Coin cell battery used to power the watch)
* TL1014BF160QG (X1  Power Button) - (This is the button that will momentarily wake the circuit from sleep mode)


What’s next?:

Next, I would like to implement a capacitive touch feature that capacitively couples with the glass on the watch. I plan to implement this by creating a circular pad on the PCB that will capacitively couple with the glass watch face. This will be controlled by a simple capacitive switch IC that will use a transistor to simulate the push button to wake the watch from its sleep. This feature would allow for the power button to be omitted. 
