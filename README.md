# Attiny85-wrist-watch
This project serves as an introduction to using specific ICs rather than relying on Arduinos. This project also serves as an introduction to using SMD packages. 

The goal:

Create a simple wrist watch circuit using specific 0805 SMD components and IC's, a custom circuitboard, and 3D modle a watch housing to be 3D printed. 


Requierments:

* The watch should be easy and convenent to use
* Must keep a small and descreate shape and form
* Must have a glass face
* Must get at least one year of battery life
* Battery must be easily replacible
* Must not use any glue and must be easily servisoble
* All PWM signals must be resonably clean with little crosstalk and interference
* Watch must keep acurate time over the course of a year (+/- 3 min per month)
* All 3D printed parts must have exilent tolarences with no exes play or slop in the wrist band mounting points
* All components should be sorced with price in mind to acheave the lowest production cost while still meeting all requierments.


Procedure:

* Create a veary simple block diagrame circuit 
* Find parts - Reserch parts and read datasheets of components
* Create a circuit scamatic in fushion360 Egaile 
* Layout PCB and create a 3d PCB modle
* Design a watch housing around the custom PCB
* Use an Arduino Uno to burn the bootloader and flash the microcontroller
* Populate the PCB and assemble watch


Components Used in this project:

* AtTiny85 (x1  Microcontroller) - (This is an 8 bit Microcontrller and was picked for its small formfactor, 4 I/O pins, sleep mode)
* DS2417P (x1  1-Wire Time chip with interrupt) - (This is a Timer IC that can keep track of time very acuratly, has a sleep mode, compunicated over 1-Wire interface)
* ECS-.327-6-13FLX-TR (32.768KHz Crystal) - (This is used to set the clock frequency for the time chip. 32.768KHz is used becauce it is a power of 2(2^15) and can get precise 1 second period at 1Hz
* IN-S85AT5UW (x12  White LED) - (This was chosen because of its voltage range matching well with the 2016 coincell battery / AtTiny voltage range)
* CRGH0805F100R (x4  100 Ohms Resistor) - (Four 100 Ohms Resistors are needed for the I/O pins of the AtTiny)
* RTAN0805BKE4K70 (x1  4.7K Ohms Resistor) - (One 4.7K Resistor is needed to pull up the Data pin on the DS2417p)
* C0805C474K4RAC7025 (x1  0.47uF Cap) - (One 0.47uF Cap is needed as a decupiling capacitor to reduce high frequency noice on the power rails)
* BAT-HLD-002-SMT (x1  2016 Battery retainer) - (This is the battery mount for the 2016 Coincell battery used to power the watch)
* TL1014BF160QG (X1  Power Button) - (This is the button that will momentaraly wake the circuit from sleep mode)


Whats next?:

Next I would like to implement a capacitive toutch feature that capasitivly couples with the glass on the watch. I plan to impliment this by creating a circuilar pad on the PCB that will capacitivly couple with the glass watch face. This will be controled by a simple capacitive switch IC that will use a transistor to simulate the push button to wake the watch from its sleep. This feature would allow for the power button to be omited. 

