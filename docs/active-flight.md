---
layout: default
title: Active Flight
nav_order: 5
parent: Features
---

# Active Flight Management
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

Once you have dispatched a flight through the Dispatcher Wizard, FlyAround begins tracking your flight in real time. The **Active Flight** screen is your command center while airborne.

---

## Accessing the Active Flight View

- Navigate to **Active Flight** from the main navigation
- Or click the **active flight shortcut** in your pilot summary (top of the hamburger menu)
- The app automatically redirects to this view when a flight is in progress

---

## Real-Time Tracking

FlyAround connects to your simulator and continuously receives:
- Current aircraft position (latitude/longitude)
- Altitude
- Speed (ground speed / airspeed)
- Heading
- Flight phase

The flight phase updates automatically as you progress through your flight.

---

## Speed Dial — Quick Actions

The **Speed Dial** is a floating menu on the right side of the active flight screen:

| Button | Action |
|--------|--------|
| **3D Map** | Toggle between 2D and 3D map view *(disabled while on ground)* |
| **My Location** | Center the map on your aircraft's current position |
| **LiveMap** | Open the full live tracking map |
| **Share** | Copy a shareable link to your flight |
| **Timeline** | View your flight phase timeline and progression |
| **Loadsheet** | View weight & balance, fuel, and payload data |
| **OFP** | Open the Operational Flight Plan document |
| **PAX** | View the passenger manifest *(PAX flights only)* |
| **Settings** | Flight-specific settings and quick actions |
| **Cancel Flight** | Cancel the active flight *(with confirmation prompt)* |
| **Complete Flight** | Mark the flight as complete *(available during taxi-in, parking, deboarding, or cleaning phase)* |

---

## Actions Bar — Radios & ATC

A floating, draggable **Actions bar** on the flight map shows your **COM1 / COM2 / XPDR** readout together with quick-action buttons:

- Click the **COM1 readout** to open the **ATC frequencies** list for your departure, destination and nearest airport, and tune a controller with one click.
- The **ATC button** opens the [ATC conversation]({% link docs/atc-communications.md %}) for the tuned station — request clearance, pushback, taxi, takeoff and more, fully voiced.
- Exterior-light and cabin-sign toggles let you flip NAV/TAXI/LANDING/BEACON/STROBE lights and the seatbelt sign directly in the sim.

When ATC clears you to taxi, the **cleared taxi route is drawn on the map** and shrinks as you advance along it — both to the departure runway and to your assigned gate after landing.

---

## Flight Phase Notifications

FlyAround sends automatic notifications as your flight progresses:

| Phase | Notification |
|-------|-------------|
| Pushback | Pushback phase started |
| Takeoff | Takeoff phase started |
| Climb | Climb phase started |
| Cruise | Cruise phase started |
| Descent | Descent phase started |
| Landing | Landing report (see below) |
| Parked | "Ready to Deboard" notification |

### Landing Report

The landing report notification includes:
- **Descent rate** (ft/min)
- **G-force** at touchdown
- **Ground speed**
- **Wind** direction and velocity

---

## Completing a Flight

A flight can be completed when your aircraft reaches one of these phases:
- Taxi-In
- Parking
- Deboarding
- Cleaning

Click **Complete Flight** in the Speed Dial. The flight is logged to your Logbook and a full flight report is generated.

---

## Cancelling a Flight

Click **Cancel Flight** in the Speed Dial. A confirmation dialog will appear — confirm to cancel. Cancelled flights are **not** saved to the Logbook.

---

## Aircraft Change Detection

If FlyAround detects that you have switched aircraft mid-flight, a warning alert appears. You will be offered the option to cancel the current flight so you can start fresh with the correct aircraft.

---

## Sharing Your Flight

Use the **Share** button in the Speed Dial to copy a public link to your flight. Anyone with the link can view your live flight on the FlyAround public map at `flyon.me`.
