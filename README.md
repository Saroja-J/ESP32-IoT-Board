# ESP32-S3 IoT Sensor Board 🌐

A custom IoT sensor board based on the **ESP32-S3-WROOM-1-N4**, designed in **KiCad** with environmental, air-quality, light, audio, and local data-storage capabilities.

## 🔧 Main Components

| Component | Function |
|-----------|----------|
| **ESP32-S3-WROOM-1-N4** | Main microcontroller with 2.4 GHz Wi-Fi and Bluetooth Low Energy (BLE) |
| **BME280** | Temperature, relative humidity, and atmospheric pressure sensing |
| **SHT40** | High-accuracy temperature and relative humidity sensing |
| **SGP40** | VOC sensing for air-quality applications |
| **MAX4466** | Low-noise microphone preamplifier |
| **Phototransistor** | Ambient light detection |
| **MicroSD Card** | Local sensor-data storage |

---

## 🧩 Block Diagram

```text
                         ┌─────────────────────────┐
                         │     ESP32-S3-WROOM-1-N4 │
                         │       Main Controller   │
                         └────────────┬────────────┘
                                      │
              ┌───────────────────────┼───────────────────────┐
              │                       │                       │
             I²C                     SPI                    ADC
              │                       │                       │
       ┌──────┼──────┐          ┌─────▼─────┐         ┌──────┴──────┐
       │      │      │          │  MicroSD  │         │             │
    BME280  SHT40  SGP40        │   Card    │      MAX4466     Phototransistor
       │      │      │          └───────────┘         │             │
       └──────┴──────┘                                └─────────────┘
```

---

## 🧠 ESP32-S3-WROOM-1-N4

The **ESP32-S3-WROOM-1-N4** acts as the main controller of the board.

### Main Responsibilities

- Reading sensor data
- Processing sensor measurements
- Managing connected peripherals
- Storing collected data
- Providing 2.4 GHz Wi-Fi connectivity
- Providing Bluetooth Low Energy (BLE) connectivity
- Controlling the overall IoT system

---

## 🌡️ Sensors

### BME280

The **BME280** is a digital environmental sensor used for:

- Temperature measurement
- Relative humidity measurement
- Atmospheric pressure measurement

**Communication:** I²C

---

### SHT40

The **SHT40** is a high-accuracy digital temperature and humidity sensor.

It provides:

- Temperature measurement
- Relative humidity measurement

**Communication:** I²C

---

### SGP40

The **SGP40** is a digital VOC sensor designed for air-quality applications.

It provides VOC-related sensing for indoor air-quality monitoring.

**Communication:** I²C

---

### 💡 Phototransistor

The **phototransistor** is used for ambient light detection.

The output is interfaced with an analog input of the ESP32-S3.

**Interface:** Analog / ADC

---

### 🎤 MAX4466

The **MAX4466** is a low-noise microphone preamplifier used to amplify a microphone signal before it is processed by the ESP32-S3.

**Interface:** Analog / ADC

**Applications:**

- Audio signal acquisition
- Sound-level monitoring
- Microphone signal amplification

---

## 💾 MicroSD Card

The **MicroSD card** provides non-volatile local storage for sensor data and system logs.

Possible stored data includes:

- Temperature
- Relative humidity
- Atmospheric pressure
- VOC / air-quality data
- Light-level measurements
- Audio-related measurements
- Time-stamped sensor logs

**Communication:** SPI

---

## 🔌 Communication Interfaces

| Interface | Connected Devices |
|-----------|-------------------|
| **I²C** | BME280, SHT40, SGP40 |
| **SPI** | MicroSD Card |
| **ADC / Analog** | MAX4466, Phototransistor |

---

## ⚡ Power Design

The board includes power-conditioning and decoupling circuitry for stable operation of the ESP32-S3 and connected peripherals.

### Key Considerations

- Power supply stability
- Power distribution
- Local decoupling
- Ground return paths
- Sensor supply requirements
- Analog and digital sections
- Proper power routing

---

## 🛠️ PCB Design

The complete PCB was designed using **KiCad**.

### Design Flow

```text
System Architecture
        ↓
Component Selection
        ↓
Schematic Design
        ↓
Footprint Assignment
        ↓
PCB Placement
        ↓
Power Routing
        ↓
Signal Routing
        ↓
Ground Plane / Copper Pour
        ↓
ERC Check
        ↓
DRC Check
        ↓
Gerber Generation
```

### PCB Design Considerations

- Component placement
- Power distribution
- Ground plane
- Decoupling capacitors
- I²C routing
- SPI routing
- Signal integrity
- Ground return paths
- PCB manufacturability
- Trace-width selection

---

## 🔍 PCB Verification

The PCB design was checked using KiCad verification tools.

- Electrical Rules Check (ERC)
- Design Rules Check (DRC)
- Connectivity verification
- Footprint verification
- PCB routing verification
- Gerber generation

---

## 3D PCB View

![ESP32-S3 IoT Board 3D View](Images/3d_view.png)

---

## 🎯 Skills Demonstrated

- ESP32-S3 hardware design
- Sensor interfacing
- I²C and SPI communication
- ADC interfacing
- Schematic design
- Component selection
- Footprint selection
- PCB layout
- Component placement
- PCB routing
- Power distribution
- Ground-plane design
- Decoupling
- Analog and digital signal routing
- ERC / DRC verification
- Gerber generation
- Hardware documentation

---

# 🚀 Future Developments

- **☁️ Cloud Monitoring** — Upload sensor data through Wi-Fi for remote monitoring and data logging.
- **📊 Web Dashboard** — Real-time visualization of temperature, humidity, pressure, VOC, and other sensor data.
- **📱 Mobile Application** — Remote monitoring through Wi-Fi or Bluetooth Low Energy.
- **🔋 Battery Operation** — Battery charging, monitoring, and low-power operation.
- **🔄 OTA Updates** — Wireless firmware updates.
- **📈 Data Analytics** — Historical data storage, visualization, and analysis.
- **🏠 Custom Enclosure** — Mechanical enclosure optimized for the sensors and connectors.
- **🔧 PCB Revision** — Further optimization of power distribution, signal integrity, placement, routing, and manufacturability.

---

## 🧰 Tools Used

| Tool | Purpose |
|------|---------|
| **KiCad** | Schematic capture and PCB design |
| **ESP-IDF** | ESP32-S3 firmware development |
| **GitHub** | Version control and documentation |

---

## 📚 Project Files

The repository contains

- KiCad schematic files
- KiCad PCB files
- Gerber files
- Component datasheets
- PCB images
- 3D PCB renders
- Project documentation

---


## Disclaimer

This project is made for educational purpose
