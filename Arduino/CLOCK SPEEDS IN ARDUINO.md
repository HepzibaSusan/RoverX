Each Arduino board operates at its specified frequency due to the clock configuration of the microcontroller it uses. The clock signal is typically provided by an external crystal oscillator or clock source connected to the microcontroller, with internal oscillator settings used to generate the system clock at the desired frequency.

The difference in clock frequencies between the ATmega328 microcontroller and ARM Cortex-M processors like those found in Arduino Due or Arduino Zero boards stems from several factors, including the underlying architecture.

### Microcontroller Architecture:

- **ATmega328 (AVR Architecture)**: The ATmega328 microcontroller, used in Arduino Uno and similar boards, belongs to the AVR (Advanced Virtual RISC) architecture. AVR microcontrollers typically operate at clock frequencies up to a few tens of megahertz. The ATmega328's maximum clock speed is 20 MHz when supplied with a 5V voltage.
    
- **ARM Cortex-M Processors**: ARM Cortex-M processors, including those used in Arduino Due and Arduino Zero boards, are based on the ARM Cortex-M architecture. These processors are designed to achieve higher clock speeds while maintaining energy efficiency and real-time performance. Cortex-M processors can operate at clock frequencies ranging from tens of megahertz to several hundred megahertz, depending on the specific model and implementation.
- ARM Cortex-M processors are designed with performance in mind, featuring advanced pipeline stages, instruction sets, and peripheral interfaces optimized for high-speed operation. These architectural enhancements enable Cortex-M processors to achieve higher clock speeds compared to older architectures like AVR.