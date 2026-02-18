# Home Assistant Family Dashboard

A family-friendly Home Assistant dashboard designed for a wall-mounted tablet. Built around a Growatt SPH inverter with battery storage, managed by [Predbat](https://github.com/springfall2008/batpred) on Octopus Intelligent Go.

## Blog Series

- [Part 1: iCloud Calendars](https://www.kerrywalker.uk/2026/02/22/family-dashboard-part-1-calendars.html)
- [Part 2: Custom Energy Gauge](https://www.kerrywalker.uk/2026/02/25/family-dashboard-part-2-energy-gauge.html)
- [Part 3: Simplifying the Energy Gauge](https://www.kerrywalker.uk/2026/02/28/family-dashboard-part-3-quad-gauge.html)

## Cards

### Energy Quad Gauge (`cards/energy-quad-gauge.yaml`)

A 2×2 grid of four horseshoe gauges inspired by Solar Assistant. Cleaner and more readable than the concentric version.

- **Load** (blue) — top left
- **Solar** (orange) — top right
- **Grid** (red/teal) — bottom left, direction flips for import/export
- **Battery** (green/orange) — bottom right, direction flips for charge/discharge, shows battery % underneath

**Requires:**
- [Lovelace HTML Jinja2 Template card](https://github.com/PiotrMachowski/Home-Assistant-Lovelace-HTML-Jinja2-Template-card)

### Energy Horseshoe (`cards/energy-horseshoe.yaml`)

A concentric horseshoe gauge showing solar, battery, grid and load on a single card using `custom:html-template-card`.

Five rings (outside → inside):
- **Solar** (orange) — PV watts
- **Battery Level** (pink) — state of charge %
- **Battery Power** (green/orange) — charge/discharge rate with direction flip
- **Grid** (red/teal) — import/export with direction flip
- **Load** (blue) — household consumption

**Requires:**
- [Lovelace HTML Jinja2 Template card](https://github.com/PiotrMachowski/Home-Assistant-Lovelace-HTML-Jinja2-Template-card)
- [card-mod](https://github.com/thomasloven/lovelace-card-mod) (optional, for background styling)

**To adapt to your inverter:** Change the entity IDs and max values at the top of the file.

### Calendar (`cards/calendar.yaml`)

Atomic Calendar Revive config for multiple iCloud calendars via CalDAV.

**Requires:**
- [Atomic Calendar Revive](https://github.com/totaldebug/atomic-calendar-revive) (HACS)
- CalDAV integration configured for each iCloud account

## Prerequisites

- HACS
- CalDAV integration (for iCloud calendars)
- Growatt SPH integration (or substitute your own inverter entities)
