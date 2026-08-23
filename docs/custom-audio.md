---
layout: default
title: Custom PA & Callout Audio
nav_order: 14
parent: Features
---

# Custom PA & Callout Audio
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

FlyAround speaks its cabin announcements and flight-deck callouts with a synthesized crew. If you would rather hear your own recordings — a real airline PA, your own voice, an announcement in a language we don't offer — drop the audio files into one folder and FlyAround plays yours instead.

Nothing is replaced unless you supply a file for it, so a folder with three recordings in it changes exactly three announcements.

---

## The folder

```
Documents\FlyAround Files\pa
```

FlyAround creates it the first time it runs and installs a reference PDF there — **How to use local clips.pdf** — listing every announcement you can replace, who speaks it and when it plays. It is the same list as the tables below.

On macOS and Linux the folder is the equivalent path under your home directory: `~/Documents/FlyAround Files/pa`.

---

## Naming a file

Every announcement has a name in capitals with underscores — `V1`, `WELCOME_ABOARD`, `FO_LINEUP`. Name your file after the announcement and FlyAround plays it in place of the crew voice.

```
Documents\FlyAround Files\pa\
  V1.mp3                  → the First Officer's "V one" callout
  WELCOME_ABOARD.mp3      → the welcome-aboard PA
  SEATBELTS_ON.fx.mp3     → played through the cabin loudspeaker effect
```

`.mp3`, `.wav`, `.flac` and `.ogg` all work. A file whose name doesn't match an announcement is ignored, and the app log says so — useful for catching a typo.

### Several files for one announcement

Add `_1`, `_2`, `_3` and the files play back-to-back in order:

```
  HELLO_CREW_1.mp3        → the Captain calls the cabin
  HELLO_CREW_2.mp3        → the cabin answers
```

This suits the crew interphone exchanges, which are a call and an answer. Recording both voices into one file works just as well.

### The `.fx` suffix

By default your file plays exactly as recorded. Name it `SEATBELTS_ON.fx.mp3` instead and FlyAround adds that announcement's own treatment — the cabin chime and loudspeaker colouring for a cabin PA, the call chime and telephone colouring for a crew interphone call. Flight-deck callouts have no treatment, so `.fx` changes nothing there.

{: .note }
A recording taken from a real cabin already sounds like a loudspeaker — leave `.fx` off. A line recorded cleanly into a microphone sounds like someone standing next to you — add `.fx` and it will sound like it is coming over the cabin speakers.

---

## When the folder is read

Once per flight, as the flight starts. Add or change files between flights and the next flight picks them up. There is no setting to switch on and nothing to restart, and an empty folder costs nothing.

{: .highlight }
Your own clips never go through the crew-voice service, so they play even with **Voice Experience** switched off in **Settings → PA & Callouts** — and they play instantly, with no internet connection involved.

{: .warning }
The announcements marked **live** below normally speak your callsign, airline, cruise altitude, arrival time or destination weather. A recording is fixed, so those details are replaced by whatever you recorded.

---

## Cabin announcements

Spoken to the passengers over the cabin loudspeakers. `.fx` adds the cabin chime and the loudspeaker colouring.

| File name | Voice | Plays when |
|-----------|-------|------------|
| `DEPARTURE_REMINDER` | Senior crew | During boarding — stow baggage, take your seats |
| `DEPARTURE_PREPARE` | Senior crew | Doors closed, cabin prepared for departure **live** |
| `WELCOME_ABOARD` | Captain + crew | Boarding complete — the welcome PA **live** |
| `SEATBELTS_ON` | Senior crew | The seat-belt sign is switched on |
| `SEATBELTS_OFF` | Senior crew | The seat-belt sign is switched off |
| `TURBULENCE` | Senior crew | Turbulence — be seated, belts fastened |
| `BE_SEATED` | Senior crew | Passengers asked back to their seats |
| `CRUISE` | Captain | Levelling off in the cruise **live** |
| `DUTY_FREE` | Senior crew | The duty-free round begins |
| `TOP_OF_DESCENT` | Captain | Starting the descent **live** |
| `FINAL_APPROACH` | Senior crew | Final approach — seats, belts, tables |
| `ARRIVAL` | Senior crew | After landing — destination, local time, weather **live** |
| `ARRIVAL_DELAY` | Captain | Held short of the gate on arrival **live** |
| `DEBOARDING_START` | Senior crew | Doors open — the farewell PA |

---

## Crew interphone

Handset calls between the flight deck and the cabin — each is a call and an answer, so these are the natural place for `_1` / `_2` files. `.fx` adds the call chime and the telephone colouring.

