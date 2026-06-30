Prepare a pre-meeting briefing by reviewing all memory files and surfacing items that need discussion.

## Steps

1. **Read all memory files:**
   - `.claude/memory/NOTES.md` — primary source for `[To Discuss]` items
   - `.claude/memory/JOURNAL.md` — read the last 5 entries only; recent decisions that may have resolved open items
   - `.claude/memory/TODO.md` — completed tasks that may have closed open questions

2. **Extract every `[To Discuss]` item** from NOTES.md — both date-level headers (`## YYYY-MM-DD [To Discuss]`) and sub-headers (`### Title [To Discuss]`). Note the date and content of each.

3. **For each item, assess its status** by cross-referencing JOURNAL.md and TODO.md:
   - **Still open**: no evidence in JOURNAL or TODO that this was addressed
   - **Likely resolved**: a JOURNAL decision or Done task clearly addresses it — explain why
   - **Uncertain**: partial evidence — something related was done but the specific question may still stand

4. **Output a pre-meeting briefing** in this format:

---

## Pre-meeting briefing — YYYY-MM-DD

### Items to discuss

For each open `[To Discuss]` item:
- **Topic** (from NOTES, dated YYYY-MM-DD)
  Context: 1-2 sentences on why this needs discussion and any relevant background from JOURNAL or TODO

### Possibly resolved — confirm before removing

For each likely-resolved item:
- **Topic** (from NOTES, dated YYYY-MM-DD)
  Likely resolved because: [specific JOURNAL decision or Done task that addressed it]

### General talking points

If there are no `[To Discuss]` items, or as a complement to them, include a short section drawn from JOURNAL and TODO:
- What was recently completed (last 1-2 sessions)
- What is currently in progress
- Anything blocked or uncertain worth flagging

---

5. **After presenting the briefing**, if there are any likely-resolved items, ask once: "Should I remove the `[To Discuss]` tag from the resolved items listed above?"
   - If yes: update NOTES.md — remove only the `[To Discuss]` tag from those headers, leave everything else untouched
   - If no: leave NOTES.md as-is

## Rules
- Never remove a `[To Discuss]` tag without explicit user confirmation
- Always produce output — if there are no `[To Discuss]` items, fall back to general talking points from JOURNAL and TODO
- Keep the briefing concise — the goal is a quick scan before a meeting, not a report
- If an item is ambiguous, lean toward keeping it open rather than marking it resolved
