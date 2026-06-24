# PIPCO Productivity Coach — On-Demand "Start Button"

Automated phone-push coaching for desk/computer work on an **~8-hour shift**.
Hours vary day to day, so coaching is triggered **on demand**: you message the
start phrase when you clock in, and the whole day is scheduled relative to that
moment.

## The "Start Button"
When you're at work, just message me any of:
- **"Let's go"**
- **"I'm at work"**
- **"Start my shift"**

I'll immediately send your kickoff push and schedule the rest of the day's
hourly nudges relative to your start time. To stop early, message **"I'm done"**
or **"End shift"** and I'll cancel the remaining nudges.

## Relative time-block plan (desk work)
| Elapsed | Block | Focus |
|---------|-------|-------|
| +0:00 | **Shift start** | Brain-dump everything, pick your top 3 must-dos, line up the first deep-work task. |
| +1:00 | **Deep work 1** | Hardest priority. Notifications off, single-task it. |
| +2:00 | **Momentum check** | Stay on #1. Push through the hard part, no tab-switching. |
| +3:00 | **Reset + admin** | 5-min stretch/water, then clear email & messages (cap ~30 min). |
| +4:00 | **Lunch / recharge** | Step away from the screen and reset for the afternoon. |
| +5:00 | **Post-lunch refocus** | Ease back in — lighter/collaborative work, replies, reviews. |
| +6:00 | **Deep work 2** | Priority #2. Phone away, full focus. |
| +7:00 | **Final push** | Finish remaining must-dos, clear quick small tasks. |
| +8:00 | **Shift wrap** | Log done/unfinished, set tomorrow's top 3, log off clean. |

## How it works
- Delivery: **Claude app phone push** (via Remote Control on this session).
- On "start": one-shot cron jobs are created for +1h … +8h from now; the +0
  kickoff push is sent immediately. They fire once then auto-delete.
- Re-trigger each workday with the start phrase.

## Caveat
Pushes fire while this Claude session/container is alive and Remote Control is
connected. If the container goes idle and is reclaimed mid-shift, remaining
nudges pause until the session is resumed.
