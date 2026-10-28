---
layout: default
title: Streaming
nav_order: 9
parent: Features
---

# Streaming
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

FlyAround broadcasts your flight live to **YouTube** and **Twitch** with one button. Connect a channel
once, choose how the flight is captured, and every flight after that goes out with a tidy title, a
cover and live chat, straight from the cockpit.

{: .note }
Streaming is a **FlyAround Pro** feature: it is available on accounts with the **Stream** feature
enabled. It is not part of the Community edition.

Everything lives on the **Streaming** page, its own item in the navigation drawer. The page walks you
through four steps; the sections below follow the same order.

---

## Step 1 — Pick where your viewers are

Connect **YouTube**, **Twitch** or both. FlyAround streams to every connected channel at once, so you
only ever press one button.

### How connecting works

1. Click **Connect** on a channel card.
2. FlyAround opens the connect page on **my.flysim.io** in your browser. The link carries a one-time
   ticket tied to your FlyAround session, so the channel attaches to the account running the app, not
   to whichever account the browser happens to be signed into.
3. Sign in with the platform and accept the consent screen.
4. Back in FlyAround the card switches to **Connected** on its own within a few seconds.

{: .note }
When connecting YouTube, sign in with the Google account that owns (or manages) the channel you want
to stream to. If your browser is signed into more than one, pick that one on Google's account screen.

### What FlyAround asks for

| Platform | Permission requested | What FlyAround uses it for |
|----------|----------------------|----------------------------|
| **YouTube** | `youtube.force-ssl` (manage your YouTube account) | Create live broadcasts for your flights or bind the ingest to one you planned, set the title, description and thumbnail of those broadcasts, list your upcoming broadcasts, read the live chat of the running stream and post your replies to it |
| **Twitch** | `channel:manage:broadcast`, `channel:read:stream_key` | Set the stream title, category and tags on your channel and send the video to your channel |
| **Twitch** | `user:read:chat`, `user:write:chat` | Read the chat of your running stream and post your replies to it |

