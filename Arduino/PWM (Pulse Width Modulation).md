Pulse Width Modulation (PWM) is a technique used to generate analog-like signals using digital outputs. It's commonly used in microcontrollers like those used in Arduino boards to control the intensity of digital signals, such as controlling the brightness of LEDs, the speed of motors, or the position of servo motors.

### PWM Working Principle:

1. **Digital Signal**: PWM works by rapidly switching a digital signal between ON and OFF states at a fixed frequency. The ratio of time spent in the ON state to the total cycle time determines the average voltage or current delivered to the load.
    
2. **Duty Cycle**: The percentage of time the signal is in the ON state during one cycle is known as the duty cycle. A higher duty cycle corresponds to a higher average voltage or current, resulting in a brighter LED or a faster motor speed.
    
3. **Analog-Like Output**: Although the PWM signal is technically a digital signal, its average value over a period of time behaves like an analog signal. By adjusting the duty cycle, you can effectively control the output level in a smooth and continuous manner.
    

### How PWM is Done in Arduino:

Arduino boards typically have several digital pins capable of PWM output. On most Arduino boards, these pins are labeled with a tilde

1. **Select PWM Pins**: Selecting one of the PWM-capable digital pins on the Arduino board. These pins are usually labeled with a tilde (~) symbol next to the pin number.
    
2. **Initialize PWM**: In the Arduino sketch, use the `analogWrite()` function to initialize PWM on the selected pin and specify the desired duty cycle. The `analogWrite()` function takes two arguments: the pin number and the desired duty cycle (ranging from 0 to 255). Higher values result in a higher duty cycle, while lower values result in a lower duty cycle.

`int ledPin = 9; // PWM pin
`int brightness = 128; // Duty cycle (0-255)

`void setup() {
  `pinMode(ledPin, OUTPUT); // Set pin as OUTPUT
`}

`void loop() {
  `analogWrite(ledPin, brightness); // Set PWM duty cycle
`}


### REASON FOR LIMITED NUMBER OF PWM PINS

In Arduino Uno, only 6 out of the 14 digital I/O pins can be used for PWM (Pulse Width Modulation) output. The reason for this limitation lies in the hardware architecture of the microcontroller used in the Arduino Uno, which is the ATmega328P.

### Hardware Limitation:

The ATmega328P microcontroller used in Arduino Uno has a limited number of hardware timers capable of generating PWM signals. These hardware timers are dedicated resources within the microcontroller and can only be used for specific purposes, including PWM generation. 

In the ATmega328P microcontroller, there are three hardware timers available (Timer 0, Timer 1, and Timer 2), each capable of generating PWM signals on specific pins. These timers are multiplexed with other functionalities of the microcontroller, such as the generation of system clock signals and control of the serial communication interface.

### Allocation of PWM Pins:

Due to the limited number of hardware timers and the need to balance various functionalities, only a subset of digital I/O pins on the ATmega328P can be configured for PWM output. In the case of Arduino Uno, six pins (D3, D5, D6, D9, D10, and D11) are dedicated to PWM output because they are connected to the hardware timers capable of PWM generation.


### OVERCOMING THE LIMITATION
This limitation can be addressed by using external hardware solutions like PWM driver chips if more PWM outputs are required for a specific project. Additionally, other Arduino boards may offer more PWM pins by using different microcontrollers like ARMCortex with more hardware timers or additional PWM peripheral modules.

 Some microcontrollers, including those used in Arduino boards, may incorporate dedicated PWM (Pulse Width Modulation) peripheral modules or hardware-based PWM generators to provide additional PWM outputs beyond what is available through the standard GPIO pins. 

### Key Features of PWM Peripheral Modules:

1. **Dedicated Hardware**: PWM peripheral modules are dedicated hardware blocks within the microcontroller specifically designed for generating PWM signals. Unlike software-based PWM implementations, which rely on CPU cycles to toggle GPIO pins, hardware PWM modules operate independently of the CPU, freeing up CPU resources for other tasks.
    
2. **Multiple Channels**: PWM peripheral modules typically support multiple PWM channels, allowing for the simultaneous generation of PWM signals on multiple pins. Each channel can have its own configurable parameters such as frequency, duty cycle, and resolution.
    
3. **Flexible Configuration**: These modules often offer flexible configuration options, allowing users to adjust parameters such as PWM frequency, duty cycle resolution, and polarity to suit their specific application requirements.
    
4. **High Precision and Accuracy**: Hardware-based PWM generators offer high precision and accuracy in PWM signal generation, as they are driven by internal clock sources and have dedicated hardware for timing control. This results in more stable and consistent PWM signals compared to software-based implementations.
    
5. **Low CPU Overhead**: Since PWM peripheral modules operate independently of the CPU, they require minimal CPU overhead, making them suitable for real-time applications and tasks where CPU resources are limited or need to be reserved for other critical tasks.
    

### Example Application:

An example of using PWM peripheral modules is in motor control applications. By utilizing hardware PWM modules, you can generate precise PWM signals to control the speed and direction of DC motors or the position of servo motors. The dedicated hardware ensures smooth and accurate motor control with minimal CPU intervention.