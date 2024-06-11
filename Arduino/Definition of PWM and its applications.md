- **Definition of PWM (Pulse Width Modulation):**
    
    PWM is a modulation technique used to control the average power delivered to a load by varying the duty cycle of a periodic signal. In simpler terms, it's a method of simulating an analog output using digital means. Instead of outputting a constant voltage or current, PWM rapidly switches the output between on and off states, with varying duty cycles, to achieve an average voltage or current proportional to the desired value.
    
- **Applications of PWM:**
    
    - **Motor Speed Control:** PWM is widely used in controlling the speed of motors, such as DC motors and servo motors. By adjusting the duty cycle of the PWM signal, the average voltage applied to the motor can be varied, thus controlling its speed.
        
    - **LED Brightness Control:** PWM is used to control the brightness of LEDs in applications like mood lighting, backlighting, and display panels. By rapidly switching the LED on and off with varying duty cycles, the perceived brightness can be adjusted.
        
    - **Power Regulation:** PWM is employed in power supplies and voltage regulators to regulate the output voltage or current. By controlling the duty cycle of the PWM signal, the average output voltage or current can be adjusted to maintain a stable output.


## **Basic Concepts of PWM:**

- **Duty Cycle:** The duty cycle of a PWM signal is the fraction of time that the signal is in the "on" state during each period. It is expressed as a percentage and represents the ratio of the pulse duration to the total period duration. A duty cycle of 0% means the signal is always off, while a duty cycle of 100% means the signal is always on.
    
- **Frequency:** The frequency of a PWM signal is the number of times the signal repeats per second, measured in Hertz (Hz). It determines how fast the PWM signal switches between on and off states. Higher frequencies generally result in smoother analog-like outputs 
    
- **Resolution:** PWM resolution refers to the number of distinct levels (steps) within the duty cycle range. It is typically determined by the number of bits used to represent the duty cycle. For example, an 8-bit PWM has 256 (2^8) distinct levels, while a 16-bit PWM has 65,536 (2^16) levels, providing finer control over the output.

## Arduino PWM
Arduino boards come with several pins capable of generating PWM signals. These pins are marked with a "~" symbol on the board, indicating their PWM capability. The number of PWM pins and their locations may vary depending on the specific Arduino model.

- **PWM Pins on Arduino Uno:** Arduino Uno, one of the most popular Arduino boards, has six PWM pins: 3, 5, 6, 9, 10, and 11.
-
-The selection of specific pins for PWM functionality on Arduino boards is primarily determined by hardware considerations related to the microcontroller's architecture and pin capabilities. 

1. **Timer/Counter Modules:** PWM functionality in Arduino is closely tied to the microcontroller's timer/counter modules. These modules are responsible for generating the PWM signals by rapidly toggling the output pin on and off according to a specified duty cycle. Not all pins on the microcontroller have direct connections to these timer/counter modules.
    
2. **Hardware Support:** The pins selected for PWM typically have dedicated hardware support for PWM generation. These pins are often connected to specific timer/counter modules that are capable of producing PWM signals efficiently. Other pins may lack this dedicated hardware support, making them unsuitable for PWM generation.
    
3. **Resource Constraints:** Microcontrollers have limited hardware resources, including timer/counter modules. Allocating PWM functionality to specific pins helps optimize resource utilization and allows for efficient PWM signal generation without overburdening the microcontroller.
    
4. **Compatibility and Consistency:** Standardizing PWM functionality on specific pins across different Arduino boards ensures compatibility and consistency for users and developers. It allows for easy porting of code between different Arduino board models without significant modifications.
    
5. **Electrical Characteristics:** PWM pins may also have specific electrical characteristics optimized for PWM operation, such as enhanced drive capabilities or filtering options to reduce noise and improve signal quality.


## **analogWrite() Function for PWM Output:**

In Arduino, the `analogWrite()` function is used to generate PWM signals on PWM-capable pins. Despite its name, `analogWrite()` does not produce true analog output; instead, it generates PWM signals with varying duty cycles to simulate analog voltage levels.

