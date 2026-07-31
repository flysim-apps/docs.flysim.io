---
layout: default
title: Settings
nav_order: 11
parent: Features
---

# Settings
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

The **Settings** screen lets you configure FlyAround's behavior, audio, streaming overlay, and AI assistant options.

---

## Opening Settings

Click **Settings** in the main navigation menu.

---

## Main Settings

- Global application configuration and behavior preferences
- **Theme** — pick one of the four app themes: **Flight Deck**, **Glass Cockpit** (frosted, the default), **Steam Gauges** and **Radar**

---

## System Tab

| Setting | Description |
|---------|-------------|
| **Parking Mode** | Toggle parking behavior on/off |
| **Ground Handling** | **GSX** (GSX ground services add-on) or **SIM** (default simulator ground handling) *(Windows/MSFS only)* |
| **Use PMDG Offsets compatibility** | Deep integration for PMDG aircraft *(Windows/MSFS only; restart needed)* |
| **First Officer auto-actions (lights, flaps, spoilers)** | The virtual First Officer handles lights, signs, APU, spoilers and flaps through every flight phase — also used by ATC-approved pushback/startup and line-up |
| **Realistic AI crew voices** | Lifelike captain, cabin-crew and ATC voices, chosen automatically by airline |
| **Crew voice gender** | System selected / Male / Female |

{: .note }
**Ground Handling — GSX vs SIM:** If you use the GSX add-on for pushback and boarding, set this to "GSX" so FlyAround correctly tracks those ground phases (and so ATC-approved pushback drives GSX). Use "SIM" for default simulator ground services. Windows-only options are hidden on macOS/Linux.

### Developer API *(Enterprise)*

The **MCP Endpoint for AI Agents** card shows the local address of FlyAround's built-in read-only MCP server, which lets AI coding agents explore the app's local API. The interactive **API reference** (Swagger UI) and the **Connector guide** live under **Support → Development Documentation**. Everything is served by the app itself and works offline.

---

## PA & Callouts

| Setting | Description |
|---------|-------------|
| **Enable PA & Callouts** | Master switch for all spoken audio — cabin announcements, First Officer callouts, and ATC voice |
| **Announcements** | Toggle individual cabin/ground announcement types on or off |
| **First Officer callouts** | Mute the spoken FO callouts (the FO still performs the actions) |

---

## AI Assistant Tab

*(Visible only if the AI feature is enabled on your account)*

| Setting | Description |
|---------|-------------|
| **Assistant Name** | Custom name for your AI Assistant (default: "FlyAround AI") |
| **Mascot** | Choose the mascot character: Kika (classic) or Bouba (cap) |
| **Voice & Push-to-Talk** | Enable push-to-talk, bind the assistant and ATC transmit keys (keyboard or joystick), pick and test your microphone, and set the recognition language — see [AI Assistant]({% link docs/ai-assistant.md %}) and [ATC Communications]({% link docs/atc-communications.md %}) |

---

## Sound Tab

| Control | Description |
|---------|-------------|
| Volume sliders | Adjust volume per audio category independently (Voice, Ambient, Co-Pilot, Flight Attendant, …) |
| Toggle individual sounds | Enable or disable specific announcement types |

Audio categories include cabin announcements, ground crew communication, and system sounds.

---

## Stream Overlay

The **Stream Overlay** page (its own item in the navigation drawer) configures the transparent HUD designed for capture in OBS or Streamlabs, with a full-screen live preview:

| Control | Description |
|---------|-------------|
| **Show/Hide Elements** | Toggle which flight data elements are visible |
| **Bot Text** | Customize text for stream chat bots |
| **Live Preview** | See overlay changes in real time |

---

## Streaming Tab

*(Visible only if the Stream feature is enabled on your account)*

Connect the platforms you broadcast to and configure how your broadcasts are posted:

| Control | Description |
|---------|-------------|
| **Platforms** | Connect your YouTube and/or Twitch channel, and download the ready-made OBS scene |
| **OBS connection** | Host, port and password for OBS' WebSocket server (defaults match OBS: `ws://127.0.0.1:4455`) |
| **Stream to OBS Studio** | Your permanent **Server** / **Stream key** for OBS running on a separate PC, with copy and regenerate |
| **Post format** | Title/description templates, default tags, visibility, and default platforms for a broadcast |

For full setup instructions (OBS scene import, enabling the WebSocket server) and how to go live,
see the [Streaming guide]({% link docs/streaming.md %}).

---

## Support

At the bottom of the navigation menu:
- **Discord** — FlyAround community Discord server
- **Email** — Direct support contact
- **Development Documentation** *(Enterprise)* — the local API reference (with try-it-out) and the step-by-step connector guide for building third-party integrations

---

## Profile Settings

Profile settings (nickname, handle, avatar, billing) are accessed separately — see [Profile & Billing]({% link docs/profile-billing.md %}).
