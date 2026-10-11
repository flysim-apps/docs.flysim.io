---
layout: default
title: FlyAround Mobile
nav_order: 17
parent: Features
---

# FlyAround Mobile
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

**FlyAround Mobile** is the companion app for iPhone, iPad and Android. Signed in with your FlyAround account, it shows your flights, events and logbook from anywhere. Paired with FlyAround Desktop on your PC, it also gets live data from the simulator and can drive the cockpit — for example the First Officer panel.

Pairing works over your home network: the phone talks to the PC directly, nothing goes through the cloud.

---

## What you need

- **FlyAround Desktop** running on your PC.
- **FlyAround Mobile** installed on your phone and signed in to the same FlyAround account.
- **Phone and PC on the same network** — the phone on the Wi-Fi of the router your PC is connected to (by Wi-Fi or cable). Mobile data or a guest Wi-Fi won't work.

---

## Pair your phone

1. On your PC, open FlyAround Desktop → **Settings → FlyAround Mobile**. It shows a QR code and this PC's address (for example `192.168.1.20:30520`).
2. On your phone, open FlyAround Mobile → **Flight Deck** → **Connect** and tap **Scan QR code**.
3. Point the phone at the QR code. The app connects, and the Connect tile turns into **Desktop** with a green dot.

{: .note }
On an iPhone with FlyAround Mobile installed, you can also scan the code with the built-in **Camera** app and tap the banner that appears.

The phone remembers the PC and reconnects to it by itself next time — you only pair once (and again if the PC's address changes).

### Without the camera

In FlyAround Mobile, tap **Enter IP** on the Connect screen and type the address shown under the QR code, including `:30520`.

### A PC with more than one network

If your PC has both Wi-Fi and Ethernet (or a VPN), the FlyAround Mobile settings show a **Network** picker. Pick the network your phone is on; the QR code and address update.

---

## Allow the connection

The first time a phone connects, Windows may ask whether to allow FlyAround on the network. Choose **Private networks** and allow it.

If you dismissed that prompt, or a third-party firewall or antivirus is in the way, allow **incoming TCP connections on port 30520** for FlyAround on private networks.

On an iPhone, iOS asks once whether FlyAround may **find devices on your local network** — tap **Allow**. To change it later: **Settings → FlyAround → Local Network**.

---

## Companion app settings

FlyAround Desktop → **Settings → FlyAround Mobile** also holds what the desktop sends to the app through the cloud while you fly (Pro):

| Setting | Description |
|---------|-------------|
| **Update interval** | How often your flight's progress is sent to the app (5–30 seconds) |
| **Send cabin activity to the phone** | Each passenger's activity, mood and call bells. Switch off on a metered connection |

Both apply after FlyAround Desktop restarts.

---

## Troubleshooting

| Problem | What to try |
|---------|-------------|
| "Your PC isn't answering" | Check that FlyAround Desktop is running and that the phone is on the same Wi-Fi as the PC — not mobile data, a guest network or a VPN |
| It worked before, now it doesn't | The PC's address may have changed — scan the QR code again |
| Connects from one phone, not another | On the iPhone that fails, turn on **Settings → FlyAround → Local Network** |
| Never connects at all | Allow FlyAround (TCP port `30520`) in Windows Firewall on private networks; check any antivirus firewall too |
| The Network picker shows several addresses | Pick the one on the same network as the phone (usually starts like the phone's Wi-Fi address, e.g. `192.168.1.`) |
| "The desktop has no first officer controls" | Update FlyAround Desktop to the latest version |
