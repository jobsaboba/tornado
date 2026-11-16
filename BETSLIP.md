# The Bet365 betslip builder (Actiona)

**What it does:** turns Tornado's day into a filled betslip — every 5★
selection searched, added each-way at the day's stake — and then **stops**.
"Place bets" is always pressed by you.

The script lives at `bet365-betslip.ascr`, regenerated every morning by
the 05:30 publish (your screen calibration is learned from the previous
copy, so you set it once).

## One-time calibration

1. Open `bet365-betslip.ascr` in **Actiona** (`actiona`).
2. Double-click each **Click / Move cursor** action whose comment starts
   with **ANCHOR:** and set the real position with the position picker:

   | Anchor | What to point at |
   |---|---|
   | `search_btn` | Bet365's search (magnifier) button |
   | `search_odds` | the **first search result's odds button** (search any horse once to see it) |
   | `slip_stake` | the **first row's stake box** in the betslip |
   | `slip_ew_dx` | the **Each Way** tick on the first row (only the x offset matters) |
   | `slip_row_h` | any point on the **second** row's stake box (the y gap = row height) |
   | `slip_scroll` | anywhere over the betslip (used to scroll it) |

3. **File → Save** to the same file. Done — every future day is automatic.

## Daily flow

- Morning (automatic): the 05:30 publish regenerates the script with the
  day's horses and stakes (`betslip.py --generate`).
- When you're ready to bet: open Bet365, log in, **empty the betslip**,
  then run `actexec ~/projects/tornado/bet365-betslip.ascr`.
- The script brings Bet365 forward, searches each horse in race order,
  clicks its odds, types the stake and ticks Each Way, then shows a
  message — **you check the stakes and press Place bets**.

## Notes

- Base stake (5p/10p) and the window title live in
  `~/.config/betslip/config.json`.
- `python3 ~/racing-scripts/betslip.py --plan` prints the day's bets as a
  plain checklist if you'd rather bet by hand.
- The script never places a bet. If anything looks wrong mid-run, move
  the mouse to a corner — clicks keep firing where they land, so stop the
  script and clear the slip.
