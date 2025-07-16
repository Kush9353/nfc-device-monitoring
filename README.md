# nfc-device-monitoring
This project demonstrates device status monitoring using a NodeMCU ESP8266 and an RF transmitter/receiver pair, with the status visualized on the Blynk IoT platform.

Project Components
A list of required hardware and software for this project includes:

Hardware

NodeMCU ESP8266 with a Micro-USB cable

RF Transmitter with 4 switches

RF Receiver with 4 LEDs

Software and Services

Arduino IDE

Blynk IoT Cloud

Blynk IoT App

System Architecture and Functionality
This system uses an RF transmitter to send the status of four switches to an RF receiver. The receiver is connected to a NodeMCU, which then relays this information to the Blynk IoT Cloud for remote monitoring.

Transmitter: An RF transmitter is connected to four switches. When a switch is pressed, it sends a signal to the RF receiver.

Receiver: The RF receiver is connected to the NodeMCU's digital pins D1, D2, D3, and D4. It also has four LEDs connected to its data output pins.

NodeMCU and Blynk Integration:

The NodeMCU is programmed to connect to a Wi-Fi network and the Blynk IoT Cloud using a specific authentication token.

The setup() function initializes the connection to Blynk and configures the output pins for the local LEDs.

In the main loop(), the receiver() function reads the digital state of the input pins (D1-D4) connected to the RF receiver.

It then sends the status of these pins to four virtual pins (V1, V2, V3, V4) on the Blynk server.

Simultaneously, the NodeMCU mirrors the received RF signal by controlling four local LEDs connected to pins D4, D5, D6, and D7.

Monitoring: The status of the four switches can be monitored in real-time on a web dashboard or through the Blynk mobile app, where the state of the virtual pins is displayed.
