# Basic Comm
This project is intended to ease serial communication between projects and create a simple standard across projects.

## Features
- Modular and Extensible: The code is structured to separate concerns, making it easier to extend or modify the communication protocol or hardware interactions.
- Custom Protocol Over Serial: The implementation of a custom communication protocol over serial is both a strength and a limitation. It provides flexibility but requires matching implementation on the communication partner's side.
- Debugging and Versioning: The use of preprocessor directives and global flags aids in debugging and maintaining version control, enhancing development and troubleshooting experiences.

## Main Functions
- setup(): Initializes the microcontroller's hardware and communication settings. It configures digital and analog pins, sets up a heartbeat timer, and initializes memory.
- loop(): Continuously processes incoming serial data, checks for heartbeat signals, and performs any scheduled tasks.
## Specialized Functions
- Memory Access Callbacks (onMemoryWrite, onMemoryRead): Functions triggered upon specific serial commands to read from or write to the simulated memory register.
- Heartbeat Mechanism (sendHeartBeat): Implements a simple heartbeat signal to indicate the device is operational.
- fastUpdate() and analogSample(): Examples of tasks that might be performed in a loop, such as updating a value based on an algorithm or reading an analog input.
## Communication and Parsing
- serviceIncomingSerial() and parseBuffer(): Manage incoming serial data, storing it in a circular buffer and parsing complete messages based on a custom protocol.
- sendMemoryMessage, burstMemoryMessage, sendAsciiMessage, sendVersion: Utilities to format and send data packets back to the connected serial device, adhering to the custom protocol.

## External Dependency
- A very optimized embedded version of a circular buffer is used and can be found here.
https://www.arduino.cc/reference/en/libraries/circularbuffer/
