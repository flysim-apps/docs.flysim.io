---
layout: default
title: Flight Planning
nav_order: 4
parent: Features
---

# Flight Planning — Dispatcher Wizard
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

The **Dispatcher Wizard** is the starting point for every flight in FlyAround. It guides you through selecting your route, aircraft, payload, and generating a full Operational Flight Plan (OFP).

---

## How to Open the Dispatcher

Click the **"Time to Fly"** button — the floating action button (FAB) on the main map screen. This button is available when:
- Your simulator is connected (FS Connection indicator is green/yellow)
- No flight is currently active (or you have completed/cancelled your previous flight)
- Your account billing is active

{: .note }
If the button is greyed out, check your FS connection status or billing account.

---

## Step 1 — Route Selection

Choose how you want to define your route:

### Option A: Manual Route

| Field | Description |
|-------|-------------|
| **Origin Airport** | Enter ICAO or IATA code (e.g. `EGLL` or `LHR`) |
| **Destination Airport** | Enter ICAO or IATA code |
| **Flight Number / Callsign** | Your flight identifier (e.g. `FA101`) |
| **Departure Time** | Date and time of departure |
| **Airways / Route** | Optional custom route string |

The estimated route distance is calculated automatically.

### Option B: Import from SimBrief

If you have a flight plan already created in SimBrief, select **"Import from SimBrief"**. FlyAround will fetch your latest OFP and pre-fill all route data — skipping manual entry entirely.

---

## Step 2 — Aircraft Selection

- Browse all aircraft you have added to your **Hangar**
- Aircraft are shown by airframe, airline livery, and tail number
- Select the aircraft you want to fly

{: .important }
If your Hangar is empty, [add an aircraft first]({% link docs/hangar-fleet.md %}).

---

## Step 3 — On-Board Services

Configure your flight's payload and cabin:

### Flight Mode

| Mode | Description |
|------|-------------|
| **Passenger (PAX)** | Carry passengers; PAX manifest will be generated |
| **Cargo** | Carry freight; no passenger manifest |

### Service Class

| Range | Tiers Available |
|-------|-----------------|
| Short-haul | Low / Standard / Luxury |
| Medium-range | Low / Standard / Luxury |
| Long-haul | Low / Standard / Luxury |

### In-Flight Services

Toggle each service on or off:
- Wi-Fi
- Meals
- Spirits / Beverages
- Duty-Free Shopping

### Payload

- **Passenger count** — Number of passengers aboard
- **Cargo weight** — Freight weight
- **Weight units** — LBS or KGS

---

## Step 4 — Flight Plan Generation

FlyAround (powered by the PAS AI flight planner) automatically builds your full flight plan:
- Generates OFP (Operational Flight Plan)
- Calculates fuel requirements, cruise altitude, cost index
- Integrates with SimBrief data if imported in Step 1
- Progress is shown during generation — this may take a few seconds

---

## Step 5 — Review & Confirm

- Review all flight details: route, aircraft, payload, OFP
- Read the generated OFP document
- Click **Confirm** to dispatch the flight and begin tracking

Once confirmed, your flight becomes **active** and real-time tracking begins.

---

## Tips

- Make sure your aircraft is loaded in MSFS **before** confirming the flight — tracking will start immediately.
- You can always **cancel** an active flight from the active flight screen if you need to start over.
- For cargo operations, loading is tracked separately from PAX flights.
- If SimBrief import fails, fall back to manual route entry.
