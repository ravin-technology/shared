# Achievement badges: how to set it up

**TL;DR:** Attach `skill.md` in a chat with your Grok bot and say "save this as a skill, and I opt into achievement badges." Your bots will then hand out a short, funny badge when you hit a real milestone.

## What it is
When you finish something real (ship a fix, close a deal, clear a backlog), your bot adds a one-line badge under the result:

> 🏆 **Achievement unlocked: Backlog Be Gone**
> *Forty tickets entered, zero survived.*

Each badge arrives as its own separate message, so it stands out from the rest of the reply. It's limited to one badge per reply and a few a day. Bots skip badges when things went wrong or the topic is serious, like health, money, grief, or legal matters.

## Setup (about 1 minute)
1. Open a chat with your main Grok bot, attach `skill.md`, and say: **"Save this as a skill. I opt into achievement badges for all my bots."**
2. Optional: ask **"Show my badges"** anytime to see your trophy case.

## Your badge catalog
When you opt in, your bot offers to seed a starter catalog of 5 to 10 badges that fit your work. You can grow it anytime: say **"Add a badge: Coffee Overflow for a fourth cup before noon."** When a bot invents a badge that could happen again, it offers to add it, and repeat wins level up (Level 2, Level 3...).

### Where it lives
You can invent badges for yourself or your team. Keep them in any place you control, like a Slack channel (for example `#badges`) or a `badges.md` file, and tell your bot where it is: **"My badge catalog is the #badges channel."** Nothing about the location is built into the skill, so use whatever you have.

Write one badge per line:

`Target:Achievement:Trigger:Description`

- **Target** is a person's name, or `All`.
- **Achievement** is the badge title.
- **Trigger** is the real event that earns it.
- **Description** is optional. Leave it blank and the bot writes its own.

Example: `All:Inbox Zero Hero:when the inbox is fully cleared:`

## Off switch
Say **"no more badges"** and your bots stop right away.
