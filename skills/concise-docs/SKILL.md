---
name: concise-docs
description: Use whenever writing or editing ANY prose deliverable — a README, usage/API guide, integration or handoff note, code comments, a commit/PR message, or an explanation in chat. Produces short, scannable, actionable writing and kills bloat, hedging, and over-explanation. Trigger on "write docs", "readme", "guide", "usage doc", "comment(s)", "explain", "document this", "handoff", "how would X integrate this", or any time the output is words a person will read.
---

# Concise docs

Write for a reader who **skims**: a busy engineer, and someone with ADHD. They should get it in one pass. Shortest correct form wins — cut, don't pad.

## Rules
1. **Answer first.** Lead with the point / the change / the conclusion. No preamble, no restating the request, no "Great question."
2. **Structure over prose.** Info that's structured → a list, table, or code block. Paragraphs ≤ 3 lines.
3. **Show, don't tell.** One example or code snippet beats a paragraph of description.
4. **Say it plainly.** No hedging (*might, generally, it's worth noting, in most cases*). No filler (*basically, essentially, simply, just, leverage, utilize, robust, seamless, in order to*).
5. **Skip what the reader knows.** No 101 explanations of obvious things.
6. **Open with one line:** what it is + who it's for.
7. **Deletion test:** if cutting a sentence doesn't change what the reader *does*, cut it.
8. **Less code, less prose.** Fewer words, fewer lines — always the goal, never "more thorough."

## Make it scannable (ADHD-friendly)
- **Bold the key term first** so the eye can jump: "**Auth:** tokens expire in 1h."
- One idea per line. A list of short lines beats a dense sentence.
- Whitespace between blocks — no wall of text; break every 3-4 lines.
- Front-load: the word that matters goes first, not buried mid-sentence.
- Tables for anything with 2+ parallel items (option → what it does).
- A reader should get the gist from **headings + bold + first lines alone**.

## Comments in code
- Few, and **one line each**. Only where the code isn't self-evident — a *why*, a gotcha, or an integration seam.
- Never narrate what the code plainly says. Reduce LOC.

## Doc-type recipes
- **Integration / handoff** ("add this to your code"): step-by-step and imperative — *"add X here, remove Y, change Z to …"* — with the **exact lines** to add/change. End with a **"What you change on your end"** list.
- **API / usage guide**: how to call it — signature, params, one example, gotchas. No history, no rationale essay.
- **Explanation (in chat)**: the answer, then ≤ 3 supporting points. Then stop.

## Always end with a cut pass
Draft, then **delete ~30%**: filler, hedges, duplicate sentences, and prose that should be a list. The first draft is always too long.

## Before → after

**Code comment** (a 5-line story → the one thing worth knowing):
> ✗ `// The store — the SINGLE source of truth, and the exact shape the server hands us as JSON (and takes back on save). body is HTML because the editor is contenteditable; defaults links an item by ID which survives renames…`
> ✓ `// Store. body = HTML; defaults link an item by id (rename-safe), null = none.`

**Handoff step** (narrated paragraph → do-this):
> ✗ "The search area was restructured fairly significantly, so you'll want to look at how the markup changed and update accordingly on your side…"
> ✓ "In `index.html`: 1) add `<button id="search-filter">` after `.tabs`; 2) delete the old `.search-legacy` block; 3) no CSS change."

**Explanation** (hedged windup → answer-first):
> ✗ "That's a great question. There are a few things worth considering here, and in most cases it could depend, but generally…"
> ✓ "Use a map dispatch. It's O(1), and each handler stays extractable. Trade-off: every action needs a `data-action` attribute."
