---
layout: default
title: Streaming
nav_order: 10
parent: Features
---

# Streaming
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

FlyAround can broadcast your flight live to **YouTube** and **Twitch**, driving [OBS Studio](https://obsproject.com/)
for you — no manual scene switching or clicking Start Streaming.

{: .note }
Streaming is available on accounts with the **Stream** feature enabled.

---

## One-time OBS setup

### 1. Install OBS Studio

Download and install [OBS Studio](https://obsproject.com/) (free) if you don't already have it.

### 2. Import the FlyAround scene collection

In FlyAround, open **Settings → Streaming** and click **Download the OBS scene** — this saves
`flyaround-scene.json`.

In OBS: **Scene Collection → Import** → select the downloaded file → activate it under
**Scene Collection**.

The scene, named **FlyAround**, contains:

| Source | Purpose |
|--------|---------|
| **Sim (Game Capture)** | Captures your fullscreen simulator |
| **FlyAround Overlay** | A browser source showing the in-game overlay (`http://localhost:5070/streaming` by default) |
| **Desktop Audio** | Sim sound |

{: .note }
If your overlay isn't served from `localhost:5070`, double-click **FlyAround Overlay** in OBS and
set the URL to your overlay's `/streaming` address. The background is transparent so it composites
cleanly over the game.

### 3. Enable OBS' WebSocket server

FlyAround controls OBS — setting the stream target and starting/stopping the stream — over
**obs-websocket v5**, which ships built into modern OBS but is off by default.

In OBS: **Tools → WebSocket Server Settings**:

- ✅ Enable WebSocket server
- Port: **4455** (default)
- Password: optional, but recommended

{: .note }
If you set a password, enter it in FlyAround's **Settings → Streaming** so it can connect. Host and
port default to `ws://127.0.0.1:4455`, matching OBS' defaults.

### 4. Connect your channel(s)

Still in **Settings → Streaming**, connect the platform(s) you broadcast to:

- **YouTube** — required to go live.
- **Twitch** — optional, for simulcasting.

---

## Streaming from a separate PC

The automatic setup above relies on FlyAround reaching OBS over `obs-websocket` on
`localhost` — it only works when OBS and FlyAround run on the **same PC**. If OBS runs
on a dedicated streaming/encoding PC instead, use your account's permanent relay
credentials:

1. Connect at least one platform under **Settings → Streaming** (see step 4 above) —
   this mints a **Stream key** for your account, shown in the **Stream to OBS Studio**
   card that appears once you've connected one.
2. Copy the **Server** and **Stream key** from that card.
3. On the OBS PC, open **Settings → Stream**, set Service to **Custom…**, and paste
   them in.
4. From then on, click **Start Streaming**/**Stop Streaming** in OBS yourself when you
   go live in FlyAround — the key doesn't change per flight, so this is a one-time
   setup.

{: .warning }
This stream key is permanent and works across every flight — treat it like a
password. If it leaks, regenerate it from the same **Stream to OBS Studio** card; any
OBS still configured with the old key will stop being able to go live until you paste
in the new one.

{: .note }
FlyAround can't start/stop OBS for you in this setup — it has no `obs-websocket`
connection to reach OBS across the network. You control OBS' Start/Stop Streaming
directly.

---

## Going live

Once OBS is set up and a channel is connected:

1. Start (or open) an active flight.
2. Use the **Go Live** button in the navbar, or the live-stream panel on the flight view.
3. FlyAround points OBS at the stream relay and starts streaming — you don't touch OBS' own Start
   Streaming button.
4. Use **Mark moment** while live to drop a highlight marker on your flight's route at your current
   position.
5. **Stop streaming** ends the broadcast and stops OBS.

### Planning a stream in advance

When scheduling a flight from the [Calendar]({% link docs/calendar-scheduling.md %}), you can also
plan a stream for it — pick platforms, visibility, and an optional cover image ahead of time. The
stream starts automatically when you go live for that flight.

---

## Notes

- Running OBS on the same PC as FlyAround? Don't set a Stream key under OBS' own
  **Settings → Stream** — FlyAround sets a custom target programmatically each time you
  go live. Running OBS on a separate PC? See
  [Streaming from a separate PC](#streaming-from-a-separate-pc) above — that flow sets
  the key manually and permanently instead.
- Background music can trigger copyright claims on your channel — use license-safe audio.
- See [Settings]({% link docs/settings.md %}) for the full Streaming tab reference.
