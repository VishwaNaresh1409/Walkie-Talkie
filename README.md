# 📻 Walkie-Talkie

A GSM-based walkie-talkie system built on the **ESP32** microcontroller with a **SIM800** modem, developed using the **PlatformIO** ecosystem and the **Arduino** framework.

---

## 📋 Overview

This project turns an ESP32-based board (specifically the LilyGO T-Call) into a walkie-talkie device by leveraging the SIM800 GSM module for cellular voice communication. It supports call initiation and receiving, enabling two-way voice communication over a GSM network — no Wi-Fi required.

---

## 🛠️ Hardware Requirements

| Component | Details |
|-----------|---------|
| Microcontroller | ESP32 (LilyGO T-Call or compatible `esp32dev` board) |
| GSM Modem | SIM800 (integrated on LilyGO T-Call) |
| SIM Card | Any active GSM SIM card with calling support |

---

## 💻 Software Requirements

- [PlatformIO](https://platformio.org/) (IDE or CLI)
- [Arduino Framework](https://www.arduino.cc/) for ESP32
- [TinyGSM](https://github.com/vshymanskyy/TinyGSM) library (`^0.12.0`)

---

## 📁 Project Structure

```
Walkie-Talkie/
├── src/               # Main source code
├── include/           # Header files
├── lib/               # Project-specific libraries
├── test/              # Unit tests
├── .vscode/           # VS Code / PlatformIO IDE settings
├── platformio.ini     # PlatformIO project configuration
└── call and recieve   # Notes/reference for call & receive logic
```

---

## ⚙️ Configuration

The project is configured via `platformio.ini`:

```ini
[env:lilygo-t-call]
platform = espressif32
board = esp32dev
framework = arduino
monitor_speed = 115200

lib_deps =
    vshymanskyy/TinyGSM@^0.12.0

build_flags =
    -DTINY_GSM_MODEM_SIM800
    -DTINY_GSM_RX_BUFFER=1024
```

- **Board:** `esp32dev` (LilyGO T-Call)
- **Monitor Speed:** 115200 baud
- **Modem:** SIM800 (set via `TINY_GSM_MODEM_SIM800` flag)
- **RX Buffer:** 1024 bytes for reliable GSM data handling

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/VishwaNaresh1409/Walkie-Talkie.git
cd Walkie-Talkie
```

### 2. Open in PlatformIO

Open the project folder in **VS Code** with the PlatformIO extension installed, or use the PlatformIO CLI.

### 3. Insert a SIM Card

Insert an active GSM SIM card (with calling enabled) into the LilyGO T-Call board's SIM slot.

### 4. Build & Upload

```bash
pio run --target upload
```

### 5. Monitor Serial Output

```bash
pio device monitor
```

---

## 📞 Features

- Make and receive GSM voice calls using the SIM800 modem
- Runs on the lightweight Arduino framework
- Serial monitor support at 115200 baud for debugging
- Configurable via PlatformIO build flags

---

## 📦 Dependencies

| Library | Version | Purpose |
|---------|---------|---------|
| [TinyGSM](https://github.com/vshymanskyy/TinyGSM) | `^0.12.0` | GSM modem communication |

---

## 🔧 Troubleshooting

- **No serial output:** Ensure your monitor speed is set to `115200`.
- **Modem not responding:** Check that the SIM card is properly inserted and the board is powered adequately (SIM800 can draw up to 2A during calls).
- **Call fails:** Verify the SIM card has active GSM service and is not PIN-locked.

---

## 🙏 Acknowledgements

- Forked from [Proestofpros/Walkie-Talkie](https://github.com/Proestofpros/Walkie-Talkie)
- Built with [TinyGSM](https://github.com/vshymanskyy/TinyGSM) by Volodymyr Shymanskyy
- Hardware: [LilyGO T-Call](https://github.com/Xinyuan-LilyGO/LilyGo-T-Call-SIM800) ESP32+SIM800 board

---

## 📄 License

This project does not currently specify a license. Please contact the repository owner for usage terms.
