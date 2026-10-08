
## 📖 Overview

This project presents a fully automated sliding door system that mimics the behavior of commercial entrance doors found in shopping malls and airports. The system combines sensing, actuation, wireless communication, and access control into a single integrated mechatronic platform.

The door operates automatically upon detecting a human presence via a PIR sensor. An onboard LCD and RGB LED provide real-time status feedback, while an HC-05 Bluetooth module enables wireless monitoring and alerts to a paired smartphone. For maintenance and secure access, an RFID module grants master override privileges. Motion is driven by a DC motor through an L298N driver using a rack & pinion mechanism for smooth, precise door travel.

---

## ✨ Key Features

- **🧠 Human Detection** — PIR sensor detects approaching individuals and triggers automatic door operation
- **📟 Real-Time Status Display** — 16x2 LCD + RGB LED indicate system state (Idle / Opening / Open / Closing / Locked)
- **📱 Wireless Monitoring** — HC-05 Bluetooth module sends status alerts and event notifications to a paired phone
- **🔐 Secure Access Control** — RFID module with master override for maintenance and authorized entry
- **⚙️ Precise Motion Control** — L298N motor driver paired with a rack & pinion mechanism for reliable linear door movement
- **🛠️ Modular Design** — Prototyped with foam board for rapid iteration and easy demonstration

---

## 🧩 System Architecture

```
        ┌──────────────┐        ┌──────────────┐
        │  PIR Sensor  │        │  RFID Module │
        └──────┬───────┘        └──────┬───────┘
               │                       │
               ▼                       ▼
        ┌─────────────────────────────────────┐
        │           Arduino (MCU)             │
        └──┬──────────┬───────────┬───────────┘
           │          │           │
           ▼          ▼           ▼
      ┌────────┐ ┌────────┐ ┌──────────────┐
      │ LCD +  │ │ L298N  │ │   HC-05      │
      │ RGB LED│ │ Driver │ │  Bluetooth   │
      └────────┘ └───┬────┘ └──────┬───────┘
                     │             │
                     ▼             ▼
                ┌─────────┐   ┌─────────┐
                │  DC     │   │  Phone  │
                │ Motor + │   │ (Alerts)│
                │Rack&Pin│   └─────────┘
                └─────────┘
```

---

## 🔧 Hardware Components

| Component | Purpose |
|-----------|---------|
| Arduino (Uno/Nano) | Main microcontroller |
| PIR Sensor (HC-SR501) | Human presence detection |
| RFID Module (RC522) | Secure access / master override |
| L298N Motor Driver | Controls DC motor direction & speed |
| DC Motor + Rack & Pinion | Drives the sliding door mechanism |
| 16x2 LCD (I2C) | Displays system status |
| RGB LED | Visual status indicator |
| HC-05 Bluetooth Module | Wireless monitoring & alerts |
| Foam Board | Physical door prototype |
| Power Supply (12V/5V) | System power |

---

## 💻 Software & Tools

- **Arduino IDE** — Embedded C/C++ programming
- **TinkerCAD** — Circuit simulation and logic verification
- **SolidWorks** — CAD design of the door frame and rack & pinion assembly
- **Bluetooth Terminal App** — For receiving wireless alerts on phone

---

## ⚙️ How It Works

1. **Idle State** — Door remains closed; LCD shows `"SYSTEM READY"`, RGB LED is green.
2. **Detection** — PIR sensor detects motion → Arduino triggers the open sequence.
3. **Opening** — L298N drives the DC motor; rack & pinion slides the door open. LCD shows `"DOOR OPENING"`, LED turns blue.
4. **Open State** — Door holds open for a preset duration. LCD shows `"WELCOME"`, LED green.
5. **Closing** — After timeout, motor reverses; door closes. LCD shows `"DOOR CLOSING"`, LED turns yellow.
6. **RFID Override** — Authorized tag → master mode (e.g., hold door open for maintenance). Unauthorized → alert sent via Bluetooth.
7. **Wireless Alerts** — Every state change is pushed via HC-05 to a paired phone.

---

## 👨‍💻 My Role

- **CAD Design & Prototyping** — Modeled the door assembly and rack & pinion mechanism in **SolidWorks**; built the physical prototype using **foam board**.
- **Circuit Simulation** — Simulated and validated circuit logic in **TinkerCAD** before hardware implementation.
- **Embedded Programming** — Wrote and debugged **Arduino** firmware for sensor fusion, motor control, display, and Bluetooth communication.
- **System Integration** — Integrated sensors, actuators, and communication modules into a cohesive working system; handled wiring, power distribution, and debugging.

---

6. **Power up** and test detection, RFID override, and Bluetooth alerts

---

## 📸 Demo & Media

> _Add photos of the prototype, a short demo video, and screenshots of the Bluetooth terminal output here._

---

## 🔮 Future Improvements

- Add ultrasonic sensor for redundancy in human detection
- Integrate WiFi (ESP8266/ESP32) for cloud-based monitoring
- Implement safety beam to prevent closing on obstructions
- Design a PCB for cleaner wiring and compact packaging

---

## 📜 License

This project was developed for academic purposes as part of a **Mechatronics course**. Feel free to reference it for learning and non-commercial use.

---

## 🙌 Acknowledgments

- Course instructors and lab staff for guidance and resources
- Open-source Arduino community for libraries and reference designs
