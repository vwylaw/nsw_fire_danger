# Info

Integrate NSW Rural Fire Service fire danger ratings into Home Assistant with a beautiful custom card.

**🛑 RESTART REQUIRED: You must restart Home Assistant after installing this integration.**

## Features

- 🎨 Beautiful custom Lovelace card matching the NSW RFS website
- 🎯 Semi-circular gauge showing fire danger levels
- 📅 3-day forecast included
- 🚫 Total fire ban alerts
- 🌏 All 21 NSW fire weather areas supported
- ⚡ Easy configuration with dropdown area selection
- 🔄 Auto-updates every 30 minutes

## What You Get

### Custom Card
A stunning visualization that replicates the official NSW RFS fire danger display:
- Color-coded semi-circular gauge (Green → Yellow → Orange → Red)
- Animated needle pointing to current danger level
- Large rating display with official colors
- Safety action messages for each rating level
- Total fire ban indicator
- 3-day forecast at the bottom

### Sensors
8 sensors per configured area:
- Fire danger ratings (Today, Tomorrow, Day 3, Day 4)
- Total fire ban status (Today, Tomorrow, Day 3, Day 4)

## Quick Setup

1. **Install via HACS**
   - HACS → Integrations → + → Search "NSW Fire Danger"
   
2. **Add Integration**
   - Settings → Devices & Services → + Add Integration
   - Search "NSW Fire Danger Ratings"
   - Select your area from dropdown
   
3. **Register Card**
   - The card is **automatically registered** for you! No manual steps required.
   - Just clear your browser cache if it doesn't show up.

4. **Add Card to Dashboard**
   ```yaml
   type: custom:nsw-fire-danger-card
   entity: sensor.nsw_fire_danger_greater_sydney_region_rating_today
   ```

## Data Source

Official NSW Rural Fire Service API - updated every 30 minutes with accurate, real-time fire danger information.

## Perfect For

- 🏡 Homeowners in fire-prone areas
- 🚒 Community fire awareness
- 📱 Mobile dashboard fire alerts
- 🔔 Automated fire danger notifications
- 👨‍👩‍👧‍👦 Family safety planning

Stay informed. Stay safe. 🔥