The syntax of the `analogWrite()` function is:

`analogWrite(pin, value);`

- `pin`: Specifies the PWM pin number where the PWM signal will be generated.
- `value`: Specifies the duty cycle of the PWM signal, ranging from 0 (always off) to 255 (always on). The value represents the ratio of on-time to the total period.

For example, to set a PWM signal with a duty cycle of 50% on pin 9, 

`analogWrite(9, 127); // 50% duty cycle (127/255)`

 `analogWrite()` only works on pins marked with a "~" symbol on Arduino boards, indicating their PWM capability. Attempting to use `analogWrite()` on non-PWM pins will not generate PWM signals.


## Timer Modules in Arduino and the Role of timers in generating PWM signals

Timer modules serve as the backbone for PWM generation in Arduino by providing precise timing control and hardware support for generating PWM signals with configurable duty cycles and frequencies. Each timer module's capabilities and configuration options influence the flexibility and performance of PWM generation in Arduino

Timer modules in Arduino are hardware components integrated into the microcontroller that provide timing and counting functionality. They consist of a timer/counter unit, which can count up or down based on clock pulses received from the system clock or an external source.

Each timer module typically consists of the following components:

- **Timer/Counter Register:** Stores the current count value of the timer.
- **Control Registers:** Configure the operating mode, clock source, and other parameters of the timer.
- **Compare Match Registers:** Used to trigger actions (e.g., generating PWM signals) when the timer count matches a specific value.


**Role of Timers in Generating PWM Signals:**

Timer modules are essential for generating PWM signals in Arduino. They facilitate the precise timing required to produce PWM waveforms with accurate duty cycles and frequencies. Here's how timers contribute to PWM generation:

- **Clock Source Selection:** Timer modules can be configured to use different clock sources, such as the system clock (CPU frequency) or an external clock. The clock frequency determines the resolution and frequency of the PWM signals generated by the timer.
    
- **Timer Counting:** Timer modules increment or decrement a counter register at each clock pulse, effectively measuring time. The counting behavior can be configured based on the specific application requirements, including the counting direction (up or down) and the counting range (maximum count value).
    
- **Compare Match Output:** Timer modules support compare match functionality, where the current count value is compared against predefined values stored in compare match registers. When the count value matches a compare match value, a hardware event, such as toggling an output pin or triggering an interrupt, can be generated.
    
- **PWM Generation:** PWM signals are generated by modulating the output state of a pin based on the timer's count value and compare match functionality. By adjusting the compare match value dynamically, the duty cycle of the PWM signal can be controlled, thereby regulating the average voltage or current applied to the load.


## Timer Registers:
![[Pasted image 20240529193814.png]]
![[Pasted image 20240529201154.png]]
![[Pasted image 20240529201238.png]]
### **TCCRnA (Timer/Counter Control Register A):**

- **Purpose:** TCCRnA is used to configure the operation mode and compare match output behavior of the timer.
- **Bits and Functions:**
    - **COMnA[1:0] :** Compare Match Output Mode for Channel A. These bits determine the action taken when a compare match occurs on Channel A (e.g., toggling, clearing, setting the output).
    - **COMnB[1:0] :** Compare Match Output Mode for Channel B. Similar to COMnA but for Channel B.
    - **WGMn[1:0] :** Waveform Generation Mode. These bits specify the operation mode of the timer, including PWM modes (e.g., Fast PWM, Phase Correct PWM) and other waveform generation modes.

### **TCCRnB (Timer/Counter Control Register B):**

- **Purpose:** TCCRnB configures the clock source and prescaler settings for the timer. It contains bits for setting the clock source (CSn[2:0]) and configuring the prescaler, which determines the frequency of the timer clock.

**CSn2, CSn1, CSn0 (Clock Select Bits):**

