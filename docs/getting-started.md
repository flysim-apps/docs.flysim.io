---
layout: default
title: Getting Started
nav_order: 2
---

# Getting Started with FlyAround
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## What is FlyAround?

FlyAround is a flight tracking and management platform designed for Microsoft Flight Simulator (MSFS) 2020/2024, X-Plane 11/12 and Prepar3D. It adds a full logistics layer to your sim — flight planning, cargo/passenger loading, real-time tracking, logbook keeping, and more — all from a desktop app that runs alongside your simulator.

---

## System Requirements

- A Windows, macOS or Linux computer with a supported flight simulator installed
- The FlyAround desktop app (installed via the FlyAround Simulations Installer)
- Active internet connection
- A FlyAround account

### Supported Simulators

FlyAround connects to the following simulators:

| Simulator | Connection | Platforms |
|-----------|------------|-----------|
| Microsoft Flight Simulator 2020 | FSUIPC | Windows |
| Microsoft Flight Simulator 2024 | FSUIPC | Windows |
| X-Plane 11 | FlyAround Simulations Connect plugin | Windows, macOS, Linux |
| X-Plane 12 | FlyAround Simulations Connect plugin | Windows, macOS, Linux |
| Prepar3D | FSUIPC | Windows |

### Simulator Connection

- **MSFS 2020 / 2024 and Prepar3D** connect through **FSUIPC** — install and run it before launching FlyAround. Download it from [fsuipc.com](https://www.fsuipc.com/).
- **X-Plane 11 / 12** connect through the **FlyAround Simulations Connect plugin**. Install it from the FlyAround Simulations Installer — open the Installer, navigate to the **Plugins** section, and enable the X-Plane Connect plugin. On macOS and Linux this is the only connection needed.

### The FlyAround Simulations Bridge

The app ships with a background service — the **FlyAround Simulations Bridge** — that talks to your simulator and keeps tracking your flight. On Windows it lives in the system tray and keeps running even if you close the FlyAround window (use the tray icon's **Exit** to stop it, or enable **Exit when FlyAround exits** in the tray settings). On macOS and Linux the bridge starts and stops together with the app.

### Third-Party Integrations

Some features depend on external services and require separate accounts or subscriptions:

| Service | Required for |
|---------|-------------|
| **Navigraph** (subscription) | Internal flight planning, ATC layer on the Live Map, en-route Center hand-offs and the automatic arrival chain in [ATC Communications]({% link docs/atc-communications.md %}) |
| **SimBrief** (free account) | External flight plan import in the Dispatcher Wizard |

---

## First Launch & Login

1. Start the FlyAround desktop application.
2. You will see the **Login** screen. Enter your credentials to authenticate.
3. After login, the app checks your account status and loads your pilot profile and settings.
4. If your account is on a **trial** or requires billing activation, a notification will appear. Some features may be limited.

---

## Main Navigation

The main menu is accessed via the **hamburger icon (☰)** in the top-left corner. It contains:

| Menu Item | Description |
|-----------|-------------|
| **Live Map** | View real-time global flight tracking |
| **Calendar** | Schedule flights and group events *(requires active subscription)* |
| **Activity** | Activity feed and pilot community list |
| **Hangar** | Manage your aircraft fleet |
| **Logbook** | Review your completed flight history |
| **Settings** | Configure the application |

At the top of the menu you will also see your **pilot profile summary**:
- Pilot nickname and avatar
- Total flights, flight hours, and distance traveled

Use the **edit icon** next to your name to open profile settings.

---

## Connection Status

The **FS Connection indicator** in the navigation bar shows whether FlyAround is communicating with your running simulator:

| Indicator | Meaning |
|-----------|---------|
| Green | Connected and receiving data |
| Yellow / Amber | Connection degraded or reconnecting |
| No indicator | Not connected |

FlyAround requires the simulator to be running for flight tracking features to work.

---

## Themes

Use the **theme toggle** in the main menu to switch between light and dark mode.

FlyAround also ships four full app themes — pick one under **Settings → Main Settings**: **Flight Deck**, **Glass Cockpit** (frosted, the default), **Steam Gauges** and **Radar**. Each restyles the whole app, the live map and even the taskbar icon.

---

## App Version & Updates

FlyAround checks for a new version on startup. If an update is available, a notification appears with release notes and a download link. Keep the app updated to access the latest features.

---

## Language

FlyAround supports multiple languages: English, German, Spanish, and French. The app language is derived from your system/browser locale setting.

---

## Next Steps

- **Add your first aircraft** → [Hangar & Fleet]({% link docs/hangar-fleet.md %})
- **Plan your first flight** → [Flight Planning]({% link docs/flight-planning.md %})
- **Explore the Live Map** → [Live Map]({% link docs/live-map.md %})
