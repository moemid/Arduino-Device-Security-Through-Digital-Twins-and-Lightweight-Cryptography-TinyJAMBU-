# Arduino-Device-Security-Through-Digital-Twins-and-TinyJAMBU-Lightweight-Cryptography
# Digital Twins Experiment Setup

This repository contains the setup and code for the Digital Twins experiment as part of the thesis "Enhancing IoT Device Security Through Digital Twins and Lightweight Cryptography: A Ditto-TinyJAMBU Approach".

## Overview

This project demonstrates the use of digital twins and lightweight cryptography to enhance the security of IoT devices. The implementation includes setting up a Mosquitto MQTT broker, connecting Arduino sensors, using TinyJAMBU for lightweight encryption, and Eclipse Ditto for digital twin management.

## Features
Secure Communication: Utilizes the TinyJAMBU lightweight cryptographic algorithm to ensure secure data transmission.

Digital Twin Integration: Facilitates the synchronization between physical IoT devices and their digital counterparts.

Arduino-Based Implementation: Leverages Arduino for IoT device management and data processing.

Docker Integration: Uses Docker Compose to run images and containers for the Digital Twins platform.

## Components
Arduino Code: Scripts for reading sensor data, encrypting it using TinyJAMBU, and transmitting it to the Digital Twin.

Digital Twin Platform: Configuration files and scripts to set up the Digital Twin on a compatible platform using Docker.

TinyJAMBU Library: Implementation of the TinyJAMBU cryptographic algorithm tailored for Arduino.

Python Serial Script: Connects Arduino to the computer and handles data transmission.

## Prerequisites
Arduino board (e.g., Arduino Uno, Arduino Nano)
Sensors (e.g., temperature, humidity)
Computer with Arduino IDE installed
Digital Twin platform (e.g., Eclipse Ditto)
MQTT broker (e.g., Eclipse Mosquitto)
Docker Desktop with Docker Compose installed
Python 3.x

## Installation
Arduino Setup
Install Arduino IDE:
Download and install the Arduino IDE.

Clone Repository:
git clone https://github.com/yourusername/ArduinoSecureTwin.git
cd ArduinoSecureTwin
Upload Code to Arduino:
Open ArduinoCode.ino in Arduino IDE.
Connect your Arduino board to the computer.
Select the appropriate board and port from the Tools menu.
Upload the code to the Arduino board.

## Docker Desktop and Digital Twin Setup
Install Docker Desktop:
Download and install Docker Desktop.

## Start Docker Desktop:
Ensure Docker Desktop is running on your system.

## Set Up Docker Compose for Digital Twin:

Navigate to the docker directory in the repository.
Run the following command om your cmd to start the containers:

docker-compose up -d
MQTT Broker Setup

## Set Up Eclipse Mosquitto:
Install and configure Eclipse Mosquitto as your MQTT broker.

## Connect Digital Twin to MQTT:

Configure your Digital Twin platform to connect to the MQTT broker.
Ensure the topic subscriptions match those used in the Arduino code.


## Python Serial Script
Install Python 3.x:
Download and install Python.

Install pySerial:
Install the pySerial library using pip:


pip install pyserial
Run Python Serial Script:
Use the provided serial_script.py to connect Arduino to the computer:

python serial_script.py

## Start MQTT Broker:

mosquitto

## Run Digital Twin Platform:
Start your Digital Twin platform using Docker and ensure it's connected to the MQTT broker.

## Monitor Data:
View the data being transmitted from the Arduino to the Digital Twin in real-time. Verify that the data is encrypted and decrypted correctly using TinyJAMBU.

## TinyJAMBU Encryption and Decryption Code
## Encryption cpp

#include <TinyJambu.h>

void setup() {
    // Initialization code
}

void loop() {
    // Example data
    uint8_t data[] = "Hello, World!";
    uint8_t key[] = "your-128-bit-key";
    uint8_t encrypted_data[sizeof(data)];

    // Encrypt data
    tinyjambu_encrypt(data, sizeof(data), key, encrypted_data);

    // Publish encrypted data
    client.publish(MQTT_TOPIC, encrypted_data);
}

## Decryption cpp
Copy code
#include <TinyJambu.h>

void setup() {
    // Initialization code
}

void loop() {
    // Example data
    uint8_t encrypted_data[] = "encrypted-data";
    uint8_t key[] = "your-128-bit-key";
    uint8_t decrypted_data[sizeof(encrypted_data)];

    // Decrypt data
    tinyjambu_decrypt(encrypted_data, sizeof(encrypted_data), key, decrypted_data);

    // Use decrypted data
}
Python Serial Script
python
Copy code
import serial

# Configure the serial port
ser = serial.Serial('/dev/ttyUSB0', 9600)

while True:
    data = ser.readline().decode('utf-8').strip()
    print(f"Received: {data}")
    
Contributing
We welcome contributions to improve ArduinoSecureTwin. Please fork the repository and create a pull request with your changes. Ensure your code follows the project's coding standards and includes appropriate tests.

License
This project is licensed under the MIT License - see the LICENSE file for details.

Contact
For any questions or inquiries, please contact:

Mohammad Al Abed - moeimid@gmail.com
  

