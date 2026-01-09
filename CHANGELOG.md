# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2026-01-09

### Added
- Initial release of NSW Fire Danger Ratings integration
- Support for all 21 NSW fire weather areas
- Custom Lovelace card with NSW RFS website design
- Semi-circular gauge visualization
- 3-day fire danger forecast
- Total fire ban indicators
- Config flow UI with dropdown area selection
- 8 sensors per area (4 ratings + 4 fire ban statuses)
- Auto-updates every 30 minutes from official NSW RFS API
- Mobile-friendly responsive card design
- Official NSW RFS color scheme
- Safety action messages for each danger level

### Features
- Beautiful custom card matching official NSW RFS design
- Color-coded gauge (Green → Yellow → Orange → Red)
- Animated needle pointing to current danger level
- Tomorrow, Day 3, and Day 4 forecast
- Fire ban status for each day
- Area name and date display
- Automatic data refresh
- Easy configuration via UI

### Technical
- Cloud polling integration
- aiohttp for async API calls
- Custom Lovelace card in JavaScript
- Config flow with dropdown selector
- Data coordinator for efficient updates
- Error handling and retry logic
- Proper Home Assistant integration structure

## [Unreleased]

### Planned
- Multi-language support
- Historical data tracking
- Custom notification service
- Additional card layouts
- Weekly forecast view
- Fire danger trends

---

[1.0.0]: https://github.com/vwylaw/nsw_fire_danger/releases/tag/v1.0.0
