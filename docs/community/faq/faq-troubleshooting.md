---
layout: default
title: Troubleshooting (Community)
nav_exclude: true
---

# Troubleshooting FAQ
{: .no_toc }

1. TOC
{:toc}

---

## FlyAround is not connecting to the simulator

**Symptoms:** Connection indicator stays yellow or absent. No flight data received.

1. Make sure your **simulator** (MSFS or X-Plane) is running
2. Make sure the **FlyAround desktop app** is running (not just the web view)
3. Wait 30–60 seconds after loading into a flight in the simulator
4. Check that no firewall or antivirus is blocking port `30520`
5. Restart both your simulator and the FlyAround app
6. Verify your Windows user has permission to run the FlyAround backend service

---

## The "Time to Fly" button is greyed out / missing

| Cause | Fix |
|-------|-----|
| No simulator connection | Start your simulator; wait for the green indicator |
| Flight already active | Complete or cancel the existing flight |

---

## Flight tracking stopped mid-flight

1. Check the FS Connection indicator — if yellow or gone, the connection dropped
2. FlyAround will auto-reconnect — wait a minute
3. If it doesn't reconnect, close and reopen FlyAround
4. **Do not exit the flight in your simulator** — tracking resumes when the connection restores
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

## Weather data is not loading

1. Check your internet connection
2. Weather data refreshes every 15 minutes — wait and retry
3. Some airports may have limited METAR availability
4. Navigate away from the flight details page and back to force a refresh

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
