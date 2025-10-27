# WebSec-Marauder-Guardian (Documentation)

**Status:** Prototype — Educational & Defensive Demonstration  
**Owner / Developer:** CodeWithMehru



## Project summary
**Marauder** is an ESP32-based wireless monitoring reference device documented here as part of the **WebSec-Marauder-Guardian** project. The goal is educational: to show hackathon students and peers how wireless threats can be *detected* and *defended against* using passive observation and logging.

This repository documents the device’s advertised capabilities for transparency, but the project is strictly **defensive**. Offensive features that actively disrupt or impersonate other devices are **explicitly disabled** and are not used. This repo contains no code or instructions that enable attacks.


## Advertised features (factual list — OFFENSIVE ITEMS MARKED)
> The list below reproduces the device’s advertised feature set for transparency. Offensive or abusive capabilities are explicitly marked **DISABLED** and will not be used in this project.

### Wi-Fi (advertised)
- **Scan APs** — scan for nearby Wi-Fi access points (SSID / BSSID / RSSI). *(allowed — passive)*
- **Scan Stations** — discover Wi-Fi client stations in range. *(allowed — passive)*
- **Deauth Flood** — send deauthentication packets to disrupt connections. **(DISABLED — OFFENSIVE)**
- **AP Clone Spam** — clone and spam access points. **(DISABLED — OFFENSIVE)**
- **Karma** — respond to probe requests to collect clients. **(DISABLED — OFFENSIVE)**
- **Evil Portal** — fake captive portal to capture credentials. **(DISABLED — OFFENSIVE)**

### Bluetooth (advertised)
- **Bluetooth Sniffer** — sniff Bluetooth advertisements in range. *(allowed — passive)*
- **Detect Card Skimmers** — detect Bluetooth-enabled skimmers (monitoring only). *(allowed — passive)*
- **Sour Apple** — perform Sour Apple attacks. **(DISABLED — OFFENSIVE)**
- **Swiftpair Spam** — spam pairing requests at nearby devices. **(DISABLED — OFFENSIVE)**
- **Samsung BLE Spam** — BLE spam targeting certain devices. **(DISABLED — OFFENSIVE)**

### Other (advertised)
- **Packet Monitor** — visualize Wi-Fi packet density on a channel. *(allowed — passive)*
- **Signal Monitor** — show RSSI / signal strength of nearby devices. *(allowed — passive)*
- **GPS** — support GPS modules for tagging event locations (for testing on owned devices). *(allowed — passive)*
- **SD Card Support** — save passive logs and statistics to SD card. *(allowed — passive)*
- **Web Update (OTA)** — update firmware via web interface (maintenance). *(allowed)*
- **Command Line Interface (CLI)** — interact with device for diagnostics and monitoring. *(allowed)*
- **Customizable Settings / Multiple Device Support** — UX/config options and compatibility features. *(allowed)*



## What I will actually use / demonstrate (allowed & ethical)
- Passive Wi-Fi scanning: SSID, BSSID, RSSI, channel (no transmission).
- Passive station discovery and counts on **networks I own or have permission to test**.
- Promiscuous-mode monitoring for counting management frame spikes as **detection only** (no injecting/transmitting).
- Passive Bluetooth advertisement scanning (no pairing, no injection).
- Signal strength visualization and immediate alerts on OLED + buzzer.
- Optional local logging to a microSD card and secure HTTP upload to a private server for later analysis.
- GPS tagging to map where events were observed (used only for owned/test networks).
- OTA firmware updates and a simple CLI for maintenance (not for spreading offensive tools).



## Safety & Ethics (must read)
- **Do not** run offensive features (deauth, jamming, fake portals, credential capture, spam) unless you have explicit written permission from the device/network owner and the activity is legal where you are.
- This repository **contains no offensive code** and does not provide instructions for performing active attacks.
- When testing, always use equipment you own or have written permission to test. Keep records of consent for audits.



## Repo contents (documentation only)
- `README.md` — project overview and safety notes (this file).  
- `JOURNAL.md` — development / testing log.  
- `LICENSE` — project license.  
- `hardware/parts-list.txt` — parts used (reference).  
- `hardware/wiring-diagram.png` — wiring/diagram or photo(s) (upload your image).



## How to contribute / learn
This repo is for documentation and education. If you want to contribute, open an issue or PR proposing **defensive, legal** improvements (UI, passive analysis, logging format, educational materials). Offensive or enabling content will be rejected.


## [Prototype render (demo image)](hardware/3D Prototype.png)

**Image disclaimer:** The product/board images in this repo are for documentation and demo purposes only. The ESP32/Marauder images were downloaded as reference/demo images from the web to represent the prototype — they do not imply the physical hardware is currently in-hand. I will update the repository with original photos and receipts when the components are available.

## Contact
Mehru — https://github.com/CodeWithMehru