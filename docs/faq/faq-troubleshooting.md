---
layout: default
title: Troubleshooting
nav_order: 5
parent: FAQ
---

# Troubleshooting FAQ
{: .no_toc }

1. TOC
{:toc}

---

## FlyAround is not connecting to the simulator

**Symptoms:** Connection indicator stays yellow or absent. No flight data received.

1. Make sure **Microsoft Flight Simulator** is running
2. Make sure the **FlyAround desktop app** is running (not just the web view)
3. Wait 30–60 seconds after loading into a flight in MSFS
4. Check that no firewall or antivirus is blocking port `30520`
5. Restart both MSFS and the FlyAround app
6. Verify your Windows user has permission to run the FlyAround backend service

---

## The "Time to Fly" button is greyed out / missing

| Cause | Fix |
|-------|-----|
| No simulator connection | Start MSFS; wait for green indicator |
| Flight already active | Complete or cancel the existing flight |
| Account is Limited | Activate a subscription in Profile → Billing |

---

## Flight tracking stopped mid-flight

1. Check the FS Connection indicator — if yellow or gone, the connection dropped
2. FlyAround will auto-reconnect — wait a minute
3. If it doesn't reconnect, close and reopen FlyAround
4. **Do not exit the flight in MSFS** — tracking resumes when the connection restores
5. If the issue persists, cancel the current flight and start a new one

---

## SimBrief import is not working

1. Ensure you have a **completed** flight plan in SimBrief (not a draft)
2. Check that your SimBrief account is linked to FlyAround in Settings
3. Verify your internet connection
4. Use manual route entry as a fallback

---

## My aircraft is not showing in the Dispatcher

1. Confirm the aircraft exists in your Hangar
2. Check that the "Loaded Aircraft" filter is not active
3. Click **Refresh** in the Hangar to reload fleet data
4. If the Hangar is empty, [add an aircraft first]({% link docs/hangar-fleet.md %})

---

## I completed a flight but it's not in my Logbook

1. Refresh the Logbook (navigate away and back)
2. Confirm the flight was **completed**, not cancelled
3. Ensure you waited for the completion confirmation before closing the app
4. Contact support with your pilot ID and approximate date/time of the missing flight

---

## The app shows "Account is Limited" but I have a subscription

1. Log out and log back in
2. Wait 2–3 minutes for billing status to sync
3. Check the Billing tab in Profile to see the status shown there
4. If unresolved, contact FlyAround support with your account email and subscription confirmation

---

## Weather data is not loading

1. Check your internet connection
2. Weather data refreshes every 15 minutes — wait and retry
3. Some airports may have limited METAR availability
4. Navigate away from the flight details page and back to force a refresh

---

## The AI Assistant mascot is not visible

1. Check **Settings → AI Assistant** tab — if this tab is missing, the AI feature is not on your plan
2. If the tab exists, verify the assistant is enabled
3. The mascot may have been dragged off-screen — try logging out and back in to reset its position

---

## The overlay is not visible in OBS

1. Go to **Settings → Overlay** in FlyAround to get the overlay page URL
2. In OBS, add a **Browser Source** with that URL
3. Set the browser source dimensions to match your stream resolution
4. Ensure FlyAround is running and a flight is active for data to appear

---

## I can't log in — authentication is failing

1. Verify your credentials are correct
2. Check your internet connection
3. If you recently changed your password, use the updated one
4. Try from a different network if possible
5. Contact support if the issue continues
