### STM32 Family 

The STM32 family of microcontrollers from STMicroelectronics is designed to provide a wide range of solutions for various applications, balancing performance, power efficiency, and integrated features. 

#### 1. STM32F Series

**General-Purpose Microcontrollers**

- **Target Applications**: consumer electronics and home automation
- **Key Features**:
    - **Core**: ARM Cortex-M0/M0+, M3, M4, and M7.
    - **Performance**: Clock speeds ranging from 24 MHz (M0) to 480 MHz (M7).
    - **Memory**: Flash memory from 16 KB to 2 MB, and SRAM from 4 KB to 1 MB.
    - **Peripherals**: Rich set of peripherals including ADCs, DACs, UARTs, SPI, I2C, USB, CAN, and Ethernet.
    - **Development**: Supported by STM32CubeF software package and STM32 Nucleo development boards.
    
- **Sub-Series**:
    - **STM32F0**: Low-cost, entry-level with Cortex-M0.
    - **STM32F1**: Mainstream MCUs with Cortex-M3.
    - **STM32F2**: Higher performance with Cortex-M3 and improved peripherals.
    - **STM32F3**: Mixed-signal with Cortex-M4 and enhanced analog peripherals.
    - **STM32F4**: High performance with Cortex-M4 and advanced peripherals.
    - **STM32F7**: Top-tier performance with Cortex-M7 and extensive connectivity.

#### 2. STM32L Series

**Ultra-Low-Power Microcontrollers**

- **Target Applications**: Battery-powered devices, wearables, medical devices and IoT applications.
- **Key Features**:
    - **Core**: ARM Cortex-M0+, M3, and M4.
    - **Performance**: Clock speeds up to 80 MHz.
    - **Memory**: Flash memory from 8 KB to 1 MB, and SRAM from 2 KB to 320 KB.
    - **Power Efficiency**: Optimized for ultra-low-power operation with various low-power modes (STOP, STANDBY, and SLEEP).
    ![[Pasted image 20240610172844.png]]
    - **Peripherals**: Low-power analog peripherals, RTC (Real-Time Clock), and support for energy-efficient communication protocols.
    - **Development**: Supported by STM32CubeL software package and development kits designed for low-power applications.
    
- **Sub-Series**:
    - **STM32L0**: Entry-level ultra-low-power with Cortex-M0+.
    - **STM32L1**: Low-power Cortex-M3 with enhanced features.
    - **STM32L4**: Higher performance with Cortex-M4 and advanced low-power capabilities.
    - **STM32L4+**: Enhanced version of L4 with higher performance and memory.

#### 3. STM32H Series

**High-Performance Microcontrollers**

