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

- Windows PC with a supported flight simulator installed
- FlyAround desktop app (Windows WebView2-based application)
- Active internet connection
- A FlyAround account

### Supported Simulators

FlyAround connects to the following simulators:

| Simulator | Notes |
|-----------|--|
| Microsoft Flight Simulator 2020 | Requires FSUIPC |
| Microsoft Flight Simulator 2024 | Requires FSUIPC|
| X-Plane 11 | Requires XPUIPC |
| X-Plane 12 | Requires XPUIPC |
| Prepar3D | Requires FSUIPC |

### Required Middleware

FlyAround communicates with your simulator through a bridge application. You must have one of the following installed and running **before** launching FlyAround:

- **FSUIPC** — required for MSFS 2020, MSFS 2024, and Prepar3D
- **XPUIPC** — required for X-Plane 11 / 12

{: .note }
Native MSFS connection (without FSUIPC) is planned and coming soon.

### Third-Party Integrations

Some features depend on external services and require separate accounts or subscriptions:

| Service | Required for |
|---------|-------------|
| **Navigraph** (subscription) | Internal flight planning, ATC layer on the Live Map |
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

## Dark / Light Theme

Use the **theme toggle** in the main menu to switch between light and dark mode.

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
