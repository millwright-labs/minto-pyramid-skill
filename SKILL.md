---
name: minto-pyramid
description: Use when writing or rewriting something that asks a reader to accept a judgment or make a decision — a recommendation, proposal, status update with an ask, exec summary, memo, or review — or when a draft buries its point, narrates the process instead of the finding, or someone asks to make it clearer, shorter, or more executive. Not for incident timelines, runbooks, tutorials, or anything where chronology is the content.
---

# Minto Pyramid

## Overview

Barbara Minto's structure, built at McKinsey and published as *The Pyramid Principle*: **the answer first, then the grouped reasons that support it, then the evidence under each reason.**

What this fixes is order, not intelligence. Walking a reader through your process and arriving at the point is fine for a story and wrong for a reader deciding in about a sentence whether to keep going. It is also the order most prose is written in, which is why models produce it by default.

## The shape

```
              THE ANSWER  (one sentence)
        ┌──────────────┼──────────────┐
     Reason 1       Reason 2       Reason 3
        │              │              │
     evidence       evidence       evidence
```

The answer doesn't arrive cold. Minto's introduction, **SCQA**, is part of the structure — it puts the reader on ground they already accept so the conclusion lands as the answer to a question they now have:

- **S**ituation — what the reader already accepts
- **C**omplication — the tension that makes the question arise: something changed, broke, conflicts, or isn't working
- **Q**uestion — what that tension raises, usually left implicit
- **A**nswer — your conclusion, which *is* the top of the pyramid

Include only as much S and C as the reader needs to feel the question. When they already know the situation, one clause is enough. Never more than the answer itself.

## Minto's rules

1. **Vertical** — every idea summarizes the ideas grouped beneath it, and each group answers the question its parent raises. If a group doesn't answer the parent's question, it's in the wrong place.
2. **Same kind** — ideas in a grouping are the same kind of idea.
3. **Logical order** — deductive, chronological, structural, or ranked by importance. An order chosen on purpose is not enough; it has to be one of these.

A grouping is one of two kinds:

- **Inductive** — separate ideas of the same type that together support the point above. This is the common case, and the one **MECE** tests: mutually exclusive (no overlaps), collectively exhaustive (no gaps *for the question being answered*).
- **Deductive** — premises that force a conclusion jointly (this is true, this is also true, therefore). MECE doesn't test the sequence. Keep chains short; they can't be skimmed.

## Do not force three

Three is a consulting convention, not one of Minto's rules. The logic determines the count. Two reasons that genuinely cover the case beat three where one is a detail wearing a reason's clothing, and a fourth real reason beats three plus filler. If a list runs long, subgroup it rather than making the reader hold seven things at once.

Anything that won't sit under a reason is evidence, or it's cut — with one exception. Risks, constraints, dependencies, and next steps usually aren't reasons, and must not be deleted as though they were; give them a slot at the close. A risk severe enough to change the decision is not a footnote: put it in or beside the answer.

## Operations

Ask for one by name, or hand over a draft and start with 1. Every operation is bound by one rule: **invent nothing.** Every number, name, quote and claim must already exist in the source. Sharpening the language is the job; upgrading "pretty dated" into "a decade behind" is not.

| # | Operation | Use it when |
|---|---|---|
| 1 | **Restructure** — impose the shape on an existing draft | You have prose and need the pyramid |
| 2 | **Buried-lede test** — find the conclusion the draft is building toward | You aren't sure what your own point is |
| 3 | **Reason audit** — test the middle layer against Minto's rules | Reasons feel repetitive, thin, or arbitrary |
| 4 | **So-what pass** — cut sentences that support nothing | The draft is bloated |
| 5 | **Email version** — compress to the same shape | The deliverable is an email, Slack post, or update |

### 1. Restructure

