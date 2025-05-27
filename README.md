2.4Ghz JAMMER CIRCUIT

A DIY educational project that explores the fundamentals of RF interference by building a jammer targeting the 2.4 GHz ISM band — home to Wi-Fi, Bluetooth, and other short-range communication protocols.

# 2.4GHz Jammer Circuit using Dual NRF24L01 Modules and ESP32-WROOM-32E

This project builds a basic 2.4GHz jammer using **two NRF24L01+ modules** connected to an **ESP32-WROOM-32E**. The setup allows parallel transmission on multiple RF channels to flood the 2.4GHz spectrum with interference packets.

> ⚠️ DISCLAIMER: This project is for **educational and research purposes only**. Jamming RF signals without permission is illegal in most countries. Use only in controlled environments.

---

## Components Used

- ESP32-WROOM-32E
- 2 × NRF24L01+ modules
- Logic-level shifter or voltage regulator (for stable 3.3V to NRF24L01)
- 2 × 10µF capacitors (for power stability)
- Breadboard or custom PCB
- Jumper wires

---

## Wiring (Dual NRF24L01 Modules)

| NRF24L01 #1 | ESP32 Pin |
|-------------|-----------|
| VCC         | 3.3V      |
| GND         | GND       |
| CE          | GPIO 4    |
| CSN         | GPIO 5    |
| SCK         | GPIO 18   |
| MOSI        | GPIO 23   |
| MISO        | GPIO 19   |

| NRF24L01 #2 | ESP32 Pin |
|-------------|-----------|
| VCC         | 3.3V      |
| GND         | GND       |
| CE          | GPIO 16   |
| CSN         | GPIO 17   |
| SCK         | GPIO 18 (shared) |
| MOSI        | GPIO 23 (shared) |
| MISO        | GPIO 19 (shared) |

Each NRF24L01 must have its own `CE` and `CSN` lines. SPI pins (SCK, MOSI, MISO) are shared between both modules.

---

## Setup Instructions

1. Install Arduino IDE or PlatformIO.
2. Install ESP32 board definitions.
3. Install the RF24 library (TMRh20 version).
4. Modify the code to initialize two RF24 objects with separate CE/CSN pins.
5. Upload the sketch to the ESP32-WROOM-32E.

---

## How It Works

Each NRF24L01 module is initialized separately and cycles through its own set of RF channels. By using two modules simultaneously, the ESP32 can transmit interference on different frequency segments in parallel, increasing the coverage and reducing latency between channel hops.

---

## Legal Notice

Use this project only for educational testing in RF-isolated environments or with explicit permission. Unauthorized use of jamming devices is prohibited by law in many jurisdictions.

---

## License

MIT License

---

## Author

Created by: IMAYAVARAMBAN L
Year: 2025
