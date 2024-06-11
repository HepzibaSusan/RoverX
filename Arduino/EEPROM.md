
EPROM stands for Electrically Erasable Programmable Read-Only Memory. It's a type of non-volatile memory that retains its stored data even when the power is turned off. EEPROM is commonly used in Arduino boards to store data that needs to persist between power cycles.

### Features of EEPROM:

1. **Non-Volatile**: EEPROM is non-volatile memory, meaning it retains its stored data even when the power is removed. This makes it suitable for storing configuration settings, calibration data, user preferences, and other critical information in embedded systems.
    
2. **Electrically Erasable**: Unlike ROM (Read-Only Memory), EEPROM can be electrically erased and reprogrammed multiple times. This allows for updating and modifying the stored data without removing the chip from the circuit or using external programming equipment.
    
3. **Random Access**: EEPROM supports random access, meaning individual bytes or words of data can be read from or written to at any time. This allows for efficient storage and retrieval of data, similar to RAM (Random Access Memory).
    
4. **Limited Endurance**: EEPROM has a limited number of write-erase cycles before it wears out. The endurance of EEPROM is typically specified in terms of the number of write cycles it can sustain before the memory cells degrade. Careful management of EEPROM usage is required to ensure longevity and reliability.