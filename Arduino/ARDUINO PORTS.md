
![[Pasted image 20240430232522.png]]

In Arduino boards, the I/O (input/output) ports B, C, and D typically refer to the ports of the microcontroller used on the board. The ATmega328P microcontroller, which is commonly used on Arduino Uno and similar boards, features three I/O port registers labeled Port B, Port C, and Port D. These ports are used to control and interface with digital pins on the Arduino board. Here's a brief overview of each:

1. **Port B**:
    
    - Port B is a 8-bit I/O port consisting of digital pins 8 to 13 on the Arduino Uno. These pins are labeled as PB0 to PB5 in the microcontroller's datasheet. Port B also includes the crystal oscillator pins (XTAL1 and XTAL2) used for clock generation.
    - In Arduino programming, you can manipulate the state of Port B pins using functions like `digitalRead()` and `digitalWrite()`.
    
1. **Port C**:
    
    - Port C is a 7-bit I/O port consisting of analog input pins A0 to A5 on the Arduino Uno. These pins are labeled as PC0 to PC5 in the microcontroller's datasheet. Additionally, pin PC6 serves as the RESET pin for the microcontroller.
    - Although Port C is primarily used for analog input, it can also be configured as digital I/O pins in Arduino programming.
    
1. **Port D**:
    
    - Port D is a 8-bit I/O port consisting of digital pins 0 to 7 on the Arduino Uno. These pins are labeled as PD0 to PD7 in the microcontroller's datasheet.
    - Port D is commonly used for digital I/O tasks, such as reading digital sensors, controlling LEDs, and interfacing with other digital devices.

Each of these ports can be configured as either input or output pins in Arduino programming. They can be used to read digital signals (input mode) or write digital signals (output mode) to control external devices. The specific functions and capabilities of each port may vary depending on the microcontroller used on the Arduino board.