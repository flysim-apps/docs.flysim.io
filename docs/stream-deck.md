---
layout: default
title: Stream Deck
nav_order: 9.5
parent: Features
---

# Stream Deck
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

The FlyAround plugin puts your flight on Stream Deck keys. One key shows the next step of your flight
and runs it, others switch camera views, start cinematic mode, play FlyAround FM, open FlyAround pages
and run your live stream. Every key shows what is going on right now, so a glance at the deck tells
you what comes next.

{: .note }
The Stream Deck plugin is a **FlyAround Pro** feature. It is not part of the Community edition.

---

## What you need

- **FlyAround Pro**, running on the same PC while you fly. The keys talk to FlyAround, and FlyAround
  talks to the simulator.
- The **Stream Deck app** from Elgato, version 7.1 or later, on Windows 10 or later.
- Any Stream Deck. The ready-made profile is laid out for the **15-key** Stream Deck; on other models
  you place the keys yourself.

---

## Install the plugin

The plugin comes with FlyAround, so there is nothing to download.

1. Open the **launch pad** and press **Stream Deck** in the top row. You can also open
   **Support → FlyAround for Stream Deck**.
2. The window tells you where you stand:
   - **The Stream Deck app isn't installed** — press **Get the Stream Deck app**, install it, then
     come back.
   - **The Stream Deck app is installed** — press **Install plugin**.
   - **The FlyAround plugin is installed** — you are done. **Reinstall plugin** puts it back if you
     removed it.
3. The Stream Deck app opens the plugin and asks you to confirm. Confirm, and the **FlyAround**
   category appears in its action list.

The Stream Deck app keeps the plugin from then on. After a FlyAround update, press **Reinstall plugin**
to pick up new keys.

---

## The ready-made profile

The plugin installs a **FlyAround** profile for the 15-key Stream Deck. It does not switch to it on its
own: pick **FlyAround** in the profile list at the top of the Stream Deck app.

| Row | Keys |
|:----|:-----|
| Top | Flight step · Go live · Stop stream · Mark moment · Stream chat |
| Middle | Wing view · Tower view · Drone view · Cinematic mode · FlyAround FM |
| Bottom | Live map · Flight Deck · Hangar · Logbook · *(free)* |

The profile is yours to change: move keys around, swap a view, or drop in other actions.

---

## Set up your own keys

1. Open the Stream Deck app. In the action list on the right, find the **FlyAround** category.
2. Drag an action onto a key. It appears on your Stream Deck right away.
3. Click the key to change its settings at the bottom of the window: which camera view it shows, or
   which page it opens.
4. Add the same action to several keys for more views or more pages.

---

## What the keys do

### Flight step

Shows the next step of your flight and runs it when you press it:

**Ready for boarding → Start boarding → Complete boarding → Request pushback → Start deboarding →
Complete deboarding → Complete flight**

The key is grey without a flight and dark while no step is due, for example in cruise.

### Camera view

Switches the simulator to the view you picked in the key's settings and lights up while that view is
on. It stays grey until a simulator is connected.

Available views: **Cockpit**, **Chase**, **Wing**, **Front**, **Left engine**, **Right engine**,
**Left flaps**, **Right flaps**, **Overhead**, **Pedestal**, **MCDU**, **Tower** and **Drone**.

{: .important }
Camera views and cinematic mode are **experimental**. Switch on experimental features first
(`"experimental": 1` in `bridge-settings.json`, see **What's new → Learn more** in the app), otherwise
these keys have nothing to switch.

### Cinematic mode

Turns the cinematic camera on or off: moving shots around your aircraft with cuts on gear, flaps,
rotation and touchdown. The key lights up while it runs.

### Open page

Brings FlyAround to the front on the page you picked: **Live map**, **Flight Deck**, **Hangar** or
**Logbook**. Flight Deck is grey without a flight.

### FlyAround FM

Turns the radio on or off and lights up while it plays.

### Stream keys

Run your live stream from the deck. See [Streaming]({% link docs/streaming.md %}) for the setup.

| Key | What it does |
|:----|:-------------|
| **Go live** | Starts the stream with your saved defaults (channels, visibility, title and description), then shows the elapsed time while you are live. |
| **Stop stream** | Ends the stream. |
| **Mark moment** | Drops a highlight on the stream timeline at your position. It shows on the flight's route after the flight. |
| **Stream chat** | Opens the viewer chat window. |

**Stop stream** and **Mark moment** read **Not live** until you are live. A key that reads **No
streaming** means streaming isn't on your account.

---

## Troubleshooting

**A key flashes a warning when I press it**
: It had nothing to do: no flight, no simulator, or a step that isn't due yet.

**Every key reads "FlyAround offline"**
: FlyAround isn't running. Start it; the keys come alive within a couple of seconds.

**Every key reads "Pro only"**
: The account signed in to FlyAround isn't on FlyAround Pro.

**Camera keys stay grey with the sim running**
: Experimental features are off, or the simulator isn't connected to FlyAround yet. See the note under
  [Camera view](#camera-view).

**"This FlyAround installation doesn't include the Stream Deck plugin"**
: Your FlyAround build is older than the plugin. Update FlyAround, then install the plugin again.

**I don't see the FlyAround profile**
: Open the profile list at the top of the Stream Deck app and pick **FlyAround**. If it isn't there,
  press **Reinstall plugin** in FlyAround. The profile is laid out for the 15-key Stream Deck.
