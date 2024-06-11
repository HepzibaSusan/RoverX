ADC stands for Analog-to-Digital Converter. It's a vital component in microcontrollers like those used in Arduino boards. ADCs are essential because they allow the microcontroller to read analog signals from sensors and convert them into digital values that can be processed and manipulated by the digital circuits.

### ADC Working Principle:

1. **Sampling**: The process starts with the ADC sampling the analog signal. This involves measuring the voltage level of the analog input signal at regular intervals. The frequency at which the signal is sampled is determined by the ADC's sampling rate.
    
2. **Quantization**: Once sampled, the analog signal is quantized into discrete digital values. The resolution of the ADC determines the number of possible digital values. For example, an 8-bit ADC can represent the analog signal with 256 (2^8) discrete digital values.
    
3. **Conversion**: The quantized analog signal is then converted into a digital value. This process typically involves comparing the sampled analog voltage to a reference voltage and determining the corresponding digital value based on the comparison result.
    
4. **Output**: The digital value obtained from the ADC represents the magnitude of the analog signal at the time of sampling. This digital value can be used by the microcontroller for further processing, such as data analysis, control algorithms, or display output.
    

### ADC in Arduino:

Arduino boards typically include one or more built-in ADCs that allow them to read analog signals from external sensors and components. Here's how ADC works in Arduino:

1. **Analog Input Pins**: Arduino boards feature analog input pins (e.g., A0, A1, ..., A5 on Arduino Uno) that are connected to the built-in ADC. These pins allow the microcontroller to read analog voltages from external sensors or devices.
    
2. **Resolution**: **Arduino boards usually use 10-bit ADCs,** which means they can represent analog signals with 10-bit precision, resulting in 1024 (2^10) discrete digital values ranging from 0 to 1023.
    
3. **Reference Voltage**: The ADC in Arduino typically uses a reference voltage to determine the range of the analog signal being measured. The default reference voltage is usually the operating voltage of the Arduino board (e.g., 5 volts for most Arduino boards), but it can be adjusted using software.
    
4. **Reading Analog Values**: In Arduino programming, functions like `analogRead()` are used to read analog values from specific analog input pins. This function returns a digital value representing the voltage level on the pin, which can then be used in your Arduino sketch for various purposes.

  
**In Arduino, the range of the analog-to-digital converter (ADC) can be altered by changing the reference voltage used by the ADC.**

### Using the `analogReference()` Function:

The `analogReference()` function in Arduino allows  to set the reference voltage for the ADC. It takes one argument, which specifies the reference voltage source. 

1. `DEFAULT`: This option sets the reference voltage to the default reference voltage of the Arduino board, which is typically the operating voltage (e.g., 5 volts for most Arduino boards).
    
2. `INTERNAL`: This option selects the internal voltage reference of the microcontroller. The actual voltage value may vary between different Arduino boards, but it's usually around 1.1 volts.
    
3. `EXTERNAL`: This option allows you to use an external reference voltage connected to the AREF pin of the Arduino board. You need to provide the external reference voltage using an external voltage source.


`void setup() {
  `// Set the reference voltage to the internal reference (1.1V) on Arduino Uno
  `analogReference(EXTERNAL);
  
  `// Initialize serial communication
  `Serial.begin(9600);
`}

`void loop() {
  `// Read analog input from pin A0
  `int sensorValue = analogRead(A0);

  `// Print the analog value to the serial monitor
  `Serial.println(sensorValue);
  
  `// Add a delay to prevent flooding the serial monitor
  `delay(1000);
`} 