| File name | Voices | Plays when |
|-----------|--------|------------|
| `HELLO_CREW` | Captain ↔ crew | Crew sign-on at the start of the day |
| `READY_FOR_BOARDING` | Captain ↔ crew | The flight deck releases boarding |
| `PREPARE_DOORS_DEPARTURE` | Captain ↔ crew | Arm doors and cross-check, before pushback |
| `BOARDING_COMPLETE` | Captain ↔ crew | The cabin reports boarding complete |
| `RELEASE_CREW` | Captain ↔ crew | The Captain releases the crew |
| `PREPARE_DOORS_ARRIVAL` | Captain ↔ crew | Disarm doors and cross-check, after landing |
| `DEBOARDING_COMPLETE` | Crew ↔ Captain | The cabin reports the last passenger off |

---

## Flight-deck callouts

Heard live in the cockpit — no chime, no colouring, and `.fx` does nothing here. Keep these short and dry; they are timed against the aircraft.

| File name | Voice | Plays when |
|-----------|-------|------------|
| `SPEED_80` | First Officer | 80 knots on the takeoff roll |
| `SPEED_100` | First Officer | 100 knots on the takeoff roll |
| `V1` | First Officer | Decision speed |
| `VR_ROTATE` | First Officer | Rotation speed |
| `V2` | First Officer | Takeoff safety speed |
| `GEAR_UP` | Captain + FO | Gear-up command and the positive-rate answer |
| `TOP_OF_CLIMB` | First Officer | Reaching cruise altitude |
| `APPROACHING_DESCENT` | First Officer | Nearing top of descent |
| `PREPARE_LANDING` | Captain ↔ crew | Cabin secured for landing |

---

## First Officer callouts

Spoken by the First Officer as they work the switches for you. These follow the **First Officer callouts** setting and are silent on single-pilot GA flights.

| File name | Plays when |
|-----------|------------|
| `FO_DEPARTURE_CONFIG` | Before departure — speedbrake armed, cabin signs on |
| `FO_DEPARTURE_CONFIG_SIGNS` | The same call on a Boeing, which arms no takeoff speedbrake — cabin signs only |
| `FO_LINEUP` | Lining up on the runway — lights on |
| `FO_AFTER_TAKEOFF` | After takeoff — positive rate, gear up, speedbrake disarmed |
| `FO_CLIMB_10000` | Passing 10,000 ft climbing — landing lights off |
| `FO_DESCENT_10000` | Passing 10,000 ft descending — lights on, belts on |
| `FO_APPROACH_CONFIG` | Configuring for the approach — speedbrake armed |
| `FO_ROLLOUT` | Rollout after landing — speedbrake up, flaps up |

---

## Cruise chatter

Idle conversation at random moments in the cruise. Each happens at most once per flight, and never inside a sterile-cockpit phase.

| File name | What it is |
|-----------|------------|
| `CREW_CHATTER_DRINKS` | The purser offers the flight deck a drink — interphone |
| `CREW_CHATTER_CABIN_CHECK` | The Captain asks how the cabin is doing — interphone |
| `COCKPIT_CHATTER_WEATHER` | Captain and First Officer talk about the weather ahead |
| `COCKPIT_CHATTER_PROGRESS` | …about how the flight is running |
| `COCKPIT_CHATTER_ROUTE` | …about the route and what is below |
| `COCKPIT_CHATTER_BANTER` | …about nothing in particular |

The two `CREW_CHATTER_` lines are interphone calls, so `.fx` gives them the handset treatment. The four `COCKPIT_CHATTER_` lines are spoken in the cockpit and stay dry.

---

## Recording tips

**Level.** Your clips play at the **Voice** and **Master** volumes from **Settings → Sound**, with nothing added. If a clip sounds quieter than the rest of the app, normalise the file rather than raising the volume for everything.

**Length.** Takeoff-roll callouts are triggered at a speed and should be over in a second or so — a long `V1` is still playing well past V1. Cabin PAs can run as long as you like; the next announcement waits its turn rather than talking over yours.

**Silence at the edges.** Trim leading and trailing silence. FlyAround already leaves a beat between a chime and the announcement, and between the two halves of a crew exchange.

**Checking your pack.** Start a flight and look at the app log: it lists every announcement it found a clip for and names any file it had to ignore. An ignored file means the name doesn't match one in this page — check the spelling and the capitals.

**Sharing a pack.** A pack is just the folder. Zip it up and another pilot can drop the files into their own `Documents\FlyAround Files\pa`.

---

## Related

- [Settings]({% link docs/settings.md %}) — the **PA & Callouts** and **Sound** tabs
- [Active Flight]({% link docs/active-flight.md %}) — where the announcements happen
