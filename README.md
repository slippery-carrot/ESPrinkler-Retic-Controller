# ESPrinkler Retic Controller

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Hardware Requirements](#hardware-requirements)
- [Software Requirements](#software-requirements)
- [Installation](#installation)
- [Configuration](#configuration)
  - [ESPHome Configuration](#esphome-configuration)
  - [Home Assistant Integration](#home-assistant-integration)
- [Usage](#usage)
- [Customization](#customization)
- [Contributing](#contributing)
- [License](#license)

## Overview

ESPrinkler Retic Controller is an ESPHome-based irrigation controller built around the ESP32. It integrates seamlessly with Home Assistant for monitoring and control, while storing schedules in onboard flash for fully independent operation so it does not rely solely on HA to run.

## Features

- **Standalone scheduling**: Up to 3 independent watering programs.
- **Multi-zone support**: Control up to 8 irrigation zones plus a main pump valve.
- **Flexible programming**: Configure watering days of the week, up to 4 start times per program, durations, and overlap.
- **Real-time status**: Expose program state, current zone, and remaining time to Home Assistant.
- **OTA updates**: Easy firmware upgrades via ESPHome.

## Hardware Requirements

- 24VAC transmformer, at least 10VA (dependant on your solenoids).
- [ESP32-WROOM-32U, 38 pin dev board](https://www.aliexpress.com/item/1005008209898668.html)
- Some sort of enclosure, such as [this](https://www.ebay.com/itm/253801792805?var=556465393265).

## Software Requirements

- [ESPHome](https://esphome.io) (>=1.0.0)
- [Home Assistant](https://www.home-assistant.io/) (>=2025.1)

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/<username>/ESPrinkler-Retic-Controller.git
   cd ESPrinkler-Retic-Controller
   ```
2. **Install ESPHome**
   ```bash
   pip install esphome
   ```
3. **Configure your secrets**
   - Copy `secrets.example.yaml` to `secrets.yaml` and fill in Wi-Fi credentials and other sensitive data.
4. **Build and upload**
   ```bash
   esphome run retic-controller.yaml
   ```

## Configuration

### ESPHome Configuration

### Home Assistant Integration

## Usage

## Customization

## Contributing

Please follow the code style and include relevant tests or documentation updates.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

