---
name: asu-shuttle-radar
description: Plans ASU intercampus commutes and sends a leave-by-time nudge with route, weather and an optional coffee stop. Use when the student asks what time to leave for a class on another campus, wants a daily commute plan, or keeps missing shuttles.
---

# ASU Shuttle Radar

This Skill uses only Cubbie's built-in capabilities. It has no scripts.

## When to use

- "What time do I need to leave for my 12pm class at West?"
- "Set up a daily commute plan for me."
- "Which shuttle is running right now?"
- "I keep missing the shuttle to Poly."

Do not use it for study plans, exam prep, or anything that changes Canvas or Google Calendar.

## Onboarding (first use only)

1. Ask: "Do you take the ASU shuttle or Valley Metro? Which campus do you usually leave from?"
2. Save the answer (mode + home campus/stop) with Cubbie's **Memory** capability.
3. If the student doesn't commute across campuses, say so and stop.

## Steps

1. Get the student's upcoming classes with Cubbie's **Google Calendar** or **Canvas** capability
   (class times and locations). If neither is connected, ask the student for their class times
   and campuses, and stop after offering to connect.
2. For each class on a different campus than the student's home campus, compute the leave-by time:
   shuttle ride time + walk to stop + 15-minute buffer. Use the published ASU shuttle schedules
   (cfo.asu.edu) for ride times; fall back to the Peak Transit rider portal
   (asu-shuttles.rider.peaktransit.com) for live tracking when the student asks "right now."
3. For each leave-by time that has not passed, propose a reminder at that time. Drop any
   reminder time that has already passed; if a class starts in under 30 minutes, say so right
   away instead of scheduling a reminder.
4. Read the day's weather for the destination campus with Cubbie's **Web** capability. If rain
   or extreme heat is expected around the leave-by time, add a short note.
5. For the first commute of the day, look up one coffee shop on the route with Cubbie's
   **Web** capability and include its open time and any drink specials, as a one-line delight.
   Skip this if no shop is found.
6. Show the plan as a short list (class, campus, leave-by time, route, notes) and ask the
   student to confirm or adjust. Do not create any reminder before the student says yes.
7. After the student confirms, create each reminder with Cubbie's **Reminders** capability.
   Each reminder names the class, the campus, the leave-by time, the route, and the weather note.

## Daily commute plan (recurring)

When the student says yes to a recurring plan, create a nightly 9 pm check-in with Cubbie's
**Reminders** capability that:
- Scans tomorrow's calendar for cross-campus classes.
- Computes leave-by times and routes.
- Sends one morning message per commute day in this style:

  "Leave in 20 mins. Route 10. Don't forget an umbrella. Coffee stop on the way: Cartel,
  opens at 9 — check out their drink specials."

## Output

After setting reminders, reply in two or three lines: how many were set, the next leave-by
time, and any class that was too soon to schedule. Keep the full list for when the student asks.

## When something fails

- No cross-campus classes tomorrow: say so and offer to look 7 days ahead.
- Shuttle schedules unavailable: fall back to "about 50 minutes between campuses" and note it.
- Portal unreachable: skip live tracking and use published schedules only.
- Some reminders could not be created: list which ones and offer to retry once.
- Use only schedule times and weather that Cubbie returned. Never guess a leave-by time.
