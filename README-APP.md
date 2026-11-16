# Tornado Racing

Every **★★★★★ horse** in every race with **8+ runners** — that's the whole
rule — staked with the **Jacobs Ladder, one day at a time**.

- Never scores anything itself — the Holy Grail's published day files
  (`projects/holy-grail/data/`) are the sheet of record; this slices.
- **Daily ladder**: the day's bet is (first + last) × the unit — ladder
  1-2-2 at 10p = **30p a horse** — and *every* 5★ bet that day stakes it
  (20 horses = £6 total). When the day is all in: **returns under the
  day's total stake → the ladder climbs** (1-2-2-3 → 40p tomorrow);
  **returns over it → the ladder shrinks** (scratch first and last, reset
  when ≤2 remain); **a day that lifts the bank past its previous high
  resets straight back to 1-2-2**.
- **The day's book** lives at the bottom of the horses list: type your
  **returns** on the left, the **total stake** sits to its right, and the
  **unit box** (5p / 10p) rescales today's planned stakes as you like.
- Each-way at Ladbrokes (½ win · ½ place at 1/5 odds), settled with the
  Grail's bet maths. Non-runners are refunded and don't stake; an
  unfinished day shows planned stakes and leaves the ladder alone.

Published by `~/racing-scripts/tornado.py --publish` — 05:30 each
morning (waits for the Grail's 05:00 sheet) and every 30 minutes,
13:00–22:00, via `results-refresh.sh` so results trickle in live.
