---
layout: default
title: AI Assistant
nav_order: 10
parent: Features
---

# AI Assistant — FlyAround Co-Pilot
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

The **FlyAround AI Assistant** is an intelligent in-app assistant that can answer aviation questions, provide real-time weather, assist with flight planning, and guide you through app features — through a natural chat interface, typed or spoken.

{: .note }
The AI Assistant is available on select subscription plans. AI features consume [AI Credits](#ai-credits) from your monthly allowance.

---

## The AI Mascot

The AI Assistant is represented by a **mascot character** — a small floating avatar on the right side of your screen.

| Interaction | How to |
|-------------|--------|
| **Move mascot** | Click and hold, then drag to any position on screen |
| **Resize mascot** | Scroll the mouse wheel over the mascot |
| **Open chat** | Click the mascot, or press **Ctrl+I** |

### Mascot Avatars

Choose between the mascot characters — **Kika** (classic) and **Bouba** (cap) — in **Settings → AI Assistant**.

---

## The Chat Panel

Click the **mascot avatar** (or press **Ctrl+I**) to open the AI chat panel — a side drawer with your conversation history and a message box (*"How can I help you?"*). Press **Enter** to send, **Shift+Enter** for a new line.

The panel header shows your assistant's name with a connection status icon (green = connected, amber = connecting, grey = disconnected — hover for the label) and two window controls:

| Control | What it does |
|---------|--------------|
| **Dock to the left / Dock to the right** | Flips the chat panel to the other edge of the screen. Your choice is remembered. |
| **Open in a separate window** | Pops the chat out into its own window *(desktop app only)*. |

### Pop-out Chat Window

The pop-out is a compact borderless window you can keep on a second monitor — drag its header to move it, and its size and position are remembered. Only one chat surface is active at a time: popping out closes the side panel, and **Back to the side panel** brings it back into the main window. While the chat is popped out, clicking the mascot focuses the pop-out window.

{: .note }
The assistant conversation may reset when the chat moves between the side panel and the pop-out window.

---

## Talking to the Assistant (Push-to-Talk)

You can speak to the assistant instead of typing — hold the push-to-talk key, say your request, and release. The chat opens automatically and your sentence is posted as if you had typed it.

1. Enable it under **Settings → AI Assistant → Voice & Push-to-Talk** (*"Enable push-to-talk"*).
2. Set the **Push-to-talk key** (default **Ctrl+T**) — a keyboard chord or a **joystick button**.
3. Pick your **Microphone** (or leave it on *System default*) and use **Test microphone** to verify the level bar moves as you speak.
4. Optionally set the **Recognition language** — *Follow app language* (default), *Auto-detect*, or a specific locale.

While you hold the key, a floating pill at the bottom of the screen shows *"Listening..."* with a live transcript, then *"Transcribing..."* after you release. A chip on the pill shows who you are addressing — **Assistant** or **ATC** (a separate key; see [ATC Communications]({% link docs/atc-communications.md %})).

{: .note }
Speech recognition runs through the FlyAround voice service and requires an internet connection and available AI credits.

---

## What You Can Ask

### Weather
- *"What's the weather at SFO?"*
- *"Give me the METAR for EGLL"*
- *"Is it safe to fly into KJFK right now?"*

### Flight Assistance
- *"What's the best cruise altitude for a 500nm flight?"*
- *"Help me plan a flight from KLAX to KSFO"*
- *"What cost index should I use for a short-haul flight?"*

### Aviation Knowledge
- *"What does a pushback phase involve?"*
- *"Explain weight and balance"*
- *"What is an OFP?"*

### FlyAround Help
- *"How do I add an aircraft to my hangar?"*
- *"How do I complete a flight?"*
- *"Where is my logbook?"*

---

## Rating AI Replies

Assistant replies show small **thumbs up / thumbs down** buttons underneath (*"Good response"* / *"Bad response"*). A thumbs up sends immediately; a thumbs down opens a *"What went wrong?"* dialog where you can optionally describe the problem before sending. Your feedback helps improve the assistant — each reply can be rated once.

---

## AI Credits

AI-powered features — realistic crew voices, AI checklists, push-to-talk speech recognition, and ATC voice — draw from a monthly **AI Credits** allowance included with your plan.

- The **AI Credits** card on your **Profile** page shows a meter (*"{remaining} of {total} monthly credits remaining"*), any top-up balance, and the renewal date.
- Your monthly allowance resets each billing cycle and does not roll over. **Top-up credits** (purchased on `my.flysim.io`) never expire and are used only after the monthly allowance runs out.
- A warning appears when you are running low.

### When credits run out

*"You're out of AI credits. Crew voice switches to the standard voice and AI checklists pause until your credits renew."*

| Feature | Behavior at zero credits |
|---------|--------------------------|
| Crew voices | Keep speaking, but switch to the standard (non-premium) voice |
| AI checklists | Paused until credits renew |
| Push-to-talk speech recognition | Unavailable |

An **Out of AI credits** dialog appears when an AI action is refused, with an **Upgrade** (trial) or **Buy credits** (paid plans) button.

---

## Customizing the AI Assistant

Open **Settings → AI Assistant**:
- **Assistant Name** — Give your AI a custom name (default: "FlyAround AI")
- **Mascot** — Select which mascot character to display
- **Voice & Push-to-Talk** — Enable voice input, set keys, microphone, and recognition language

Crew voice options (realistic AI crew voices, crew voice gender, voice volumes) live in the **System → Voices** and **Sound** settings — see [Settings]({% link docs/settings.md %}).

---

## Tips

- Include ICAO codes in weather questions for precise results (e.g., `EGLL` not `Heathrow`)
- The AI remembers context within the current session — follow-up questions work naturally
- Use it during flight planning for quick weather or route advice without switching apps
- Bind push-to-talk to a spare joystick button so you can query the assistant hands-on-yoke
