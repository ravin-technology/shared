---
name: Ayla phone calls
description: Use when the user asks to have "Ayla" (or the assistant) make a phone call for them to a business or someone they know: setting it up, writing the script, placing it, and logging the result.
---
# Ayla phone calls

"Ayla" (pronounced EYE-la) is the team's name for placing a live phone call through Grok Bot's built-in phone-call tool. "Ayla" is our shorthand for this workflow.

## Known limits (as of Nov 2026)
- The voice agent's spoken name, intro, AI/recorded-line disclosure and voice are fixed by the app. Never script a name, persona or intro. It will not introduce itself as "Ayla". (Feature request sent to the Grok team.)
- Transcript and recording stop when the user takes over; the call can't be handed back to the agent.
- The agent can't draft or send an email mid-call.
- The approval card is interrupted if the user sends a new message while it waits, and expires after 30 minutes.
- A more configurable voice agent would need a third-party tool; for now we use the built-in one.

## Before the call
1. Gather from notes, memory and the owning bot (whoever has the most context, e.g. the estate bot for estate calls): who to call, the objective, account/reference numbers, names and dates the callee will ask for, and what NOT to agree to.
2. Verify the number on the callee's official website. Prefer the official number over one from notes; say which you used.
3. Callback/transfer number: use the user's own primary number from their vault (check shared memory for which line is theirs). Never use a family member's line.
4. Name pronunciation: write the user's surname phonetically in the script (e.g. "Dee-ter", plus the spelling D-E-I-T-E-R). A pronunciation note alone doesn't work; the agent reads the spelling.
5. Sensitive IDs (SSN, account numbers): include only if the user explicitly approved sharing them for this call; never echo them in chat.
6. Known contacts: check notes, the owning bot's wiki and memory for anyone we've already dealt with at this place (name, direct number, extension, email, past case number). Put what's on file into the script so the agent confirms it instead of asking from scratch.
7. Ask the user only for what's missing, in one widget with steps.

## Script (Objective / Additional context)
- Tone: polite, assertive, slightly terse; act with full authority for the user so reps have less reason to ask for them.
- Early in the call: get the rep's name, a direct number or extension, and a case/reference number (for dropped calls and callbacks).
  - Known contact on file: ask for them by name, then confirm by reading back what we have instead of asking again, e.g. "Is this Danylle? If we need to reach you again, the number we have is (844) 555-0100, extension 123. Is that still right?" Take down any correction. Ask only for what isn't on file (often a case/reference number).
  - New contact: ask for the rep's name, direct number or extension, and case number.
- After the call, save any new or corrected contact details to the notes (or the owning bot's wiki) so the next call can just confirm them.
- If authority is questioned: first offer to email written authorization (ask for the rep's email address), then offer to bring the user on the line.
- Ask for written confirmation by email to the user's address.
- Answer hold requests right away ("Yes, I'll hold").
- No payments or promises to pay unless the user explicitly approved.
- Before ending: read back what was agreed and the reference number.

## Placing it
- Show the user a bulleted summary (who, goal, key details shared, transfer number), then place the call in the same turn. Re-raise an expired card only when the user asks.
- Remind the user that the transcript and recording stop when they take over, so they should note the rep's name, reference number and outcome, or text them to the bot right after.

## After the call
- Summarize the result for the user: who they spoke with, what was agreed, the reference number, and the next step.
- Log it with the owning bot / tracker and in the relevant notes file.
- If a message was left with no reply, offer a follow-up email draft and a next-day callback referencing the earlier message.
- Add new lessons to this skill (commit here and keep the installed skill in sync).