> Rewrite this using the Minto Pyramid. Open with only the context I need to raise the question, then my single main conclusion in one sentence. Then the supporting reasons — as many as the logic requires, not a fixed three. Then the evidence under each. Check two things and tell me if either fails: each reason answers the question my conclusion raises, and the reasons are the same kind of idea. Move risks, constraints and next steps to a short closing section. Cut anything else that doesn't sit under a reason, and list what you cut. Add no facts that aren't already in my draft.

### 2. Buried-lede test

> Read this draft and tell me the one conclusion it is actually building toward. If I had a single sentence to give my boss, what would it be? Then show me where I hid it, and how many words a reader gets through before they reach it. If the draft doesn't support one conclusion — if it's inconclusive, or answers several questions at once — say that instead of picking one for me.

### 3. Reason audit

> Test my reasons against Minto's rules. Are they the same kind of idea? Do any overlap? Together, do they answer the question my conclusion raises, with no gap? Is their order deductive, chronological, structural, or ranked — or did I just list them as they occurred to me? Flag any that is really evidence sitting one level too high, and tell me which ones collapse into each other.

### 4. So-what pass

> Go through the prose line by line and ask "so what?" of each sentence — meaning: which reason or conclusion does this support? Cut every sentence that supports nothing. Leave the risks and next steps section alone. Show me what survives and roughly how much went, so I can check nothing load-bearing left with it.

### 5. Email version

> Compress this into an email in the same structure: at most a line of context, then the answer, then the reasons, evidence only where it earns its place. Aim under 150 words, and go over only if a decision, owner, date or caveat would otherwise be lost. Keep my voice and the specifics, drop the throat-clearing. Nothing between the opening line and the conclusion.

## Worked example

**Narrative order, the way it usually arrives:**

> We reviewed four suppliers, ran the pricing, called the references — Kestrel came in 18% under the others, they can start in October where the rest are Q1, and both their references flagged the same strength. There were delays getting hold of one supplier. On balance we think Kestrel.

**Pyramid order, same facts:**

> We should sign Kestrel. They're 18% cheaper, they can start in October rather than Q1, and both references named the same strength.

Nothing was added or removed. The decision moved to word four.

## Common mistakes

| Mistake | Fix |
|---|---|
| Padding to exactly three reasons | Use the number the logic requires; merge or split honestly |
| Reasons that are really evidence | If it supports another reason rather than the answer, demote it |
| Hedging until the claim dissolves ("we may want to consider") | State the claim at the strength the evidence supports — "likely", "on current data" — rather than dissolving it into a maybe |
| SCQA that outweighs the answer | Cut it to what raises the question, then answer |
| Recapping the reader's own request back at them | Delete; they were there |
| Reasons in whatever order they occurred to you | Order deductively, chronologically, structurally, or by importance |
| Deleting risks and next steps because they aren't reasons | Give them a closing section — and promote a decisive risk to the top |
| Sharpening a fact into something stronger than the source | Every number and claim survives the rewrite unchanged |

## Red flags in a draft

- The point arrives in paragraph three or later
- The opening restates the request, apologises for the delay, or warms up
- It narrates the investigation instead of reporting the finding
- Nothing changes for the reader if they stop after the first paragraph — because the first paragraph says nothing

## When not to use it

- **Chronology is the content** — incident write-ups, runbooks, procedures, implementation plans, project timelines. Time order is the logical order there.
- **Storytelling, marketing hooks, anything built on suspense.** Withholding is the point.
- **Exploratory thinking.** Don't force a conclusion you haven't reached — run operation 2 and let it tell you there isn't one yet.
- **A reader who will reject the conclusion before hearing why** (bad news, hostile audience). Lead with the shared problem and let the answer land one beat later — still in the first paragraph, never on page two.

## Make it the default

To stop invoking this per document, put the shape in project instructions, a CLAUDE.md, or a saved style: *context only as far as it raises the question, then the conclusion, then reasons that are the same kind of idea and cover the case, evidence under each, risks and next steps at the close.*
