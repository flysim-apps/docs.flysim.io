---
layout: default
title: PMDG Data Broadcast
nav_order: 15
parent: Features
---

# PMDG Data Broadcast
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

PMDG aircraft — the 737, the 777 and the 777F — keep their switches, signs, lights and MCP entirely inside their own systems. A generic simulator variable cannot see them: ask the simulator whether the seatbelt sign is on and a PMDG aircraft answers for a sign it does not use.

PMDG solves this with a **data broadcast**: a feed the aircraft publishes with everything on the flight deck in it. FlyAround reads that feed, which is how it knows your cabin signs are on, which landing lights you selected, what altitude is in the MCP, and what V1 and VR your FMC computed.

The broadcast is **off by default** and is enabled per aircraft, in a text file. This page shows you where.

---

## Do I need this?

Only if you fly a PMDG aircraft. Everything else in FlyAround works without it.

With the broadcast off, FlyAround falls back to the generic simulator variables. Your flight still tracks and still scores — but on a PMDG aircraft the cabin signs, exterior lights, door state and MCP readouts come from switches the aircraft is not really using, so they can disagree with what you see in the cockpit.

FlyAround tells you when this is the case: load a PMDG aircraft with the broadcast off and a notice appears pointing you back at this page.

---

## Where the file lives

Each aircraft has its own options file, in a **work folder** belonging to the simulator you fly. Which folder that is depends on the simulator — this is the step people most often get wrong, because both folders can exist on the same PC and only one of them is read.

### Microsoft Flight Simulator 2024

```
%LOCALAPPDATA%\Packages\Microsoft.Limitless_8wekyb3d8bbwe\LocalState\WASM\MSFS2024\<aircraft>\work\
```

### Microsoft Flight Simulator 2020

```
%APPDATA%\Microsoft Flight Simulator\Packages\<aircraft>\work\
```

Paste the path into the Windows Explorer address bar and press Enter — Windows expands `%LOCALAPPDATA%` and `%APPDATA%` for you.

### The aircraft folder and file name

| Aircraft | Folder | File |
|---|---|---|
| 737-600/700/800/900 | `pmdg-aircraft-73<n>` | `737_Options.ini` |
| 777-300ER | `pmdg-aircraft-77w` | `777_Options.ini` |
| 777-200ER | `pmdg-aircraft-77er` | `777_Options.ini` |
| 777F | `pmdg-aircraft-77f` | `777_Options.ini` |

Each variant you fly has its own folder and its own file. Turning the broadcast on for the 737 does nothing for the 777.

{: .warning }
> If you have both simulators installed you will find the same file in both places. Only the copy under the simulator you actually fly is read. Check the **Date modified** column: the live one is the one the simulator wrote recently.

---

## Turning it on

1. **Close the simulator.** PMDG reads this file when the aircraft loads and writes it back when the aircraft unloads, so an edit made while the aircraft is loaded is either ignored or overwritten.
2. Open the options file in a plain text editor — Notepad is fine.
3. Scroll to the very bottom and add these four lines:

```ini
[SDK]
EnableDataBroadcast=1
EnableCDUBroadcast.0=1
EnableCDUBroadcast.1=1
```

4. Save, start the simulator, and load the aircraft.

If a `[SDK]` section is already there, do not add a second one — set `EnableDataBroadcast` to `1` in the section that exists.

{: .important }
> Type the lines rather than pasting them from a formatted document. Each line must end right after the value: `[SDK]` and nothing else, `EnableDataBroadcast=1` and nothing else. Trailing spaces after `[SDK]` are enough to stop PMDG recognising the section, and the symptom is identical to not having added it at all.

`EnableDataBroadcast` is the line FlyAround needs. The two `EnableCDUBroadcast` lines publish the CDU screens; they are harmless to leave in and are what other tools on your PC — hardware CDUs, stream overlays — read.

---

## Checking it worked

Load the aircraft and give it a minute. If the broadcast is running, the notice in FlyAround clears on its own, and the cabin signs and exterior lights in the app start following the real switches in the flight deck.

If the notice is still there:

- **Did you edit the file for the simulator you are flying?** This is by far the most common cause. Compare the **Date modified** on both copies.
- **Did you edit the file for the variant you loaded?** The 777-300ER and the 777-200ER are separate folders.
- **Is the section spelled exactly `[SDK]`, on a line of its own, with nothing after it?**
- **Did you restart the simulator?** Changing the file with the aircraft loaded does not take effect, and PMDG may write its own copy back over your edit when the aircraft unloads.

---

## Why it is off by default

The broadcast is a PMDG setting, not a FlyAround one, and PMDG ships it off so that an aircraft is not publishing its full state to anything on the PC that cares to listen. Turning it on affects nothing in the simulator and costs no performance — it simply makes the data available to add-ons like FlyAround, and you can turn it off again by setting the same line to `0`.
