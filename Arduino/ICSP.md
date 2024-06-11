ICSP stands for "In-Circuit Serial Programming." It's a method used to program microcontrollers while they are still mounted on a circuit board, without the need to remove them from the circuit. In Arduino boards, ICSP is commonly used to program the bootloader or directly upload sketches to the microcontroller.

### Components of ICSP:

1. **Programming Header**: The Arduino board includes a 6-pin programming header labeled ICSP (In-Circuit Serial Programming). This header provides access to the programming lines of the microcontroller.
    
2. **SPI Interface**: ICSP uses the Serial Peripheral Interface (SPI) protocol to communicate with the microcontroller. SPI requires four signals: MOSI (Master Out Slave In), MISO (Master In Slave Out), SCK (Serial Clock), and RESET.

### ICSP Working in Arduino Boards:

1. **Connecting the Programmer**: The programming cable is connected to the ICSP header on the Arduino board and the programmer. The programmer supplies the necessary signals for programming and communicates with the microcontroller.
    
2. **Entering Programming Mode**: The microcontroller is placed into programming mode by asserting the RESET signal and following specific timing requirements. This resets the microcontroller and prepares it to receive programming commands.
    
3. **Programming Commands**: The programmer sends programming commands and data to the microcontroller over the SPI interface. These commands include instructions to erase the flash memory, write new code and verify the programming.
    
4. **Uploading Bootloader/Sketch**: In Arduino, ICSP is commonly used to burn the bootloader onto the microcontroller, which initializes the microcontroller and allows it to accept sketches uploaded over USB.
    
5. **Exiting Programming Mode**: After programming is complete, the microcontroller is taken out of programming mode, and the RESET signal is released. The microcontroller then starts executing the newly programmed code.