FlyAround reads and writes nothing else on either platform: no private videos, no subscriber or
viewer lists, no posts outside your own live chat. The access tokens are stored encrypted by the
FlyAround stream service and are used only while you stream. **Disconnect** on a channel card revokes
the token with the platform and deletes it. The [privacy policy](https://flysim.io/legal/privacy)
has the full description of the data involved.

{: .note }
Connected Twitch before the chat scopes existed? Chat stays silent until you **Disconnect** and
**Connect** Twitch again, which grants the two chat permissions.

---

## Step 2 — Choose how FlyAround captures your flight

Two modes. **Built-in capture** needs nothing else installed; **OBS Studio** stays there for pilots who
like to run their own scenes.

### Built-in capture

Pick your sim display, pick your mic, press Go live. FlyAround records, encodes and sends everything
itself, straight to the FlyAround relay.

| Setting | What it does |
|---------|--------------|
| **What viewers see** | The display your simulator runs on, or a single window. Displays are listed first, the simulator window is tagged **Simulator**. The FlyAround overlay is on the stream whenever it is open on that display. **Look again** rescans after you start the sim. |
| **Preview the capture** | A quick look at exactly what goes out. |
| **Game and system sound** | Engines, ATC and your music, everything your PC plays. Turn it off for a commentary-only stream. |
| **Microphone** | Any input device, the Windows default, or **No microphone**. The **Your voice** meter shows the level. |
| **Quality** | 1080p · 60 fps (6000 kbps, needs a solid 8 Mbps upload), 1080p · 30 fps (4500 kbps), 720p · 60 fps (4500 kbps) or 720p · 30 fps (3000 kbps, for slow connections). |

{: .important }
Run the simulator in borderless or windowed mode: exclusive fullscreen cannot be captured. Capturing
only the simulator window leaves the FlyAround overlay out, so a display is the better pick.

Known limits of built-in capture:

- Exclusive-fullscreen simulators cannot be captured (see above).
- HDR displays and multi-GPU setups are edge cases; if the preview looks wrong, capture a display on
  the GPU that renders the sim, or use OBS Studio.
- Game and system sound capture is available on Windows only.

Built-in capture is new in this release. It is offered on the desktop app with the experimental
features; OBS Studio remains the default until it has flown enough hours.

### OBS Studio

Your own scenes, sources and plugins. FlyAround drives OBS through its WebSocket: it points OBS at the
relay, starts the stream and keeps an eye on it. Set this up once and forget it.

#### 1. Install OBS Studio

Download and install [OBS Studio](https://obsproject.com/) (free) if you don't already have it.

#### 2. Import the FlyAround scene collection

On the Streaming page, click **Download the ready-made OBS scene**. This saves `flyaround-scene.json`,
a scene with the sim capture and the FlyAround overlay already in place.

In OBS: **Scene Collection → Import** → select the downloaded file → activate it under
**Scene Collection**.

| Source | Purpose |
|--------|---------|
| **Sim (Window Capture)** | Captures your simulator window (MSFS / X-Plane) |
| **FlyAround Overlay** | A browser source showing the stream overlay (`http://localhost:30500/share/#/streaming`) |
| **Desktop Audio** | Sim sound |

{: .note }
FlyAround detects your running simulator window and fills in the Window Capture target each time you
download the scene. If no sim is running when you download it, start your sim first and re-download,
or set the capture window under that source's **Properties** in OBS.

{: .note }
The overlay is served by FlyAround's own embedded server on port 30500, at the `/share/#/streaming`
path. If it isn't reachable there, double-click **FlyAround Overlay** in OBS and set the URL to
`http://localhost:30500/share/#/streaming`. The background is transparent so it composites cleanly
over the game.

#### 3. Enable OBS' WebSocket server

In OBS: **Tools → WebSocket Server Settings**:

- ✅ Enable WebSocket server
- Port: **4455** (default)
- Newer OBS versions enable authentication and generate a random password by default. Copy that
  password into the **OBS WebSocket password** field on the Streaming page, or FlyAround won't be able
  to reach OBS to go live.

Leave the address blank when OBS and FlyAround run on the same PC: the default is `ws://127.0.0.1:4455`.
Don't paste OBS' "Server IP" from its Connect Info dialog there; that is for pairing a different device.
**Test connection** confirms the link.

#### Streaming from a second PC

FlyAround reaches OBS over the WebSocket on `localhost` only. If OBS runs on a dedicated streaming rig,
use your account's permanent relay credentials from the **Streaming from a second PC?** section of the
OBS card:

1. Connect at least one channel first; that mints the **Stream key** for your account.
2. Copy the **Server** and **Stream key**.
3. On the OBS PC, open **Settings → Stream**, set Service to **Custom…**, and paste them in.
4. From then on, click **Start Streaming** / **Stop Streaming** in OBS yourself when you go live in
   FlyAround. The key doesn't change per flight, so this is a one-time setup.

{: .warning }
The stream key is permanent and works across every flight. Treat it like a password: anyone with it
can stream as you. If it leaks, click **Regenerate stream key**; any OBS still configured with the old
key stops being able to go live until you paste in the new one.

{: .note }
Running OBS on the same PC? Don't set a stream key under OBS' own **Settings → Stream**. FlyAround
sets the target itself each time you go live.

---

## Step 3 — Make every stream look like you

The **Stream title** and **Stream description** are what your viewers see first. Write them once with
placeholders, and FlyAround fills in the airports, aircraft and callsign for each flight. Tap a
placeholder to drop it into the field you were typing in; **Use the FlyAround default** restores the
built-in pattern.

| Placeholder | Fills in |
|-------------|----------|
| `{origin}` / `{destination}` | Departure / arrival airport ICAO (`EGLL`, `KJFK`) |
| `{originCity}` / `{destinationCity}` | Departure / arrival city (`London`, `New York`) |
| `{originName}` / `{destinationName}` | Departure / arrival airport name (`London Heathrow`) |
| `{airline}` | Airline name (`British Airways`) |
| `{airlineCode}` | Airline ICAO code (`BAW`) |
| `{aircraft}` | Aircraft name (`Boeing 777-200ER`) |
| `{type}` | Aircraft ICAO type (`B772`) |
| `{reg}` | Registration (`G-YMMA`) |
| `{callsign}` | Callsign (`BAW117`) |
| `{route}` | Filed route |
| `{date}` | Today's date |
| `{flyonLink}` | Public link to the flight on flyon.me |
| `{donateLink}` | Your FlyDonate tip page (empty until FlyDonate is connected) |

A line of the description whose placeholders are all empty for this flight is dropped, so a free
flight without a filed route doesn't end up with an empty "Route:" line. **How it will look** previews
the result with your current flight, or a sample flight until you start one.

**Tags** are added to every stream, next to the airports and callsign FlyAround adds on its own.

{: .note }
Twitch trims tags to 25 letters/digits (no spaces). Its go-live notification text can't be set through
the API; set it once in your Twitch dashboard (Settings → Notifications) and it applies to every stream.

---

## Step 4 — Let viewers tip the crew

[FlyDonate](https://flydonate.com) puts a tip page under your stream. Once you are approved on
FlyDonate, FlyAround picks it up on its own:

- Tips pop up on the overlay. The **donation goal** and the **tip alert** are overlay blocks: drop them
  wherever you like in the [overlay editor]({% link docs/settings.md %}#stream-overlay). Alerts, goals
  and sounds are set up on your FlyDonate dashboard.
- Each tip lands on the flight timeline as a moment.
- The `{donateLink}` placeholder fills your tip page into the stream description, and the chat window
  has a one-tap **Tip link** reply with it.

Not on FlyDonate yet? **Apply on FlyDonate** from the card.

---

## Defaults for the Go live button

Set who can find the stream (**Public**, or **Unlisted** for people with the link on YouTube), which
connected channels are selected by default, and whether the stream is **Made for kids** (tells YouTube
the stream is aimed at children; leave it off for a normal flight stream). You can still change any of
these right before a stream.

### Start and stop the stream with the flight

Two switches, both off by default:

- **Start the stream automatically** at the moment you choose: boarding started, pushback or takeoff.
  FlyAround goes live with your saved defaults (channels, visibility, tags, title and description
  patterns, cover rule, and a planned YouTube stream when one matches) through the capture mode you
  set up, OBS or built-in. If it can't, a notice in the main window says why and opens the Go live
  window; the flight carries on regardless.
- **Stop the stream automatically** at engine shutdown or when the flight completes. A countdown of
  30 seconds appears in the main window first; cancel it to keep streaming, otherwise the normal stop
  runs: the broadcast completes and the recording is resolved.

While a start trigger is armed, the Go live tile on the launch pad shows it.

---

## Going live

Start (or open) an active flight, then press **Go live** on the Streaming page or the Go live tile on
the launch pad. The **Live Stream** window opens with everything about this stream:

**Broadcast to**
: Tick the connected channels for this stream. The last channels you actually streamed to are
  pre-selected next time.

**Planned on YouTube**
: Shown when YouTube is selected and your channel has upcoming broadcasts, planned in FlyAround
  (from the Calendar) or created in YouTube Studio. The one planned for around now is tagged
  **Planned for now** and pre-selected; **New stream** makes a fresh broadcast instead. A planned
  stream is picked up exactly as you published it: FlyAround leaves the title, description, cover and
  visibility untouched and only binds the video to it. Twitch gets the same title. If auto-start is off
  on that broadcast, FlyAround starts it for you once the video is flowing.

**Title**
: Filled from your title pattern; edit it freely.

**Cover image**
: **Upload cover** for your own image, or **Generate cover with AI** for a cover that matches the
  description. AI generation is one-time per flight; upload your own image any time before you go live
  to replace it. Covers apply to YouTube only; Twitch shows an auto-captured live preview instead.

**Advanced — description, tags, visibility**
: The description filled from your pattern, with **Write it for me ✨** to let the AI Assistant write
  an intro from the flight details and **Back to my template** to undo it, the tags, and the
  visibility (**Public** or **Unlisted**; Twitch has no unlisted mode).

{: .note }
Pressing **Go live** on the launch pad while a YouTube stream is planned for around now goes straight
live with that stream's settings, without opening the window first.

Press **Go live**. FlyAround creates the broadcasts, provisions the relay and starts the capture. The
running simulator is detected and becomes the Twitch category; YouTube reads the same name from the
title suffix FlyAround adds.

### Planning a stream in advance

When scheduling a flight from the [Calendar]({% link docs/calendar-scheduling.md %}), tick
**Stream this flight live** to plan the stream ahead of time: platforms, visibility, title, cover and
description. The stream is created on YouTube right away and picked up when you go live for that
flight.

---

## While you are live

The Live Stream window becomes the control room:

- **Health** and the elapsed time. **Checking…**, **Waiting for OBS to start pushing…** during the
  first seconds, **Healthy** once the relay sees video. **OBS isn't streaming** (or **The capture
  stopped** with built-in capture) offers **Reconnect**, which restarts the capture without ending the
  broadcasts. **Reconnecting to the relay…** means built-in capture lost the relay and is retrying on
  its own.
- **Bitrate**. FlyAround measures the outgoing bitrate and warns when it exceeds what Twitch accepts.
- **Mark moment** drops a highlight marker on your route at your current position, with an optional
  note. Moments become clips on the flight's map after the stream.
- **Open chat** opens the chat window with the messages from every platform in one feed. Your reply
  goes to every platform the stream is on. New messages also pop up as toasts in the main window and in
  the Live Stream window while the chat window is closed; your own replies never toast. A burst of
  messages shows the first three and a "+N more" line.
- **Watch stream** opens the public watch page.
- **Stop streaming** ends the broadcast on every platform and stops the capture.

### Twitch limits

Twitch takes at most 1080p at 60 fps and 6000 kbps H.264 with 160 kbps AAC audio and a 2-second
keyframe interval. One stream feeds every selected platform, so the limits apply to YouTube too when
both are picked.

With OBS Studio, FlyAround adjusts the resolution and frame rate when you go live and lists what it
changed under **Adjusted for Twitch at go-live**. The bitrate is only auto-adjusted when OBS uses
Simple output; with Advanced output, set it yourself under OBS Settings → Output. Built-in capture
presets already fit these limits.

### Reconnects

The relay keeps your broadcasts alive across short gaps: a stalled capture or a dropped connection
does not end the stream on YouTube or Twitch. YouTube's own auto-stop is disabled on FlyAround
broadcasts for the same reason, and every stop goes through FlyAround so the broadcast is completed
properly.

---

## After the flight

Every major phase (pushback, takeoff, cruise, landing) and every moment you marked is a key point on
the route, with a thumbnail taken from the recording and a link to that moment in the VOD on each
platform. They show on the flight's route map on the [Live Map]({% link docs/live-map.md %}) and in the
[Logbook]({% link docs/logbook.md %}), and on the flight's public page on flyon.me, where viewers can
open the recording at that exact moment.

A stream outlives the flight that started it: if you don't stop it, the Go live tile stays on
**Live — manage stream** until you do.

---

## Stream Deck keys

The FlyAround plugin for Stream Deck (see **Support → FlyAround for Stream Deck** in the app) gets four
streaming keys: **Go Live** (uses your saved defaults, the same path as the automatic start),
**Stop stream**, **Mark moment** and **Chat** (opens the chat window). The keys show the live state with
the elapsed time and stay dimmed without a flight or when streaming isn't on your account.

---

## Troubleshooting

**"Can't reach OBS" when going live**
: OBS is not running, its WebSocket server is off, or the password is wrong. In OBS open
  **Tools → WebSocket Server Settings**, enable the server on port **4455**, and copy its password into
  the OBS card on the Streaming page. **Test connection** should answer before you try again.

**"Link expired" on the connect page**
: The one-time ticket in the link was already used or timed out. Go back to FlyAround and press
  **Connect** again to get a fresh link.

**Twitch chat shows nothing**
: The Twitch connection predates the chat permissions. **Disconnect** and **Connect** Twitch again.

**The stream ended on its own**
: A long gap in the video can still end a platform broadcast. FlyAround reconnects the relay by itself
  and keeps YouTube's auto-stop off, but if the window shows **Stream ended unexpectedly**, stop and go
  live again; the new session gets a fresh broadcast.

**Built-in capture shows a black picture**
: The simulator runs in exclusive fullscreen. Switch it to borderless or windowed and press
  **Look again**.

**The stream buffers or drops on Twitch**
: The outgoing bitrate is above Twitch's 6 Mbps cap. Lower the video bitrate in OBS (Settings →
  Output), or pick a lower quality preset for built-in capture.

---

## Notes

- Background music can trigger copyright claims on your channel; use license-safe audio.
- See [Settings]({% link docs/settings.md %}#stream-overlay) for the Stream Overlay page, where the
  overlay you see on the stream is designed.
