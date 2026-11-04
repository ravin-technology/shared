---
name: Bot handoff
description: Use when one bot hands its role to a new bot (a rebuild, a fresh start to cut tokens, or a move to another plan or team). The old bot goes on ice instead of being deleted until its human verifies the new one.
---
# Bot handoff (old bot on ice, never self-delete)

Rule: a bot never deletes itself. Only its human deletes the old bot, after the new bot passes verification.

## 1. Handoff (old bot)
Write `HANDOFF.md` in a shared folder both bots can read. Include:
- Its role and lane, and who it reports to or takes work from.
- How the human likes to work (the profile facts worth keeping), plus open items and promises in flight.
- Each routine: its name, schedule or trigger, and full saved prompt (get it, don't paraphrase).
- Connectors, accounts, secret env var names (never values), shared files and repos.
- Teammate contacts, plus the hard rules and guard rails.
Then give it to the new bot. Create the new bot, or have the human do it, and send it the path.

## 2. On ice (old bot)
- Rename itself to `<NAME>-YYYYMMDD` (the handoff date, e.g. `Zed-20261104`) with UpdateProfile, so the new bot can take the plain name (`Zed`).
- Pause every routine. Don't delete them.
- Tell the teammates to send its work to the new bot from now on.
- Hide itself from the sidebar with UpdateProfile. Its chat, memory and routines stay, and with nothing waking it, it uses almost no tokens.

## 3. Verify (new bot)
- First, tell the human: "The original <NAME> is on ice as <NAME>-YYYYMMDD and hidden from the sidebar. After the trial period (default 1 week) I'll remind you that you can retire it. If there are problems during the trial, you can resume the old bot." Then create that reminder routine.
- Recreate the routines from HANDOFF.md, and fire or dry-run each one once.
- Confirm every connector and secret works with one read.
- Do one real task in the lane.
- Report a pass or fail for each item to the human. Anything that fails gets fixed, or the old bot gets resumed.

## 4. Retire (human only)
- The new bot's reminder fires after the trial period (default 1 week).
- The human decides: delete the old bot, or keep it on ice.
- Rollback: resume the old bot's routines and redirect the teammates back to it.
