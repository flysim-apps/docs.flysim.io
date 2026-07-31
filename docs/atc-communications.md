---
layout: default
title: ATC Communications
nav_order: 6
parent: Features
---

# ATC Communications
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

FlyAround includes a fully voiced **ATC conversation** for your flight — request your IFR clearance, pushback, taxi, takeoff and landing, get handed from controller to controller as you fly, and talk to ATC with your own voice using push-to-talk. Every exchange is spoken with realistic radio audio and written to a live transcript.

{: .note }
The ATC conversation works in every edition. Spoken ATC audio uses the crew-voice pipeline (**Settings → PA & Callouts → Realistic AI crew voices**), and talking to ATC by voice additionally requires the AI Assistant feature — see [Push-to-Talk](#talking-to-atc-with-your-voice).

---

## Tuning In and Opening the Conversation

ATC is driven by your **COM1 radio** — tune the frequency of a real controller position at your airport and the matching station comes alive.

1. On the active-flight screen, find the floating **Actions bar** (it shows your COM1/COM2/XPDR readout).
2. Click the **COM1 readout** to open the **ATC frequencies** list for your departure, destination, and nearest airport — grouped by position (ATIS, Clearance, Ground, Tower, Departure, Approach, Center).
3. Tune a controller frequency. The **ATC button** on the Actions bar lights up and its tooltip names the position you reached — *Clearance Delivery*, *Ground Operations*, *Tower*, *Departure*, *Approach*, or *Center*.
4. Click the button to open the conversation window.

The button stays disabled while no request is available on the tuned frequency (for example on ATIS). At smaller fields that don't publish every position, **Tower absorbs the missing ones** — clearance, ground and departure requests simply appear on Tower.

---

## The Conversation Window

The window title shows the position, station callsign and frequency — e.g. `Ground Operations — Kennedy Ground · 121.9`. It has two parts:

- **Request list** (left) — only the requests that are legal *right now* on this frequency.
- **Live transcript** (right) — pilot calls on the right with your pilot avatar, controller replies on the left. Lines appear in sync with the spoken audio, with a typing indicator on the side of whoever speaks next. Every exchange is a real three-part call: your request, the controller's reply, and your read-back.

New lines auto-scroll only while you're at the bottom — scroll up to re-read history and the transcript stays put until you scroll back down.

When a controller has nothing further for you, the request column tells you who to call next: *"Nothing further on {station}. Tune {controller} to {request}."*

### Mute

The **mute button** in the title row silences ATC voice entirely — muting skips voice generation (it doesn't just lower the volume), so a muted radio consumes no AI credits. The transcript keeps flowing normally.

### Pop-out Window

In the desktop app, use **Open in window** in the title row to detach the conversation into its own borderless window — handy on a second monitor. Drag the header to move it, resize from the edges, and use **Back to dialog mode** to return it to the main window. The transcript and session stay in sync between both surfaces.

---

## Requests Through a Flight

| Phase | Request | Controller |
|-------|---------|-----------|
| Pre-flight | **Request IFR clearance** | Clearance Delivery |
| Ground | **Request startup** / **Request pushback** | Ground |
| Ground | **Request taxi to runway** | Ground |
| Departure | **Request takeoff / line-up** | Tower |
| Climb-out | **Report airborne (Departure)** | Departure |
| En-route | **Report level / check in**, **Request higher**, **Request lower**, **Request direct to destination** | Center |
| Arrival | **Request approach clearance** | Approach |
| Arrival | **Request landing clearance** | Tower |
| After landing | **Request gate** | Ground |

The session enforces the real-world order — asking for taxi before pushback gets you an authentic refusal (*"Unable, complete pushback first."*), not an error.

A few requests do more than talk:

- **IFR clearance** assigns a squawk code and **writes it into your transponder** automatically.
- **Taxi clearance** reads the actual taxiway sequence (*"Taxi to runway 27L via A, B, C, hold short."*) and draws the **cleared taxi route on the map**, updating as you advance along it. The same happens for the taxi to your gate after landing.
- **Approved pushback and startup are carried out by your virtual First Officer** — beacon on and pushback started (through GSX if you use it as your ground handling, otherwise sim-native), fuel pumps and APU running.

---

## Automatic Hand-offs

As your flight progresses, ATC proactively calls **you** — each hand-off retunes COM1 automatically and appears (voiced) in the transcript:

- **Ground → Tower** — approaching your departure runway during taxi-out, Ground hands you to Tower and the crew checks in holding short. The First Officer also runs the line-up preparation (landing lights, strobes) as you near the runway.
- **Tower → Departure** — climbing through 1,000 ft after takeoff, Tower hands you off and your airborne report is made for you.
- **Center hand-offs en-route** — each time you cross a FIR boundary you're handed to the next Center, with check-in and *"radar contact"*.
- **Arrival chain** — nearing your top of descent, ATC starts working you down: descent clearances, hand-off to Approach, an approach clearance for the **runway best aligned with the live wind**, hand-off to Tower, and finally a landing clearance that includes the current surface wind.

---

## Picking a Gate

After landing, ask Ground to **Request gate**. The **Pick a gate** list shows the stands at your destination, nearest first, labelled by kind (Gate / Ramp / Cargo / Dock) with a size class, stand diameter and distance — e.g. `Gate 12 · S · Ø18 m · 250 m`.

- Stands too small for your aircraft are filtered out — an airliner is never offered a GA spot, and widebodies only see heavy stands.
- Stands **occupied by parked AI traffic** are disabled and marked *Occupied*.

Once assigned, you get a taxi clearance to the gate and the route is drawn on the map.

---

## Talking to ATC with Your Voice

You can make any request by voice instead of clicking — even with the ATC window closed.

1. In **Settings → AI Assistant → Voice & Push-to-Talk**, enable push-to-talk and bind the **ATC transmit key** (a keyboard chord or joystick button — separate from the assistant key, like radio transmit versus intercom).
2. Hold the key, speak your request — *"request pushback"*, *"ready for departure"*, *"taxi to gate A12"* — and release.
3. A floating pill shows *Listening...* with a live transcript, then *Transcribing...*, with an **ATC** chip confirming who you're addressing.

Your phrase is matched against standard phraseology; if nothing matches confidently, nothing is transmitted — you'll never send a garbled call. Speech recognition runs through the FlyAround voice service, so it needs an internet connection and available [AI credits]({% link docs/ai-assistant.md %}#ai-credits).

{: .note }
Push-to-talk requires the AI Assistant feature on your plan. Joystick binding and the global hotkey (which works while the sim has focus) are currently Windows-only.

---

## Requirements & Notes

| Topic | Details |
|-------|---------|
| **Simulators** | Works on both MSFS (2020/2024) and X-Plane 11/12. |
| **Navigraph** | Not needed for the ground/departure side — frequencies fall back to FlyAround's bundled airport data. A Navigraph subscription is required for the en-route Center hand-offs and the automatic arrival chain. |
| **GSX** | Not required. With GSX selected as your ground handling, approved pushback drives GSX; otherwise the sim's native pushback is used. |
| **First Officer** | The ATC-triggered actions (pushback, startup, line-up lights) use the virtual FO — keep **First Officer auto-actions** enabled in Settings → System. |
| **Voice audio** | ATC lines are spoken through the crew-voice pipeline with a VHF radio effect. Requires **PA & Callouts** and **Realistic AI crew voices** to be on; use the in-window mute to silence ATC specifically. |
| **Persistence** | The conversation, clearance state, squawk and assigned gate survive an app restart mid-flight. |
