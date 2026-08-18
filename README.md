# playable

a save file for your actual life.

    REAL ACTION → RECORDED EVENT → RULE → PERSISTENT STATE

not a productivity app with game decorations. a personal game engine for real life.

## it has a destination

first thing it asks: **who are you trying to become?** one sentence, plus the three
stats that person is made of. every number afterwards is measured against it — not
just against last week. that line stays on screen, and the app tells you what
percent of your last thirty days actually pointed there.

without that, this is telemetry. with it, it's a game.

## the seven

five are **domains** — where an action landed:

    💪 vitality     evidence you invested in your body
    🤝 connection   evidence you invested in people
    💰 prosperity   evidence you invested in what you are building
    📖 wisdom       evidence you invested in knowing more
    ✷ creativity   evidence you made a thing that did not exist

two are **earned** — they say something about *how* you acted, and you cannot tag a
task with them. only the rules can award them:

    ⚔ courage      evidence you did the thing you were avoiding
    ⛓ discipline   evidence you kept going after it stopped being novel

courage is paid when you finish something that had been sitting for a week or more,
scaled by how long it sat, or when you take the hard version. discipline is paid for
consecutive days, for clearing the bar you set, and for touching several domains in
one day. both are computed from timestamps — nothing is judged.

no stat claims to measure the thing itself. health xp does not say you are healthy.
it says: evidence you invested.

## bosses are not created, they accrue

you never make a boss. a boss is what a task **becomes** when you keep not doing it.
anything open seven days or more surfaces on its own, priced in courage by how long
it has been sitting.

## the day declares its own difficulty

    full · normal · low · recovery

this moves what **clearing the day** means, never what anything is worth. the streak
counts days you hit the bar *you set*, not days you were perfect. on recovery days
rest is a completable action worth vitality, because rest is play and not its absence.

effort per completion: **min** 0.5× · normal 1× · **hard** 2×.

## chapters, as story

each week seals into prose, not a stat dump:

    — week of aug 3 —
      you gained 240 courage. you finally did "15 second mograph"
      after 17 days of not doing it.
      discipline held — 7 of 7 days cleared the bar you set.
      wisdom led the week.
      40% of the week pointed at who you said you are becoming.

## the ledger

every event and the rule that produced it. no model runs at any point. the same
events always produce the same state.

## arcs · rewards

an arc is a chapter you are trying to live, with stages and a final one. rewards are
things you define and spend xp on; lifetime never drops, spent is tracked separately.

## data

`tasks.json` keeps v1's exact shape and is the event source — the `todo` CLI and the
GitHub Actions keep working untouched. everything here lives in `state.json`, which
they never read.

no punishment for missed days. no manufactured streak anxiety. effort over
perfection. rest is legitimate. difficulty bends to the person. progress is
identity and story, not only numbers.