- These three bits (CSn[2:0]) determine the clock source for the timer/counter.
- The clock source options vary depending on the specific microcontroller and timer module being used.
- Different combinations of these bits select different clock sources, such as the system clock (CPU frequency), an external clock source, or a divided version of the system clock.
- The clock source directly influences the frequency of the timer/counter, which, in turn, affects the PWM signal's frequency and resolution.
- Here are some common clock source configurations:
    - **CSn2 = 0, CSn1 = 0, CSn0 = 0:** No clock source (timer stopped).
    - **CSn2 = 0, CSn1 = 0, CSn0 = 1:** System clock (no pre-scaling).
    - **CSn2 = 0, CSn1 = 1, CSn0 = 0:** System clock divided by 8.
    - **CSn2 = 0, CSn1 = 1, CSn0 = 1:** System clock divided by 64.
    - **CSn2 = 1, CSn1 = 0, CSn0 = 0:** External clock on Tn pin (rising edge).
    - **CSn2 = 1, CSn1 = 0, CSn0 = 1:** External clock on Tn pin (falling edge).
    - **CSn2 = 1, CSn1 = 1, CSn0 = 0:** System clock divided by 256.
    - **CSn2 = 1, CSn1 = 1, CSn0 = 1:** System clock divided by 1024.

###### FOCnA and FOCnB:

1. **FOCnA (Force Output Compare A):**
    
    - This bit, when set to 1, forces the output compare action for Output Compare Unit A of the timer associated with the specific register (e.g., Timer/Counter n).
        
    - When FOCnA is set, it causes the action specified by the COMnA[1:0] bits in the Timer/Counter Control Register A (TCCRnA) to occur immediately, regardless of the current count value of the timer.
        
    - Typically, this action involves toggling or setting/resetting the PWM output pin associated with Output Compare Unit A, depending on the configuration specified by the COMnA bits.
        
2. **FOCnB (Force Output Compare B):**
    
    - Similar to FOCnA, FOCnB is associated with Output Compare Unit B of the timer.
        
    - When FOCnB is set to 1, it forces the output compare action specified by the COMnB[1:0] bits in the Timer/Counter Control Register A (TCCRnA) to occur immediately, regardless of the current count value of the timer.
        
    - Like FOCnA, the action triggered by FOCnB typically involves toggling or setting/resetting the PWM output pin associated with Output Compare Unit B.
        

The main purpose of the FOCnA and FOCnB bits is to provide a mechanism for manually triggering the output compare action on specific PWM output pins. This can be useful in certain scenarios where immediate control over the PWM output state is required

### Output Compare Registers (OCRnA and OCRnB)

#### Timer/Counter0 (8-bit)

- **OCR0A**: Output Compare Register A for Timer/Counter0
- **OCR0B**: Output Compare Register B for Timer/Counter0

These registers are used to generate PWM signals or trigger an action at a specific timer count value. For example, in CTC mode, the timer counts up to the value in OCR0A and then resets, which can be used to create precise time intervals.

#### Timer/Counter1 (16-bit)

- **OCR1A**: Output Compare Register A for Timer/Counter1
- **OCR1B**: Output Compare Register B for Timer/Counter1

Being a 16-bit timer, Timer1 can handle larger values and longer timing intervals than the 8-bit timers. The OCR1A and OCR1B registers are particularly useful for applications requiring higher precision and longer delays, such as servo control or high-resolution PWM.

#### Timer/Counter2 (8-bit)

- **OCR2A**: Output Compare Register A for Timer/Counter2
- **OCR2B**: Output Compare Register B for Timer/Counter2

Similar to Timer0, Timer2 is also an 8-bit timer but operates independently, which allows for more flexibility in applications requiring multiple timers.


### TIMSKn & TIFRn
1. **TIMSKn (Timer/Counter Interrupt Mask Register)**:
    
    - `OCIEnA/B` (Timer/Counter n Output Compare Match A/B Interrupt Enable): These bits enable/disable the Timer/Counter n Output Compare A and B Match Interrupt.
    - `TOIEn` (Timer/Counter n Overflow Interrupt Enable): This bit enables/disables the Timer/Counter n Overflow Interrupt.
    - `OCIEnA` (Timer/Counter n Output Compare Match A Interrupt Enable): This bit enables/disables the Timer/Counter n Output Compare Match A Interrupt.
    
