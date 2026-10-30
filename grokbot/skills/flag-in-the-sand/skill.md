---
name: Flags in the sand
description: >-
  Use when the user says to add/drop/plant a "flag" (an untimed note-to-self or
  tangent thought), wants to attach extra context or research to a flag, asks
  where something is or what we know about a person/project/topic, asks "any
  flags?", "any flags with you?" or "any flags we should review?", or wants to
  resolve or clear a flag.
---
# Flags in the sand

A flag is an untimed note the user drops so they don't have to switch context. It is NOT a timed reminder; if the user gives a time, use a routine instead. There are two kinds:
- **action**: something to do, decide, or review, usually with a specific bot or person ("review the DO architecture with Kewl").
- **remember**: a fact to recall later, like where something is ("the helmet is on the desk").

## Store
- One shared file on the box: `/home/box/agent-data/shared/flags.md`. Every bot reads and writes the same file. The user's primary assistant curates it.
- Line format under `## Open`:
  `- F### | YYYY-MM-DD | <action|remember> | by:<your bot name> | tags: Noun, Noun | with:<who, or -> | <the flag in plain words>`
- Resolved flags move under `## Resolved` with ` | resolved YYYY-MM-DD: <outcome>` appended. Never delete a flag line.
- **Notes (extra context):** anything longer than the one-line flag (research, links, options, background, who said what) goes in its own file, `/home/box/agent-data/shared/flags/F###.md`, named by the flag's number. Mark the flag line by appending ` [notes]` to the end. The notes file stays with the flag forever, including after it's resolved, so nobody has to re-research it.

## Add a flag
1. Read the file. Use the next F number after the highest one in the file.
2. Kind: **action** if it asks for a task, decision, review, question, or follow-up, or names someone to do it with. Otherwise **remember**. When unsure, choose action if a person or bot is named.
3. Tags: 1 to 5 nouns (people, places, projects, systems, objects). Reuse tag spellings already in the file.
4. `with:` is the bot or person it should be reviewed or done with ("with Kewl", "for Tim"). If an action flag names nobody but clearly sits in a teammate's lane, set that bot. Use `-` for remember flags.
5. Append the line at the bottom of `## Open`, rewording the flag into one clear sentence without changing its meaning.
6. If the conversation already produced useful context (you looked something up, the user explained why, links came up), write it to the flag's notes file now and add ` [notes]`. Don't go researching just to fill notes.
7. Confirm in one short line, e.g. "Flagged for Kewl: <flag>." or "Noted: <flag>, with notes." Don't ask follow-up questions unless the flag can't be understood.

## Add context to an existing flag
- Create or append to `flags/F###.md`. Start each addition with a dated heading, `## YYYY-MM-DD, by:<your bot name>`, then the context in plain markdown (bullets, links, short paragraphs). Never overwrite what's already there.
- Make sure the flag line ends with ` [notes]`.
- If you're a teammate and can't write the file, send the context to the primary assistant (the flag keeper) with the F number, and it files it.

## Recall ("where is X?", "what do we know about Y?")
- Search case-insensitively (`rg -i`) for the noun and close variants in `flags.md` (Open and Resolved) and in `flags/`. Answer straight from the flag and give its date, e.g. "As of Oct 29, Jace's helmet is on Pop's old computer desk."

## Review ("any flags?", "any flags with you?", "what flags do I have for X?")
- Asked of a teammate bot about itself: list the open **action** flags whose `with:` is that bot.
- For a named person, bot, or project: list the open action flags with that `with:` or tag. Include remember flags only if asked.
- Show each flag on one line with its F number. For a flag marked [notes], say it has notes and summarize them in a line; read the notes file in full when the user digs into that flag. After the discussion, offer to resolve the ones that are handled.

## Count (for reports)
- Count open **action** flags grouped by `with:`, e.g. "Flags: Kewl 2, Trevor 4, Tim 1." Ignore remember flags and notes. Leave the line out when there are none.

## Resolve or change
- When the user says a flag is done, handled, or wrong, move it to `## Resolved` with the date and a short outcome. To edit one, rewrite its line in place and keep the F number. A remember flag that's out of date ("the helmet moved") gets resolved, and the new fact becomes a new flag.
- If a flag turns into real work, it can become a task or routine. Note that in the resolution.
- Never delete a notes file. If the outcome is worth keeping, add a dated line to it.

## Rules
- Never put passwords, codes, or other secrets in a flag or its notes. Point to where they're kept instead.
- Keep edits small (append or edit one line or section), and re-read the file right before writing so bots don't overwrite each other.
