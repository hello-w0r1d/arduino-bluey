# What's different from the arduino-bluey repository?

* There is no Serial port for TX on the Bluey module other than the interface that connects to CP2104. This is because nRF52 supports only one UART peripheral.
* The developers at Bluey suggested that the only way you can use UART on custom pins is by disabling the UART on CP2104 pins 6 and 8 and configuring them to the pins of your choice in the Arduino pin mapping
* While working with this BLE module, found this to be a strong limitation since the single serial port was needed for debugging over the USB interface. Desperately needed another Serial port. Hence, started exploring the Software Serial options
* The software serial libarary did not work out of the box with the arduino libraries in https://github.com/electronut/arduino-bluey since there were further fixes in it's parent repository that did not reflect in this, so had to make some local changes from the nRF52 Arduino libraries.


# Usage instructions

* Follow the steps mentioned in the parent repository https://github.com/electronut/arduino-bluey to get the Arduino libraries setup for Bluey
* On Windows, Copy and replace the contents in "C:\Users\<username>\AppData\Local\Arduino15\packages" with the contents of this repository
