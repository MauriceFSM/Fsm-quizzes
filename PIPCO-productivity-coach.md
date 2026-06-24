# PIPCO Productivity Coach — Hourly Time-Block Playbook

Automated phone-push coaching for a **6:30 AM – 3:00 PM** shift, weekdays.
Each hour you get a short push notification telling you what to focus on.

| Time | Block | Focus |
|------|-------|-------|
| 6:30 AM | **Shift start** | Brain-dump everything, pick your top 3 must-dos, line up the first deep-work task. |
| 7:00 AM | **Deep work 1** | Hardest priority. Notifications off, single-task it. |
| 8:00 AM | **Block 1 momentum** | Stay on #1. Push through the hard part, no tab-switching. |
| 9:00 AM | **Reset + admin** | 5-min stretch/water, then clear email & messages (cap at ~30 min). |
| 10:00 AM | **Deep work 2** | Priority #2. Phone away, full focus. |
| 11:00 AM | **Late-morning** | Close out the morning task before lunch. |
| 12:00 PM | **Lunch** | Step away from the screen and recharge. |
| 1:00 PM | **Post-lunch refocus** | Lighter/collaborative work — meetings, replies, reviews. |
| 2:00 PM | **Final push** | Finish remaining must-dos, clear quick small tasks. |
| 3:00 PM | **Shift wrap** | Log what's done/unfinished, set tomorrow's top 3, log off clean. |

## How it works
- Delivery: **phone push** (via Claude Remote Control on this session).
- Schedule: durable cron jobs (survive session restarts) firing on weekdays.
- Recurring jobs auto-expire after 7 days — re-run setup weekly, or migrate to a
  standing automation (e.g. a GitHub Action) if you want it to run indefinitely.

## Caveat
The scheduler fires while this Claude session/container is alive and Remote
Control is connected. If the container goes idle and is reclaimed, pushes pause
until the session is resumed.
