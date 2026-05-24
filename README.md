# 🌱 ESPrinkler Retic Controller

An open-source, ESP32-based smart irrigation controller built with **ESPHome** and designed for seamless integration with **Home Assistant**.

ESPrinkler gives you full local control over your irrigation system—no cloud services, no subscriptions, and no reliance on external servers. All schedules are stored directly on the device, ensuring your system continues to run even if Home Assistant or network connectivity is unavailable.

---

## 🚀 Features

- Fully local operation (no cloud dependencies)  
- Home Assistant integration via ESPHome  
- Standalone operation with onboard schedule storage  
- Solid-state design with optically isolated outputs  
- Control up to **8 irrigation zones + pump/master valve**  
- Support for **up to 3 independent watering programs**  
- Flexible scheduling:
  - Day-of-week control  
  - Up to 4 start times per program  
  - Configurable zone durations and repeat cycles  
- LED indicators for system status and outputs  

---

## 🧠 How It Works

ESPrinkler operates using up to **three independent watering programs**, each of which defines:

- When watering occurs (days + start times)  
- Which zones are active  
- How long each zone runs  
- Whether the cycle repeats  

All configuration is done through **Home Assistant entities**, and once configured, the controller runs autonomously.

⚠️ Programs **do not prevent overlap automatically**, so you must ensure schedules don’t conflict.

---

## 🏗️ Hardware Overview

The controller is built around an **ESP32 (ESP32-DevKitC compatible)** and a custom PCB designed for irrigation control.

Key hardware characteristics:

- Compatible with 24VAC reticulation systems
- Solid-state solenoid switching  
- Isolated AC/DC sections
- Fused solenoid power output
- Terminal block wiring for:
  - Power input  
  - Pump/master valve  
  - 8 irrigation zones  
- Optional external LEDs for:
  - Wi-Fi status  
  - System status  

For full specifications, wiring diagrams, and pinouts, see:  
**[Hardware Specifications Wiki](../../wiki/Hardware-Specifications)**

---

## ⚡ Requirements

To build and use ESPrinkler, you’ll need:

- ESP32 Dev Board (ESP32-DevKitC compatible)  
- ESPrinkler PCB (assembled or DIY)  
- 24VAC transformer (~30VA recommended)  
- Fuse (M205 1A Quick Blow)  
- Suitable enclosure  
- Wiring/connectors for your installation  
- Home Assistant with ESPHome installed  

---

## 🛠️ Getting Started

### 1. Set Up ESPHome

Install and configure ESPHome in Home Assistant:  
https://esphome.io/guides/getting_started_hassio/

---

### 2. Prepare Firmware

- Copy the provided `secrets.yaml` values into your ESPHome setup  
- Import the `retic-controller.yaml` file into ESPHome (Add new device -> Import from file) 
- Update the substitutions (Wi-Fi, API key, device name, etc.)  

---

### 3. Flash the Device

- Click the 3 dots under the new configuration
- Click "install" and follow your preferred method to flash your ESP32
- I recommend choosing "manual download" and then navigate to [ESPHome Web](https://web.esphome.io/) to flash your device using the binary file
- Once flashed, the device will appear in Home Assistant

---

### 4. Wire the Hardware

- Connect 24VAC input  
- Connect solenoids (zones + common)  
- Install fuse  
- Optional: connect status LEDs  

⚠️ **Warning:** This involves working with mains/low-voltage AC systems. Follow all relevant electrical safety standards and regulations.
👉 See the **[Hardware Specifications Wiki](../../wiki/Hardware-Specifications)** for full wiring details and pinouts.

---

### 5. Configure in Home Assistant

Once the device is online:

- Enable one or more programs  
- Set watering days  
- Configure start times  
- Enable zones and durations
- An example [dashboard page .yaml file](https://github.com/slippery-carrot/ESPrinkler-Retic-Controller/blob/main/ESPHome/ESPrinkler_Dashboard_Example.yaml) has been provided as an example layout in Home Assistant

⚠️ **NOTE:** The example dashboard yaml uses [Mushroom Cards](https://github.com/piitaya/lovelace-mushroom), so make sure to install that if you want it to function.
👉 See the **[Home Assistant Entities Wiki](../../wiki/Home-Assistant-Entities)** for a full breakdown of all controls, sensors, and configuration options.

---

## 🌿 Program Basics

Each program requires:

- ✅ Program enabled  
- ✅ At least one watering day  
- ✅ At least one start time  
- ✅ At least one active zone with duration  

Optional settings:

- Repeat cycles (repeat full zone sequence)  

---

## 📊 Home Assistant Integration

ESPrinkler exposes a full set of:

- **Controls** (start/stop, enable program, pause)  
- **Sensors** (current zone, time remaining, next cycle)  
- **Configuration entities** (days, times, durations, repeats)  
- **Diagnostics** (Wi-Fi signal, uptime, firmware, etc.)  

👉 Full details here:  
**[Home Assistant Entities Wiki](../../wiki/Home-Assistant-Entities)**

---

## 🧩 Project Structure

- Firmware: ESPHome YAML configuration and secrets example, including example dashboard layout  
- Hardware: Custom PCB design in KiCad and production files
- Documentation:
  - README (this file)  
  - Hardware Wiki  
  - Home Assistant Wiki  

---

## ⚠️ Important Notes

- Programs **can overlap** if configured incorrectly—this is not automatically prevented  
- Default start times may be active—always verify configuration  
- Ensure the transformer you choose is correctly sized for your solenoid load
- Always use appropriate fuse protection  

---

## 🔗 Documentation

- 📘 **Hardware Wiki** – Pinouts, wiring, electrical specs  
- 📗 **Home Assistant Wiki** – Entities, controls, automation  

---
