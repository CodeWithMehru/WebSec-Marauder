# WebSec Marauder Guardian — Development Journal

### Day 1 (Project kickoff & research)
- Researched defensive vs offensive Wi-Fi tools and legal/ethical considerations.
- Collected references on passive Wi-Fi scanning, BLE sniffing, and signal analysis.
- Decided to keep project strictly passive and educational; documented ethics in README.
- Created initial project outline, scope, and success criteria.
**Time spent:** 12 hours

### Day 2 (BOM & parts selection)
- Surveyed vendors (Amazon, Robu) for ESP32 boards, TFT displays, LiPo, chargers, antenna, buzzer.
- Compiled BOM.csv and optimized costs; added notes on parts I already own vs planned purchases.
- Chose ESP32-DevKitC-32UE for BLE + Wi-Fi dual support and ILI9341 TFT for visualization.
**Time spent:** 10 hours

### Day 3 (Mechanical design & 3D case)
- Modeled case layout concept (dimensions, mounting points) in Fusion360 / CAD.
- Exported STL for front/back case and iterated on fastening points and ventilation.
- Rendered a prototype image for repo documentation (placeholder image used).
**Time spent:** 18 hours

### Day 4 (Wiring diagrams & prototyping plan)
- Drew wiring-diagram.png showing connections: ESP32 SPI → TFT, TP4056 → LiPo, buzzer, switch, SD module.
- Added notes on pin choices, voltage rails, JST connector recommendations, and safety.
- Planned breadboard test steps and required tools (soldering, JST crimp).
**Time spent:** 10 hours

### Day 5 (Firmware architecture & module design)
- Designed firmware modular structure: wifi_scanner, bt_scanner, display, logger, gps, ota.
- Wrote API/CLI plan for logging format and HTTP upload schema (fields: timestamp, ssid, bssid, rssi, channel, gps).
- Prepared PlatformIO/Arduino structure and dependencies list.
**Time spent:** 23 hours

### Day 6 (Passive scanning experiments)
- Ran local experiments with ESP32 example sketches (WiFi.scanNetworks, BLEScanner) on devboard I have (or simulated).
- Measured timings and power draw; recorded sample outputs and filtered noisy SSIDs.
- Determined appropriate scan interval (tradeoff between battery and detection latency).
**Time spent:** 16 hours

### Day 7 (Logging & data format)
- Created CSV/JSON log schema for SD and HTTP upload. Example entry: `ts,ssid,bssid,rssi,chan,gps_lat,gps_lng`.
- Wrote logger pseudo-code and SD rotation policy (max file size, daily logs).
- Planned secure upload: HTTPS + token-based auth (no plaintext).
**Time spent:** 16 hours

### Day 8 (Safety, ethics, and documentation)
- Expanded README safety section; explicitly marked all offensive features as DISABLED.
- Wrote testing policy: only test on owned/permissioned networks, record consent.
- Added image disclaimer in README and updated journal.
**Time spent:** 8 hours

### Day 9 (UI/UX: display & alerts) 
- Designed on-screen UI for TFT: status bar, top N SSIDs, RSSI bar graph, alert banner.
- Decided buzzer behavior for passive alert thresholds (short beep for new unknown AP, longer for suspicious spike).
- Sketched CLI commands for querying logs and setting thresholds.
**Time spent:** 15 hours

### Day 10 (Roadmap, testing plan & next steps)
- Compiled final roadmap: purchase parts, assemble prototype, run controlled tests, publish firmware v0.1.
- Created test plan (lab tests, field tests, consent forms) and checklist for submission.
- Prepared files to push to repo (firmware skeleton, BOM, wiring, journal).
**Time spent:** 12 hours

---

### 2025-10-31 — Prototype wiring sketch, BOM update & visual mockup (est. 6 hours)
- Created a hand-drawn prototype wiring sketch and a photoreal wiring mockup showing how modules will connect: ESP32 DevKitC → ILI9341 TFT (SPI), TP4056 → LiPo battery → slide power switch → ESP32 VIN, INA219 on battery positive, MicroSD module on SPI, buzzer on GPIO25, and optional GPS on UART. The sketches include labeled pins and color-coded signal rails (VCC, GND, SPI, I2C, UART) to validate wiring before assembly.
- Updated BOM with planned parts and supplier references; prioritized low-cost, easy-to-source modules for fast prototyping.
- Uploaded the wiring mockup and schematic to `pcb_design/` as visual references. These images are design-stage visuals; I will replace them with in-hand photos and assembly logs after components arrive or are borrowed.
Time spent: 6 hours


 **Notes:**  
- The uploaded image in the repo is a prototype to visualize how the final build will look. Once physical components arrive and the assembly begins, actual device photos will be uploaded.  
- Firmware and documentation are developed from scratch for educational and ethical demonstration of Wi-Fi safety.  
- The design showcases a secure and educational replica for hackathon participants to understand wireless threats responsibly.
