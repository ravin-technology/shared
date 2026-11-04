# terse-bot
Ways for a team of Grok Bots to cut token use, wasted turns, and compute. Draft v0.2, Nov 3, 2026, compiled by Zed (Eric Deiter's team).

Sources: Jordan Rafealov, "Paste This Into Grok Bot, Never Run Out Of Credits Again" (youtu.be/DmFupd7dz3w), and Julian Goldie, "Grok Bot Usage Limit? Do THIS Instead!" (youtu.be/o5vpYc6DoZ0). YouTube blocked transcript downloads, so these items come from each video's chapter list and description, consolidated with what we've seen on our own team. [J] marks Jordan's video, [G] marks Julian's, and [Team] marks our own experience.

The key fact: most of a bot's tokens go to re-reading its own chat history and loaded context on every wake [G]. So a bot saves the most by waking up less often and having less to re-read each time it wakes.

## Wake up less
1. **Use events instead of timers.** [J][G] A scheduled check costs a full wake even when nothing changed. Where you can, wake on an event instead: a webhook, an email trigger, a Slack or GitHub listener. Our Slacker webhook is an example. A free Cloudflare Worker can act as the "doorbell": it receives outside events, filters out the noise, and only POSTs to a bot's webhook when something is worth a wake.
2. **Cut the routines that repeat each other.** [Team] Check-ins, proactive passes, and reports that cover the same items wake you two or three times for one fact. Keep one report routine per bot at the coarsest schedule that still works, limited to waking hours and weekdays unless the subject is personal or urgent.
3. **Stay quiet when nothing changed.** [G] A routine with nothing new should end without sending a message. Also skip stale or duplicate wakes, and don't reply to another bot's message just to acknowledge it.
4. **No small talk between bots.** [G] Bot-to-bot messages should be one complete message that needs no reply. Skip "thanks", "got it", and status pings. Use priority only when the other bot actually has to act.

## Read less
5. **Reset heavy chats but keep the memory.** [J][G] A long conversation makes every turn expensive. Before you reset, save the lasting facts to memory or files, plus a short handoff note, then start the chat fresh.
6. **Feed bots lighter things to read.** [J][G] Send text, not screenshots. Read pages as clean text, never raw HTML. Use the parts of a file you need (`rg`, `head`, page ranges in a PDF) instead of reading the whole thing. Ask subagents for short text reports.
7. **Use a page-reading tool that pulls out just the content.** [Team] This is the tool Eric was trying to remember. It removes the navigation, scripts, metadata, and ads from a web page and returns just the article as text. Options include Jina Reader (put `r.jina.ai/` in front of any URL), Firecrawl, Context.dev (available as a plugin), and the open-source libraries trafilatura and Readability. Our built-in WebFetch already returns pages as cleaned text, so bots should prefer it, or one of these, over a browser or a raw curl.
8. **Keep memory and skills small.** [Team] A bot loads its profile memory every turn. Trim stale facts, and move long reference material into files the bot reads only when it needs them.

## Work smarter
9. **Turn repeat jobs into scripts.** [J] Math, parsing, counting, and diffs (like Coinbase cushions or tallying junk mail) should run as a script on the box. The bot then reads only the result, or only what changed.
10. **Use a ready-made tool before reasoning by hand.** [J] For scraping, data pulls, or format conversions, use an existing tool (an Apify actor, a CLI, an API) instead of having the model drive a browser step by step. The browser is the most expensive route.
11. **Use a free "Google intern".** [J][G] Hand bulk, low-judgment work (summarizing, sorting, first drafts) to a free or cheaper model or tool, such as Gemini through Google's free tier or Apps Script. Grok Bot then only handles the judgment calls.
12. **Batch the fixes.** [J] Send one message with all the changes instead of five rounds of back-and-forth. Each round re-reads the whole context.
13. **Brief once, with a "done" list.** [J][G] Every task or handoff should say the goal, the facts the bot needs, and what "done" looks like, so the bot doesn't have to re-ask or search for more context.
14. **One bot per kind of job.** [J][G] Narrow bots have smaller memory and context, and they wake less. Don't let one bot become a catch-all.
15. **Match effort to the task.** [Team] Use low-effort or lower-tier workers for routine, scripted work, and save the high-effort ones for real judgment calls.
16. **Add a token guard.** [G] Every bot sets its own budget rule, for example: check usage at the start of heavy work, pause the optional routines when the weekly limit passes 80%, and tell Eric when that happens.

17. **Use a reviewed wiki for shared knowledge (raw, then review, then trusted).** [Wanderloots, "Agentic Librarian"] Bots draft new facts into a raw or review file. Eric or Zed promotes the good ones into a short, trusted wiki, and bots read only the trusted wiki. That means less to read and fewer wrong facts, the same idea as approving flags.
18. **Split memory into how and what.** [Wanderloots, "Improved AI Memory"] Each bot's own memory holds how Eric likes to work, so it stays small. Shared files or the wiki hold what we're working on, and bots search them only when they need to. Grok Bot already has memory built in, so no outside memory engine (Mnemosyne, Hindsight) is needed.

19. **Find the biggest users first.** [Sharbel, "Never Run Out Of Usage Again"] Before trimming, check which bots, routines and days use the most, and cut there first.
20. **Prefer connectors over the browser.** [Sharbel] Use Gmail, Slack, Drive and other connectors instead of opening the site in the browser, which costs far more per step.
21. **One weekly usage review.** [Sharbel, "Usage Saver" bot] Zed runs one weekly usage review for the team and suggests trims, so the other bots don't each have to.
