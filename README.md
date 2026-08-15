# playable

a replica of playable v1, in one unstyled HTML file, with RPG depth added on top.

**same `tasks.json` contract.** the CLI (`todo`), the four GitHub Actions and the v1
web app all keep working against the same repo unchanged. nothing is written that
they can't ignore.

## replicated from v1, unchanged

3 pillars · quest types (daily/main/side/story) · the XP table (daily 25/day,
main 200, story 100, side 50, legacy priority fallback) · `100 × L^1.5` curve ·
the stats block · seeded daily shuffle · balance % with the `(low)` flag ·
tri-pillar +100 · streak · this-week counts · filters · double-click to edit ·
XP logs · the anime pass and the rewards vault · GitHub load/save with sha
conflict retry · PWA.

verified against the real save: task XP 6350, pillars 5 / 3 / 14, player lvl 17 —
identical to v1.

## the read

the app's opinion of your state, in sentences, at the top of the screen:

    ── the read ─────────────────────────────────
      today is 9/14 — your best day yet (previous best 8, aug 6).
      wealth is carrying this run — 79% of everything you have done.
      health has been under 15% for 17 days.
      this week 17 done, last week 40 — slowing.
      1 more completion to wealth lvl 15.

every line is derived from the same rules that move the numbers. nothing is
generated at runtime and no model is involved — the same save always produces
the same read.

it judges the day against *your own history*, not against 100%. a 14-daily list
means "clear them all" is not a real target; "better than your usual 7" is.

## the RPG layer

**bosses.** a task with more than one session is a boss. it holds hp, each
session lands a hit, and it only flips to `done:true` when the hp is gone —
so the CLI and the Actions see an ordinary open task the whole way and the XP
arrives exactly when v1 would have paid it.

    ⚔ obsessive startup application  [███░░░░░░░] 2/6  [strike]

this is the gap v1 had. a checkbox has two states, and the things that sat
untouched for weeks — the startup application, the mograph — sat there because
they were never one tick's worth of work. now they show progress.

**steps.** a named checklist inside a task, for the things that aren't "more
sessions" but "these four specific parts". clearing the last one completes it.

**the map.** three regions, one per pillar. exploration measures *breadth* —
distinct things done there, habits that took root, bosses felled — so grinding
one task forever doesn't fill the bar and a neglected region reads as neglected.

**next move.** the one line at the top. an open world is only useful if it tells
you where to go, so it reads the same data the stats block does and answers what
to do right now, in priority order: overdue → due today → a boss one session from
dying → the third pillar that closes tri-pillar → the region under 15% → a long
habit streak about to lapse → whatever's left.

## added

- **pair bonus (+25).** v1 paid nothing for a 2/3 day, so a day where you did two
  pillars scored the same as a day where you did one. two of three now pays 25 on
  the way to the 100. this is the only change to your totals: +50 lifetime.
- **habit levels and per-habit streaks.** each daily shows `lv3 🔥5 ·12×`, derived
  from `completedDates` — no new data stored. tells you which habits are actually
  strong and which one is about to lapse.
- **a reward shop.** the anime pass generalised: define rewards with an XP price and
  redeem them. spent XP is tracked separately, so lifetime XP never goes down.
  written using the exact reward-task shape v1 already produced.
- **due dates surfaced.** v1 computed `isOverdue` / `isDueToday` and then never
  rendered them. they now show, and the edit prompt can set a due date.
- **dailies-today bar** in the stats block.
- **the anime pass is gone.** it was claimed zero times in seventeen days —
  gated behind 14/14 dailies when the best day on record was 8/14.
- **`hp` / `hits` / `steps`** are fields v1's CLI and Actions don't read; they
  round-trip through `tasks.json` untouched.
- **task text is escaped.** v1 injected it raw into `innerHTML` on a page holding
  a repo-scoped token.

## use

put `index.html`, `manifest.json`, `sw.js`, `icon.svg` in a repo with Pages on,
or open the file directly. enter `user/repo` and a token with `repo` scope.
