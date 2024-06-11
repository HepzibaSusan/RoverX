
![[Pasted image 20240426231745.png]]

1. **Microcontroller:** At the heart of the Arduino Uno is a microcontroller unit (MCU). The Uno uses the [[Atmega328P]] microcontroller, which is an 8-bit AVR (Advanced Virtual RISC) microcontroller manufactured by Atmel (now Microchip Technology). The Atmega328P runs at a clock speed of 1**6 MHz** and has 32 KB of Flash memory for storing program code, 2 KB of [[SRAM]] for data storage, and 1 KB of [[EEPROM]] for non-volatile data storage.
    
2. **Physical Layout:** The Arduino Uno is a compact board with a standard form factor. It measures approximately 68.6 mm in length and 53.4 mm in width. The board features a white silkscreen overlay that labels the various components and pins for easy identification.
    
3. **Input/Output (I/O) Pins:** The Arduino Uno has a total of 14 digital I/O pins, of which 6 can be used as [[PWM (Pulse Width Modulation)]] outputs. Additionally, there are 6 analog input pins. These pins allow the Uno to interface with a wide range of sensors, actuators, and other electronic components.
    
4. **Power Supply:** The Uno can be powered via a USB connection or an external power supply. When powered via USB, it draws power from the computer or USB power source. Alternatively, it can be powered using a DC power adapter connected to the barrel jack. The Uno supports a wide range of input voltages, typically between 7V and 12V, although it can accept up to 20V.
    
5. **USB Interface:** The Uno features a USB interface (type B connector) that allows it to communicate with a computer for programming and serial communication. It uses the Atmega16U2 microcontroller as a USB-to-serial converter, enabling seamless communication with the Arduino IDE (Integrated Development Environment) running on the computer.
    
6. **Reset Button:** A reset button is provided on the Uno board, allowing users to restart the microcontroller and reset the program running on it. Pressing the reset button triggers a reset signal, which restarts the program from the beginning.
    
7. **LEDs:** The Uno board includes built-in LEDs for visual feedback. There are typically three LEDs: a power LED (usually red), a TX LED (transmit), and an RX LED (receive). These LEDs indicate the status of the board's power supply and serial communication activity.
    
8. **Clock Crystal:** The Uno board includes a 16 MHz crystal oscillator that provides the clock signal for the microcontroller. The crystal ensures accurate timing for the operation of the microcontroller and other components on the board.
