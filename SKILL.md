---
name: minto-pyramid
description: Use when writing or rewriting anything a busy reader has to act on — email, status update, memo, proposal, exec summary, deck, PR description, report — or when a draft buries its point, opens with background, reads like thinking out loud, or someone asks to make it clearer, shorter, punchier, or more executive.
---

# Minto Pyramid

## Overview

Barbara Minto's structure, built at McKinsey and published as *The Pyramid Principle*: **the answer first, then the grouped reasons that support it, then the evidence under each reason.**

What this fixes is order, not intelligence. Walking the reader through your process and arriving at the point is fine for a story and wrong for a reader who decides in about a sentence whether to keep going. Models default to that order because prose does.

## The shape

```
              THE ANSWER  (one sentence)
        ┌──────────────┼──────────────┐
     Reason 1       Reason 2       Reason 3
        │              │              │
     evidence       evidence       evidence
```

The answer doesn't arrive cold. Minto's introduction, **SCQA**, is part of the structure, not a preamble to skip — it puts the reader on ground they already accept so the conclusion lands as an answer to a question they now have:

- **S**ituation — what the reader already accepts
- **C**omplication — what changed
- **Q**uestion — the question that raises (usually left implicit)
- **A**nswer — your conclusion, which *is* the top of the pyramid

Keep it to a few sentences. In a short email it compresses to one clause; it does not disappear.

## Minto's three rules

1. Every idea summarizes the ideas grouped beneath it.
2. Ideas in a grouping are the same kind of idea.
3. Ideas in a grouping are in a deliberate order.

A grouping is one of two kinds, and the order rule means something different in each:

- **Inductive** — separate reasons of the same type, ordered by importance, time, or structure. This is the common case, and the one **MECE** tests (Minto's coinage): mutually exclusive, collectively exhaustive. No overlaps, no gaps.
- **Deductive** — a chain where each step depends on the one before (premise → premise → therefore). Order is the logic itself. MECE does not apply; chains build, they don't partition. Keep chains short; they're harder to skim.

## Do not force three

Three is a convention, not Minto's rule. The count is whatever the logic requires — commonly three to five, since Minto ties grouping size to the limits of short-term memory. Two reasons that genuinely cover the case beat three where one is a detail wearing a reason's clothing, and a fourth real reason beats three plus filler.

Anything that won't sit under a reason is evidence, or it's cut — with one exception. Risks, constraints, and next steps are not reasons and must not be deleted as though they were; they get their own slot after the pyramid closes.

## Operations

Run these on demand; each is independently useful.

| # | Operation | Use it when |
|---|---|---|
| 1 | **Restructure** — impose the shape on an existing draft | You have prose and need the pyramid |
| 2 | **Buried-lede test** — find the conclusion the draft is actually building toward | You are not sure what your own point is |
| 3 | **Reason audit** — MECE-check the middle layer | Reasons feel repetitive, thin, or arbitrary |
| 4 | **So-what pass** — delete every line that can't answer "so what?" | The draft is bloated |
| 5 | **Email version** — compress to under 150 words in the same shape | The deliverable is an email, Slack post, or update |

### 1. Restructure

> Rewrite this using the Minto Pyramid. Open with my single main conclusion in one sentence, after at most two sentences of situation and complication. Then the supporting reasons — as many as the logic requires, not a fixed three. Then the evidence under each. Move risks, constraints and next steps to a short closing section. Cut anything else that doesn't sit under a reason, and list what you cut so I can check nothing load-bearing went out.

### 2. Buried-lede test

> Read this draft and tell me the one conclusion it is actually building toward. If I had a single sentence to give my boss, what would it be? Then show me exactly where in the draft I hid it, and how many words a reader has to get through before they reach it.

### 3. Reason audit

> Look at my reasons against Minto's rules. Do any overlap (not mutually exclusive)? Together, do they cover the whole case (collectively exhaustive)? Are they the same kind of idea, and in a deliberate order? Flag any that is really evidence wearing a reason's clothing, and tell me which ones collapse into each other.

### 4. So-what pass

> Go through this line by line and ask "so what?" after every sentence. Delete every line that can't answer it. Show me only what survives, then tell me what percentage of the original I just lost.

### 5. Email version

> Compress this into an email under 150 words in the same structure: the answer, the reasons, evidence only where it earns its place. Keep my voice, keep the specifics, drop the throat-clearing. No preamble before the conclusion.

## Worked example

**Narrative order (the way it usually arrives):**

> We reviewed four suppliers, ran the pricing, called the references, there were delays getting hold of one of them, and on balance we think Kestrel.

**Pyramid order:**

> We should sign Kestrel. Three reasons: they're 18% cheaper, they can start in October, and both references named the same strength.

Identical facts. The decision moved to word four.

## Common mistakes

| Mistake | Fix |
|---|---|
| Padding to exactly three reasons | Use the number the logic requires; merge or split honestly |
| Reasons that are really evidence | If it supports another reason rather than the answer, demote it |
| Hedging until the claim dissolves ("we may want to consider") | State the claim, then state your confidence in it. Uncertainty is a fact about the answer, not a reason to hide the answer |
| SCQA that runs four paragraphs | Two or three sentences, then the answer |
| Recapping the reader's own request back at them | Delete; they were there |
| Reasons in whatever order they occurred to you | Order by importance, time, or structure — on purpose |
| Deleting risks and next steps because they aren't reasons | Give them a closing section |

## Red flags in a draft

- The point arrives in paragraph three or later
- Opens with "As you know," or "I wanted to reach out"
- Chronological narration of your process instead of your finding
- Nothing changes for the reader if they stop after the first paragraph — because the first paragraph says nothing

## When not to use it

- **Storytelling, marketing hooks, tutorials, anything built on suspense.** Withholding is the point there.
- **Exploratory thinking.** Don't force a conclusion you haven't reached — run operation 2 first and find out what you actually think.
- **A reader who will reject the conclusion before hearing why** (bad news, hostile audience). Lead with the shared problem via SCQA and let the answer land one beat later — still in the first paragraph, never on page two.

## Make it the default

To stop invoking this per document, put the shape in project instructions, a CLAUDE.md, or a saved style: *situation and complication in two sentences, then the conclusion, then MECE reasons, evidence under each, risks and next steps at the close.*