1. **TIFRn (Timer/Counter Interrupt Flag Register)**:
    
    - `OCFnA/B` (Output Compare A/B Match Flag for Timer/Counter n): These bits get set when an output compare match occurs between the Timer/Counter n output and the contents of the compare register A or B.
    - `TOVn` (Timer/Counter n Overflow Flag): This bit is set when Timer/Counter n overflows.
    - `OCFnA` (Output Compare Match Flag for Timer/Counter n): This bit gets set when an output compare match occurs between the Timer/Counter n output and the contents of the compare register A.

These registers and bits are essential for configuring and handling timer/counter interrupts in the ATmega328P microcontroller for precise timing operations or events.


## PWM modes in atmega328

The ATmega328P microcontroller supports several PWM (Pulse Width Modulation) modes, which are implemented through its timers. Each timer has different modes and capabilities. Here's an overview of the PWM modes available for each timer in the ATmega328P:

### Timer/Counter0 (8-bit)

#### Fast PWM Mode

- **Description**: The counter counts from 0 to 255 and then resets to 0. The output compare registers (OCR0A and OCR0B) determine the duty cycle.
- **Registers**:
    - `TCCR0A`: Set `WGM00` and `WGM01` for Fast PWM.
    - `TCCR0B`: Set `CS` bits for prescaling.
