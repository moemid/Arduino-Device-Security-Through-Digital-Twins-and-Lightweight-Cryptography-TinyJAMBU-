# Arduino-Device-Security-Through-Digital-Twins-and-TinyJAMBU-Lightweight-Cryptography
# Digital Twins Experiment Setup

This repository contains the setup and code for the Digital Twins experiment as part of the thesis "Enhancing IoT Device Security Through Digital Twins and Lightweight Cryptography: A Ditto-TinyJAMBU Approach".

## Overview

This project demonstrates the use of digital twins and lightweight cryptography to enhance the security of IoT devices. The implementation includes setting up a Mosquitto MQTT broker, connecting Arduino sensors, using TinyJAMBU for lightweight encryption, and Eclipse Ditto for digital twin management.

## Contents

- `arduino/`: Contains Arduino sketches for sensor data collection.
- `python/`: Python scripts for serial communication and MQTT publishing.
- `docs/`: Documentation and setup guides.
- `images/`: Diagrams and images used in the documentation.
- `tinyjambu/`: TinyJAMBU lightweight cryptography implementation.

## Getting Started

### Prerequisites

- Arduino with DHT11 sensor
- Python 3.x
- Mosquitto MQTT broker
- Docker Desktop
- Eclipse Ditto
- MQTT Explorer

### Installation

1. **Mosquitto MQTT Broker:**
   Follow the instructions in `docs/Mosquitto_Setup.md`.

2. **Arduino Setup:**
   - Connect the DHT11 sensor to your Arduino.
   - Upload the sketch from `arduino/DHT11_Sensor.ino`.

3. **Python Script:**
   - Install the required Python packages: `pip install -r python/requirements.txt`
   - Run the script: `python python/MQTT_Arduino.py`

4. **TinyJAMBU Lightweight Cryptography:**
   - Navigate to the `tinyjambu/` directory.
   - Follow the instructions in `tinyjambu/README.md` to set up and use TinyJAMBU for encrypting and decrypting data.

5. **Eclipse Ditto:**
   Follow the instructions in `docs/Eclipse_Ditto_Setup.md`.

## Authors

- Mohammad Al Abed - [Faculty of Computer Studies, Arab Open University, Beirut, Lebanon](mailto:moeimid@gmail.com)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
