![ESP-IDF](https://img.shields.io/badge/ESP--IDF-v5.5.2-ff69b4?style=for-the-badge)
![ESP32](https://img.shields.io/badge/ESP32-Classic_BT-orange?style=for-the-badge)
![A2DP](https://img.shields.io/badge/A2DP-Source-blueviolet?style=for-the-badge)
![FreeRTOS](https://img.shields.io/badge/FreeRTOS-Enabled-brightgreen?style=for-the-badge)
![C](https://img.shields.io/badge/C-Language-blue?style=for-the-badge)

# ESP32 A2DP Source – Carvaan Mini

This project streams generated 440Hz stereo audio from ESP32
to a Carvaan Mini Bluetooth speaker using Classic Bluetooth A2DP.

## Features
- ESP-IDF v5.x
- Classic Bluetooth
- A2DP Source
- Real-time audio generation
- Stable stereo streaming (44.1kHz)

## Hardware
- ESP32 Dev Board
- Carvaan Mini Bluetooth Speaker

## Result
Successful Bluetooth connection and audio playback.
# ESP32 A2DP Source • Carvaan Mini 🎧

An **ESP32 Classic Bluetooth A2DP Source** demo that streams audio (e.g., sine tone and future WAV files) from an ESP32 to a Bluetooth speaker like the **Saregama Carvaan Mini** using **ESP-IDF v5.x**.

---

## 🚀 Features

✅ Classic Bluetooth A2DP Source implementation  
✅ Auto discovery & connect to Carvaan Mini  
✅ Generates real-time 44.1kHz stereo PCM audio  
✅ ESP-IDF native solution — no Arduino  
✅ Simple audio callback for custom sound

---

## 🛠 Supported Audio Format

If you load audio data from a file (future feature):

| Property | Value |
|----------|--------|
| Format | `.wav` |
| Codec | PCM |
| Bitrate | 1411 kbps |
| Sample rate | 44.1 kHz |
| Channels | Stereo |

> NOTE: This is the native SBC/A2DP expected format for Bluetooth audio streaming. (Source: ESP32-A2DP docs)

---

## 📦 Folder Structure

```sh
.
├── main
│   └── main.c                 # Your A2DP Source code
├── components
│   └── ESP32-A2DP            # (optional future WAV/decoder libs)
├── CMakeLists.txt
├── sdkconfig                # Excluded from repo via .gitignore
├── .gitignore
└── README.md
Build & Flash

Ensure you have the ESP-IDF environment set up:

cd ESP32-A2DP-Source-Carvaan
idf.py fullclean
idf.py build
idf.py -p COM3 flash monitor

Replace COM3 with your serial port.

📡 Pair & Play

Turn ON your Carvaan Mini

Switch to Bluetooth mode

ESP32 will start discovery automatically

You should see:


Pair & connect — simple audio should start

📈 Expected Output (Serial)
Starting device discovery...
Found device: Carvaan mini
Carvaan Found! Connecting...
A2DP Connected!
Media Start Acknowledged
❗ Common Notes

BT_BTC: A2DP Enable without AVRC: This warning is OK

osi_mem_dbg_... warnings are harmless for audio

Classic Bluetooth only — BLE memory is released

🚧 Next Enhancements

✔ Play WAV from SPIFFS
✔ Add MP3 decoding support
✔ Stream audio over Wi-Fi
✔ Add control buttons (play/pause/next)
