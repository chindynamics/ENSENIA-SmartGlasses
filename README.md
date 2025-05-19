# ENSENIA-SmartGlasses
This project presents an innovative pair of smart glasses designed to bridge the communication gap between people with hearing impairments and the rest of society. The system leverages a visual projection mechanism that displays text or symbols directly in front of the user's eyes, allowing for real-time transcription of spoken language. Additionally, the device incorporates an educational feature to support the learning of Mexican Sign Language (LSM), enabling interactive lessons projected through the glasses.

The hardware consists of a mini OLED display, mirrors, and a custom lens system designed to magnify and reflect the image toward the user's line of sight without obstructing normal vision. The software pipeline processes incoming audio, transcribes it using speech recognition, and converts it into visual content. The educational mode includes visual guides to help users learn sign language interactively.

This project was created with the goal of improving accessibility, autonomy, and social inclusion for deaf individuals in Mexico and beyond. It aims to offer a dual solution: assistive communication and sign language learning, all within a wearable and affordable format.

![lentes](https://github.com/user-attachments/assets/52b6201c-5ab9-48de-bff0-e031ff3eab7a)

## Technical Specifications

### Hardware
- **Microcontrollers**  
  - Arduino Nicla Vision (gesture capture & inference)  
  - Arduino Nano ESP32 (OLED UI & control)  
- **Display & Optics**  
  - 0.96″ monochrome OLED display (128×64 px)  
  - Semi–transparent beam splitter, 45° mirror & Fresnel lens array  
  - Custom 3D‑printed mounts and adapters for ergonomic fit  
- **Sensors & Controls**  
  - Capacitive touch buttons (Left, Select, Right)  
  - Power management via lithium‑ion battery + charging module  
- **Interconnections**  
  - UART serial link between Nicla Vision and ESP32  
  - (Future work) BLE module for wireless data sync

### Software & Firmware
- **Gesture Recognition**  
  - MobileNetV2 deep neural network (quantized for low‑power)  
  - Trained and exported via Edge Impulse  
  - Inference runtime running on Nicla Vision’s OpenMV environment  
- **User Interface**  
  - Custom UI animations created in After Effects, exported as frame sequences  
  - Menu modes:  
    1. **Translate** — live sign‑to‑text  
    2. **Learning** — interactive practice mini‑game  
    3. **Settings** — user preferences  
- **Codebase**  
  - Arduino C++
  - MicroPython
  - u8g2 library for display frame buffering  
- **3D Modeling & PCB Design**  
  - 3D parts designed in Fusion 360; exported as STL for printing  
  - PCBs laid out in KiCad:  
    - Power & camera board  
    - UI & controls board  
    - Sensor interface board

### Performance
- **Inference**  
  - 21 static hand‑shape classes  
  - 99% classification accuracy; 98.5% F1‑score  
  - Average inference latency: ~50 ms per frame  
- **Power**  
  - Continuous operation: ~2 hours on a 500 mAh battery  
  - Standby mode for idle periods to conserve energy
