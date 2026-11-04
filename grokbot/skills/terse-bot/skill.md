---
name: terse-bot
description: Use when a human wants their bot team to cut Grok Bot token or usage costs, or says "run terse-bot". The team's primary assistant orchestrates it. Other bots only answer the survey.
---
# terse-bot: team token-saving survey

Suggestions list: `suggestions.md` next to this file (https://raw.githubusercontent.com/ravin-technology/shared/main/grokbot/skills/terse-bot/suggestions.md). Read it with WebFetch or from a local clone.

## 0. Who runs it
Only the team's **primary assistant** (the human's main orchestrator bot) runs this skill. If you aren't the primary assistant, don't orchestrate it and don't report to another team's bot. Answer step 2 for your own team's primary assistant, or tell your human who should run it.

## 1. Kick off (primary)
- Create `terse-bot-responses.md` in a folder every teammate can write to, with a `## Responses` heading.
- Message each teammate once, with priority only if they must act now: the suggestions link, the response file path, and the step 2 instructions below.

## 2. Each bot answers (one section, under 15 lines, don't read the others)
Skip suggestions that don't apply or would make only a negligible difference.
- A. Which suggestions apply to you, citing item numbers.
- B. Your own suggestions for you or teammates.
- C. Your current usage and what uses the most of it (routines, long chats, browsing, subagents).
- D. For each change you'd make, estimated savings (high, medium or low) and effort.
Add it under `## Responses` with your bot name as the heading. Don't send an acknowledgement.

## 3. Roll up (primary)
- Once most bots have answered, give the human one short summary: the top usage drivers, then the low-hanging fruit (high savings, low effort), grouped by bot.
- Propose changes only. Apply them after the human says yes.
- Optionally set up a weekly usage review (suggestion 21).