- **Target Applications**: Complex and demanding applications such as industrial automation, robotics, audio processing, and advanced control systems.
- **Key Features**:
    - **Core**: ARM Cortex-M7.
    - **Performance**: Clock speeds up to 480 MHz.
    - **Memory**: Flash memory up to 2 MB and SRAM up to 1 MB.
    - **Advanced Features**: Enhanced computation power, double-precision Floating Point Unit, advanced graphics support (Chrom-ART Accelerator
    - **Development**: Supported by STM32CubeH software package and high-performance development boards.
- **Sub-Series**:
    - **STM32H7**: High-end MCUs with dual-core options (Cortex-M7 + Cortex-M4) for advanced processing capabilities.

#### 4. STM32G Series

**General-Purpose Microcontrollers with Enhanced Performance and Energy Efficiency**

- **Target Applications**: Industrial and consumer applications requiring a balance of performance and power efficiency, such as smart appliances, industrial sensors, and portable devices.
- **Key Features**:
    - **Core**: ARM Cortex-M4 and Cortex-M23.
    - **Performance**: Clock speeds up to 170 MHz.
    - **Memory**: Flash memory up to 512 KB and SRAM up to 128 KB.
    - **Energy Efficiency**: Optimized power consumption with dynamic voltage scaling and various low-power modes.
    - **Integrated Features**: Advanced analog and digital peripherals, hardware cryptography, and safety features.
    - **Development**: Supported by STM32CubeG software package and comprehensive development kits.
- **Sub-Series**:
    - **STM32G0**: Entry-level with Cortex-M0+.
    - **STM32G4**: Higher performance with Cortex-M4 and enhanced peripherals.

#### 5. STM32WB Series

**Wireless Microcontrollers with Integrated Bluetooth and 802.15.4 Radio**

- **Target Applications**: Wireless communication applications, smart home, wearable technology, IoT devices
- **Key Features**:
    - **Core**: ARM Cortex-M4 (main application processor) and Cortex-M0+ (network processor).
    - **Performance**: Application processor up to 64 MHz and network processor up to 32 MHz.
    - **Wireless Capabilities**: Integrated Bluetooth 5.0 and IEEE 802.15.4 radio for Zigbee protocols.
    - **Memory**: Flash memory up to 1 MB and SRAM up to 256 KB.
    - **Integrated Security**: Secure firmware update (SFU), hardware cryptography, and trust zone for secure application execution.
    - **Development**: Supported by STM32CubeWB software package, Bluetooth stacks, and development boards focused on wireless applications.


### Key features of the STM32 microcontroller family

### 1. Scalability:

The STM32 microcontroller family offers a wide range of performance, memory, and peripheral options to suit diverse application requirements. 

- **Performance Options**: STM32 microcontrollers come in various series and families, ranging from entry-level Cortex-M0 to high-performance Cortex-M7 and Cortex-M33 cores. This diversity enables developers to select a microcontroller with the appropriate processing power for their application.
    
- **Memory Options**: STM32 microcontrollers offer different memory configurations, including Flash memory for program storage and SRAM for data storage. Memory sizes can vary significantly across different microcontroller models, allowing developers to choose the optimal memory configuration for their applications.
    
- **Peripheral Options**: The STM32 family integrates a wide range of peripherals, including communication interfaces (UART, SPI, I2C, CAN, USB, Ethernet), analog-to-digital converters (ADC), digital-to-analog converters (DAC), timers, pulse-width modulation (PWM), and more. This extensive peripheral set caters to various application needs and simplifies system design.
    

### 2. Connectivity:

STM32 microcontrollers provide support for various communication protocols, enabling seamless connectivity with external devices and networks. These communication interfaces facilitate data exchange and interoperability in embedded systems.

- **UART (Universal Asynchronous Receiver-Transmitter)**: Used for serial communication between microcontrollers and peripheral devices.
    
- **SPI (Serial Peripheral Interface)**: Enables high-speed synchronous communication between microcontrollers and peripheral devices, such as sensors, displays, and memory chips.
    
- **I2C (Inter-Integrated Circuit)**: Facilitates communication between microcontrollers and peripherals using a two-wire serial interface, suitable for connecting sensors, EEPROMs, and other low-speed peripherals.
    
- **CAN (Controller Area Network)**: Supports robust communication in automotive and industrial applications, allowing microcontrollers to exchange data over a high-speed serial bus.
    
- **USB (Universal Serial Bus)**: Provides connectivity for USB-enabled devices, allowing microcontrollers to interface with computers, peripherals, and USB accessories.
    
- **Ethernet**: Enables network connectivity in embedded systems, allowing microcontrollers to communicate over Ethernet networks and the internet.
    

### 3. Integrated Peripherals:

STM32 microcontrollers integrate a wide range of peripherals, offering a comprehensive set of features to meet the requirements of embedded applications.

- **ADC (Analog-to-Digital Converter)**: Converts analog signals from sensors and other analog devices into digital data for processing by the microcontroller.
    
- **DAC (Digital-to-Analog Converter)**: Converts digital data into analog signals, useful for generating analog output signals for audio applications, control systems, and instrumentation.
    
- **Timers**: Provide timing and counting functionalities for generating precise time delays, measuring time intervals, and controlling periodic events.
    
- **PWM (Pulse-Width Modulation)**: Generates PWM signals for controlling the speed of motors, brightness of LEDs, and other analog devices.
    
- **Interrupt Controllers**: Manage interrupt signals from peripheral devices, allowing the microcontroller to respond to external events in real-time.
    
- **Communication Interfaces**: Include UARTs, SPI, I2C, CAN, USB, and Ethernet controllers for interfacing with external devices and networks.


### STM32 Clock System: 

#### 1. **Clock Sources**

- **HSI (High-Speed Internal)**: An internal RC oscillator typically running at 16 MHz. It is the default system clock source and is used during the initial startup.
- **HSE (High-Speed External)**: An external crystal oscillator, commonly running at frequencies like 8 MHz or 25 MHz. *It provides a more accurate and stable clock source compared to HSI.*
- **LSI (Low-Speed Internal)**: An internal low-speed clock running at around 32 kHz. It is used for watchdog timers and other low-power applications.
- **LSE (Low-Speed External)**: An external crystal clock running at 32.768 kHz, used primarily for the Real-Time Clock (RTC) due to its accuracy and stability.

##### Real-Time Clock (RTC) in STM32 Microcontrollers

###### Overview:

The Real-Time Clock (RTC) is a low-power clock module integrated into STM32 microcontrollers. It provides accurate timekeeping functions even when the microcontroller is in low-power modes or completely powered off, as long as the backup battery is connected.

###### Key Features:

1. **Time and Date Keeping**:
    
    - Tracks time (hours, minutes, seconds) and date (day, month, year).
    - Can automatically adjust for leap years.
2. **Alarms**:
    
    - Supports multiple alarms to trigger interrupts at specific times or dates.
    - Useful for waking the microcontroller from low-power modes.
3. **Backup Domain**:
    
    - RTC runs on a separate power domain, often referred to as the backup domain, which can be powered by a dedicated backup battery 
    - Ensures the RTC continues to function during power loss or microcontroller resets.
4. **Clock Sources**:
    
    - RTC can be clocked by the Low-Speed External (LSE) oscillator, the Low-Speed Internal (LSI) oscillator, or the High-Speed External (HSE) divided by 128.
    - **LSE** is preferred for its accuracy and stability.
5. **Tamper Detection**:
    
    - Some STM32 models include tamper detection features that can trigger an interrupt if tampering is detected, such as unauthorized access to the backup domain.
6. **Timestamping**:
    
    - The RTC can timestamp events, which is particularly useful for logging purposes in data acquisition systems.
    
###### **Real-Time Clock (RTC) Configuration**

- **Clock Source Selection**: RTC can use LSE, LSI, or HSE/128 as its clock source.
- **LSE**: Preferred for its accuracy and stability, especially in timekeeping applications.
- **Backup Domain**: The RTC configuration, along with LSE, is in the backup domain, which means it remains powered during standby and reset operations, ensuring continuous timekeeping.

RTC configuration typically involves:

- Selecting the clock source (LSE, LSI, or HSE/128).
- Setting the time and date.
- Configuring alarms and wakeup timers.
- Enabling interrupts if needed.

#### 2. **PLL (Phase-Locked Loop)**

- **Function**: The PLL is used to generate higher system clock frequencies by multiplying the frequency of the HSI or HSE clock sources.
- **Configuration**: The PLL configuration involves setting the multiplication and division factors to achieve the desired system clock frequency. For example, to achieve a system clock of 84 MHz, the HSE (8 MHz) might be multiplied by 336 and then divided by 4.

#### 3. **System Clock Configuration**

- **System Clock Mux**: Selects the main system clock source from HSI, HSE, or PLL output. This selection can be changed dynamically to suit different operational modes.
- **Configuration Steps**:
    1. **Clock Source Selection**: Choose between HSI, HSE, or PLL.
    2. **PLL Setup**: Configure PLL parameters if PLL is used.
    3. **Bus Prescalers**: Set the prescalers for different buses (AHB, APB1, APB2) to ensure they run within their maximum frequency limits.
    4. **Flash Latency**: Configure the Flash memory access latency based on the system clock speed to ensure proper operation.


#### 4. **Independent Watchdog (IWDG) Clock**

- **Clock Source**: The IWDG typically uses the LSI clock. It operates independently of the main system clock, providing a reliable time base for the watchdog functionality.
- **Use Case**: Ensures system recovery in case of software failures by resetting the microcontroller if the watchdog timer is not refreshed periodically.

#### 5. **Peripheral Clocks**

- **Bus Clocks**: Different buses (AHB, APB1, APB2) have their own clock domains, which are derived from the system clock.
    - **AHB (Advanced High-performance Bus)**: High-speed bus for core, memory, and DMA operations.
    - **APB1 and APB2 (Advanced Peripheral Buses)**: Used for connecting peripherals like timers, UARTs, and ADCs. APB1 typically runs at a lower frequency than APB2.
- **Peripheral Clock Enable**: Each peripheral has an associated clock enable bit in the RCC (Reset and Clock Control) registers. The peripheral clocks must be enabled before using the peripherals.

##### AHB and APB Buses in STM32 Microcontrollers

##### 1. **AHB (Advanced High-performance Bus)**

The AHB is a high-speed bus designed for fast data transfer and efficient communication between the core, memory, and DMA (Direct Memory Access) controllers.

- **Core Access**: The CPU accesses memory and peripherals via the AHB. It ensures high-speed interaction with SRAM, Flash memory, and other critical components.
- **DMA**: The DMA controller uses the AHB for fast memory-to-memory, peripheral-to-memory, and memory-to-peripheral transfers without CPU intervention, freeing up the CPU for other tasks.
- **Memory Interface**: The AHB connects directly to the internal and external memories, enabling quick data read and write operations.

##### 2. **APB (Advanced Peripheral Bus)**

The APB is designed for connecting peripheral devices to the AHB. It is divided into two main buses: APB1 and APB2, each serving different sets of peripherals.

- **APB1**:
    
    - **Lower Frequency**: Typically runs at a lower frequency than APB2, making it suitable for peripherals that do not require high-speed operation.
    - **Peripherals**: Includes timers, UARTs, I2C, SPI, CAN, and other peripherals that can operate at slower clock rates.
    - **Power Efficiency**: Running at a lower frequency helps reduce power consumption, which is beneficial for battery-powered applications.
- **APB2**:
    
    - **Higher Frequency**: Operates at a higher frequency than APB1, catering to peripherals that need faster clock rates.
    - **Peripherals**: Includes high-speed peripherals like advanced timers, ADCs (Analog-to-Digital Converters), and high-speed communication interfaces.
    - **Performance**: Ensures that time-sensitive peripherals receive the clock speeds necessary for optimal performance.

##### Bus Architecture and Clock Configuration

The STM32 microcontroller's clock tree allows configuring the clock speed for the AHB and APB buses separately, enabling fine-tuned performance and power management.

- **Clock Pre scalers**: Each bus can have different pre scalers to adjust the clock speed derived from the system clock.
- **Independent Clocks**: The ability to configure clocks independently for AHB, APB1, and APB2 ensures that each peripheral operates at the optimal clock frequency.

#### 6. **Advanced Timer Functionalities**

- **Input Capture**: Captures the value of a timer counter based on an external event, useful for measuring time intervals.
- **Output Compare**: Generates a specific output signal when the timer counter reaches a predefined value, useful for generating PWM signals or toggling GPIOs.
- **PWM Generation**: Timers configured in PWM mode generate signals with varying duty cycles, used for motor control, LED dimming, etc.