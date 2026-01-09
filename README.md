# 🔥 NSW Fire Danger Ratings for Home Assistant

[![hacs_badge](https://img.shields.io/badge/HACS-Default-orange.svg)](https://github.com/custom-components/hacs)
[![GitHub release](https://img.shields.io/github/release/vwylaw/nsw_fire_danger.svg)](https://github.com/vwylaw/nsw_fire_danger/releases)
[![License](https://img.shields.io/github/license/vwylaw/nsw_fire_danger.svg)](LICENSE)

A custom Home Assistant integration that provides NSW Rural Fire Service fire danger ratings with a beautiful custom Lovelace card. Matches the official NSW RFS website design!

![NSW Fire Danger Card](https://raw.githubusercontent.com/vwylaw/nsw_fire_danger/main/images/card-preview.png)

---

## ✨ Features

- 🎨 **Beautiful Custom Card**: Matches the official NSW RFS website design.
- 🎯 **Semi-Circular Gauge**: Color-coded fire danger meter (Green → Yellow → Orange → Red).
- 📅 **3-Day Forecast**: See fire danger for tomorrow, day 3, and day 4.
- 🚫 **Total Fire Ban Alerts**: Visual indicators and badges for fire ban status.
- 🌏 **21 NSW Regions**: Full support for all NSW fire weather areas.
- ⚙️ **Easy Configuration**: User-friendly dropdown UI for area selection.
- 🔄 **Auto-Updates**: Data refreshes every 30 minutes from the official NSW RFS API.
- 📱 **Mobile Friendly**: Responsive design that looks great on all devices.

---

## 🚀 Quick Start Guide

### 1. Installation

#### HACS (Recommended)
1. Open **HACS** in Home Assistant.
2. Go to **Integrations**.
3. Click the **+** button.
4. Search for "**NSW Fire Danger Ratings**".
5. Click **Download**.
6. **🛑 IMPORTANT: Restart Home Assistant required after installation.**

#### Manual Installation
1. Download the latest release.
2. Extract the `nsw_fire_danger` folder to your `/config/custom_components/` directory.
3. **🛑 IMPORTANT: Restart Home Assistant required after installation.**

### 2. Configuration

1. After restarting, go to **Settings** → **Devices & Services**.
2. Click **+ Add Integration**.
3. Search for "**NSW Fire Danger Ratings**".
4. Select your **Fire Weather Area** from the dropdown.
5. Click **Submit**.

### 3. Setup Custom Card

The custom card is **automatically registered** for you when the integration is set up! No manual resource configuration is required.

**💡 Pro Tip**: If the card doesn't appear immediately, clear your browser cache (**Ctrl+Shift+R**) or use Incognito mode to ensure the new card code is loaded.

---

## 🎨 Using the Custom Card

Add a new card to your dashboard and use the following YAML:

```yaml
type: custom:nsw-fire-danger-card
entity: sensor.nsw_fire_danger_greater_sydney_region_rating_today
```

### Card Features:
- **Header**: Area name and current date.
- **Gauge**: Animated needle pointing to current danger level.
- **Safety Message**: Official action messages (e.g., "Be ready to act").
- **Fire Ban**: Today's status with color-coded badge.
- **Forecast**: 3-day grid showing rating and fire ban status.

---

## 📊 Sensors Created

For each configured area, mortality created 8 sensors:

| Sensor Type | Description |
|-------------|-------------|
| **Rating Today** | Current fire danger level (MODERATE, HIGH, EXTREME, CATASTROPHIC) |
| **Rating Tomorrow** | Forecasted rating for tomorrow |
| **Rating Day 3** | Forecasted rating for the day after tomorrow |
| **Rating Day 4** | Forecasted rating for day 4 |
| **Total Fire Ban Today** | Status for today (Yes/No) |
| **Total Fire Ban Tomorrow** | Forecasted status for tomorrow |
| **Total Fire Ban Day 3** | Forecasted status for day 3 |
| **Total Fire Ban Day 4** | Forecasted status for day 4 |

---

## 🔔 Automation Example

Get notified when fire danger reaches EXTREME:

```yaml
automation:
  - alias: "Fire Danger EXTREME Alert"
    trigger:
      - platform: state
        entity_id: sensor.nsw_fire_danger_greater_sydney_region_rating_today
        to: "EXTREME"
    action:
      - service: notify.mobile_app
        data:
          title: "⚠️ EXTREME Fire Danger"
          message: "Fire danger is EXTREME for Greater Sydney Region. Take action now!"
```

---

## 🌏 Available Areas

The integration supports all 21 NSW fire weather areas, including:
- Far North Coast
- North Coast
- Greater Hunter
- Greater Sydney Region
- Illawarra/Shoalhaven
- Far South Coast
- Monaro Alpine
- ACT
- ... and all others.

---

## 🛠️ Troubleshooting

### Card Not Appearing?
1. Verify the resource is registered in **Settings** → **Dashboards** → **Resources**.
2. Perform a hard refresh in your browser (**Ctrl+Shift+R** or **Cmd+Shift+R**).
3. Check the Home Assistant logs for any setup errors.

### Sensors Show "Unknown"?
1. Wait up to 30 minutes for the first polling cycle.
2. Check your internet connection.
3. Verify your selected area in the integration settings.

---

## 👩‍💻 For Developers

### HACS Submission
This integration is prepared for HACS. Requirements:
- `hacs.json` for metadata.
- `manifest.json` with versioning.
- Semi-circular gauge logic in `nsw-fire-danger-card.js`.

### Contributing
Please see [CONTRIBUTING.md](CONTRIBUTING.md) for details on how to contribute to this project.

---

## 📜 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

**Stay safe and fire aware!** 🔥
