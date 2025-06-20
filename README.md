
# TB6612FNG_ESP32

## Overview

The **TB6612FNG_ESP32** project is designed to control DC motors using the **TB6612FNG motor driver** and an **ESP32** microcontroller. This repository provides a set of code and examples to easily interface the motor driver with the ESP32, enabling precise control over motor speed and direction. Whether you're building a robot, an automated system, or any other motorized project, this library can help you integrate the TB6612FNG motor driver with minimal setup.

### Key Features:
- Control DC motors via the TB6612FNG motor driver.
- Compatible with the **ESP32** microcontroller.
- Provides functions for forward, backward, stop, and speed control.
- Easy integration and setup using Arduino IDE.

## Table of Contents

1. [Installation](#installation)
2. [Usage](#usage)
3. [Features](#features)
4. [Contributing](#contributing)
5. [License](#license)
6. [Contact Information](#contact-information)

## Installation

To get started with this project, follow these steps:

### Prerequisites
- An **ESP32** board (e.g., ESP32 DevKit).
- A **TB6612FNG motor driver**.
- Two DC motors to control.
- Arduino IDE installed (ensure you have the ESP32 board support added to the IDE).

### Steps to Install:
1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/pablopeza/TB6612FNG_ESP32.git
   ```

2. Open the project in the Arduino IDE.
   - Go to **File** → **Open** and select the `TB6612FNG_ESP32` directory.

3. Install the required libraries:
   - Open the **Arduino Library Manager** (Sketch → Include Library → Manage Libraries).
   - Search for **“TB6612FNG”** (if needed) or use custom libraries from the repository.

4. Select your **ESP32 board** from **Tools** → **Board**.

5. Connect the ESP32 to your computer via USB and select the correct **port** under **Tools** → **Port**.

6. Upload the example code to your ESP32.

## Usage

Once the code is uploaded to your ESP32, you can use the library to control the motor. The example sketches provided in this repository demonstrate how to:

- Set up motor pins for forward, backward, and stop commands.
- Control the motor speed using PWM (Pulse Width Modulation).
- Turn the motor in both directions.

Here’s a simple code example to get you started:

```cpp
#include "TB6612FNG.h"

// Define motor driver pins
#define AIN1 14
#define AIN2 12
#define PWMA 13
#define BIN1 27
#define BIN2 26
#define PWMB 25

TB6612FNG motor(AIN1, AIN2, PWMA, BIN1, BIN2, PWMB);

void setup() {
  Serial.begin(115200);

  motor.begin();  // Initialize motor driver
}

void loop() {
  motor.setMotorPower(255); // Set motor power (0 to 255)
  motor.motorForward();     // Move forward
  delay(2000);
  
  motor.motorStop();        // Stop motor
  delay(1000);
  
  motor.motorBackward();    // Move backward
  delay(2000);
}
```

## Features

- **Motor Control**: Allows for precise control of two DC motors.
- **PWM Speed Control**: Adjust motor speed using PWM signals.
- **Simple Wiring**: Minimal wiring needed between ESP32 and TB6612FNG.
- **Example Code**: Ready-to-use examples for easy implementation.
- **ESP32 Compatibility**: Fully compatible with ESP32 development boards.

## Contributing

We welcome contributions! If you’d like to help improve this project, please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes and commit them (`git commit -am 'Add new feature'`).
4. Push to your branch (`git push origin feature-branch`).
5. Open a pull request for review.

Feel free to open issues if you encounter bugs or have suggestions for new features!

## License

Sparkfun library adapted for working on esp32

Source:
https://github.com/sparkfun/SparkFun_TB6612FNG_Arduino_Library
https://github.com/vincasmiliunas/ESP32-Arduino-TB6612FNG

## Contact Information

For questions or support, feel free to reach out to the project maintainers via GitHub issues.

## Contributors / Thanks
https://github.com/ellensp