- **Example**
  `void setup()
  `{`
  `pinMode(6, OUTPUT); // OC0A
  `pinMode(5, OUTPUT); // OC0B
  `// Set Fast PWM mode
  `TCCR0A = (1 << WGM00) | (1 << WGM01) | (1 << COM0A1) | (1 << COM0B1);
  `TCCR0B = (1 << CS00); // No prescaling
  `OCR0A = 128; // 50% duty cycle on OC0A
  `OCR0B = 64;  // 25% duty cycle on OC0B
   `}

   `void loop() {
  `// Main loop does nothing, PWM is handled by hardware
  `}`

    

#### Phase Correct PWM Mode

- **Description**: The counter counts from 0 to 255 and then back down to 0, creating a symmetrical PWM signal.
- **Registers**:
    - `TCCR0A`: Set `WGM00`.
    - `TCCR0B`: Set `CS` bits for prescaling.
- **Example**:
    
    `void setup() 
    `{   pinMode(6, OUTPUT); // OC0A   
    `   pinMode(5, OUTPUT); // OC0B   
    `// Set Phase Correct PWM mode   
    `TCCR0A = (1 << WGM00) | (1 << COM0A1) | (1 << COM0B1);   
    `TCCR0B = (1 << CS00); // No prescaling   
    `OCR0A = 128; // 50% duty cycle on OC0A   
    `OCR0B = 64;  // 25% duty cycle on OC0B }  
    
    `void loop() {   // Main loop does nothing, PWM is handled by hardware }`
    

### Timer/Counter1 (16-bit)

#### Fast PWM Mode

- **Description**: Provides higher resolution PWM using a 16-bit counter.
- **Registers**:
    - `TCCR1A`: Set `WGM10` and `WGM11`.
    - `TCCR1B`: Set `WGM12` and `WGM13`, and set `CS` bits for prescaling.
- **Example**:
    
    `void setup() 
    `{   
    `pinMode(9, OUTPUT); // OC1A   
    `pinMode(10, OUTPUT); // OC1B   
    `// Set Fast PWM mode   
    `TCCR1A = (1 << WGM10) | (1 << WGM11) | (1 << COM1A1) | (1 << COM1B1);   
    `TCCR1B = (1 << WGM12) | (1 << WGM13) | (1 << CS10); // No prescaling  
    `` OCR1A = 32768; // 50% duty cycle on OC1A (16-bit resolution)   OCR1B = 16384; // 25% duty cycle on OC1B (16-bit resolution) }  
    
    `void loop() {   // Main loop does nothing, PWM is handled by hardware }`
    

#### Phase Correct PWM Mode

- **Description**: Similar to Fast PWM but the counter counts up and down, providing symmetrical PWM.
- **Registers**:
    - `TCCR1A`: Set `WGM10` and `WGM11`.
    - `TCCR1B`: Set `CS` bits for prescaling.
- **Example**:

    
    `void setup() 
    `{   pinMode(9, OUTPUT); // OC1A   
    `pinMode(10, OUTPUT); // OC1B   // Set Phase Correct PWM mode   TCCR1A = (1 << WGM10) | (1 << WGM11) | (1 << COM1A1) | (1 << COM1B1);   
    `TCCR1B = (1 << CS10); // No prescaling   
    `OCR1A = 32768; // 50% duty cycle on OC1A (16-bit resolution)   OCR1B = 16384; // 25% duty cycle on OC1B (16-bit resolution) }  
    
    `void loop() {   // Main loop does nothing, PWM is handled by hardware }`
    

### Timer/Counter2 (8-bit)

#### Fast PWM Mode

- **Description**: Similar to Timer0 Fast PWM but uses Timer2.
- **Registers**:
    - `TCCR2A`: Set `WGM20` and `WGM21`.
    - `TCCR2B`: Set `CS` bits for prescaling.
- **Example**:

    `void setup() 
    `{   pinMode(11, OUTPUT); // OC2A   
    `pinMode(3, OUTPUT);  // OC2B   
    `// Set Fast PWM mode   
    `TCCR2A = (1 << WGM20) | (1 << WGM21) | (1 << COM2A1) | (1 << COM2B1);   
    `TCCR2B = (1 << CS20); // No prescaling   
    `OCR2A = 128; // 50% duty cycle on OC2A  
    `OCR2B = 64;  // 25% duty cycle on OC2B }  

    `void loop() {   // Main loop does nothing, PWM is handled by hardware }`
    

#### Phase Correct PWM Mode

- **Description**: Similar to Timer0 Phase Correct PWM but uses Timer2.
- **Registers**:
    - `TCCR2A`: Set `WGM20`.
    - `TCCR2B`: Set `CS` bits for prescaling.
- **Example**:
    
    `void setup() 
    `{   pinMode(11, OUTPUT); // OC2A   
    `pinMode(3, OUTPUT);  // OC2B   
    `// Set Phase Correct PWM mode   
    `TCCR2A = (1 << WGM20) | (1 << COM2A1) | (1 << COM2B1);   
    `TCCR2B = (1 << CS20); // No prescaling   
    `OCR2A = 128; // 50% duty cycle on OC2A   
    `OCR2B = 64;  // 25% duty cycle on OC2B }  
    
    `void loop() {   // Main loop does nothing, PWM is handled by hardware }`
    

### Summary of PWM Modes

- **Fast PWM Mode**: Counter counts from 0 to TOP (255 for 8-bit timers, 65535 for 16-bit timer) and resets. Provides high frequency PWM signals but with possible asymmetrical pulses at lower duty cycles.
- **Phase Correct PWM Mode**: Counter counts from 0 to TOP and back to 0. Provides symmetrical PWM signals, suitable for applications requiring stable frequency output with minimal harmonic distortion.

## Methods to generate PWM

### 1. **Hardware PWM using Microcontroller Timers**

Microcontrollers like the ATmega328P (used in Arduino) have built-in hardware timers that can be configured to generate PWM signals. These timers operate independently of the main program, providing precise control over the PWM frequency and duty cycle.

#### **Hardware PWM on ATmega328P**

- **Timers**: ATmega328P has three timers (Timer0, Timer1, Timer2).
- **Registers**: Configuration is done using registers such as `TCCRnA`, `TCCRnB`, `OCRnA`, `OCRnB`, `TIMSKn`, and `TIFRn`.
- **Modes**: Supports various PWM modes like Fast PWM, Phase Correct PWM, and Phase and Frequency Correct PWM.


### 2. **Software PWM**

When hardware PWM is insufficient (e.g., not enough PWM channels), software PWM can be implemented. This method uses timed interrupts or the main program loop to toggle output pins, simulating PWM.

#### **Software PWM Example**
![[Pasted image 20240529211029.png]]



### 3. **Analog Output (DAC) for PWM-like Signals**

Some microcontrollers feature Digital-to-Analog Converters (DACs) which can generate analog signals that approximate PWM when combined with filtering techniques.

#### **Using DAC for PWM-like Signals**

![[Pasted image 20240529211310.png]]

## PWM AS A MODE OF DATA TRANSFER

PWM (Pulse Width Modulation) can be used for data transfer in various applications, especially in scenarios where digital communication is required but traditional communication protocols like UART, SPI, or I2C are not feasible. Here are some methods and examples of how PWM can be utilized for data transfer:

### Basic Concept

PWM encodes data into the width of pulses in a signal. By varying the pulse width, different data values can be represented. The receiving system interprets the pulse widths and decodes the data.

### Methods of Using PWM for Data Transfer

1. **Binary Data Transfer**:
    
    - In binary data transfer, different pulse widths represent binary '0' and '1'. For example, a short pulse might represent a '0', while a longer pulse represents a '1'.
    - This method can be extended to represent multiple bits in a single pulse by using more precise timing.
    
##### TRASMITTER CODE 
 `const int pwmPin = 9; // PWM output pin

`void setup() {
  `pinMode(pwmPin, OUTPUT);
`}

`void loop() {
  `// Example data: 10101010
  `sendBit(1);
  `sendBit(0);
  `sendBit(1);
  `sendBit(0);
  `sendBit(1);
  `sendBit(0);
  `sendBit(1);
  `sendBit(0);

  `delay(1000); // Send data every second
`}

`void sendBit(bool bit) {
  `if (bit) {
    `analogWrite(pwmPin, 128); // 50% duty cycle for '1'
    `delayMicroseconds(1000);  // Pulse duration for '1'
  `} 
  `else {
    `analogWrite(pwmPin, 64);  // 25% duty cycle for '0'
    `delayMicroseconds(1000);  // Pulse duration for '0'
  `}
  `analogWrite(pwmPin, 0); // Turn off the PWM signal between bits
  `delayMicroseconds(500); // Gap between bits
`}

##### RECIEVER CODE 
`const int pwmPin = 2; // PWM input pin
`unsigned long duration;
`bool receivedBit;

`void setup() {
 `` pinMode(pwmPin, INPUT);
  `Serial.begin(9600);
`}

`void loop() {
  `// Measure the duration of the pulse
  `duration = pulseIn(pwmPin, HIGH);

  `// Determine if the bit is '1' or '0' based on the duration
  `if (duration > 800 && duration < 1200) {
    `receivedBit = 1;
  `} 
  `else if (duration > 400 && duration < 800) {
    `receivedBit = 0;
  `} 
  `else {
    `// Invalid pulse duration
    `return;
  `}

  `// Print the received bit to the Serial Monitor
  `Serial.print(receivedBit);
  `delay(500); // Wait before reading the next bit
`}

1. **Analog Signal Representation**:
    
    - PWM can be used to represent analog signals in a digital format. The duty cycle of the PWM signal corresponds to the analog value.
    - This is commonly used in applications like Digital-to-Analog Converters (DACs) where the PWM signal is filtered to produce an analog voltage.
    
1. **Manchester Encoding**:
    
    - Manchester encoding can be employed to transmit data using PWM. In Manchester encoding, a logical '1' is represented by a high-to-low transition, and a logical '0' is represented by a low-to-high transition within each bit period.
    - PWM signals with specific transition points can be used to implement this encoding scheme.