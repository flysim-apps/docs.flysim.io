---
layout: default
title: Shared Skies
nav_order: 13
parent: Features
---

# Shared Skies
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

**Shared Skies** puts other FlyAround pilots into your simulator. When another
pilot is flying within the radius you choose, their aircraft appears in your
sim — on your traffic displays, and, once set up, out of the window.

Traffic comes from the same live feed the Live Map draws, so anyone flying with
FlyAround at that moment is a candidate. No configuration is shared between
pilots and nobody has to be on your friends list.

## Turning it on

**Settings → System → Shared skies**

| Setting | What it does |
|---|---|
| **Show other FlyAround pilots in the sim** | The master switch. Off by default. |
| **Range** | How far out pilots are picked up: 20, 40, 100 or 200 nm. |

The switch takes effect immediately — there is no need to restart the app or
the simulator. Aircraft appear within a few seconds and are removed again when
a pilot leaves your range or stops flying.

Pick the range to match how busy the skies are. At 20–40 nm you will usually
share the sky only around a hub or during an event; 100–200 nm is the setting
to use when you want to see that the feature is working at all.

## Microsoft Flight Simulator

Nothing to install. FlyAround spawns visible aircraft directly and matches each
pilot's aircraft type and airline against the AI models already on your system.

If you fly with **FSLTL** or **AIG** models installed, airline liveries will
match closely — those packs are exactly what the matcher looks for. Without
them you will still see aircraft, just in whatever generic AI models your
install provides.

{: .note }
> MSFS 2024 draws only legacy, non-modular AI models. Its own current-generation
> aircraft are accepted by the simulator but never rendered, so FlyAround will
> not use them — it would look like success while showing you empty sky.

## X-Plane

X-Plane has two levels, and the difference matters.

| | What you get | What it needs |
|---|---|---|
| **Traffic contacts** | Other pilots on TCAS, the ND and any add-on that reads traffic | The FlyAround Connect plugin — nothing else |
| **Visible aircraft** | Aeroplanes you can actually see, in airline liveries | A CSL model library, installed once (below) |

Contacts work out of the box. Visible aircraft need aircraft *models*, and
X-Plane does not ship any that a plugin may draw — which is why this is a
one-time download.

### Step 1 — check whether you already have the models

If you use **LiveTraffic**, you almost certainly do. FlyAround looks for a CSL
library in two places, in order:

1. `X-Plane 12/Resources/plugins/FlyAroundConnect/Resources/CSL`
2. `X-Plane 12/Resources/plugins/LiveTraffic/Resources/CSL`

If LiveTraffic's library is there, FlyAround uses it as-is. Skip to step 3.

### Step 2 — install the Bluebell CSL models

The usual model set is **Bluebell**, a free package of around 1,800 liveries
across 80 aircraft types, maintained for exactly this purpose.

1. Download all 12 zip files from the
   [Bluebell OBJ8 CSL packages](https://forums.x-plane.org/index.php?/files/file/37041-bluebell-obj8-csl-packages/)
   page on the X-Plane.org forum. (The model definitions are also on
   [GitHub](https://github.com/oktal3700/bluebell), but the forum download is
   the complete package including textures.)
2. Create the folder
   `X-Plane 12/Resources/plugins/FlyAroundConnect/Resources/CSL`.
3. Unpack all 12 zips into it. You should end up with folders named
   `BB_Airbus`, `BB_Boeing`, `BB_Props`, `BB_GA` and so on — the `BB_` folders
   go directly inside `CSL`, not in a further subfolder.

The full set is around 4 GB. You can install fewer packages if disk space is
tight — FlyAround uses whatever is present and substitutes a related type when
an exact match is missing.

### Step 3 — enable visible aircraft

Create an empty file named **`xpmp2.enable`** in

```
X-Plane 12/Resources/plugins/FlyAroundConnect/Resources/
```

The file's contents do not matter; only its presence does. Visible traffic
stays off until it exists, so that a FlyAround update can never start drawing
aircraft in your simulator unless you asked for it.

### Step 4 — restart X-Plane and check

Restart X-Plane, then open `X-Plane 12/Log.txt` and search for `FlyAround`.

```
[FlyAround] XPMP2 CSL library: Resources/plugins/FlyAroundConnect/Resources/CSL
[FlyAround] XPMP2 ready with 2027 CSL model(s)
[FlyAround] Traffic drawn with XPMP2 (visible aircraft)
```

That is a working setup. Anything else is covered below.

## If aircraft do not appear

Check `Log.txt` first — the plugin says exactly which step is missing.

| Log line | What it means |
|---|---|
| `XPMP2 stays off — no xpmp2.enable marker` | Step 3 not done. Create the marker file. |
| `No CSL model library found — TCAS-only traffic` | No models in either location. Do step 2. |
| `XPMP2 has no CSL models — falling back to TCAS-only traffic` | The `CSL` folder exists but is empty, or the `BB_` folders are nested one level too deep. |
| `Traffic shown on TCAS only (no CSL models)` | Same as above — you will still get traffic contacts. |
| `XPMP2 could not take over AI planes: <plugin> controls TCAS / AI` | Harmless. Another traffic add-on holds the TCAS slots, so FlyAround's aircraft are drawn but do not show on traffic displays. |

If the log looks healthy and you still see nothing, the likeliest answer is
that there is genuinely nobody near you. Raise **Range** to 200 nm and check
the Live Map to see where other pilots are flying right now — an empty sky and
a broken setup look identical from the cockpit.

Two more things worth knowing:

* **A parked aircraft can be behind a building.** Traffic is placed at the
  pilot's real position, which at a busy airport may be on the far side of a
  terminal. Look for airborne traffic when checking that the feature works.
* **Traffic costs frames.** Every injected aircraft is drawn like any other. If
  your frame rate suffers around a hub, reduce the range.

## What you will see

Each aircraft is matched on the pilot's ICAO type and airline, so a Qatar A350
appears as a Qatar widebody and a Delta 737 in Delta colours. When your model
library has no exact type, FlyAround substitutes the closest related one rather
than showing nothing — a plausible silhouette in the right livery beats an
empty sky.

Other pilots see nothing of you beyond what you already broadcast to the Live
Map. Shared Skies only draws; it does not change what you share.
