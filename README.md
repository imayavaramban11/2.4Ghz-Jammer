2.4Ghz JAMMER CIRCUIT

A DIY educational project that explores the fundamentals of RF interference by building a jammer targeting the 2.4 GHz ISM band — home to Wi-Fi, Bluetooth, and other short-range communication protocols.

> ⚠️ **For Educational Purposes Only**  
> This project is strictly meant for academic and research exploration. Unauthorized usage of signal jammers is illegal in many countries. Always follow your local laws and regulations.

---


🔧 ESP32 + NRF24L01 Dual Setup (HSPI & VSPI)
ESP32 has two usable SPI interfaces:

HSPI (Hardware SPI)

VSPI (Default SPI)

Both modules are NRF24L01, a 2.4 GHz transceiver used for wireless communication—not jamming.

🧠 How It Works:
ESP32 is the central controller.

Two NRF24L01 modules are connected:

One to HSPI pins.

One to VSPI pins.

The ESP32 can send/receive data from both modules independently, potentially acting like a relay, monitor, or signal bridge.

🧵 Pin Mapping (from your image):
NRF24L01 Pin	Function	HSPI (left)	VSPI (right)
GND	Ground	GND	GND
VCC	Power	3.3V	3.3V
CE	Chip Enable	GPIO 4	GPIO 17
CSN (CS)	SPI Select	GPIO 5	GPIO 16
SCK	Clock	GPIO 14	GPIO 18
MOSI	Master Out	GPIO 13	GPIO 23
MISO	Master In	GPIO 12	GPIO 19
IRQ	Not used	(optional)	(optional)

⚙️ Use Cases This Could Support (Legally):
📡 Wireless bridge (e.g., forwarding data from one NRF node to another)

📊 Data logger with multiple sensor clusters

📶 Signal interference monitor (NOT jamming)

🔄 Bluetooth-to-NRF gateway

🛠️ Libraries You Might Use in Arduino:
RF24 for controlling NRF24L01

SPI for communication

✅ Next Steps:
If you're working on legal RF communication, I can give you full example code to:

Set up both NRF24L01 modules on the ESP32.

Transmit and receive data between them or with remote NRF nodes.

Let me know your intended use case (e.g., wireless messaging, sensor network, etc.), and I’ll write a working Arduino sketch for it.







You said:
what does nrf24l01 does
ChatGPT said:
The nRF24L01 is a 2.4 GHz wireless transceiver module made by Nordic Semiconductor. It's commonly used for low-power, short-range wireless communication in DIY and embedded systems, especially with Arduino, ESP32, Raspberry Pi, and similar platforms.

🔍 Key Features of nRF24L01:
Feature	Details
Frequency	2.4 GHz ISM band (same as WiFi, Bluetooth)
Range	Up to 100 meters (line of sight, with PA+LNA versions)
Data Rate	250 kbps, 1 Mbps, or 2 Mbps
Power Usage	Very low power consumption (ideal for battery-powered devices)
Communication Type	Half-duplex (can transmit or receive, but not both at the same time)
SPI Interface	Connects to microcontrollers using SPI (Serial Peripheral Interface)
Addressable Pipes	Supports up to 6 communication channels (pipes) with unique addresses
Data Packet Size	Up to 32 bytes per packet

📡 What It Can Do:
Wireless Communication

Between two microcontrollers (e.g., ESP32 ↔ Arduino)

Between a controller and multiple nodes (star topology)

Remote Control

For RC cars, drones, or robotic arms

Sensor Networks

Wireless temperature, humidity, or motion sensor reporting

Data Transmission

Telemetry data in embedded systems or wearables

🧠 How It Works:
Uses SPI to talk to a microcontroller (like ESP32).

You assign it an address.

You can send and receive small data packets (max 32 bytes).

You can configure roles:

One as transmitter (TX)

Another as receiver (RX)

