---
layout: default
title: First Officer Voice Commands
nav_order: 16
parent: Features
---

# First Officer Voice Commands
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

Your virtual First Officer already works the aircraft with you — lights, signs, APU, spoilers and flaps at the right moments of every flight (see [Your Virtual First Officer]({% link docs/active-flight.md %}#your-virtual-first-officer)). With a **First Officer key** bound, you can also *tell* the FO what to do: hold the key, say *"flaps one"*, *"gear up"*, *"APU on"* or *"check flaps"*, release, and it is done and read back in the crew voice.

When **GSX Pro** is installed, the same key drives ground handling: request boarding, refuelling, catering or pushback by voice, ask for the GSX menu, and answer it by saying the option — the FO reads every menu out loud so you never have to look away from the cockpit.

{: .note }
First Officer voice commands need the **AI Assistant** feature (the same speech recognition the assistant uses). Matching what you said to a command happens locally and instantly — it does not use the assistant or AI credits. Spoken replies use the crew-voice pipeline (**Settings → PA & Callouts → Realistic AI crew voices**).

---

## Setting Up

1. Open **Settings → AI Assistant → Voice & Push-to-Talk** and enable **push-to-talk**.
2. Bind the **First Officer key** — a keyboard chord or a joystick button. It is a *third* binding, separate from the assistant key and the ATC transmit key, so voice never reaches the cockpit switches by accident. Leave it unbound to keep the FO listening only to the automatic actions.
3. Pick your microphone and, if you fly in another language, set the **recognition language** hint. Short commands give automatic detection little to work with, so the hint matters more here than for the assistant.
4. Test it with the microphone check, then in the cockpit: hold the key, say *"check flaps"*, release. The FO answers with the current flap setting.

The cockpit commands work on **MSFS and X-Plane** — on X-Plane they go through the FlyAround Connect plugin, so keep it up to date. The GSX commands are MSFS-only, like GSX itself.

---

## Cockpit Commands

Hold the FO key, speak, release. The FO acts on the aircraft through its profile (Fenix, FlyByWire, iniBuilds, ToLiss, PMDG and the generic profile for everything else) and confirms in the crew voice. Anything the FO cannot do on this aircraft or in this phase is refused with a short *"negative"* and the reason.

| Say | The FO does |
|-----|-------------|
| *"flaps one"*, *"flaps 5"*, *"flaps full"*, *"flaps up"* | Sets the flap lever — Airbus handle positions (0–4) or Boeing degrees, whichever the aircraft uses |
| *"gear up"* / *"gear down"* | Moves the landing gear |
| *"arm the spoilers"*, *"speedbrakes"*, *"stow the speedbrakes"* | Arms, deploys or stows the speed brake |
| *"APU on"* / *"APU off"*, *"APU bleed on"* / *"off"* | APU master and APU bleed |
| *"fuel pumps on"* / *"off"* | Fuel boost pumps |
| *"landing lights on"*, *"taxi lights off"*, *"strobes on"*, *"beacon on"*, *"nav lights on"* | Exterior lights |
| *"seatbelts on"*, *"no smoking off"* | Cabin signs |
| *"check flaps"*, *"confirm gear"*, *"what's the APU"*, *"read back speed"*, *"what's our altitude"* | Reads the current state back without touching anything |

Any natural phrasing around the key words works — *"give me flaps two"*, *"let's have the gear down"*, *"landing lights, on please"*.

---

## GSX Ground Services by Voice

With **GSX Pro** running and **Use GSX PRO for ground handling** switched on for the flight, the FO key also commands the ground crew. Nothing changes in how FlyAround tracks boarding and pushback — the voice commands simply replace opening the GSX menu and pressing numbers.

### Requesting a service

| Say | What happens |
|-----|--------------|
| *"start boarding"*, *"board the passengers"* | Boarding starts through FlyAround's cabin flow — the same as pressing **Start boarding** in the app, so the passenger count and the cabin crew stay in sync with GSX |
| *"deboarding"*, *"disembark"*, *"unload"* | Deboarding after arrival, likewise through the cabin flow |
| *"request pushback"*, *"call the tug"* | Pushback through FlyAround's pushback flow — once per flight, with the beacon on. This is the same request ATC-approved pushback makes |
| *"refuelling"*, *"fuel truck"* | Fuel service |
| *"catering"* | Catering |
| *"jetway"*, *"jet bridge"* | Connect or disconnect the jetway |
| *"stairs"* | Airstairs |
| *"ground power"*, *"GPU"* | External power |
| *"de-icing"* | De-icing |
| *"water service"* | Potable water |
| *"lavatory service"*, *"lav"* | Lavatory service |
| *"cabin cleaning"* | Cleaning |

The FO confirms — *"Requesting refuelling."* — and GSX takes it from there. If GSX says the service is not available at this stand, is already running or cannot start yet, the FO tells you instead of firing the request.

### The GSX menu

Say *"ground services menu"* or *"handling menu"* and GSX opens its menu — and the FO **reads it out**: the title, then each numbered option. Every time GSX shows a new menu (the stand list after a pushback request, the "Yes / No" confirmations, the pushback direction) the FO reads that one too. Press the FO key or give any other command to stop the read-out.

Answer the open menu by voice:

| Say | Picks |
|-----|-------|
| *"two"*, *"option 3"*, *"the first one"*, *"number seven"* | That entry, by position |
| *"yes"*, *"affirm"*, *"go ahead"* / *"no"*, *"negative"* | The Yes / OK or No / Cancel entry |
| *"gate A12"*, *"stand alpha one two"*, *"remote 45"* | The stand with that designator on a stand list |
| *"activate services"*, *"the pushback"*, *"deboarding"* | The entry whose wording matches best |

Greyed-out entries are never picked, and when two entries match your words equally well the FO does nothing rather than guess — say the number instead.

### When the FO refuses

| The FO says | Why |
|-------------|-----|
| *"GSX is not connected."* | GSX Pro is not running, or its **Remote control server** is off (GSX Settings → Network; on by default in GSX Pro 4.0 and later) |
| *"GSX is switched off for this flight."* | **Use GSX PRO for ground handling** is off on the active flight |
| *"This aircraft talks to GSX itself."* | The aircraft has its own built-in GSX integration (the Fenix A320 family). Use the aircraft's EFB for ground services on those |
| *"No flight loaded."* | Boarding and deboarding need a dispatched flight — the ground crew belongs to the flight, not the aircraft |
| *"Refuelling is not available at this stand."* | GSX reports the service unavailable where you are parked |
| *"Boarding is already under way."* | Nothing to do — it is already running |

---

## Tips

- **Say the thing, not the letters.** *"ground services menu"* is recognised far more reliably than *"GSX menu"*, which speech recognition tends to hear as something else.
- Keep commands short — one action per press. *"Flaps two and gear down"* is two commands.
- The FO's replies are spoken with the realistic crew voices; with those off the FO still acts, silently, and the log shows what it would have said.
- Every command is written to the log: `[FO] Command <verb> … accepted=<true/false>` followed by what the FO said. A phrase that matched nothing is logged as `FO instruction not understood locally` with what was heard — the quickest way to see why a command went nowhere.
- The same commands are available to other tools through the local API (`POST /inapp/fo/command`) — the FO key and the API share one vocabulary.
