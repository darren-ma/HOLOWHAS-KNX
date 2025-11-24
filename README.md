# HOLOWHAS Multi-Room Streaming Amplifier – KNX Integration

[![OpenAudio](https://img.shields.io/badge/OpenAudio-Official-blue)](https://www.openaudiohome.com/)

This repository provides guidance for integrating **HOLOWHAS multi-room streaming amplifiers** with KNX-based home automation systems using ETS software. It focuses on **ETS configuration, device setup, and Group Address (GA) read/write**.

---

## OpenAudio Official Website

For more information about HOLOWHAS products: [openaudiohome.com](https://www.openaudiohome.com/)

---

## Supported HOLOWHAS Models

| Model | Description |
|-------|------------|
| **HOLO‑WHAS** | 8 zones, total 960W (16×60W), supports AirPlay 2 / Spotify Connect / DLNA / Bluetooth / USB Audio |
| **HOLO‑WHAS Ultra** | Adds RCA, HDMI ARC, SPDIF, and USB disk inputs |
| **HOLO‑WHAS Ultra‑GC** | Ultra features + Google Cast support |
| **HOLO‑WHAS Plus** | Higher power: 100W per channel, total 1600W |
| **HOLO‑WHAS Max** | Flagship: 16×200W, total 3200W, supports BTL mode and line-out |

---

## ETS Configuration Guide

### 1. Project Setup
1. Open **ETS5 or ETS6** → `File → New Project`  
2. Name your project (e.g., `HOLOWHAS_KNX_Home`)  
3. Save the project

### 2. Add Devices
1. In **Topology → Insert Device**, select:
   - Manufacturer: `HOLOWHAS`
   - Device Model: select corresponding amplifier model  
2. The device appears in the topology tree  
3. Each device has a **Physical Address** (format: `Area.Line.Device`, e.g., `1.1.10`)

### 3. Group Address (GA) Configuration
KNX uses Group Addresses for logical communication.

1. Open **Group Addresses** tab  
2. Example GA structure:
3. 1/0/1 → Living Room Zone On/Off
1/0/2 → Living Room Zone Volume
2/0/1 → Bedroom Zone On/Off
2/0/2 → Bedroom Zone Volume
3. Create new GA:
- Click `New Group Address`
- Enter name (e.g., `LivingRoom_Zone_OnOff`)
- Select type (Switch, Dimming, Percentage, etc.)
4. Drag GA to the corresponding device function in the ETS topology

### 4. Download Configuration
1. Connect the device to the KNX bus  
2. Click **Download → Selected Devices**  
3. ETS programs the device with physical address and GA mapping

### 5. Monitoring & Testing
- Use **ETS Monitor** to read/write GAs and verify functionality  
- Control zones using switches, KNX sensors, or visualization panels  
- Ensure GA type matches the function (e.g., Switch vs Percentage)

---

## Recommended GA Naming Convention
